# Dagger (dagger)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
