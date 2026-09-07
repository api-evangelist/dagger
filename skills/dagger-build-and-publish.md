---
name: dagger-build-and-publish
description: >-
  Build a container from source and publish it to an OCI registry using the Dagger
  Engine API. Covers the sandbox rules for getting host files in, and the one
  operation in this flow that is not reversible.
api: dagger:graphql
generated: '2026-09-07'
method: generated
source: >-
  Grounded in graphql/dagger-schema.graphqls (Container, Directory, Host, Service
  types read from the SDL), openapi/dagger-graphql-api-openapi.yml, and
  conventions/dagger-conventions.yml
operations:
  - executeGraphQLQuery
---

# Build a container and publish it

## Model

Every step returns a **new immutable value**. `Container.withExec` does not mutate
a container, it produces another one. That is why almost nothing here needs undoing
— the previous value is still addressable — and why you should stop thinking about
"the container" and start thinking about a chain of values.

## Steps

1. **Get the source in.** Host files only enter the graph through explicit typed
   arguments. Use `Host.directory` for a local path or `Query.git` →
   `GitRepository.branch` → `GitRef.tree` for a repository. Nothing else on the
   host is reachable — Dagger Functions are sandboxed and "do not have direct
   access to the host system".

2. **Start a container.** `Query.container` → `Container.from` with a base image
   address.

3. **Mount and build.** `Container.withDirectory` to bring the source in,
   `Container.withWorkdir`, then `Container.withExec` for each build step. Add
   `Query.cacheVolume` + `Container.withMountedCache` for dependency caches — this
   is where Dagger's speed comes from, and skipping it is the most common reason a
   Dagger pipeline feels no faster than the CI it replaced.

4. **Verify before you publish.** Chain `Container.stdout` or run tests with
   another `withExec`. Because evaluation is lazy, none of the above has actually
   run until you request a leaf value like this.

5. **Publish.** `Container.publish` with the destination address. Since v0.21.6 it
   accepts a `registryService` option so you can publish to a registry provided by
   a Dagger `Service` — useful for ephemeral local registries.

## Reversibility — read this before step 5

Steps 1–4 are pure and cost you nothing to redo. **Step 5 is not.**
`Container.publish` pushes to an external registry and **Dagger has no unpublish
operation**. There is no window, no undo, no `withoutPublish`. If the tag needs
retracting, that is the registry's problem and the registry's API, not Dagger's.
Publish to a disposable tag first if you are unsure. Same posture applies to
`Container.export` / `Directory.export`, which write to the caller's host
filesystem and cannot be undone by Dagger either.

## Idempotency

There is no `Idempotency-Key`. What you have instead is content addressing:
identical inputs resolve from cache rather than re-executing, which makes the
build half of this flow naturally replay-safe. It does **not** make `publish`
replay-safe — that reaches a remote registry. Do not treat Dagger's caching as an
idempotency guarantee on the operations that leave the sandbox.
