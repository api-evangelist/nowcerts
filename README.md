# NowCerts (nowcerts)

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

NowCerts is a cloud insurance agency management system (AMS) for independent agencies. In late 2024 the company rebranded to **Momentum AMP**, but the API is still served from `api.nowcerts.com`, so this entry keeps the NowCerts name. The API lets an agency and its integration partners import, update, search, and retrieve their own book of business: insureds and prospects, policies and coverages, carriers and underwriters, endorsements and commissions, tasks and workflow, plus drivers, vehicles, properties, claims, certificates of insurance, notes, SMS, and payments.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/nowcerts/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/nowcerts/refs/heads/main/apis.yml)

## Access model (be honest)

- **Public docs, account-gated.** The ASP.NET Web API help page at [api.nowcerts.com/Help](https://api.nowcerts.com/Help) is publicly viewable and documents 160+ REST endpoints (version 2.1.5). The collection can be imported into Postman.
- **You need a NowCerts / Momentum agency account** to make authenticated calls, and the user must be granted the **"API Integration"** agent role.
- **API access is tier-gated.** Essentials has no API access; Professional adds a limited number of API integrations; Business is unlimited; Enterprise adds custom and unlimited integrations. See the plans file for grounded (but unreconciled) pricing.
- **Authentication** is a bearer token obtained from `https://api.nowcerts.com/token` via the OAuth2 password grant. The help page also references `/Identity/Login` and `/Identity/TokenRefresh`.
- **Base URL:** `https://api.nowcerts.com/api`

### What is confirmed vs. modeled

Endpoint **paths and methods** in the OpenAPI and collections are **confirmed real** from the live help page. Request and response **schemas are honestly modeled** from documented behavior and standard AMS field sets — NowCerts does not publish a machine-readable OpenAPI, so payloads are marked modeled and left open (`additionalProperties: true`). Many list endpoints behave as OData-style detail lists (`$filter`, `$top`, `$skip`, `$orderby`).

## Tags

- Insurance
- Insurtech
- Agency Management System
- AMS
- Policies
- Insureds
- Certificates of Insurance
- REST

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

This entry organizes the large NowCerts surface around five core resources.

### NowCerts Insureds API

Create, update, search, and retrieve insureds and prospects (customers), including custom fields, contacts, tags, notes, tasks, claims, and associated policies. Confirmed endpoints include `/api/Insured/Insert`, `/api/InsuredDetailList`, and `/api/Customers/GetCustomers`.

- **Human URL:** [https://api.nowcerts.com/Help](https://api.nowcerts.com/Help)
- **Base URL:** `https://api.nowcerts.com/api`

### NowCerts Policies API

Insert and partially update policies, search the book of business by number/carrier/LOB/dates, and read policy detail, coverages, and status types. Confirmed endpoints include `/api/Policy/Insert`, `/api/Policy/PartialUpdate`, `/api/Policy/FindPolicies`, `/api/PolicyDetailList`, and `/api/Policy/Coverages`.

- **Human URL:** [https://api.nowcerts.com/Help](https://api.nowcerts.com/Help)
- **Base URL:** `https://api.nowcerts.com/api`

### NowCerts Carriers API

Retrieve carrier, underwriter, and line-of-business reference data. Confirmed endpoints include `/api/CarrierDetailList`, `/api/UnderwriterDetailList`, and `/api/LineOfBusinessList`.

- **Human URL:** [https://api.nowcerts.com/Help](https://api.nowcerts.com/Help)
- **Base URL:** `https://api.nowcerts.com/api`

### NowCerts Endorsements API

Read policy endorsement records and their financial detail (agency commissions, receivables, payables, financing), and insert a policy tied to an endorsement id. Confirmed endpoints include `/api/PolicyEndorsementDetailList`, `/api/PolicyEndorsementAgencyCommissionDetailList`, and `/api/Policy/InsertWithEndorementId`.

- **Human URL:** [https://api.nowcerts.com/Help](https://api.nowcerts.com/Help)
- **Base URL:** `https://api.nowcerts.com/api`

### NowCerts Tasks API

Insert and update tasks and task work groups, and read task, to-do, and task-category lists that drive agency workflow. Confirmed endpoints include `/api/TasksWork/InsertUpdate`, `/api/TasksList`, `/api/TasksWorkGroupList`, and `/api/ToDoList`.

- **Human URL:** [https://api.nowcerts.com/Help](https://api.nowcerts.com/Help)
- **Base URL:** `https://api.nowcerts.com/api`

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/momentumamp)
- [Website](https://www.nowcerts.com)
- [Documentation](https://api.nowcerts.com/Help)
- [Plans](plans/nowcerts-plans-pricing.yml)
- [Rate Limits](rate-limits/nowcerts-rate-limits.yml)
- [Fin Ops](finops/nowcerts-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
