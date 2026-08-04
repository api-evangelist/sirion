# Sirion (sirion)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

> **Access model: enterprise / contract-gated.** Sirion (SirionLabs) is an
> AI-native enterprise Contract Lifecycle Management (CLM) platform. There is
> **no public self-service developer signup and no public pricing**. API access
> is delivered through Sirion's "Business API & Integrations" program: a tenant
> administrator provisions an **OAuth 2.0 Client Id and Client Secret**, and the
> **API reference is available only to authenticated Sirion users**
> (`docs.sirion.ai` is login-walled; the help guide is reached inside the tenant
> app via My Account → Resources → Help Guide). Because the reference is gated,
> the endpoint paths and schemas in this repository are **MODELED** from public
> product references and honestly flagged as such — they are not copied from an
> official public reference document.

Sirion manages the full agreement lifecycle — authoring, negotiation,
e-signature, a searchable contract repository, AI metadata and clause
extraction, obligation and performance management, and supplier / counterparty
governance. SirionOne is RESTful ("any activity possible in the web application
is possible via the APIs"), with pre-built connectors (Salesforce, SAP Ariba,
SAP S/4HANA, DocuSign), iPaaS support, and configurable outbound webhooks that
deliver event-based, asynchronous notifications.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sirion/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sirion/refs/heads/main/apis.yml)

## What is confirmed vs modeled

**Confirmed (public sources):**
- SirionOne is RESTful; the web application's activities are available via the API.
- Authentication is **OAuth 2.0 client credentials** (OAuth Client Id + Client Secret) for Sirion B2B APIs, generated under Admin 2.0 → Business API & Integrations (OAuth Client Setup).
- Configurable **outbound webhooks** with filtering on static and custom single/multi-select fields; event-based, asynchronous processing.
- Core entities: contracts, contract requests (CDRs), metadata/clauses, obligations, suppliers/counterparties.
- Pre-built connectors and iPaaS (Salesforce, SAP Ariba, SAP S/4HANA, DocuSign).

**Modeled (not publicly confirmable):**
- All specific endpoint paths and request/response schemas in `openapi/sirion-openapi.yml`.
- The OAuth token URL and the per-tenant API host (modeled on the confirmed product domain `sirioncloud.com`).

## Tags

- Contract Management
- Contract Lifecycle Management
- CLM
- Contracts
- AI
- Enterprise
- Legal
- Agreements
- Supplier Management
- Obligations

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs (MODELED surfaces)

### Sirion Contracts API
List, retrieve, create, update, and search executed contracts / agreements in the SirionOne repository. Base host: `https://{tenant}.sirioncloud.com` (modeled).

### Sirion Contract Requests API
Create and track Contract Requests (CDRs) that drive intake and authoring workflows. Confirmed conceptually by the SAP Ariba integration (a CDR reaching a workflow stage triggers a Contract Workspace); paths modeled.

### Sirion Metadata & Clauses API
Read and update contract metadata fields and AI-extracted clauses kept consistent across integrated CRM/ERP systems.

### Sirion Obligations API
Manage contractual obligations and performance / compliance tracking derived from agreements.

### Sirion Suppliers & Counterparties API
Manage suppliers and counterparties associated with contracts, synchronized with procurement systems such as SAP Ariba.

### Sirion Integrations & Webhooks API
Configure outbound webhooks and integration flows. Webhook rules support filtering on static and custom single/multi-select fields, delivering event-based, asynchronous notifications (server-to-endpoint HTTP POST, not a client WebSocket).

## Common Properties

- [Authentication](authentication/sirion-authentication.yml)
- [Website](https://www.sirion.ai)
- [Documentation](https://docs.sirion.ai) — login-walled
- [Plans](plans/sirion-plans-pricing.yml)
- [Rate Limits](rate-limits/sirion-rate-limits.yml)
- [Fin Ops](finops/sirion-finops.yml)
- [Domain Security](security/sirion-domain-security.yml)
- [LinkedIn](https://www.linkedin.com/company/sirionlabs)

## WebSocket review

**Does Sirion expose a documented public WebSocket API? No.** Sirion's surface is
OAuth2 REST plus outbound webhooks (HTTP POST callbacks). No `wss://` endpoint is
documented in any public Sirion material. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
