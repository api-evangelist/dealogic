---
name: dealogic-company-coverage
description: Build a coverage picture for a corporate client using the Dealogic Analytics Company API — which banks it pays, how that is trending, who lends to it, what debt is maturing, and its deal history.
api: Dealogic Analytics Company API
base_url: https://company.analytics.dealogic.com/
generated: '2026-09-05'
method: generated
source: openapi/dealogic-analytics-company-openapi.json
operations:
  - GET /{companyId}/BankingRelationships
  - GET /{companyId}/BankingRelationshipsMomentum
  - GET /{companyId}/TopBanksByRevenue
  - GET /{companyId}/TopBanksByLendingVolume
  - GET /{companyId}/TopRevenueByBanksDrilldown
  - GET /{companyId}/DebtMaturing
  - GET /{companyId}/Deals
---

# Build a corporate coverage picture

No `operationId` exists in this contract. Steps are method + verbatim path from
`openapi/dealogic-analytics-company-openapi.json`.

## Scope parameters

Most operations take `dateRange`, `region` and `product`; `DebtMaturing` and
`TopRevenueByBanksDrilldown` take `industry` instead of `region`. Hold `dateRange` constant
across a single analysis or the revenue and lending views will not reconcile.

## Step 1 — Who banks this company

`GET /{companyId}/BankingRelationships?dateRange=…&region=…&product=…`

## Step 2 — Is that changing

`GET /{companyId}/BankingRelationshipsMomentum?companyId=…`

Momentum takes **only** `companyId` — no date range. It is a fixed comparison window defined by
Dealogic, not one you choose, so do not present it as if it matched the window in step 1.

## Step 3 — Who earns from it, and who lends to it

- `GET /{companyId}/TopBanksByRevenue`
- `GET /{companyId}/TopBanksByLendingVolume`

Revenue and lending are different league tables. A bank can dominate one and be absent from the
other; a coverage argument that conflates them is wrong.

## Step 4 — Drill into a revenue line

`GET /{companyId}/TopRevenueByBanksDrilldown?dateRange=…&industry=…&product=…&year=…&productSubType=…`

This is the only operation with `year` and `productSubType`. Use it to answer "which product
sub-type drove that fee in that year", not as a general listing.

## Step 5 — What is coming up

`GET /{companyId}/DebtMaturing?dateRange=…&industry=…&product=…`

Maturities are the pitch trigger. Pair them with step 3 to say who is likely to be called.

## Step 6 — What has already happened

`GET /{companyId}/Deals?numberOfDeals=…&dateRange=…&region=…&product=…`

`numberOfDeals` is the only size control anywhere in this API — there is no pagination.
Ask for what you need; you cannot page for more.

## Conventions that apply

- **Auth:** OAuth 2.0 bearer from `https://login.dealogic.com`, scope `dealogic`.
- **Read-only.** Nothing here writes, so there is nothing to make idempotent or reverse.
- **Errors:** only `200` is declared; unauthenticated calls return an empty `401`.
- **Versioning:** none in path, header or query. See `lifecycle/dealogic-lifecycle.yml`.
