---
name: Manage Raven Thunder CTAs, behaviour tags and the event catalog
description: >-
  Register events, define behaviour tags, and manage the lifecycle of CTAs on the Raven Thunder admin
  API — the serving side of Dream Sports' in-app messaging stack. Use this when an agent maintains the
  targeting vocabulary or drives CTA status, rather than authoring a full journey.
api: openapi/dream-sports-thunder-admin-openapi.yml
generated: '2026-08-04'
method: generated
source: openapi/dream-sports-thunder-admin-openapi.yml and openapi/dream-sports-thunder-api-openapi.yml
operations:
  - getAllEventNames
  - getAllEvents
  - getEvent
  - upsertEvents
  - patchEvent
  - deleteEvent
  - listBehaviourTags
  - getBehaviourTag
  - createBehaviourTag
  - updateBehaviourTag
  - getFilters
  - listCTAs
  - getCTA
  - createCTA
  - updateCTA
  - scheduleCTA
  - activateCTA
  - pauseCTA
  - concludeCTA
  - terminateCTA
  - getNudgePreview
  - createOrUpdateNudgePreview
  - appLaunch
  - mergeSnapshotDelta
---

# Manage Raven Thunder CTAs, behaviour tags and the event catalog

Raven Thunder is the serving half of Dream Sports' in-app messaging platform: a client-facing SDK API
and an admin API. Both are self-hosted.

## Before you start

- **`x-tenant-id` on every request.** It is the most-used header across the whole Dream Sports API
  estate (25 declared occurrences). The admin API also takes `user` and `x-source` context headers.
- The admin surface declares only **400** and **404** — there is no 5xx contract. Treat a 400 as
  either a validation failure or an illegal state transition, and read the message before acting.

## Order of operations

The three admin concepts are layered, and building them out of order produces 400s:

1. **Events first** — `upsertEvents` registers the events the platform can react to. Inspect what
   exists with `getAllEventNames` (cheap) or `getAllEvents` (full), and `getEvent` for one.
   `patchEvent` edits, `deleteEvent` removes.
2. **Behaviour tags next** — `listBehaviourTags`, `getBehaviourTag`, `createBehaviourTag`,
   `updateBehaviourTag`. Tags are built on registered events; creating a tag against an unregistered
   event will fail validation.
3. **Filters** — `getFilters` returns the targeting vocabulary. Read it; do not invent filter fields.
4. **CTAs last** — `createCTA` / `updateCTA`, read back with `getCTA`, and browse with `listCTAs`.

## CTA lifecycle

`scheduleCTA` → `activateCTA` → (`pauseCTA` ↔ `activateCTA`) → `concludeCTA`. `terminateCTA` is the
hard stop.

The spec is explicit that transitions are validated: a CTA "cannot be terminated from current status.
Only DRAFT, SC…". **A 400 on a lifecycle call is an illegal transition, not a transient error.**
Re-read with `getCTA` and choose a legal transition; never retry the same call.

## Previewing

`createOrUpdateNudgePreview` stores a preview; `getNudgePreview` reads it back. On the client SDK API,
`getNudgePreview` (by id) renders it. Preview before activating anything user-facing.

## Client-side operations (Thunder SDK API)

`appLaunch` returns the active CTA state machines for a device on launch, and `mergeSnapshotDelta`
merges a snapshot delta. These take client context headers — `api_version`, `app_version`,
`package_name`, `codepush_version`, `auth-userid` — which are used for **targeting**, so sending wrong
values silently changes which CTAs a user is eligible for. Do not fabricate them.

## Rules

- **Never terminate or delete on your own initiative.** `terminateCTA` and `deleteEvent` are
  destructive and irreversible; require an explicit human instruction naming the object.
- **Deleting an event breaks every behaviour tag and CTA built on it.** Check usage first with
  `getAllEvents` and `listBehaviourTags`.
- **No idempotency key.** `createCTA`, `createBehaviourTag` and `upsertEvents` are not safe to blind-
  retry — read back instead. See `conventions/dream-sports-conventions.yml`.
