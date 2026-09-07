---
name: dagger-run-service
description: >-
  Stand up a backing service (database, cache, API dependency) as a Dagger Service,
  bind it to a container, and shut it down. Use this for integration tests and for
  local development stacks.
api: dagger:graphql
generated: '2026-09-07'
method: generated
source: >-
  Grounded in graphql/dagger-schema.graphqls (Service, Port, Container types read
  from the SDL) and openapi/dagger-graphql-api-openapi.yml
operations:
  - executeGraphQLQuery
---

# Run a service alongside a container

## Steps

1. **Define the service container.** `Query.container` → `Container.from` with the
   service image, then `Container.withExposedPort` for each port it listens on.

2. **Turn it into a service.** `Container.asService`. A `Service` is a distinct
   type in the schema with its own lifecycle, not just a container you left
   running.

3. **Start it and get an address.** `Service.start`, then `Service.endpoint` for a
   reachable address, or `Service.ports` to enumerate the bound `Port` values.

4. **Bind it to the consumer.** `Container.withServiceBinding` on the container
   that needs it, giving the hostname the consumer will resolve.

5. **Stop it.** `Service.stop`. This is one of the few genuinely reversible
   operations in the API — the schema exposes both start and stop, and stopping
   releases the ports. There is no time window on it.

## Watch out for

- **Ports are real.** Starting a service binds actual ports on the host network
  namespace the engine manages. Repeating `Service.start` is not free the way
  repeating a pure transformation is — this is one of the two write surfaces
  (with `Container.publish`) where Dagger's content-addressed caching does not
  protect you.
- **Health.** `Container.dockerHealthcheck` exposes the image's declared
  `HealthcheckConfig`. Use it rather than sleeping and hoping.
- **Errors still arrive as HTTP 200.** A service that fails to start reports it in
  the GraphQL `errors` array, not in the status code.
