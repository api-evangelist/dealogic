---
name: dealogic-sponsor-coverage
description: Profile a financial sponsor with the Dealogic Analytics Sponsor API — investment activity, portfolio entries and exits, and which banks it uses measured both by fees and by deal count.
api: Dealogic Analytics Sponsor API
base_url: https://sponsor.analytics.dealogic.com/
generated: '2026-09-05'
method: generated
source: openapi/dealogic-analytics-sponsor-openapi.json
operations:
  - POST /CheckSponsorProfiles
  - GET /{sponsorId}/InvestmentActivity
  - GET /{sponsorId}/PortfolioCompanies/Entry
  - GET /{sponsorId}/PortfolioCompanies/Exit
  - GET /{sponsorId}/BankingRelationshipsByFees
  - GET /{sponsorId}/BankingRelationshipsByNumberOfDeals
  - GET /{sponsorId}/Deals
---

# Profile a financial sponsor

No `operationId` exists in this contract. Steps are method + verbatim path from
`openapi/dealogic-analytics-sponsor-openapi.json`.

## Step 1 — Confirm the sponsor has a profile

`POST /CheckSponsorProfiles?latestYear=…`

Send the `sponsorId` values you plan to use. This reads only; retrying is safe. Doing it first
avoids spending data calls on identifiers that do not resolve, which fail without a readable
error body.

## Step 2 — Activity over time

`GET /{sponsorId}/InvestmentActivity`

Takes `sponsorId` alone — no scope parameters.

## Step 3 — Portfolio in and out

- `GET /{sponsorId}/PortfolioCompanies/Entry` — acquisitions into the portfolio
- `GET /{sponsorId}/PortfolioCompanies/Exit` — realisations

Both take `sponsorId` alone. Entry and exit are separate calls; there is no combined view.

## Step 4 — Which banks it uses, two ways

- `GET /{sponsorId}/BankingRelationshipsByFees?latestYear=…&industry=…&region=…`
- `GET /{sponsorId}/BankingRelationshipsByNumberOfDeals?latestYear=…&industry=…&region=…`

These are the only two operations here that take scope parameters, and they take the same three.
Fees and deal count rank differently — a bank doing many small financings for a sponsor will lead
one table and trail the other. Report which one you used.

## Step 5 — The deal history

`GET /{sponsorId}/Deals`

## Conventions that apply

- **Auth:** OAuth 2.0 bearer from `https://login.dealogic.com`, scope `dealogic`.
- **No pagination, no versioning, only `200` declared.** Same shape as the Bank and Company
  analytics APIs — see `conventions/dealogic-conventions.yml`.
