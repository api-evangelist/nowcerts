# NowCerts (nowcerts)

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
