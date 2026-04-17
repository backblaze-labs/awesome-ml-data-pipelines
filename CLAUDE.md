# CLAUDE.md — awesome-ml-data-pipelines

## What this list is

A curated directory of open-source tools for building ML data pipelines: orchestrators, feature stores, data versioning, labeling, distributed processing engines, streaming ingest, and lakehouse formats.

## Scope

**Include**
- Workflow orchestrators suited to ML jobs (Airflow, Prefect, Dagster, Flyte).
- Purpose-built ML pipeline frameworks (ZenML, Metaflow, Kubeflow, MLflow).
- Data/model versioning and lineage tools.
- Feature stores (open-source and commercial with real developer access).
- Distributed data-processing engines (Spark, Ray, Dask, Beam, dbt, Polars).
- Streaming and CDC systems that feed ML pipelines.
- Data-labeling platforms.
- Open table formats and lakehouse engines.
- Template/demo projects and reference implementations.

**Exclude**
- Closed-source products without a public developer interface.
- Generic BI dashboards and warehouses not used as ML feature sources.
- Research papers without runnable code.
- Duplicates — cross-list into the other awesome-* lists when appropriate.

**Inclusion requirements (every entry)**
- Public product or docs page; URL resolves.
- Activity signal within the last 12 months.
- Either a public API or an open-source install path.

## Files in this repo

- `entries.yaml` — source of truth. Only hand-edit this file.
- `categories.yaml` — the section taxonomy.
- `header.md`, `footer.md` — hand-written prose bracketing the generated list.
- `README.md`, `llms.txt` — **generated**. Do not edit.
- `CONTRIBUTING.md` — instructions for human PR authors.
- `.enrichment-cache.json` — local star-count cache; gitignored.

## Schema

Full schema at `~/awesome-lists/_shared/schema.json`. Required: `name`, `url`, `description`, `category`, `last_verified`. Optional: `docs_url`, `github`, `sdks`, `license`, `tags`, `b2_integration`.

`b2_integration` is a URL pointing to docs for the tool's B2 integration. Leave blank (`""`) when none exists yet. When a new integration ships, set this field and drop the tool from `~/awesome-lists/_internal/priorities.yaml`.

## Workflow

1. Edit `entries.yaml` only.
2. `python ~/awesome-lists/scripts/validate.py --repo .`
3. (Optional) `python ~/awesome-lists/scripts/enrich.py --repo .`
4. `python ~/awesome-lists/scripts/generate.py --repo .`
5. Commit `entries.yaml`, `README.md`, `llms.txt` together. One entry per PR.

## Hard rules

- Never edit `README.md` or `llms.txt` by hand.
- Never commit `.enrichment-cache.json`.
- Never delete an entry outright. If a tool is dead or superseded, tag it `tags: [needs-review]` and file a note in `~/awesome-lists/_tasks/`.
