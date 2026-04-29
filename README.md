# Dagger (dagger)

Dagger is an open-source programmable CI/CD engine that runs pipelines in containers using a unified, introspectable GraphQL API. Pipelines are written as code in the developer's preferred language (Go, Python, TypeScript, PHP, Java, .NET, Elixir, Rust) using Dagger SDKs and packaged as Dagger Modules that can be published to the Daggerverse module index. The Dagger Engine exposes Container, Directory, File, Secret, and CacheVolume as first-class GraphQL types backed by a content-addressed store. Dagger Cloud is the hosted control plane for pipeline traces, checks, and module observability.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/dagger/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** Open Source
- **x-type:** opensource

## Tags

- Build Automation, BuildKit, CI/CD, Containers, DAG, Daggerverse, DevOps, GraphQL, Modules, OCI, Open Source, Pipelines, Programmable Pipelines, SDKs

## Timestamps

- **Created:** 2026-03-26
- **Modified:** 2026-04-28

## APIs

### Dagger Engine GraphQL API

The Dagger Engine exposes a unified, introspectable GraphQL type system at a per-session endpoint. The schema includes Container, Directory, File, Secret, and CacheVolume as first-class types and is dynamically extended at runtime by loaded Dagger Modules. There is no publicly-hosted REST endpoint.

- **Human URL:** https://docs.dagger.io/api/
- **Capabilities:** [capabilities/dagger-graphql-capabilities.yml](capabilities/dagger-graphql-capabilities.yml)

### Dagger SDKs

Native SDKs for Go, Python, TypeScript, PHP, Java, .NET, Elixir, and Rust generate strongly typed clients against the Dagger Engine's GraphQL schema.

- **Human URL:** https://docs.dagger.io/sdk/

### Daggerverse Module Index

Free, public index of Dagger Modules. Developers search for, browse, and consume reusable Modules contributed by the Dagger community.

- **Human URL:** https://daggerverse.dev/

### Dagger Cloud

Hosted control plane providing pipeline traces, checks, module observability, and team collaboration.

- **Human URL:** https://dagger.io/cloud

## Capabilities

- Programmable, language-native CI/CD pipelines
- Deterministic content-addressed builds with aggressive caching
- Container build, exec, and publish via GraphQL types
- Module reuse and discovery via the Daggerverse
- Pipeline observability and traces in Dagger Cloud
- Pluggable runtime supporting any CI provider

## Use Cases

- Replace YAML-based CI configurations with code-based pipelines
- Run identical pipelines locally, in CI, and in production
- Build and publish multi-arch container images
- Share build modules across teams and the open-source community
- Stream pipeline traces to Dagger Cloud for observability
- Execute pipelines from any CI provider (GitHub Actions, GitLab, Jenkins, CircleCI, etc.)

## Common Resources

- [Dagger Website](https://dagger.io/)
- [Documentation](https://docs.dagger.io/)
- [Quickstart](https://docs.dagger.io/quickstart)
- [Reference](https://docs.dagger.io/reference/)
- [GitHub Organization](https://github.com/dagger)
- [GitHub Repository](https://github.com/dagger/dagger)
- [Daggerverse](https://daggerverse.dev/)
- [Blog](https://dagger.io/blog)
- [Discord](https://discord.gg/dagger-io)
- [JSON-LD Context](json-ld/dagger-context.jsonld)
- [Vocabulary](vocabulary/dagger-vocabulary.yml)
- [Capabilities](capabilities/dagger-graphql-capabilities.yml)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
