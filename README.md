# Sirion (sirion)

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
