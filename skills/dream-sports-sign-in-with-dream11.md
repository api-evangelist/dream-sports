---
name: Sign a user in with "Login with Dream11" (OpenID Connect)
description: >-
  Run the OpenID Connect authorization-code flow against Dream11's production identity service to
  authenticate a user as their Dream11 account and read consented profile claims. Use this when
  integrating Dream11 sign-in, or when reasoning about which claims an app is entitled to.
api: https://auth.dream11.com/.well-known/openid-configuration
generated: '2026-08-04'
method: generated
source: well-known/dream-sports-openid-configuration.json (live, HTTP 200) + https://guardianhq.io/docs/
operations:
  - GET /authorize
  - POST /token
  - GET /userinfo
  - GET /certs
  - POST /revokeToken
---

# Sign a user in with "Login with Dream11"

Dream11's identity service is the one Dream Sports API surface that is live, public and
machine-discoverable. It publishes an OpenID Connect discovery document; there is no OpenAPI for it,
so **the discovery document is the contract** — fetch it, do not hardcode endpoints.

- Issuer: `https://auth.dream11.com`
- Discovery: `https://auth.dream11.com/.well-known/openid-configuration` (also served from
  `https://api.dream11.com/.well-known/openid-configuration`)

## What the service supports

- `response_types_supported`: `code` — **authorization code only**. There is no implicit flow and no
  client-credentials flow. Do not attempt one.
- `grant_types_supported`: `authorization_code`, `refresh_token`.
- `id_token_signing_alg_values_supported`: `RS256`. Keys at `https://auth.dream11.com/certs`
  (currently RS512-signed JWKS entries — read `alg` per key, never assume).
- `token_endpoint_auth_methods_supported` is **empty**, which means the server advertises no client
  authentication method at the token endpoint. Treat this as an unspecified detail to confirm with
  Dream11 during onboarding rather than something to infer.

## Steps

1. **Fetch discovery.** Read `authorization_endpoint`, `token_endpoint`, `userinfo_endpoint`,
   `revocation_endpoint` and `jwks_uri` from the document; they are the only authoritative source.
2. **Redirect to `/authorize`** with `response_type=code`, your `client_id`, `redirect_uri`, `state`,
   and the scopes you actually need. Guardian (the engine behind this service) supports PKCE — use
   `code_challenge`/`code_verifier`.
3. **The user consents.** Dream11 runs an in-built consent screen; the user chooses which profile
   details are shared, so **a granted scope is not a guaranteed claim**. Always handle a claim being
   absent from `/userinfo`.
4. **Exchange the code at `/token`** for an ID token, access token and refresh token.
5. **Validate the ID token** against the JWKS at `/certs`, checking `iss` = `https://auth.dream11.com`
   and your `aud`.
6. **Read claims from `/userinfo`** when you need more than the ID token carries.
7. **Refresh** with the `refresh_token` grant. **Revoke** at `https://auth.dream11.com/revokeToken`
   when the user disconnects — note this path differs from Guardian's open-source `/token/revoke`;
   use the `revocation_endpoint` value from discovery.

## Scopes (exactly seven — do not request others)

`openid`, `profile`, `email`, `phone`, `masked_phone_number`, `pan_verified`, `team_name`.

Claims: `sub`, `email`, `phone_number`, `masked_phone_number`, `pan_verified`, `picture`, `team_name`.

## Rules

- **Request the narrowest scope set.** `phone` and `pan_verified` are sensitive: `pan_verified` is an
  Indian KYC signal, and `masked_phone_number` exists precisely so an app can display a number
  without holding it. If a masked number will do, do not ask for `phone`.
- **Never log or persist an ID token, access token, refresh token, or any claim beyond what your
  purpose requires.**
- `pan_verified` is a boolean verification status, not a PAN. Never treat it as, or ask for, the
  identifier itself.
- Full scope and claim detail: `scopes/dream-sports-scopes.yml`. Auth profile:
  `authentication/dream-sports-authentication.yml`.
