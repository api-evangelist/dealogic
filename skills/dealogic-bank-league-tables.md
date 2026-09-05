---
name: dealogic-bank-league-tables
description: Pull a bank's Dealogic league-table position and the deals and clients behind it — overall ranking, rankings by region, industry and product, top deals, pipeline, top fee payers and lending commitments — with the five scope parameters every operation shares.
api: Dealogic Analytics Bank API
base_url: https://bank.analytics.dealogic.com/
generated: '2026-09-05'
method: generated
source: openapi/dealogic-analytics-bank-openapi.json
operations:
  - POST /CheckBankProfiles
  - GET /{bankIdentifier}/BankRanking
  - GET /{bankIdentifier}/Regions/Ranking
  - GET /{bankIdentifier}/Industry/Ranking
  - GET /{bankIdentifier}/Products/Ranking
  - GET /{bankIdentifier}/Deals/TopDeals
  - GET /{bankIdentifier}/Deals/RecentCompleted
  - GET /{bankIdentifier}/Deals/Pipeline
  - GET /{bankIdentifier}/Clients/TopFeePayers
  - GET /{bankIdentifier}/Clients/TopLendingCommitments
  - GET /{bankIdentifier}/Clients/TopLendingByRegions
  - GET /{bankIdentifier}/Clients/TopLendingByIndustries
  - GET /{bankIdentifier}/Sponsors/FinancialSponsorsRanking
---

# Read a bank's league-table position from Dealogic

No `operationId` exists in this contract. Every step is method + verbatim path from
`openapi/dealogic-analytics-bank-openapi.json`.

## The five scope parameters

Twelve of the thirteen operations take the **same** query parameters, and they are the whole
game — the same bank ranks differently under different scopes:

`region`, `product`, `dateType`, `basisType`, `latestYear`

Fix all five before you compare two banks, and carry them unchanged across every call in a single
analysis. A ranking pulled with one `basisType` and a fee table pulled with another do not
reconcile, and nothing in the response will tell you that.

## Step 1 — Confirm the identifier resolves

`POST /CheckBankProfiles`

Send the `bankIdentifier` values you intend to use. This is the only cheap way to find out that
an identifier has no profile: a miss on a data operation returns an undeclared status with no
error body (`errors/dealogic-problem-types.yml`). Do this first for any identifier you did not
get from a previous Dealogic response.

Despite being a `POST`, this operation reads — it creates nothing, so retrying it is safe.

## Step 2 — Get the headline position

`GET /{bankIdentifier}/BankRanking?region=…&product=…&dateType=…&basisType=…&latestYear=…`

## Step 3 — Decompose it

- `GET /{bankIdentifier}/Regions/Ranking` — where the position comes from geographically
- `GET /{bankIdentifier}/Industry/Ranking` — which sectors carry it
- `GET /{bankIdentifier}/Products/Ranking` — ECM vs DCM vs loans vs M&A

## Step 4 — Get the deals behind the number

- `GET /{bankIdentifier}/Deals/TopDeals` — the marquee mandates
- `GET /{bankIdentifier}/Deals/RecentCompleted` — what just closed
- `GET /{bankIdentifier}/Deals/Pipeline` — what is still live

## Step 5 — Get the clients behind the number

- `GET /{bankIdentifier}/Clients/TopFeePayers`
- `GET /{bankIdentifier}/Clients/TopLendingCommitments`
- `GET /{bankIdentifier}/Clients/TopLendingByRegions`
- `GET /{bankIdentifier}/Clients/TopLendingByIndustries`
- `GET /{bankIdentifier}/Sponsors/FinancialSponsorsRanking` — sponsor coverage

## Conventions that apply

- **Auth:** OAuth 2.0 bearer from `https://login.dealogic.com`, scope `dealogic`.
- **Versioning:** none. This contract carries no version in the path, header or query;
  `info.version` is a build number. A change here will arrive unannounced —
  see `lifecycle/dealogic-lifecycle.yml`.
- **Pagination:** none. There is no `$top`/`$skip`/cursor on this API; response size is whatever
  the profile returns.
- **Errors:** only `200` is declared. Unauthenticated calls return an empty `401`.
