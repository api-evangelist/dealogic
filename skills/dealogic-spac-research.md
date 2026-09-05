---
name: dealogic-spac-research
description: Research a SPAC (special purpose acquisition company) end to end using the Dealogic Analytics SPAC API's OData surface — find the entry, expand its IPO syndicate, sponsors, listings, redemptions and related or withdrawn M&A, without over-fetching a 230-field root object.
api: Dealogic Analytics SPAC API
base_url: https://spac.analytics.dealogic.com/
generated: '2026-09-05'
method: generated
source: openapi/dealogic-analytics-spac-v2-openapi.json
operations:
  - GET /odata/SpacEntry
  - GET /odata/SpacEntry/{key}
  - GET /api/SpacReader/GetAllDepthExpand
  - GET /odata/SpacEntry({key})/Listings
  - GET /odata/SpacEntry({key})/IpoSyndicate
  - GET /odata/SpacEntry({key})/IpoFinancialSponsors
  - GET /odata/SpacEntry({key})/CompanyManagement
  - GET /odata/SpacEntry({key})/CompanyRedemptions
  - GET /odata/SpacEntry({key})/RelatedEcmDeals
  - GET /odata/SpacEntry({key})/WithdrawnMnaDeals
  - GET /odata/SpacEntry({key})/CompanyCornerstoneInvestors
  - GET /odata/SpacEntry({key})/RelatedNews
---

# Research a SPAC with the Dealogic Analytics SPAC API

The published contract declares **no `operationId` on any operation**, so every step below is
identified by its verbatim method and path from `openapi/dealogic-analytics-spac-v2-openapi.json`.
Do not invent an operationId.

## Before you start

- **Auth.** OAuth 2.0 bearer token from `https://login.dealogic.com`. The only flow the spec
  declares is `implicit`; the discovery document at
  `https://login.dealogic.com/.well-known/openid-configuration` also advertises
  `authorization_code`, `client_credentials` and `refresh_token`. Scope: `dealogic`.
  There is no self-service signup — clients are provisioned to licensed customers.
- **Unauthenticated calls return `401` with a zero-byte body.** No message, no problem document.
  If you get an empty 401, the token is missing or expired; there is nothing else to read.
- **Every operation declares only a `200`.** Treat any non-200 as opaque and retry or escalate;
  see `errors/dealogic-problem-types.yml`.
- **No rate limit is published and no rate-limit header is returned.** Pace yourself; there is no
  runtime signal to back off on. See `rate-limits/dealogic-rate-limits.yml`.

## Step 1 — Find the SPAC

`GET /odata/SpacEntry?api-version=2.0&$filter=...&$select=...&$top=25`

Use `$select` from the first call. `SpacEntry` carries **230 scalar fields**; pulling the whole
object for a list view wastes the call. `$top` defaults to 15 if you omit it.

`$filter` accepts at most **100 expressions**, `$orderby` at most **5**.

## Step 2 — Learn the expansion shape before you expand

`GET /api/SpacReader/GetAllDepthExpand?entityName=SpacEntry&api-version=2.0`

This returns the full-depth `$expand` expression Dealogic itself would use. Build your own
narrower expression from it rather than guessing navigation-property names — `$expand` is capped
at **depth 5** and a rejected expression costs you a round trip you cannot read an error from.

## Step 3 — Fetch the entry

`GET /odata/SpacEntry/{key}?api-version=2.0&$select=...&$expand=...`

Note the two key syntaxes in this contract, and that they are not interchangeable:

- `/odata/SpacEntry/{key}` — the single-entity read.
- `/odata/SpacEntry({key})/<NavigationProperty>` — the navigation reads in step 4.

## Step 4 — Pull only the sections you need

Each of these is its own operation, each supports the full `$select/$filter/$orderby/$top/$skip/$count`
set, and each is cheaper than expanding the root:

| Question | Operation |
|---|---|
| Where does it trade? | `GET /odata/SpacEntry({key})/Listings` |
| Who underwrote the IPO? | `GET /odata/SpacEntry({key})/IpoSyndicate` |
| Which sponsors backed it? | `GET /odata/SpacEntry({key})/IpoFinancialSponsors` |
| Who runs it? | `GET /odata/SpacEntry({key})/CompanyManagement` |
| How much was redeemed? | `GET /odata/SpacEntry({key})/CompanyRedemptions` |
| What deal did it do? | `GET /odata/SpacEntry({key})/RelatedEcmDeals` |
| What deal fell over? | `GET /odata/SpacEntry({key})/WithdrawnMnaDeals` |
| Who anchored it? | `GET /odata/SpacEntry({key})/CompanyCornerstoneInvestors` |
| What has been said about it? | `GET /odata/SpacEntry({key})/RelatedNews` |

## Step 5 — Follow composite keys carefully

Related deal entities are keyed on **two** values, and the path spells both out:

`GET /odata/RelatedEcmDeal(Id={keyId},SpacEntryId={keySpacEntryId})/Syndicate`
`GET /odata/WithdrawnMnaDeal(Id={keyId},SpacEntryId={keySpacEntryId})/TargetAdvisors`

The `SpacEntryId` half is the SPAC you started from. Passing only `Id` will not resolve.

## What this API will not do

It is **read-only** for customers. There is no create, update or delete on the v2.0 surface, so
there is nothing to make idempotent and nothing to reverse. The v1.0 document on the same Swagger
UI exposes loader and database-migration endpoints (`POST /api/SpacAdmin/MigrateSpacDatabase`,
`POST /api/SpacLoader/TriggerLoadAll`) — those are Dealogic's own pipeline controls, not customer
operations. Do not call them.
