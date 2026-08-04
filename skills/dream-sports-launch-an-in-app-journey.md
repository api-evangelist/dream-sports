---
name: Launch an in-app journey with Raven
description: >-
  Create, review and take live a Raven in-app messaging journey (CTA) against a tenant, then pause or
  terminate it. Use this when an agent needs to ship or control an in-app nudge campaign on the Dream
  Sports Raven platform.
api: openapi/dream-sports-raven-journey-openapi.yml
generated: '2026-08-04'
method: generated
source: openapi/dream-sports-raven-journey-openapi.yml (every operationId below is verbatim from the spec)
operations:
  - healthCheck
  - googleLogin
  - refreshToken
  - getFilters
  - listJourneys
  - createJourney
  - getJourney
  - updateJourney
  - scheduleJourney
  - activateJourney
  - pauseJourney
  - concludeJourney
  - terminateJourney
  - createTestJourney
  - removeTestJourney
---

# Launch an in-app journey with Raven

Raven is Dream Sports' open-source in-app messaging and journey platform, published through Dream
Horizon. It is self-hosted: the base URL is whatever host the operator runs Raven on. The hosted
reference instance is `https://raven.dreamhorizon.org/`.

## Before you start

- **Tenant scoping is mandatory.** Raven declares a `TenantIdHeader` API-key scheme carrying the
  `TENANT-ID` header. Every request needs it. A missing or wrong tenant returns **401**, and a user
  who is not onboarded for that tenant returns **403** — not 404. Do not retry either; fix the header
  or the onboarding.
- **Authenticate first.** Call `googleLogin` to exchange a Google credential for an access token, and
  `refreshToken` when it expires. Send the token as `Authorization: Bearer <token>`.
- **Check the service is up** with `healthCheck` before a long orchestration; Raven returns **502** on
  a downstream auth failure and **504** on a downstream timeout, and those are infrastructure states,
  not request errors.

## Steps

1. **Confirm reachability** — `healthCheck`.
2. **Get a token** — `googleLogin`. Keep the refresh token; call `refreshToken` rather than
   re-authenticating.
3. **Read the targeting vocabulary** — `getFilters` returns the filter surface a journey can target
   on. Build targeting from this, never from guessed field names.
4. **See what already exists** — `listJourneys`. It is page-number paginated (`pageNumber`,
   `pageSize`). Read the existing set before creating anything, because there is no idempotency key
   on this API and a retried `createJourney` creates a second journey.
5. **Create the journey** — `createJourney`. A **400** here is a validation error on the body; read
   the `error` field of the response envelope and fix the payload rather than retrying unchanged.
6. **Read it back** — `getJourney` with the returned `ctaId`. This read-back is the substitute for
   idempotency: it is how you tell a timeout-then-success apart from a real failure.
7. **Adjust if needed** — `updateJourney`.
8. **Dry-run it** — `createTestJourney` puts a test journey in front of a test audience; clean up with
   `removeTestJourney`.
9. **Schedule or go live** — `scheduleJourney` for a future window, `activateJourney` to take it live
   now.
10. **Control it in flight** — `pauseJourney` to hold, `concludeJourney` to end it normally.
    `terminateJourney` is the hard stop.

## Rules

- **Never call `terminateJourney` on your own initiative.** Terminate is irreversible and stops a
  live campaign; require an explicit human instruction naming the journey. Same for
  `deleteBehaviourTag` and the `deleteConsoleUser*` operations in the same spec.
- **Status transitions are validated server-side.** The sibling Thunder admin API returns 400 with
  "cannot be terminated from current status" — treat a 400 on a lifecycle operation as an illegal
  transition, re-read the journey with `getJourney`, and do not retry the same call.
- **409 means it already exists.** Re-read rather than re-create.
- **No retry key exists.** See `conventions/dream-sports-conventions.yml` — Dream Sports publishes no
  `Idempotency-Key` header on any surface. Every write in this skill is unsafe to blind-retry.
- Errors are a vendor JSON envelope (`{error: ...}`), not RFC 9457 problem+json. See
  `errors/dream-sports-problem-types.yml`.
