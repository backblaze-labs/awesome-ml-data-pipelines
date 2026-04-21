# Awesome ML Data Pipelines [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) [![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

A curated list of open-source frameworks, engines, and platforms for building production ML data pipelines — orchestration, processing, versioning, feature storage, and everything in between.

Maintained by [Backblaze](https://www.backblaze.com).

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
- **[Mage AI](https://www.mage.ai)** – Notebook-style data pipeline builder supporting Python, SQL, and R. Handles batch, streaming, and dbt transformations with built-in scheduling and observability. [Docs](https://docs.mage.ai) | SDK: Python (pip install mage-ai)

## ML Pipeline Frameworks

> Frameworks purpose-built for reproducible ML training and experiment pipelines.

- **[MLflow](https://mlflow.org)** – Open-source platform for experiment tracking, model registry, packaging, and deployment. Supports arbitrary artifact stores. [Docs](https://mlflow.org/docs/latest/) | SDK: Python (pip install mlflow), Java, R
- **[Metaflow](https://metaflow.org)** – Human-friendly ML framework created at Netflix. Native AWS, Kubernetes, and Argo backends. [Docs](https://docs.metaflow.org) | SDK: Python (pip install metaflow)
- **[ZenML](https://zenml.io)** – MLOps framework standardising production ML pipelines across orchestrators, experiment trackers, and model registries. [Docs](https://docs.zenml.io) | SDK: Python (pip install zenml)
- **[Kubeflow Pipelines](https://www.kubeflow.org/docs/components/pipelines/)** – Container-based ML workflow platform running on Kubernetes. Standard on Vertex AI Pipelines. [Docs](https://www.kubeflow.org/docs/components/pipelines/overview/)
- **[Apache Hamilton](https://hamilton.apache.org)** – Lightweight Python framework for defining modular, testable dataflows as DAGs of regular functions. Runs in scripts, notebooks, Airflow, and FastAPI. [Docs](https://hamilton.apache.org) | SDK: Python (pip install sf-hamilton)

## Data Versioning and Lineage

> Git-like versioning, lineage tracking, and reproducibility for data and models.

- **[DVC](https://dvc.org)** – Git-based data and model versioning with pluggable remote storage (including S3-compatible backends). [Docs](https://dvc.org/doc) | SDK: Python (pip install dvc)
- **[Pachyderm](https://www.pachyderm.com)** – Data-versioned pipelines on Kubernetes. Auto-incremental reprocessing when upstream data changes. [Docs](https://docs.pachyderm.com)
- **[lakeFS](https://lakefs.io)** – Git-like branching/versioning for data lakes over S3-compatible object storage. [Docs](https://docs.lakefs.io)
- **[OpenLineage](https://openlineage.io)** – Open standard for collecting lineage metadata from data pipelines. Integrations for Airflow, Spark, dbt, Flink, and more. [Docs](https://openlineage.io/docs/)
- **[Cleanlab](https://github.com/cleanlab/cleanlab)** – Data-centric AI library that automatically detects label errors, outliers, near-duplicates, and class overlap in ML training datasets using any model's predicted probabilities. [Docs](https://docs.cleanlab.ai/stable/index.html) | SDK: Python (pip install cleanlab)
- **[Elementary](https://www.elementary-data.com)** – dbt-native data observability CLI. Runs anomaly detection tests and schema change alerts inside dbt, generates a lineage-aware observability report, and pushes alerts to Slack or Teams. [Docs](https://docs.elementary-data.com) | SDK: Python (pip install elementary-data)
- **[Evidently AI](https://www.evidentlyai.com)** – Open-source framework for evaluating, testing, and monitoring ML and LLM pipelines. 100+ built-in metrics covering drift, quality, and performance. [Docs](https://docs.evidentlyai.com) | SDK: Python (pip install evidently)
- **[Great Expectations](https://greatexpectations.io)** – Data quality framework using "Expectations" to define, validate, and document data contracts inside ML pipelines. [Docs](https://docs.greatexpectations.io) | SDK: Python (pip install great-expectations)
- **[Marquez](https://marquezproject.ai)** – LF AI & Data metadata service for collecting and visualizing data lineage across pipelines. Reference implementation of the OpenLineage standard; REST API with a lineage graph UI. [Docs](https://marquezproject.ai/docs/)
- **[Oxen](https://oxen.ai)** – Git-like version control for ML datasets. Handles millions of files and terabytes of data with fast indexing for images, audio, video, and Parquet. [Docs](https://docs.oxen.ai) | SDK: Python (pip install oxenai)
- **[Pandera](https://www.union.ai/pandera)** – Statistical data validation library for pandas, Polars, and PySpark DataFrames. Define schemas with type hints or object API; validates column types, ranges, and custom checks. [Docs](https://pandera.readthedocs.io/en/stable/) | SDK: Python (pip install pandera)
- **[Project Nessie](https://projectnessie.org)** – Transactional catalog for data lakes with Git-like branching and tagging semantics. Works with Iceberg tables across Spark, Trino, and Flink. [Docs](https://projectnessie.org/nessie-latest/)
- **[PyDeequ](https://github.com/awslabs/python-deequ)** – Python API for Deequ, AWS's Spark-based data quality library. Defines unit tests for data, computes metrics, suggests constraints, and persists quality results. [Docs](https://pydeequ.readthedocs.io/) | SDK: Python (pip install pydeequ)
- **[Soda Core](https://www.soda.io)** – Data-contract verification engine. Defines quality checks in YAML, validates schema and data values against contracts, and integrates with Airflow, dbt, and Spark pipelines. [Docs](https://docs.soda.io/soda-core/overview-main.html) | SDK: Python (pip install soda-core)
- **[TensorFlow Data Validation](https://www.tensorflow.org/tfx/guide/tfdv)** – Library for computing data statistics, inferring schemas, and detecting anomalies in training and serving data for TFX ML pipelines. [Docs](https://www.tensorflow.org/tfx/data_validation/get_started) | SDK: Python (pip install tensorflow-data-validation)

## Feature Stores

> Online/offline feature serving for training and inference.

- **[Feast](https://feast.dev)** – Open-source feature store with pluggable offline stores (Parquet on S3), online stores (Redis/DynamoDB), and registries. [Docs](https://docs.feast.dev) | SDK: Python (pip install feast)
- **[Hopsworks](https://www.hopsworks.ai)** – End-to-end ML platform with a built-in feature store. Supports time-travel on Hudi/Iceberg offline tables. [Docs](https://docs.hopsworks.ai)
- **[Featureform](https://www.featureform.com)** – Virtual feature store that orchestrates existing data infrastructure. Define, version, and serve ML features via a declarative Python API without replacing current systems. [Docs](https://docs.featureform.com) | SDK: Python (pip install featureform)
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
- **[Airbyte](https://airbyte.com)** – ELT data integration platform with 600+ connectors. Pulls from APIs, databases, and files into data lakes and lakehouses for ML pipeline ingestion. [Docs](https://docs.airbyte.com) | SDK: Python (pip install airbyte)
- **[dlt (data load tool)](https://dlthub.com)** – Lightweight Python library for loading data from APIs, databases, and files into structured datasets. Auto-infers schemas and normalises nested JSON; pluggable destinations include DuckDB, BigQuery, and S3. [Docs](https://dlthub.com/docs) | SDK: Python (pip install dlt)
- **[Meltano](https://meltano.com)** – Declarative, code-first ELT engine built on Singer taps and targets. 500+ connectors, git-managed configuration, and native integrations with dbt, Airflow, and Dagster. [Docs](https://docs.meltano.com) | SDK: Python (pip install meltano)
- **[Pathway](https://pathway.com)** – Python streaming ETL framework backed by a Rust engine. Unified batch/streaming API with stateful windowing, exactly-once guarantees, and connectors for Kafka, PostgreSQL, and S3. [Docs](https://pathway.com/developers/) | SDK: Python (pip install pathway)
- **[Quix Streams](https://quix.io)** – Python library for building real-time data pipelines on Apache Kafka. Streaming DataFrame API with stateful operations, windowing, and exactly-once guarantees. [Docs](https://quix.io/docs/quix-streams/introduction.html) | SDK: Python (pip install quixstreams)
- **[RisingWave](https://risingwave.com)** – Distributed SQL streaming database, PostgreSQL-compatible. Continuously ingests events, maintains materialized views, and serves features at sub-100ms freshness. [Docs](https://docs.risingwave.com)

## Data Labeling

> Annotation platforms for supervised training and human-in-the-loop workflows.

- **[Label Studio](https://labelstud.io)** – Open-source labeling platform supporting text, image, audio, video, time-series, and more. [Docs](https://labelstud.io/guide/) | SDK: Python (pip install label-studio-sdk)
- **[CVAT](https://www.cvat.ai)** – Computer vision annotation tool with strong video and 3D support. Originally from Intel. [Docs](https://docs.cvat.ai)
- **[Doccano](https://doccano.github.io/doccano/)** – Open-source text annotation tool for NER, text classification, and sequence-to-sequence tasks.
- **[Argilla](https://argilla.io)** – Collaboration platform for AI engineers and domain experts. Part of HuggingFace since 2024. Focused on LLM data curation. [Docs](https://docs.argilla.io) | SDK: Python (pip install argilla)
- **[LabelU](https://opendatalab.github.io/labelU/)** – Multimodal annotation toolbox supporting 2D bounding boxes, segmentation, keypoints, polylines, and AI-assisted labeling for image, audio, and video data. SDK: Python (pip install labelu)

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

[Backblaze B2 Cloud Storage](https://www.backblaze.com/cloud-storage) is S3-compatible object storage designed for AI and media workloads. This list is maintained as part of our work making B2 a convenient storage layer for AI workflows.
