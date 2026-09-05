---
name: dealogic-report-execution
description: Execute a saved Dealogic or Cortex report from an agent — read the report definition or criteria first, then run it with the right valid-dates type, extended criteria or drill-down.
api: Dealogic Reporting API and Cortex Reporting API
base_url: https://api.reporting.dealogic.com/
generated: '2026-09-05'
method: generated
source: openapi/dealogic-reporting-openapi.json, openapi/dealogic-cortex-reporting-openapi.json
operations:
  - GET /api/v1.0/ReportDefinition/{ReportId}
  - GET /api/v1.0/Data/{ReportId}/{ValidDatesType}
  - POST /api/v1.0/ExecuteWithCriteria/{reportId}/{validDatesType}
  - POST /api/v1.0/ExecuteWithDrilldown/{reportId}/{validDatesType}
  - GET /api/v1.2/Criteria/{reportId}
  - GET /api/v1.2/Data/{reportId}/{validDatesType}
  - POST /api/v1.2/ExecuteReportWithAdditionalCriteria/{reportId}/{validDatesType}
  - GET /Admin/Version
---

# Execute a saved Dealogic report

Two separate services, two separate hosts, two separate path versions. Pick one and stay on it.

| Service | Host | Path version |
|---|---|---|
| Dealogic Reporting API | `https://api.reporting.dealogic.com/` | `/api/v1.0/` |
| Cortex Reporting API | `https://api.reporting.cortex.dealogic.com/` | `/api/v1.2/` |

Neither contract declares an `operationId`; steps below are method + verbatim path.

## Step 1 — Learn the report's shape before running it

- Dealogic Reporting: `GET /api/v1.0/ReportDefinition/{ReportId}`
- Cortex Reporting: `GET /api/v1.2/Criteria/{reportId}`

Do this first. `{ReportId}` is opaque and comes from the customer's own saved reports — you cannot
enumerate reports through this API, and the definition/criteria call is the only way to know what
columns and criteria the report accepts.

## Step 2 — Run it

- `GET /api/v1.0/Data/{ReportId}/{ValidDatesType}?toleranceLevel=…`
- `GET /api/v1.2/Data/{reportId}/{validDatesType}?toleranceLevel=…`

`ValidDatesType` is a **path segment, not a query parameter** — it is required, and the report will
not run without it.

## Step 3 — Run it with more than the saved criteria

- `POST /api/v1.0/ExecuteWithCriteria/{reportId}/{validDatesType}` — extend the saved criteria
- `POST /api/v1.0/ExecuteWithDrilldown/{reportId}/{validDatesType}` — drill into a cell
- `POST /api/v1.2/ExecuteReportWithAdditionalCriteria/{reportId}/{validDatesType}` — the Cortex equivalent

These are `POST` because they carry a criteria body, not because they write. They are queries:
nothing is created, and re-sending the same body is safe.

## Step 4 — Know which build you are talking to

`GET /Admin/Version` (Cortex Reporting only) returns the deployed version — `2.3.3.0` at the time
this skill was written. There is no equivalent on the Dealogic Reporting API and no changelog for
either, so this call is the only version signal available. Log it with the results.

## Conventions that apply

- **Auth:** OAuth 2.0 bearer from `https://login.dealogic.com`, scope `dealogic`. The Swagger UI on
  both hosts uses client id `Reporting.API`.
- **Errors:** only `200` is declared on all seven operations. An empty `401` means the token is bad.
- **No rate limits published and no rate-limit headers returned.** Reports can be expensive; serialise
  them rather than firing in parallel.
