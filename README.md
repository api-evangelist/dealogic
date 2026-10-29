# Dealogic

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Dealogic is a global provider of content and software for the capital markets — deal management, analytics, league tables and compliance — used by investment banks, syndicate and sales/trading desks, investment managers and corporates, and is part of ION Analytics. Its platforms are Cortex, Dealogic Connect, Analytics and ComplianceManager. Dealogic runs no developer portal of its own: its APIs are catalogued on the ION Analytics Data Portal, and eight OpenAPI 3.0.1 documents covering 153 operations are served from Dealogic's own Swagger UIs on spac/bank/company/sponsor.analytics.dealogic.com, api.reporting.dealogic.com, api.reporting.cortex.dealogic.com and api.profiles.dealogic.com. The SPAC API is OData v4; the rest are plain REST. All are read-only and gated by OAuth 2.0 at login.dealogic.com with one 'dealogic' scope — no self-service signup, no published pricing, no SDK. Bulk delivery is the Primary Market Deals & Entities Feed: XML over secure FTP or a service bus.

**Areas:** Analytics · Capital Markets · Compliance · Deal Management · Debt Capital Markets · Equity Capital Markets · Finance · Financial Data · Investment Banking · League Tables · M&A · OData

## Dealogic on APIs.io

Everything profiled for Dealogic is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/dealogic/](https://apis.io/providers/dealogic/)** — or go straight to one of the APIs or properties below.

### APIs (15)

- [Dealogic Primary Market Deals & Entities Feed](https://apis.io/apis/dealogic/dealogic-primary-market-deals-entities-feed/) — File-based bulk data feed of Dealogic's investment banking content: over 2 million transactions since 1995 across Equity Capital Markets, Debt Capital…
- [Dealogic Admin API](https://apis.io/apis/dealogic/dealogic-admin-api/) — The Admin API from Dealogic — 1 operation(s) for admin.
- [Dealogic Data API](https://apis.io/apis/dealogic/dealogic-data-api/) — The Data API from Dealogic — 27 operation(s) for data.
- [Dealogic Dcm Deal API](https://apis.io/apis/dealogic/dealogic-dcmdeal-api/) — The DcmDeal API from Dealogic — 1 operation(s) for dcmdeal.
- [Dealogic Entity Navigation API](https://apis.io/apis/dealogic/dealogic-entity-navigation-api/) — The Entity Navigation API from Dealogic — 44 operation(s) for entity navigation.
- [Dealogic Levfin Market Update API](https://apis.io/apis/dealogic/dealogic-levfinmarketupdate-api/) — The LevfinMarketUpdate API from Dealogic — 16 operation(s) for levfinmarketupdate.
- [Dealogic Loan Deal API](https://apis.io/apis/dealogic/dealogic-loandeal-api/) — The LoanDeal API from Dealogic — 1 operation(s) for loandeal.
- [Dealogic Organization Spac Profile API](https://apis.io/apis/dealogic/dealogic-organizationspacprofile-api/) — The OrganizationSpacProfile API from Dealogic — 8 operation(s) for organizationspacprofile.
- [Dealogic Related Entities API](https://apis.io/apis/dealogic/dealogic-related-entities-api/) — The Related Entities API from Dealogic — 32 operation(s) for related entities.
- [Dealogic Report Data API](https://apis.io/apis/dealogic/dealogic-reportdata-api/) — The ReportData API from Dealogic — 7 operation(s) for reportdata.
- [Dealogic Root Entity API](https://apis.io/apis/dealogic/dealogic-root-entity-api/) — The Root Entity API from Dealogic — 1 operation(s) for root entity.
- [Dealogic Spac Admin API](https://apis.io/apis/dealogic/dealogic-spac-admin-api/) — The Spac Admin API from Dealogic — 4 operation(s) for spac admin.
- [Dealogic Spac Reader API](https://apis.io/apis/dealogic/dealogic-spac-reader-api/) — The Spac Reader API from Dealogic — 1 operation(s) for spac reader.
- [Dealogic Spac Writer API](https://apis.io/apis/dealogic/dealogic-spac-writer-api/) — The Spac Writer API from Dealogic — 9 operation(s) for spac writer.
- [Dealogic Test API](https://apis.io/apis/dealogic/dealogic-test-api/) — The Test API from Dealogic — 1 operation(s) for test.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Dealogic Events](https://apis.io/asyncapis/dealogic/dealogic-events/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [dealogic-mcp.yml](https://apis.io/servers/dealogic/dealogic-mcp-yml/)

#### Overlays (8)

OpenAPI overlays, including conversational phrasing for each operation.

- [Dealogic Analytics Bank Overlay](https://apis.io/overlays/dealogic/dealogic-analytics-bank-overlay/)
- [Dealogic Analytics Company Overlay](https://apis.io/overlays/dealogic/dealogic-analytics-company-overlay/)
- [Dealogic Analytics Spac V1 Overlay](https://apis.io/overlays/dealogic/dealogic-analytics-spac-v1-overlay/)
- [Dealogic Analytics Spac V2 Overlay](https://apis.io/overlays/dealogic/dealogic-analytics-spac-v2-overlay/)
- [Dealogic Analytics Sponsor Overlay](https://apis.io/overlays/dealogic/dealogic-analytics-sponsor-overlay/)
- [Dealogic Cortex Reporting Overlay](https://apis.io/overlays/dealogic/dealogic-cortex-reporting-overlay/)
- [Dealogic Iona Profiles Overlay](https://apis.io/overlays/dealogic/dealogic-iona-profiles-overlay/)
- [Dealogic Reporting Overlay](https://apis.io/overlays/dealogic/dealogic-reporting-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Dealogic Authentication](https://apis.io/security/dealogic/dealogic-authentication/)
- [Dealogic Domain Security](https://apis.io/security/dealogic/dealogic-domain-security/)
- [Dealogic Trust Center](https://apis.io/security/dealogic/dealogic-trust-center/)
- [Dealogic Vulnerability Disclosure](https://apis.io/security/dealogic/dealogic-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Dealogic Scopes](https://apis.io/scopes/dealogic/dealogic-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Dealogic Plans Pricing](https://apis.io/plans/dealogic/dealogic-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Dealogic Rate Limits](https://apis.io/rate-limits/dealogic/dealogic-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.dealogic.com/)
- [Documentation](https://iongroup.com/analytics/data-portal/apis-data-feeds/)
- [API reference](https://iongroup.com/analytics/data-portal/apis-data-feeds/spac-api/documentation/low-level-documentation/)
- [Sign up](https://iongroup.com/analytics/data-portal/request-info/)
- [Support](https://dealogic.com/about-us/contact-us/)
- [Blog](https://dealogic.com/insights/)
- [Terms of service](https://dealogic.com/terms-of-use/)
- [Privacy policy](https://dealogic.com/privacy-policy/)
- [GitHub](https://github.com/Dealogic)

## API Evangelist rating

**Kin Score 40.5** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 70.5 |
| Contract quality | 41.9 |
| Contract governance | 0.0 |
| Operational transparency | 2.6 |
| Developer ergonomics | 54.2 |
| Access clarity | 50.0 |

**Agent readiness 39.3** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | mostly |

**Regulatory alignment 37.0** — Banking & Open Finance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/dealogic/](https://apis.io/providers/dealogic/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Dealogic: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/dealogic/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
