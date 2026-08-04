---
name: Deploy and operate services on Odin through the MCP server
description: >-
  Use Dream Sports' first-party odin-mcp server to list, describe, deploy and operate services and
  environments on Odin, its internal developer platform. Use this when an agent has been given access
  to an Odin installation and needs to act on it safely.
api: mcp/dream-sports-mcp.yml
generated: '2026-08-04'
method: generated
source: >-
  https://github.com/dream-horizon-org/odin-mcp (README tool tables) and the protobuf service
  definitions in grpc/dream-sports-odin-*.proto
operations:
  - deployer_health
  - deployer_grpc_health
  - deployer_component_catalogue
  - deployer_component_operations
  - deployer_operation_schemas_list
  - deployer_operation_schema_get
  - deployer_grpc_list_environment
  - deployer_grpc_describe_environment
  - deployer_grpc_status_environment
  - deployer_grpc_list_services
  - deployer_grpc_describe_service
  - deployer_grpc_list_service_versions
  - deployer_grpc_operate_component_diff
  - deployer_grpc_deploy_service
  - deployer_grpc_operate_service
  - deployer_operate_component
  - deployer_operate_status
  - deployer_grpc_release_service
  - deployer_grpc_check_service_release_name_unique
  - deployer_grpc_export_service
  - scout_accounts_list
  - scout_account_details_get
  - user_auth_orgs_list
  - user_auth_teams_list
  - user_auth_team_members_list
---

# Deploy and operate services on Odin through the MCP server

`odin-mcp` is a **stdio** MCP server. It is a thin adapter — all logic stays in the Java services —
calling odin-deployer over REST (default `:9000`) and gRPC (default `:8080`), odin-scout over REST
(`:8080`), and user-auth over REST (`:8081`).

## Setup you must confirm before acting

- `ODIN_DEPLOYER_AUTH_TOKEN` must hold the full `Authorization` value (usually `Bearer <jwt>`).
  Protected tools fail with 401/403 without it.
- Org-scoped user-auth routes need `X-Org-Id`. The server fills it from the tool's `org_id` argument,
  or from the JWT `orgid` claim on an org-scoped token. **If your token is user-level, pass `org_id`
  explicitly.**
- Long streams: `deployer_grpc_*` operations that stream accept `stream_completion`. Use
  `first_progress` when the client may drop a long wait — the operation continues server-side and you
  poll `deployer_grpc_describe_service` / `deployer_grpc_status_environment` for the outcome. Never
  interpret an early return as completion.

## Read before you write

1. `deployer_health` and `deployer_grpc_health` — confirm both transports are reachable.
2. `scout_accounts_list`, then `scout_account_details_get` — know which cloud account you are in.
3. `deployer_grpc_list_environment` → `deployer_grpc_describe_environment` — know the target
   environment and its current state.
4. `deployer_grpc_list_services` → `deployer_grpc_describe_service` — know the service's current
   deployed shape.
5. `deployer_component_catalogue`, `deployer_component_operations`,
   `deployer_operation_schemas_list`, `deployer_operation_schema_get` — **the operation schema is the
   contract for what `operate` will accept.** Read it rather than guessing an operate payload.
6. `deployer_grpc_operate_component_diff` — see what a change would do before doing it.

## Deploying and operating

- `deployer_grpc_deploy_service` deploys; `deployer_grpc_operate_service` performs service-level
  operations; `deployer_operate_component` (REST) operates a single component, and
  `deployer_operate_status` polls the resulting `service_task_id`.
- `deployer_grpc_check_service_release_name_unique` before `deployer_grpc_release_service` — release
  names must be unique, and checking first avoids a failed release.
- `deployer_grpc_list_service_versions` and `deployer_grpc_export_service` are the safe read paths for
  rollback planning.

## Rules — these are the load-bearing part of this skill

- **Never call a destructive tool without an explicit, current human instruction naming the target.**
  Destructive: `deployer_grpc_delete_environment`, `deployer_grpc_undeploy_service`,
  `deployer_grpc_create_environment` (provisions real infrastructure), and every user-auth tool that
  the provider gates with `type_to_confirm`: `user_auth_org_delete`, `user_auth_team_delete`,
  `user_auth_team_transfer_owner`, `user_auth_team_remove_member`,
  `user_auth_org_member_remove`, `user_auth_org_member_promote_admin`,
  `user_auth_org_member_set_role`.
- **`type_to_confirm` is not a formality to satisfy — it is a human checkpoint.** The value must be
  re-supplied by the user (the team name, the member email, or the numeric org id). An agent that
  fills it in from its own earlier read has defeated the guard the provider built.
- **No idempotency key exists anywhere in this stack.** A retried create makes a second object.
  Read back before retrying.
- **Do not read tokens from, or write tokens into, the environment or config files.** The README is
  explicit: do not commit real tokens or `.env` files.
- Tool-to-contract bindings, and which tools have no published contract at all, are recorded in
  `mcp/dream-sports-tool-crosswalk.yml`. The 28 REST-backed tools have no OpenAPI behind them — their
  input shapes come from README prose, so validate responses rather than assuming a schema.
