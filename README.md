# Dealogic (dealogic)

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

Dealogic is a global provider of content and software for the capital markets — deal management, analytics, league tables and compliance — used by investment banks, syndicate and sales/trading desks, investment managers and corporates. Dealogic is part of ION Analytics.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/dealogic/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Producing
- **Access:** Customer
- **x-type:** company

## Tags

- Analytics, Capital Markets, Compliance, Deal Management, Debt Capital Markets, Equity Capital Markets, Finance, Financial Data, Investment Banking, League Tables, M&A, OData, Private Equity, Reporting, SPAC, Syndicated Loans

## Timestamps

- **Created:** 2024-01-20
- **Modified:** 2026-09-05

## APIs

Dealogic operates no developer portal on `dealogic.com`. Its APIs and data feeds are catalogued on the **ION Analytics Data Portal**, and the machine-readable contracts are served from Dealogic's own Swagger UIs on `*.dealogic.com` hosts. Eight OpenAPI 3.0.1 documents covering **153 operations** were harvested verbatim on 2026-09-05:

| API | Host | Operations |
|---|---|---|
| Dealogic Analytics SPAC API (v2.0, OData v4) | `spac.analytics.dealogic.com` | 78 |
| Dealogic Analytics SPAC API (v1.0, loader/admin) | `spac.analytics.dealogic.com` | 13 |
| Dealogic Analytics Bank API | `bank.analytics.dealogic.com` | 13 |
| Dealogic Analytics Company API | `company.analytics.dealogic.com` | 7 |
| Dealogic Analytics Sponsor API | `sponsor.analytics.dealogic.com` | 7 |
| Dealogic Reporting API | `api.reporting.dealogic.com` | 4 |
| Cortex Reporting API | `api.reporting.cortex.dealogic.com` | 4 |
| IONA Profiles API | `api.profiles.dealogic.com` | 27 |

Alongside them, the **Dealogic Primary Market Deals & Entities Feed** delivers over 2 million investment banking transactions since 1995 as XML over the Dealogic secure FTP server or a service-bus topic, loaded into MS SQL Server by the client-installed Dealogic Data Loader.

Every HTTP API is **read-only for customers** and gated by OAuth 2.0 against the shared identity provider at `login.dealogic.com`, which advertises a single product scope, `dealogic`. There is no self-service signup, no published pricing, no rate limit, no error contract and no SDK in any language.

The sibling APIs on the same ION Analytics Data Portal that are served from `api.acuris.com` — the Acuris, Mergermarket, Merger Review, Entities and Private Equity APIs — belong to other ION Analytics brands and are **not** attributed to Dealogic here.

## Common Properties

- [Website](https://www.dealogic.com/)
- [Cortex Login](https://cortex.dealogic.com/)
- [Developer Portal — ION Analytics Data Portal](https://iongroup.com/analytics/data-portal/)
- [API Reference — SPAC API low-level documentation](https://iongroup.com/analytics/data-portal/apis-data-feeds/spac-api/documentation/low-level-documentation/)
- [Platform](https://dealogic.com/platform/)
- [Investment Banking / Capital Markets](https://www.dealogic.com/our-platforms/investment-banking/)
- [Syndicate / Sales, Trading & Research](https://dealogic.com/platform/syndicate-str/)
- [Investment Managers](https://www.dealogic.com/our-platforms/investment-managers/)
- [Corporations](https://www.dealogic.com/our-platforms/corporations/)
- [ComplianceManager](https://dealogic.com/product/compliancemanager/)
- [Security](https://dealogic.com/security/)
- [Terms of Use](https://dealogic.com/terms-of-use/)
- [Privacy Policy](https://dealogic.com/privacy-policy/)
- [Insights](https://dealogic.com/insights/)
- [Contact](https://dealogic.com/about-us/contact-us/)

Three product links carried in earlier revisions of this profile were confirmed dead on 2026-09-05 and removed: `/our-platforms/sales-trading-research/`, `/products/analytics/` and `/products/connect/` all return HTTP 404.

## Maintainers

- **Kin Lane** - kin@apievangelist.com
