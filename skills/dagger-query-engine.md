---
name: dagger-query-engine
description: >-
  Call the Dagger Engine's GraphQL API directly over HTTP from inside a running
  Dagger session, and handle its errors correctly. Use this when you need engine
  behaviour that no SDK method exposes, or when you are writing tooling that
  speaks to Dagger without a language SDK.
api: dagger:graphql
generated: '2026-09-07'
method: generated
source: >-
  Grounded in openapi/dagger-graphql-api-openapi.yml (operationIds supplied by
  overlays/dagger-graphql-api-overlay.yaml), graphql/dagger-schema.graphqls, and
  https://docs.dagger.io/0.21/getting-started/api/http/
operations:
  - executeGraphQLQuery
  - executeGraphQLQueryViaGet
---

# Query the Dagger Engine directly

## Before you start

There is no hosted Dagger endpoint. The API exists only inside a session, on
loopback, and disappears when the session ends. Do not look for a public base URL
— there isn't one, and anything claiming otherwise is not Dagger.

## Steps

1. **Start a session.** Run your program under `dagger run`. The engine sets two
   environment variables in that process: `DAGGER_SESSION_PORT` and
   `DAGGER_SESSION_TOKEN`. If either is unset, you are not inside a session and
   every request will fail — start there rather than debugging the request.

2. **Build the endpoint.** `http://127.0.0.1:$DAGGER_SESSION_PORT/query`.

3. **Authenticate.** HTTP Basic, with the token as the *username* and an empty
   password: `-u $DAGGER_SESSION_TOKEN:`. The trailing colon matters. A missing or
   wrong token returns `401` (`executeGraphQLQuery`, response 401).

4. **POST the query** with `content-type: application/json` and a body of
   `{"query": "...", "variables": {...}}`. Reference invocation, verbatim from
   Dagger's docs:

   ```bash
   curl -s \
     -u $DAGGER_SESSION_TOKEN: \
     -H "content-type:application/json" \
     -d @- \
     http://127.0.0.1:$DAGGER_SESSION_PORT/query
   ```

5. **Read the response as GraphQL, not as REST.** This is the step most
   integrations get wrong. `executeGraphQLQuery` returns HTTP **200 even when the
   operation failed** — the failure is in the `errors` array of the body. Check
   `errors` before you touch `data`. A response can carry *both*: `data` present
   with a non-empty `errors` array is a partial failure of the named path, not a
   success. See `errors/dagger-problem-types.yml`.

6. **Prefer one chained query over many round trips.** Dagger evaluates lazily —
   nothing executes until a leaf value is requested — so chaining the whole
   pipeline into a single query lets the engine plan it as one DAG. Splitting it
   across requests is slower and defeats the point.

## Grounding the query

Field names come from `graphql/dagger-schema.graphqls` (84 object types). Start
from a `Query` constructor — `container`, `directory`, `file`, `git`,
`currentWorkspace` — and chain. Do not invent field names; the schema is in this
repo, grep it.

## Watch out for

- **The schema is dynamic.** Loading a module adds fields. The saved SDL is the
  core schema, not necessarily the schema of the session you are talking to.
- **`GET /query` exists** (`executeGraphQLQueryViaGet`) but the SDKs use POST.
  Use POST unless you have a specific reason.
- **Deprecated fields are marked in the schema itself**, with `@deprecated` and a
  reason. There is no published removal window — see
  `lifecycle/dagger-lifecycle.yml`.
