# Dream Sports

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

Dream Sports is India's largest sports technology company, founded by Harsh Jain and Bhavit Sheth, whose consumer brands include Dream11 (fantasy sports), FanCode (sports content, streaming and commerce), DreamSetGo (sports travel and experiences), Dream Cricket, Dream Money and DreamStreet, alongside the Dream Sports Foundation. Its public machine-readable API surface is not a consumer product API but two engineering surfaces: the "Login with Dream11" OpenID Connect identity service at auth.dream11.com, which publishes an OIDC discovery document, and Dream Horizon (also branded HorizonOS) — the company's open-source initiative that releases the platform engineering stack built to run Dream11 at 250M+ users. Dream Horizon publishes real OpenAPI 3.x specifications for Guardian (authentication and authorization), Checkmate (test management), Raven and Raven Thunder (in-app messaging and journeys), Delivr and DOTA (over-the-air mobile updates), protobuf service definitions for Odin (its internal developer platform), a first-party stdio MCP server for Odin, an llms.txt, and client SDKs published to npm under the @d11 scope and to LuaRocks under the dream11 namespace.

**Areas:** Company · Sports Technology · Fantasy Sports · Open Source · Developer Tools · Platform Engineering · Authentication · OpenID Connect · Mobile · React Native · DevOps · Observability

## Dream Sports on APIs.io

Everything profiled for Dream Sports is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/dream-sports/](https://apis.io/providers/dream-sports/)** — or go straight to one of the APIs or properties below.

### APIs (61)

- [Odin MCP Server](https://apis.io/apis/dream-sports/odin-mcp-server/) — First-party Model Context Protocol server (stdio transport) published by Dream Horizon that exposes Odin — Dream Sports' internal developer platform — to…
- [Dream Sports Access Keys API](https://apis.io/apis/dream-sports/dream-sports-access-keys-api/) — The Access Keys API from Dream Sports — 2 operation(s) for access keys.
- [Dream Sports Account API](https://apis.io/apis/dream-sports/dream-sports-account-api/) — The Account API from Dream Sports — 4 operation(s) for account.
- [Dream Sports Acquisition API](https://apis.io/apis/dream-sports/dream-sports-acquisition-api/) — The Acquisition API from Dream Sports — 6 operation(s) for acquisition.
- [Dream Sports Admin API](https://apis.io/apis/dream-sports/dream-sports-admin-api/) — The Admin API from Dream Sports — 1 operation(s) for admin.
- [Dream Sports Admin - Console Users API](https://apis.io/apis/dream-sports/dream-sports-admin-console-users-api/) — Admin-only console user operations — user onboarding and updates that include project IDs (stored in Firebase custom claims). Requires appropriate admin…
- [Dream Sports Apps API](https://apis.io/apis/dream-sports/dream-sports-apps-api/) — The Apps API from Dream Sports — 10 operation(s) for apps.
- [Dream Sports Auth API](https://apis.io/apis/dream-sports/dream-sports-auth-api/) — Authentication operations — Google login and token refresh
- [Dream Sports Authentication API](https://apis.io/apis/dream-sports/dream-sports-authentication-api/) — The Authentication API from Dream Sports — 7 operation(s) for authentication.
- [Dream Sports Behaviour Tags API](https://apis.io/apis/dream-sports/dream-sports-behaviour-tags-api/) — APIs for managing Behaviour Tags. Behaviour Tags define user segments and their exposure rules for CTAs. They control which CTAs are shown or hidden to…
- [Dream Sports Cache Management API](https://apis.io/apis/dream-sports/dream-sports-cache-management-api/) — The Cache Management API from Dream Sports — 1 operation(s) for cache management.
- [Dream Sports Client SDK API](https://apis.io/apis/dream-sports/dream-sports-client-sdk-api/) — Client SDK operations — endpoints consumed by the SDK for active journeys and state machine snapshots
- [Dream Sports Collaborators API](https://apis.io/apis/dream-sports/dream-sports-collaborators-api/) — The Collaborators API from Dream Sports — 2 operation(s) for collaborators.
- [Dream Sports Communication API](https://apis.io/apis/dream-sports/dream-sports-communication-api/) — The Communication API from Dream Sports — 2 operation(s) for communication.
- [Dream Sports Configuration API](https://apis.io/apis/dream-sports/dream-sports-configuration-api/) — System configuration endpoints (labels, priorities, platforms, etc.)
- [Dream Sports Console Users API](https://apis.io/apis/dream-sports/dream-sports-console-users-api/) — Console user management via Firebase Admin SDK
- [Dream Sports CTA Status API](https://apis.io/apis/dream-sports/dream-sports-cta-status-api/) — APIs for managing CTA lifecycle status transitions. CTAs move through states: DRAFT → SCHEDULED → LIVE → PAUSED → CONCLUDED/TERMINATED.
- [Dream Sports CT As API](https://apis.io/apis/dream-sports/dream-sports-ctas-api/) — APIs for managing Call-to-Actions (CTAs). Includes CRUD operations for creating, updating, retrieving, and listing CTAs with filtering and pagination support.
- [Dream Sports Deployments API](https://apis.io/apis/dream-sports/dream-sports-deployments-api/) — The Deployments API from Dream Sports — 2 operation(s) for deployments.
- [Dream Sports Device-Bound Authentication API](https://apis.io/apis/dream-sports/dream-sports-device-bound-authentication-api/) — The Device-Bound Authentication API from Dream Sports — 2 operation(s) for device-bound authentication.
- [Dream Sports Events API](https://apis.io/apis/dream-sports/dream-sports-events-api/) — APIs for managing Events. Events define the structure and properties of user actions that can trigger CTAs. Events include event names and their associated…
- [Dream Sports Events Catalog API](https://apis.io/apis/dream-sports/dream-sports-events-catalog-api/) — Event schema management — create, update, and manage event definitions and their properties
- [Dream Sports Filters API](https://apis.io/apis/dream-sports/dream-sports-filters-api/) — APIs for retrieving filter values used in the admin UI. Provides available options for tags, teams, statuses, behaviour tags, and creators.
- [Dream Sports Guest Authentication API](https://apis.io/apis/dream-sports/dream-sports-guest-authentication-api/) — The Guest Authentication API from Dream Sports — 1 operation(s) for guest authentication.
- [Dream Sports Health API](https://apis.io/apis/dream-sports/dream-sports-health-api/) — The Health API from Dream Sports — 2 operation(s) for health.
- [Dream Sports Journey Behaviour API](https://apis.io/apis/dream-sports/dream-sports-journey-behaviour-api/) — Journey behaviour tag management — define and manage behaviour tags linked to journeys
- [Dream Sports Journey Lifecycle API](https://apis.io/apis/dream-sports/dream-sports-journey-lifecycle-api/) — Journey lifecycle status transitions. Journeys move through states: DRAFT -> SCHEDULED -> LIVE -> PAUSED -> CONCLUDED/TERMINATED. Each status transition has…
- [Dream Sports Journey Test API](https://apis.io/apis/dream-sports/dream-sports-journey-test-api/) — Test journey operations — create and remove test journeys for validating behaviour before going live
- [Dream Sports Journeys API](https://apis.io/apis/dream-sports/dream-sports-journeys-api/) — Journey management operations — create, read, update, and delete journeys
- [Dream Sports Key Management API](https://apis.io/apis/dream-sports/dream-sports-key-management-api/) — The Key Management API from Dream Sports — 1 operation(s) for key management.
- [Dream Sports Metrics API](https://apis.io/apis/dream-sports/dream-sports-metrics-api/) — The Metrics API from Dream Sports — 1 operation(s) for metrics.
- [Dream Sports Nudge Preview API](https://apis.io/apis/dream-sports/dream-sports-nudge-preview-api/) — Nudge preview management — create, update, and retrieve nudge preview templates with TTL configuration
- [Dream Sports Nudge Previews API](https://apis.io/apis/dream-sports/dream-sports-nudge-previews-api/) — APIs for managing Nudge Previews. Nudge Previews are used to preview nudge templates before they are used in CTAs. The preview includes the nudge template…
- [Dream Sports OIDC API](https://apis.io/apis/dream-sports/dream-sports-oidc-api/) — The OIDC API from Dream Sports — 7 operation(s) for oidc.
- [Dream Sports OIDC Client Management API](https://apis.io/apis/dream-sports/dream-sports-oidc-client-management-api/) — The OIDC Client Management API from Dream Sports — 3 operation(s) for oidc client management.
- [Dream Sports OIDC Client Scope Management API](https://apis.io/apis/dream-sports/dream-sports-oidc-client-scope-management-api/) — The OIDC Client Scope Management API from Dream Sports — 1 operation(s) for oidc client scope management.
- [Dream Sports OIDC Discovery API](https://apis.io/apis/dream-sports/dream-sports-oidc-discovery-api/) — The OIDC Discovery API from Dream Sports — 1 operation(s) for oidc discovery.
- [Dream Sports OIDC Scope Management API](https://apis.io/apis/dream-sports/dream-sports-oidc-scope-management-api/) — The OIDC Scope Management API from Dream Sports — 2 operation(s) for oidc scope management.
- [Dream Sports Openapi.{type} API](https://apis.io/apis/dream-sports/dream-sports-openapi-type-api/) — The Openapi.{type} API from Dream Sports — 1 operation(s) for openapi.{type}.
- [Dream Sports Organizations API](https://apis.io/apis/dream-sports/dream-sports-organizations-api/) — Organization management endpoints
- [Dream Sports Password API](https://apis.io/apis/dream-sports/dream-sports-password-api/) — The Password API from Dream Sports — 3 operation(s) for password.
- [Dream Sports Passwordless API](https://apis.io/apis/dream-sports/dream-sports-passwordless-api/) — The Passwordless API from Dream Sports — 6 operation(s) for passwordless.
- [Dream Sports Projects API](https://apis.io/apis/dream-sports/dream-sports-projects-api/) — Project management endpoints
- [Dream Sports Provider API](https://apis.io/apis/dream-sports/dream-sports-provider-api/) — The Provider API from Dream Sports — 1 operation(s) for provider.
- [Dream Sports Public Keys API](https://apis.io/apis/dream-sports/dream-sports-public-keys-api/) — The Public Keys API from Dream Sports — 1 operation(s) for public keys.
- [Dream Sports Releases API](https://apis.io/apis/dream-sports/dream-sports-releases-api/) — The Releases API from Dream Sports — 4 operation(s) for releases.
- [Dream Sports Reports API](https://apis.io/apis/dream-sports/dream-sports-reports-api/) — Reporting and download endpoints
- [Dream Sports Runs API](https://apis.io/apis/dream-sports/dream-sports-runs-api/) — Test run management endpoints
- [Dream Sports SDK API](https://apis.io/apis/dream-sports/dream-sports-sdk-api/) — APIs for SDK clients to interact with Thunder. These endpoints handle app launch, state machine synchronization, and nudge preview retrieval for mobile and…
- [Dream Sports Session Management API](https://apis.io/apis/dream-sports/dream-sports-session-management-api/) — The Session Management API from Dream Sports — 5 operation(s) for session management.
- [Dream Sports Sessions API](https://apis.io/apis/dream-sports/dream-sports-sessions-api/) — The Sessions API from Dream Sports — 1 operation(s) for sessions.
- [Dream Sports Social API](https://apis.io/apis/dream-sports/dream-sports-social-api/) — The Social API from Dream Sports — 6 operation(s) for social.
- [Dream Sports Tenants API](https://apis.io/apis/dream-sports/dream-sports-tenants-api/) — The Tenants API from Dream Sports — 2 operation(s) for tenants.
- [Dream Sports Tests API](https://apis.io/apis/dream-sports/dream-sports-tests-api/) — Test case management endpoints
- [Dream Sports Token Exchange API](https://apis.io/apis/dream-sports/dream-sports-token-exchange-api/) — The Token Exchange API from Dream Sports — 1 operation(s) for token exchange.
- [Dream Sports Token Management API](https://apis.io/apis/dream-sports/dream-sports-token-management-api/) — The Token Management API from Dream Sports — 1 operation(s) for token management.
- [Dream Sports User API](https://apis.io/apis/dream-sports/dream-sports-user-api/) — The User API from Dream Sports — 2 operation(s) for user.
- [Dream Sports User Flow Block API](https://apis.io/apis/dream-sports/dream-sports-user-flow-block-api/) — The User Flow Block API from Dream Sports — 3 operation(s) for user flow block.
- [Dream Sports Users API](https://apis.io/apis/dream-sports/dream-sports-users-api/) — User management endpoints
- [Dream Sports Health Check API](https://apis.io/apis/dream-sports/dream-sports-health-check-api/) — The Health Check API from Dream Sports — 2 operation(s) for health check.
- [Dream Sports Open API](https://apis.io/apis/dream-sports/dream-sports-open-api-api/) — The Open API API from Dream Sports — 1 operation(s) for open api.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Dream Sports Webhooks](https://apis.io/asyncapis/dream-sports/dream-sports-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [odin-mcp](https://apis.io/servers/dream-sports/odin-mcp/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Dream Sports Agentic Access](https://apis.io/agentic-access/dream-sports/dream-sports-agentic-access/)

#### JSON Schema (119)

The data models the API reads and writes.

- [AccessKey](https://apis.io/schemas/dream-sports/dream-sports-access-key/)
- [AccessKeyRequest](https://apis.io/schemas/dream-sports/dream-sports-access-key-request/)
- [Account](https://apis.io/schemas/dream-sports/dream-sports-account/)
- [AccountCreate](https://apis.io/schemas/dream-sports/dream-sports-account-create/)
- [AccountStorage](https://apis.io/schemas/dream-sports/dream-sports-account-storage/)
- [AddProviderDetailsRequest](https://apis.io/schemas/dream-sports/dream-sports-add-provider-details-request/)
- [AdminConsoleUserUpdateRequest](https://apis.io/schemas/dream-sports/dream-sports-admin-console-user-update-request/)
- [ApiResponse](https://apis.io/schemas/dream-sports/dream-sports-api-response/)
- [App](https://apis.io/schemas/dream-sports/dream-sports-app/)
- [AppCreationRequest](https://apis.io/schemas/dream-sports/dream-sports-app-creation-request/)
- [AuthLoginRequest](https://apis.io/schemas/dream-sports/dream-sports-auth-login-request/)
- [AuthRefreshRequest](https://apis.io/schemas/dream-sports/dream-sports-auth-refresh-request/)
- [AuthTokenApiResponse](https://apis.io/schemas/dream-sports/dream-sports-auth-token-api-response/)
- [AuthenticateUserRequest](https://apis.io/schemas/dream-sports/dream-sports-authenticate-user-request/)
- [AutomationStatus](https://apis.io/schemas/dream-sports/dream-sports-automation-status/)
- [BehaviourTag](https://apis.io/schemas/dream-sports/dream-sports-behaviour-tag/)
- [BehaviourTagCreateRequest](https://apis.io/schemas/dream-sports/dream-sports-behaviour-tag-create-request/)
- [BehaviourTagPutRequest](https://apis.io/schemas/dream-sports/dream-sports-behaviour-tag-put-request/)
- [BehaviourTagRequest](https://apis.io/schemas/dream-sports/dream-sports-behaviour-tag-request/)
- [BehaviourTagUpdateRequest](https://apis.io/schemas/dream-sports/dream-sports-behaviour-tag-update-request/)
- [BehaviourTagsResponse](https://apis.io/schemas/dream-sports/dream-sports-behaviour-tags-response/)
- [BiometricChallengeRequest](https://apis.io/schemas/dream-sports/dream-sports-biometric-challenge-request/)
- [BiometricChallengeResponse](https://apis.io/schemas/dream-sports/dream-sports-biometric-challenge-response/)
- [BiometricCompleteRequest](https://apis.io/schemas/dream-sports/dream-sports-biometric-complete-request/)
- [ClientListResponse](https://apis.io/schemas/dream-sports/dream-sports-client-list-response/)
- …and 94 more published on APIs.io

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Dream Sports Context](https://apis.io/jsonld/dream-sports/dream-sports-context/)

#### Collections (59)

Postman and Open Collection request collections.

- [Delivr OTA Server Access Keys API](https://apis.io/collections/dream-sports/open-dream-sports-access-keys-api/)
- [DOTA Access Keys API](https://apis.io/collections/dream-sports/open-dream-sports-accesskeys-api/)
- [Dream Sports Account API](https://apis.io/collections/dream-sports/open-dream-sports-account-api/)
- [Delivr OTA Server Acquisition API](https://apis.io/collections/dream-sports/open-dream-sports-acquisition-api/)
- [Guardian Admin API](https://apis.io/collections/dream-sports/open-dream-sports-admin-api/)
- [Raven Journey Admin - Console Users API](https://apis.io/collections/dream-sports/open-dream-sports-admin-console-users-api/)
- [Dream Sports Apps API](https://apis.io/collections/dream-sports/open-dream-sports-apps-api/)
- [Raven Journey Auth API](https://apis.io/collections/dream-sports/open-dream-sports-auth-api/)
- [Delivr OTA Server Authentication API](https://apis.io/collections/dream-sports/open-dream-sports-authentication-api/)
- [Thunder Admin Behaviour Tags API](https://apis.io/collections/dream-sports/open-dream-sports-behaviour-tags-api/)
- [Guardian Cache Management API](https://apis.io/collections/dream-sports/open-dream-sports-cache-management-api/)
- [Raven Journey Client SDK API](https://apis.io/collections/dream-sports/open-dream-sports-client-sdk-api/)
- [Delivr OTA Server Collaborators API](https://apis.io/collections/dream-sports/open-dream-sports-collaborators-api/)
- [Guardian integration endpoints Communication API](https://apis.io/collections/dream-sports/open-dream-sports-communication-api/)
- [Checkmate Test Management Configuration API](https://apis.io/collections/dream-sports/open-dream-sports-configuration-api/)
- [Raven Journey Console Users API](https://apis.io/collections/dream-sports/open-dream-sports-console-users-api/)
- [Thunder Admin CTA Status API](https://apis.io/collections/dream-sports/open-dream-sports-cta-status-api/)
- [Thunder Admin CT As API](https://apis.io/collections/dream-sports/open-dream-sports-ctas-api/)
- [Delivr OTA Server Deployments API](https://apis.io/collections/dream-sports/open-dream-sports-deployments-api/)
- [Guardian Device-Bound Authentication API](https://apis.io/collections/dream-sports/open-dream-sports-device-bound-authentication-api/)
- [Thunder Admin Events API](https://apis.io/collections/dream-sports/open-dream-sports-events-api/)
- [Raven Journey Events Catalog API](https://apis.io/collections/dream-sports/open-dream-sports-events-catalog-api/)
- [Thunder Admin Filters API](https://apis.io/collections/dream-sports/open-dream-sports-filters-api/)
- [Guardian Guest Authentication API](https://apis.io/collections/dream-sports/open-dream-sports-guest-authentication-api/)
- [Dream Sports Health API](https://apis.io/collections/dream-sports/open-dream-sports-health-api/)
- …and 34 more published on APIs.io

#### Overlays (8)

OpenAPI overlays, including conversational phrasing for each operation.

- [Dream Sports Checkmate Overlay](https://apis.io/overlays/dream-sports/dream-sports-checkmate-overlay/)
- [Dream Sports Delivr Ota Overlay](https://apis.io/overlays/dream-sports/dream-sports-delivr-ota-overlay/)
- [Dream Sports Dota Overlay](https://apis.io/overlays/dream-sports/dream-sports-dota-overlay/)
- [Dream Sports Guardian Integrations Overlay](https://apis.io/overlays/dream-sports/dream-sports-guardian-integrations-overlay/)
- [Dream Sports Guardian Overlay](https://apis.io/overlays/dream-sports/dream-sports-guardian-overlay/)
- [Dream Sports Raven Journey Overlay](https://apis.io/overlays/dream-sports/dream-sports-raven-journey-overlay/)
- [Dream Sports Thunder Admin Overlay](https://apis.io/overlays/dream-sports/dream-sports-thunder-admin-overlay/)
- [Dream Sports Thunder Api Overlay](https://apis.io/overlays/dream-sports/dream-sports-thunder-api-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Dream Sports API Rules](https://apis.io/rules/dream-sports/dream-sports-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Dream Sports Authentication](https://apis.io/security/dream-sports/dream-sports-authentication/)
- [Dream Sports Domain Security](https://apis.io/security/dream-sports/dream-sports-domain-security/)
- [Dream Sports Vulnerability Disclosure](https://apis.io/security/dream-sports/dream-sports-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Dream Sports Scopes](https://apis.io/scopes/dream-sports/dream-sports-scopes/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.dreamsports.group/)
- [Documentation](https://dreamhorizon.org/projects)
- [Getting started](https://guardianhq.io/docs/)
- [API reference](https://guardianhq.io/docs/)
- [Support](https://discord.gg/HrJZCrkeAs)
- [Blog](https://blog.dream11engineering.com/)
- [Security](https://github.com/dream-horizon-org/logwise/blob/master/SECURITY.md)
- [Terms of service](https://www.dreamsports.group/terms-of-use)
- [Privacy policy](https://www.dreamsports.group/privacy-policy)
- [GitHub](https://github.com/dream-horizon-org)

## API Evangelist rating

**Kin Score 50.3** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 53.3 |
| Contract governance | 4.5 |
| Operational transparency | 42.1 |
| Developer ergonomics | 73.2 |
| Access clarity | 21.1 |

**Agent readiness 39.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | — |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 40.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/dream-sports/](https://apis.io/providers/dream-sports/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Dream Sports: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/dream-sports/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
