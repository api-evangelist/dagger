# Dagger (dagger)

Dagger is an open-source programmable CI/CD engine that runs pipelines in containers using a unified, introspectable GraphQL API. Pipelines are written as code in the developer's preferred language (Go, Python, TypeScript, PHP, Java, .NET, Elixir, or Rust) using Dagger SDKs and packaged as Dagger Modules that can be published to the Daggerverse module index. The Dagger Engine exposes Container, Directory, File, Secret, and CacheVolume as first-class GraphQL types backed by a content-addressed store, enabling deterministic builds and aggressive caching. Dagger Cloud provides the hosted control plane for pipeline traces, checks, and module observability. Dagger does not expose a public REST API; clients connect to a per-session Dagger Engine GraphQL endpoint and the optional Dagger Cloud Web UI.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/dagger/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/dagger/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** Open Source

## Tags

- Build Automation
- BuildKit
- CI/CD
- Containers
- DAG
- Daggerverse
- DevOps
- GraphQL
- Modules
- OCI
- Open Source
- Pipelines
- Programmable Pipelines
- SDKs

## Timestamps

- **Created:** 2026-03-26
- **Modified:** 2026-04-28

## APIs

### Dagger Engine GraphQL API

The Dagger Engine exposes a unified, introspectable GraphQL type system at a per-session endpoint. The schema includes Container, Directory, File, Secret, CacheVolume, and other first-class types and is dynamically extended at runtime by loaded Dagger Modules. All Dagger SDKs (Go, Python, TypeScript, PHP, Java, .NET, Elixir, Rust) are generated against this schema. There is no publicly-hosted REST endpoint.

- **Human URL:** [https://docs.dagger.io/api/](https://docs.dagger.io/api/)

#### Tags

- GraphQL
- Introspection
- Modules
- SDK

#### Properties

- [Documentation](https://docs.dagger.io/api/)
- [API Reference](https://docs.dagger.io/reference/)
- [A P I Internals](https://docs.dagger.io/api/internals/)
- [Blog](https://dagger.io/blog/graphql)
- [Capabilities](capabilities/dagger-graphql-capabilities.yml)
- [Postman Collection](collections/dagger.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/dagger.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Dagger SDKs

Native SDKs for Go, Python, TypeScript, PHP, Java, .NET, Elixir, and Rust that generate strongly typed clients against the Dagger Engine's GraphQL schema, allowing pipelines to be written as regular code in the developer's preferred language.

- **Human URL:** [https://docs.dagger.io/sdk/](https://docs.dagger.io/sdk/)

#### Tags

- .NET
- Elixir
- Go
- Java
- PHP
- Python
- Rust
- SDKs
- TypeScript

#### Properties

- [Documentation](https://docs.dagger.io/sdk/)
- [GitHub Repository](https://github.com/dagger/dagger)
- [Postman Collection](collections/dagger.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/dagger.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Daggerverse Module Index

Daggerverse is the free, public index of Dagger Modules. Developers search for, browse, and consume reusable Modules contributed by the Dagger community.

- **Human URL:** [https://daggerverse.dev/](https://daggerverse.dev/)

#### Tags

- Daggerverse
- Modules
- Registry

#### Properties

- [Website](https://daggerverse.dev/)
- [Quickstart](https://docs.dagger.io/ci/quickstart/simplify/)
- [Postman Collection](collections/dagger.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/dagger.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Dagger Cloud

Dagger Cloud is the hosted control plane providing pipeline traces, checks, module observability, and team collaboration. It integrates with the local Dagger Engine for seamless trace uploads.

- **Human URL:** [https://dagger.io/cloud](https://dagger.io/cloud)

#### Tags

- Cloud
- Observability
- Telemetry
- Traces

#### Properties

- [Website](https://dagger.io/cloud)
- [Sign Up](https://dagger.cloud/signup)
- [Postman Collection](collections/dagger.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/dagger.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/dagger-io)
- [Website](https://dagger.io/)
- [Documentation](https://docs.dagger.io/)
- [Getting Started](https://docs.dagger.io/quickstart)
- [Reference](https://docs.dagger.io/reference/)
- [GitHub Organization](https://github.com/dagger)
- [GitHub Repository](https://github.com/dagger/dagger)
- [Daggerverse](https://daggerverse.dev/)
- [Blog](https://dagger.io/blog)
- [Pricing](https://dagger.io/pricing)
- [Sign Up](https://dagger.cloud/signup)
- [Discord](https://discord.gg/dagger-io)
- [YouTube](https://www.youtube.com/@dagger-io)
- [Twitter](https://twitter.com/dagger_io)
- [License](https://github.com/dagger/dagger/blob/main/LICENSE)
- [JSON-LD](json-ld/dagger-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/dagger-vocabulary.yml)
- [Capabilities](capabilities/dagger-graphql-capabilities.yml)
- [Integrations](https://dagger.io/partners/)
- [L L Ms Txt](https://docs.dagger.io/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
