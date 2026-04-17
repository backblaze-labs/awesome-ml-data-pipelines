# Awesome ML Data Pipelines [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) [![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

A curated list of open-source frameworks, engines, and platforms for building production ML data pipelines — orchestration, processing, versioning, feature storage, and everything in between.

Maintained by [Backblaze](https://www.backblaze.com/cloud-storage?utm_source=github&utm_medium=referral&utm_campaign=ai_artifacts&utm_content=awesomelist). Backblaze B2 is the storage cloud for innovators building at the speed of AI. 

### Related Lists

- [Awesome Multimodal Data](https://github.com/backblaze-labs/awesome-multimodal-data)
- [Awesome Agent Infrastructure](https://github.com/backblaze-labs/awesome-agent-infrastructure)
- [Awesome Physical AI](https://github.com/backblaze-labs/awesome-physical-ai)
- [Awesome Image Generation](https://github.com/backblaze-labs/awesome-image-generation)
- [Awesome Video Generation](https://github.com/backblaze-labs/awesome-video-generation)
- [Awesome Audio Generation](https://github.com/backblaze-labs/awesome-audio-generation)

## Contents

- [Workflow Orchestration](#workflow-orchestration)
- [ML Pipeline Frameworks](#ml-pipeline-frameworks)
- [Data Versioning and Lineage](#data-versioning-and-lineage)
- [Feature Stores](#feature-stores)
- [Data Processing Engines](#data-processing-engines)
- [Streaming and Ingest](#streaming-and-ingest)
- [Data Labeling](#data-labeling)
- [Storage Formats and Lakehouses](#storage-formats-and-lakehouses)
- [Templates and Example Projects](#templates-and-example-projects)

---

## Workflow Orchestration

> General-purpose orchestrators for scheduling and running data and ML jobs.

- **[Apache Airflow](https://airflow.apache.org)** – The de-facto open-source workflow orchestrator. Python-defined DAGs, thousands of operators, huge ecosystem. [Docs](https://airflow.apache.org/docs/) | SDK: Python (pip install apache-airflow)
- **[Prefect](https://www.prefect.io)** – Python-first orchestration with dynamic flows, hybrid cloud execution, and strong observability. [Docs](https://docs.prefect.io) | SDK: Python (pip install prefect)
- **[Argo Workflows](https://argoproj.github.io/workflows/)** – Kubernetes-native workflow engine using container-per-step DAGs. Popular as a Kubeflow Pipelines backend. [Docs](https://argo-workflows.readthedocs.io/)
- **[Dagster](https://dagster.io)** – Asset-oriented orchestrator with strong typing, data-asset lineage, and dev/prod parity. [Docs](https://docs.dagster.io) | SDK: Python (pip install dagster)
- **[Kedro](https://kedro.org)** – Opinionated Python framework for modular, reproducible data-science code. Pluggable runners for Airflow, Dagster, Databricks. [Docs](https://docs.kedro.org) | SDK: Python (pip install kedro)
- **[Flyte](https://flyte.org)** – Kubernetes-native workflow engine focused on typed, reproducible ML pipelines. Graduated LF AI & Data project. [Docs](https://docs.flyte.org) | SDK: Python (pip install flytekit)

## ML Pipeline Frameworks

> Frameworks purpose-built for reproducible ML training and experiment pipelines.

- **[MLflow](https://mlflow.org)** – Open-source platform for experiment tracking, model registry, packaging, and deployment. Supports arbitrary artifact stores. [Docs](https://mlflow.org/docs/latest/) | SDK: Python (pip install mlflow), Java, R
- **[Metaflow](https://metaflow.org)** – Human-friendly ML framework created at Netflix. Native AWS, Kubernetes, and Argo backends. [Docs](https://docs.metaflow.org) | SDK: Python (pip install metaflow)
- **[ZenML](https://zenml.io)** – MLOps framework standardising production ML pipelines across orchestrators, experiment trackers, and model registries. [Docs](https://docs.zenml.io) | SDK: Python (pip install zenml)
- **[Kubeflow Pipelines](https://www.kubeflow.org/docs/components/pipelines/)** – Container-based ML workflow platform running on Kubernetes. Standard on Vertex AI Pipelines. [Docs](https://www.kubeflow.org/docs/components/pipelines/overview/)

## Data Versioning and Lineage

> Git-like versioning, lineage tracking, and reproducibility for data and models.

- **[DVC](https://dvc.org)** – Git-based data and model versioning with pluggable remote storage (including S3-compatible backends). [Docs](https://dvc.org/doc) | SDK: Python (pip install dvc)
- **[Pachyderm](https://www.pachyderm.com)** – Data-versioned pipelines on Kubernetes. Auto-incremental reprocessing when upstream data changes. [Docs](https://docs.pachyderm.com)
- **[lakeFS](https://lakefs.io)** – Git-like branching/versioning for data lakes over S3-compatible object storage. [Docs](https://docs.lakefs.io)
- **[OpenLineage](https://openlineage.io)** – Open standard for collecting lineage metadata from data pipelines. Integrations for Airflow, Spark, dbt, Flink, and more. [Docs](https://openlineage.io/docs/)

## Feature Stores

> Online/offline feature serving for training and inference.

- **[Feast](https://feast.dev)** – Open-source feature store with pluggable offline stores (Parquet on S3), online stores (Redis/DynamoDB), and registries. [Docs](https://docs.feast.dev) | SDK: Python (pip install feast)
- **[Hopsworks](https://www.hopsworks.ai)** – End-to-end ML platform with a built-in feature store. Supports time-travel on Hudi/Iceberg offline tables. [Docs](https://docs.hopsworks.ai)
- **[Tecton](https://www.tecton.ai)** – Enterprise feature platform from the creators of Michelangelo at Uber. Real-time and batch feature engineering. [Docs](https://docs.tecton.ai)

## Data Processing Engines

> Distributed compute for transforming, joining, and aggregating data at scale.

- **[Apache Spark](https://spark.apache.org)** – Unified analytics engine for large-scale data processing. PySpark is the default distributed compute for many ML shops. [Docs](https://spark.apache.org/docs/latest/)
- **[Ray](https://ray.io)** – Unified framework for distributed Python. Ray Data, Ray Train, Ray Tune, and Ray Serve cover the ML pipeline end-to-end. [Docs](https://docs.ray.io) | SDK: Python (pip install ray)
- **[Polars](https://pola.rs)** – Rust-backed DataFrame library with a lazy query engine. Often 5–10x faster than pandas on single-node workloads. [Docs](https://docs.pola.rs) | SDK: Python (pip install polars), Rust
- **[Dask](https://www.dask.org)** – Parallel computing for Python. Scales NumPy, pandas, and scikit-learn to clusters with familiar APIs. [Docs](https://docs.dask.org) | SDK: Python (pip install dask)
- **[dbt Core](https://www.getdbt.com)** – SQL-first transformation framework for analytics and ML feature tables. Deep integration with warehouses and lakehouses. [Docs](https://docs.getdbt.com) | SDK: Python (pip install dbt-core)
- **[Apache Beam](https://beam.apache.org)** – Unified programming model for batch and streaming data processing. Runs on Flink, Spark, Dataflow, and more. [Docs](https://beam.apache.org/documentation/)

## Streaming and Ingest

> Message brokers, CDC, and streaming frameworks that feed ML pipelines.

- **[Apache Kafka](https://kafka.apache.org)** – Industry-standard distributed event-streaming platform. Backbone of streaming ML feature pipelines. [Docs](https://kafka.apache.org/documentation/)
- **[Apache Flink](https://flink.apache.org)** – Stateful stream processing at scale. Exactly-once semantics, event-time windowing, and rich SQL support. [Docs](https://nightlies.apache.org/flink/flink-docs-stable/)
- **[Debezium](https://debezium.io)** – Distributed CDC platform. Streams database changes into Kafka for downstream ML and analytics. [Docs](https://debezium.io/documentation/)
- **[Redpanda](https://redpanda.com)** – Kafka-API-compatible streaming platform written in C++. No JVM, no ZooKeeper, simpler ops. [Docs](https://docs.redpanda.com)
- **[Apache NiFi](https://nifi.apache.org)** – Data-flow management with a drag-and-drop UI. Rich processor library for ingesting from heterogeneous sources. [Docs](https://nifi.apache.org/documentation/)

## Data Labeling

> Annotation platforms for supervised training and human-in-the-loop workflows.

- **[Label Studio](https://labelstud.io)** – Open-source labeling platform supporting text, image, audio, video, time-series, and more. [Docs](https://labelstud.io/guide/) | SDK: Python (pip install label-studio-sdk)
- **[CVAT](https://www.cvat.ai)** – Computer vision annotation tool with strong video and 3D support. Originally from Intel. [Docs](https://docs.cvat.ai)
- **[Doccano](https://doccano.github.io/doccano/)** – Open-source text annotation tool for NER, text classification, and sequence-to-sequence tasks.
- **[Argilla](https://argilla.io)** – Collaboration platform for AI engineers and domain experts. Part of HuggingFace since 2024. Focused on LLM data curation. [Docs](https://docs.argilla.io) | SDK: Python (pip install argilla)

## Storage Formats and Lakehouses

> Open table formats, columnar formats, and lakehouse engines.

- **[DuckDB](https://duckdb.org)** – In-process analytical database. Reads Parquet/CSV directly from S3-compatible stores. Excellent for feature exploration. [Docs](https://duckdb.org/docs/)
- **[Apache Arrow](https://arrow.apache.org)** – Language-independent columnar memory format. Powers pandas, Polars, DuckDB, and cross-process zero-copy data sharing. [Docs](https://arrow.apache.org/docs/)
- **[Delta Lake](https://delta.io)** – ACID-compliant lakehouse format over Parquet. Time travel, schema enforcement, and unified batch/streaming. [Docs](https://docs.delta.io)
- **[Apache Iceberg](https://iceberg.apache.org)** – Open table format for huge analytic tables. Partition evolution, hidden partitioning, and engine-agnostic design. [Docs](https://iceberg.apache.org/docs/latest/)
- **[Apache Hudi](https://hudi.apache.org)** – Lakehouse format with incremental processing, record-level indexing, and streaming ingestion. [Docs](https://hudi.apache.org/docs/overview/)
- **[Apache Parquet](https://parquet.apache.org)** – Columnar storage format optimized for analytics and ML workloads. De-facto standard for feature tables on object storage. [Docs](https://parquet.apache.org/docs/)

## Templates and Example Projects

> Reference implementations, demos, and starter projects.

- **[Awesome MLOps (visenger)](https://github.com/visenger/awesome-mlops)** – Broader MLOps reference. Useful companion when you need end-to-end deployment + monitoring beyond pipelines.

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md). One entry per PR — edit `entries.yaml` only and let the maintainers regenerate `README.md`.

## License

Released under [CC0 1.0 Universal](LICENSE). You may copy, modify, and redistribute without attribution.

## About Backblaze B2

[Backblaze B2 Cloud Storage](https://www.backblaze.com/cloud-storage?utm_source=github&utm_medium=referral&utm_campaign=ai_artifacts&utm_content=awesomelist) is S3-compatible object storage designed for AI and media workloads. This list is maintained as part of our work making B2 a convenient storage layer for AI workflows.
