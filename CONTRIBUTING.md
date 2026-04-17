# Contributing

Thanks for your interest in contributing. This list is the single source for developer-focused ML data pipeline tooling; small, careful PRs keep it useful.

## How to contribute

1. Fork this repo.
2. Edit **`entries.yaml`** only. Do not edit `README.md` or `llms.txt` — those are regenerated.
3. Place your entry in the appropriate category (see `categories.yaml`).
4. Open a PR. One entry per PR.

## What belongs in the list

**We accept**
- Workflow orchestrators, ML pipeline frameworks, feature stores.
- Data versioning, lineage, and lakehouse tooling.
- Distributed processing engines and streaming/ingest systems.
- Data-labeling platforms.
- Template/demo projects and reference implementations.

**We don't accept**
- Research papers without runnable code or an API.
- Closed-source tools without developer access.
- Duplicate entries.
- Self-promotional content without developer value.

## Inclusion requirements

- Public product or documentation page; URL resolves.
- Activity signal within the last 12 months.
- Either a public API or an open-source install path.

## Entry format

```yaml
- name: Dagster
  url: https://dagster.io
  docs_url: https://docs.dagster.io
  description: Asset-oriented orchestrator with strong typing and data-asset lineage.
  category: workflow-orchestration
  github: dagster-io/dagster
  license: Apache-2.0
  sdks:
    - {language: Python (pip install dagster)}
  b2_integration: ""
  last_verified: 2026-04-17
```

Field reference is identical across all awesome-* lists in this family.

## Code of conduct

This project follows standard open-source community norms. Be kind, be constructive, focus on the contribution.
