# Awesome Apache Iceberg [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of awesome Apache Iceberg resources, libraries, tools, and learning materials. Apache Iceberg is a high-performance open table format for huge analytic datasets, bringing reliability and simplicity to data lakes.

## Contents

- [Core Project](#core-project)
- [Query Engines](#query-engines)
- [Catalogs](#catalogs)
- [Libraries and SDKs](#libraries-and-sdks)
- [Data Ingestion](#data-ingestion)
- [Data Quality and Governance](#data-quality-and-governance)
- [Monitoring and Observability](#monitoring-and-observability)
- [Table Maintenance](#table-maintenance)
- [Migration Tools](#migration-tools)
- [Cloud Integrations](#cloud-integrations)
- [Commercial Products](#commercial-products)
- [Development Tools](#development-tools)
- [Testing](#testing)
- [Community](#community)
- [Learning Resources](#learning-resources)

## Core Project

- [Apache Iceberg](https://iceberg.apache.org) - Official website for Apache Iceberg, a high-performance open table format for analytic datasets. Open source (Apache 2.0).
- [Apache Iceberg GitHub](https://github.com/apache/iceberg) - Reference Java implementation with core table format specifications, catalog implementations, and processing engine integrations. Open source (Apache 2.0).
- [Documentation](https://iceberg.apache.org/docs/latest/) - Comprehensive official documentation covering all features, APIs, and integrations. Open source.

## Query Engines

### Open Source Engines

- [Apache Spark](https://iceberg.apache.org/docs/latest/spark-queries/) - First-class native Iceberg support with full read/write capabilities, streaming, time travel, and all DDL/DML operations. Supports Spark 3.3, 3.4, 3.5. Open source (Apache 2.0).
- [Apache Flink](https://iceberg.apache.org/docs/latest/flink/) - Native streaming and batch support with CDC pipeline connectors, incremental reads, and equality delete writes for efficient streaming use cases. Open source (Apache 2.0).
- [Trino](https://trino.io/docs/current/connector/iceberg.html) - Production-ready native connector with full read/write support, time travel, multiple catalog types, and metadata table access. Open source (Apache 2.0).
- [PrestoDB](https://prestodb.io/docs/current/connector/iceberg.html) - Native connector with V1/V2 table support, time travel queries, and REST catalog integration. Open source (Apache 2.0).
- [Apache Impala](https://impala.apache.org/docs/build/html/topics/impala_iceberg.html) - Native C++ implementation with read/write support, partition transforms, time travel, and OPTIMIZE statement for maintenance. Open source (Apache 2.0).
- [Apache Hive](https://iceberg.apache.org/docs/latest/hive/) - StorageHandler-based integration with full DDL/DML support in Hive 4.0+, table migration capabilities from Avro/Parquet/ORC. Open source (Apache 2.0).
- [StarRocks](https://docs.starrocks.io/docs/data_source/catalog/iceberg_catalog/) - MPP SQL engine with native Iceberg catalog support, materialized views, and local caching for performance. Open source (Apache 2.0).
- [Apache Doris](https://doris.apache.org/docs/3.0/lakehouse/catalogs/iceberg-catalog/) - Real-time MPP data warehouse with native read/write support for V1/V2 tables, position/equality deletes, and CTAS operations. Open source (Apache 2.0).
- [DuckDB](https://duckdb.org/docs/extensions/iceberg.html) - In-process analytical database with Iceberg support via extension, excellent for local analytics and single-machine deployments. Open source (MIT).
- [ClickHouse](https://clickhouse.com/docs/en/engines/table-engines/integrations/iceberg) - Columnar database with read-only Iceberg support via table function and engine, optimized for real-time analytics. Open source (Apache 2.0).
- [Polars](https://docs.pola.rs/api/python/stable/reference/api/polars.scan_iceberg.html) - Dataframe query engine with read support for Iceberg & experimental support for writes. Open source.

### Cloud and Commercial Engines

- [Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/querying-iceberg.html) - Serverless query engine with native Iceberg support for DDL/DML operations, time travel, and automatic metadata generation. Commercial (AWS).
- [Google BigQuery](https://cloud.google.com/bigquery/docs/iceberg-tables) - BigLake Iceberg tables with fully managed storage, automatic optimization, high-throughput streaming, and cross-engine compatibility. Commercial (Google Cloud).
- [Snowflake](https://docs.snowflake.com/en/user-guide/tables-iceberg) - Native Iceberg support (GA April 2025) with managed and external tables, catalog integrations, and data sharing capabilities. Commercial.
- [Databricks](https://docs.databricks.com/aws/en/iceberg/) - Unity Catalog-managed Iceberg tables (Public Preview) with Predictive Optimization, REST Catalog API, and Delta UniForm for interoperability. Commercial.
- [Dremio](https://docs.dremio.com/current/developer/data-formats/apache-iceberg/) - SQL lakehouse platform with native Iceberg integration, Apache Polaris catalog, automatic optimization, and sub-second BI performance. Commercial with open source components.
- [Starburst/Trino Enterprise](https://docs.starburst.io/latest/connector/iceberg.html) - Enterprise Trino distribution with Iceberg v3 support, deletion vectors, materialized view auto-refresh, and AI-powered features. Commercial.

## Catalogs

### Open Source Catalogs

- [Apache Polaris (Incubating)](https://polaris.apache.org/) - Fully-featured REST catalog donated by Snowflake with multi-engine interoperability, RBAC, credential vending, and support for internal/external modes. Open source (Apache 2.0).
- [Project Nessie](https://projectnessie.org/) - Git-like transactional catalog with branches, tags, commits, and multi-table transaction support for data-as-code workflows. Open source (Apache 2.0).
- [Hive Metastore Catalog](https://iceberg.apache.org/docs/latest/hive/) - Traditional HMS integration storing Iceberg metadata in relational databases, best for existing Hive ecosystems. Open source (Apache 2.0).
- [REST Catalog](https://iceberg.apache.org/docs/latest/rest-catalog/) - RESTful specification enabling standardized catalog operations across any language and platform. Open source specification (Apache 2.0).
- [Hadoop/File-Based Catalog](https://iceberg.apache.org/docs/latest/hadoop-catalog/) - File-based catalog using version-hint.text files, suitable for testing and single-writer scenarios but not recommended for production with object storage. Open source (Apache 2.0).
- [JDBC Catalog](https://iceberg.apache.org/docs/latest/jdbc/) - Uses relational database table for Iceberg metadata management with serializable isolation for ACID transactions. Open source (Apache 2.0).
- [OpenMetadata](https://open-metadata.org/) - Unified metadata platform with native Iceberg connector for automated metadata extraction, lineage tracking, and data quality integration across 90+ sources. Open source (Apache 2.0).
- [DataHub](https://datahubproject.io/) - Metadata management platform with native Iceberg source connector and REST Catalog API implementation for discovery and governance. Open source (Apache 2.0).

### Cloud and Commercial Catalogs

- [AWS Glue Data Catalog](https://iceberg.apache.org/docs/latest/aws/) - Native AWS catalog with optimistic locking, automatic table optimization, REST API endpoint, and integration with Athena, EMR, and Redshift. Commercial (AWS).
- [DynamoDB Catalog](https://iceberg.apache.org/docs/latest/aws/) - AWS DynamoDB-based catalog with optimistic locking and high write throughput for streaming workloads. Commercial (AWS).
- [Google Dataproc Metastore](https://cloud.google.com/dataproc-metastore/docs/apache-iceberg) - Fully managed Hive metastore service with BigLake REST Catalog support and native Iceberg integration. Commercial (Google Cloud).
- [Unity Catalog](https://www.databricks.com/product/unity-catalog) - Databricks unified governance solution with full Iceberg REST API implementation, multi-format support, and lakehouse federation. Commercial.
- [Snowflake Catalog](https://docs.snowflake.com/en/user-guide/tables-iceberg) - Native catalog for Snowflake-managed Iceberg tables with external volume integrations and Polaris catalog support. Commercial.
- [Dremio Arctic](https://www.dremio.com/) - Managed Nessie-based catalog with Git-like versioning, automated optimization, and branch/tag management. Commercial.

## Libraries and SDKs

### Official Implementations

- [PyIceberg](https://github.com/apache/iceberg-python) - Official Python library with full read/write capabilities, multiple catalog support, PyArrow integration, and DuckDB queries on Iceberg tables. Python 3.9+. Open source (Apache 2.0).
- [Apache Iceberg Java API](https://github.com/apache/iceberg) - Reference implementation containing core specifications, all catalog types, transaction support, and processing engine integrations. Java 11+. Open source (Apache 2.0).
- [iceberg-rust](https://github.com/apache/iceberg-rust) - Official Rust implementation with DataFusion integration, multiple catalog support, and Arrow-based data processing. Stable Rust. Open source (Apache 2.0).
- [iceberg-go](https://github.com/apache/iceberg-go) - Official Golang implementation with read/write capabilities, REST/Hive/Glue catalog support, and CLI tool similar to PyIceberg. Go 1.23+. Open source (Apache 2.0).
- [iceberg-cpp](https://github.com/apache/iceberg-cpp) - Official C++ implementation with Apache Arrow integration and CMake build system. C++23 compliant. Open source (Apache 2.0).

### Community Implementations

- [Icebird](https://github.com/hyparam/icebird) - JavaScript/TypeScript library for reading Iceberg tables with Parquet/Avro support, browser and Node.js compatible. Read-only. Open source.

## Data Ingestion

### CDC Tools

- [Debezium Server Iceberg](https://github.com/memiiso/debezium-server-iceberg) - Direct CDC to Iceberg without Kafka or Spark, supporting PostgreSQL, MySQL, MongoDB, SQL Server, Oracle with real-time change capture. Open source (Apache 2.0).
- [AWS DMS with Amazon Data Firehose](https://aws.amazon.com/blogs/aws/replicate-changes-from-databases-to-apache-iceberg-tables-using-amazon-data-firehose/) - Captures database changes and streams updates to Iceberg tables with automatic table creation and schema management. Commercial (AWS).
- [Upsolver](https://www.upsolver.com/) - Cloud-based CDC platform with native Iceberg support, equality deletes as first-class citizen, and aggressive compaction for 1000s of changes per minute. Commercial (acquired by Qlik 2025).
- [Estuary Flow](https://estuary.dev/blog/kafka-to-apache-iceberg/) - Real-time data integration with sub-100ms latency, automatic schema evolution, and CDC capabilities from Kafka to Iceberg. Commercial.

### Streaming Connectors

- [Apache Iceberg Kafka Connect](https://iceberg.apache.org/docs/nightly/kafka-connect/) - Official sink connector with exactly-once semantics, multi-table fan-out, automatic schema evolution, and DebeziumTransform SMT for CDC. Open source (Apache 2.0).
- [Apache Flink Iceberg Connector](https://iceberg.apache.org/docs/latest/flink/) - Native streaming and batch integration with equality delete support, CDC processing, and both DataStream API and Table/SQL API. Open source (Apache 2.0).
- [Apache Flink CDC Pipeline Connector](https://nightlies.apache.org/flink/flink-cdc-docs-master/docs/connectors/pipeline-connectors/iceberg/) - Dedicated CDC connector with automatic table creation, schema synchronization, and direct pipeline from databases to Iceberg. Open source (Apache 2.0).
- [Apache Spark Structured Streaming](https://iceberg.apache.org/docs/1.9.0/spark-structured-streaming/) - Native streaming reads and writes with micro-batch processing, checkpoint support, and fanout writer for low-latency ingestion. Open source (Apache 2.0).
- [Confluent Tableflow](https://www.confluent.io/blog/streaming-etl-flink-tableflow/) - Automatically exposes Kafka topics as Iceberg tables with Flink SQL transformations and seamless integration with Confluent Cloud. Commercial.

### Batch Ingestion

- [Airbyte](https://airbyte.com/connectors/apache-iceberg) - Open-source ELT platform with 600+ connectors, S3 Data Lake destination supporting Iceberg format, and automated schema mapping with AWS Glue/Nessie catalogs. Open source core with Cloud offering.
- [Fivetran](https://fivetran.com/docs/destinations/s3-data-lake) - Managed data movement with 700+ connectors, Managed Data Lake Service with native Iceberg support, ACID transactions, and Iceberg REST catalog. Commercial.
- [dbt](https://docs.getdbt.com/docs/mesh/iceberg/apache-iceberg-support) - Data transformation framework with native Iceberg materializations for Snowflake, BigQuery, Spark, and Databricks, supporting incremental strategies and catalog integrations. Open source core with Cloud offering.
- [AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-etl-format-iceberg.html) - Managed ETL service with native Iceberg connector, optimistic locking, and Lake Formation integration. Commercial (AWS).
- [DLT](https://github.com/sidequery/dlt-iceberg) - Lightweight Python code to move data. Open Source with 3rd party connector. Open source.

## Data Quality and Governance

### Data Quality Tools

- [Great Expectations](https://docs.greatexpectations.io/) - Expectations-based testing framework working with Iceberg through Spark/Trino, supporting Write-Audit-Publish pattern with Iceberg branching. Open source (Apache 2.0).
- [Soda Core](https://github.com/sodadata/soda-core) - Python-based data quality framework with native Iceberg branch-level checks, 25+ built-in metrics, and YAML-based SodaCL. Open source (Apache 2.0).
- [Soda Cloud](https://www.soda.io/) - Commercial platform with AI-powered metrics observability (SodaGPT), collaborative data contracts, and metrics storage in Iceberg tables. Commercial.
- [Monte Carlo](https://www.montecarlodata.com/) - Data observability platform with end-to-end pipeline monitoring, anomaly detection, and incident management for Iceberg tables. Commercial.
- [Microsoft Purview](https://learn.microsoft.com/en-us/purview/unified-catalog-data-quality-iceberg) - Data quality assessment on Iceberg assets with profiling, schema import, and time travel for historical quality views. Commercial (Microsoft, Public Preview).

### Governance Tools

- [OpenMetadata](https://open-metadata.org/) - Unified metadata platform with native Iceberg connector (v0.9.0+), automated lineage tracking, and support for REST, Hive, Glue, and DynamoDB catalogs. Open source (Apache 2.0).
- [DataHub](https://datahubproject.io/) - Metadata management with native Iceberg connector, REST Catalog API implementation, and real-time metadata updates using PyIceberg. Open source (Apache 2.0).
- [Apache Atlas](https://atlas.apache.org/) - Metadata management for Hadoop ecosystems with native Iceberg integration in Cloudera CDP, lineage tracking, and schema evolution support. Open source (Apache 2.0).
- [Project Nessie](https://projectnessie.org/) - Git-like catalog with reference-based and path-based access control, commit-level governance, and branch-specific permissions. Open source (Apache 2.0).
- [AWS Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/notes-ns-catalog.html) - Cell-level access permissions, fine-grained access control, and row/column-level security for Iceberg tables on AWS. Commercial (AWS).
- [Unity Catalog](https://www.databricks.com/product/unity-catalog) - Unified governance for Delta, Iceberg, Hudi, and Parquet with centralized access control, lineage, and business metrics governance. Commercial.

## Monitoring and Observability

- [Apache Iceberg Metrics API](https://iceberg.apache.org/docs/1.4.1/metrics-reporting/) - Built-in MetricsReporter API (v1.1.0+) with ScanReport and CommitReport metrics for scan planning, file operations, and commit tracking. Open source (Apache 2.0).
- [AWS CloudWatch for Iceberg](https://github.com/aws-samples/monitoring-apache-iceberg-table-metadata-layer) - Time-series metrics collection from Iceberg metadata with EventBridge triggers, Lambda functions, and dashboard templates. Open source sample + AWS service.
- [Monte Carlo](https://www.montecarlodata.com/) - Full observability platform with automatic anomaly detection, data freshness/volume/schema monitoring, and integration with Slack/PagerDuty/Jira. Commercial.
- [Dremio Arctic](https://www.dremio.com/) - Automatic table optimization monitoring, branch/tag health tracking, and query performance metrics with Git-like version control observability. Commercial.

## Table Maintenance

- [Apache Spark Actions](https://iceberg.apache.org/docs/1.5.1/maintenance/) - Built-in maintenance operations including rewriteDataFiles (binpack, sort, z-order), expireSnapshots, rewriteManifests, and removeOrphanFiles with parallel execution. Open source (Apache 2.0).
- [Spark SQL Procedures](https://iceberg.apache.org/docs/latest/spark-procedures/) - SQL-based maintenance commands like `CALL system.rewrite_data_files()` for no-code command-line execution of compaction and cleanup. Open source (Apache 2.0).
- [AWS Glue Optimization](https://docs.aws.amazon.com/prescriptive-guidance/latest/apache-iceberg-on-aws/best-practices-compaction.html) - Automatic compaction configuration with binpack, sort, z-order strategies and integration with AWS Glue jobs and EMR Serverless. Commercial (AWS).
- [Amazon Athena Maintenance](https://docs.aws.amazon.com/athena/latest/ug/querying-iceberg.html) - OPTIMIZE command for compaction and VACUUM for orphan file cleanup with table property-based configuration. Commercial (AWS).
- [Snowflake Automatic Maintenance](https://docs.snowflake.com/en/user-guide/tables-iceberg-manage) - Automatic compaction for Snowflake-managed tables with configurable target file sizes and position delete handling. Commercial.
- [Upsolver](https://www.upsolver.com/) - Continuous table optimization with small file compaction, sorting, compression, repartitioning, and health analysis of Iceberg tables. Commercial.
- [Dremio Arctic Optimizer](https://www.dremio.com/blog/maintaining-iceberg-tables-compaction-expiring-snapshots-and-more/) - Automatic background optimization with compaction strategies, snapshot management, orphan file cleanup, and branch-based optimization. Commercial.
- [Amazon S3 Tables](https://aws.amazon.com/blogs/aws/new-improve-apache-iceberg-query-performance-in-amazon-s3-with-sort-and-z-order-compaction/) - Managed Iceberg with automatic maintenance scheduling including binpack, sort, and z-order compaction strategies. Commercial (AWS).

## Migration Tools

- [Iceberg Table Migration](https://iceberg.apache.org/docs/1.4.2/table-migration/) - Built-in migration capabilities supporting in-place metadata migration (Snapshot Table, Migrate Table, Add Files) and full data migration via CTAS/INSERT. Open source (Apache 2.0).
- [Hive Migration Module](https://iceberg.apache.org/docs/1.4.1/hive-migration/) - Official migration from ORC, Parquet, and Avro Hive tables via Spark Procedures. Open source (Apache 2.0).
- [Delta Lake Migration Module](https://iceberg.apache.org/docs/1.4.3/delta-lake-migration/) - iceberg-delta-lake module with snapshotDeltaLakeTable action supporting Delta protocol minReaderVersion 1, minWriterVersion 2. Open source (Apache 2.0).
- [Iceberg Catalog Migrator](https://github.com/projectnessie/iceberg-catalog-migrator) - CLI tool for bulk catalog migrations without data copy, supporting migrate and register commands. Requires Java 21+. Open source (Apache 2.0).
- [Delta Lake UniForm](https://docs.databricks.com/aws/en/delta/uniform) - Enables Iceberg reads on Delta Lake tables by generating Iceberg metadata asynchronously without data rewriting. Requires Unity Catalog. Commercial (Databricks).
- [Apache XTable (Incubating)](https://xtable.apache.org/) - Seamless interoperability between Hudi, Delta, and Iceberg co-launched by Microsoft, Google, and Onehouse. Open source (Apache incubating).

## Cloud Integrations

### AWS

- [Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/querying-iceberg.html) - Serverless query engine with native Iceberg support, MERGE/UPDATE/DELETE operations, time travel, and automatic metadata generation. Commercial.
- [Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-iceberg.html) - Managed big data platform with Spark integration, Iceberg v3 deletion vectors (EMR 7.10.0+), and AWS Glue catalog integration. Commercial.
- [AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-etl-format-iceberg.html) - Managed ETL with native Iceberg connector, optimistic locking by default (Glue 4.0+), and REST catalog support (Glue 5.0+). Commercial.
- [Amazon Redshift](https://aws.amazon.com/blogs/big-data/access-amazon-redshift-managed-storage-tables/) - Query RMS tables as Iceberg tables via SageMaker Lakehouse with REST catalog backed by AWS Glue. Commercial.
- [AWS Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/notes-ns-catalog.html) - Row and column-level security, fine-grained access control, and centralized permissions management for Iceberg tables. Commercial.
- [Amazon SageMaker Lakehouse](https://aws.amazon.com/sagemaker/) - Unified lakehouse experience with Iceberg REST catalog backed by AWS Glue, accessing Redshift and S3 data via Iceberg format. Commercial.
- [Amazon S3 Tables](https://aws.amazon.com/s3/features/tables/) - Fully managed Iceberg tables with automatic maintenance (compaction, snapshot expiration, orphan removal) and sort/z-order strategies. Commercial.
- [Amazon Data Firehose](https://aws.amazon.com/blogs/aws/replicate-changes-from-databases-to-apache-iceberg-tables/) - Streaming CDC to Iceberg tables with automatic scaling and schema management for PostgreSQL, MySQL, Oracle, SQL Server, MongoDB. Commercial.

### Google Cloud Platform

- [BigQuery](https://cloud.google.com/bigquery/docs/iceberg-tables) - BigLake Iceberg tables (GA) with fully managed storage, automatic optimization, high-throughput streaming, and cross-engine compatibility via Spark/Flink connectors. Commercial.
- [Google Dataproc](https://cloud.google.com/dataproc) - Managed Spark/Hadoop with full Iceberg capabilities through Apache Spark, BigLake metastore integration, and serverless Spark option. Commercial.
- [BigLake Metastore](https://cloud.google.com/bigquery/docs/iceberg-external-tables) - REST Catalog implementation with unified catalog access and BigQuery Storage API integration. Commercial.
- [Google Cloud Storage](https://iceberg.apache.org/docs/latest/gcp/) - Native GCS integration with GCSFileIO, Application Default Credentials, and customer-managed encryption keys. Commercial.

### Microsoft Azure

- [Azure Synapse Analytics](https://learn.microsoft.com/en-us/azure/synapse-analytics/) - Spark pools with Iceberg support (manual JAR configuration), ACID transactions, schema evolution, and ADLS Gen2 integration. Commercial.
- [Microsoft Fabric](https://learn.microsoft.com/en-us/fabric/onelake/onelake-iceberg-tables) - OneLake bidirectional table format virtualization (Public Preview Nov 2024) with Delta-Iceberg interoperability and shortcut integration to external Iceberg tables. Commercial.
- [Azure Data Factory](https://learn.microsoft.com/en-us/azure/data-factory/) - Data pipeline support for Iceberg format (Nov 2024) with copy activity and transformation capabilities. Commercial.
- [Microsoft Purview](https://learn.microsoft.com/en-us/purview/) - Data governance with Iceberg support for metadata management, lineage tracking, and data quality assessment. Commercial.

## Commercial Products

- [Snowflake](https://docs.snowflake.com/en/user-guide/tables-iceberg) - Cloud data platform with native Iceberg support (GA April 2025), managed and external tables, multiple catalog integrations, data sharing, and Polaris catalog. Commercial.
- [Databricks](https://docs.databricks.com/aws/en/iceberg/) - Lakehouse platform with Unity Catalog-managed Iceberg (Public Preview), acquired Tabular (June 2024), Predictive Optimization, and Delta UniForm for interoperability. Commercial.
- [Dremio](https://www.dremio.com/) - SQL lakehouse with native Iceberg integration, Apache Polaris catalog, automatic optimization, Git-like versioning, and sub-second BI performance. Commercial with open source components.
- [Starburst Galaxy](https://www.starburst.io/) - Managed Trino with Iceberg v3 support, deletion vectors, materialized view auto-refresh, Apache Polaris connector, and AI-powered features. Commercial.
- [Tabular](https://www.tabular.io/) - Managed Iceberg service created by Iceberg founders with centralized RBAC, auto-optimization, and multi-engine support (acquired by Databricks June 2024). Commercial.
- [Cloudera Data Platform](https://www.cloudera.com/open-source/apache-iceberg.html) - Hybrid cloud platform with first-class Iceberg support via Hive, Impala, Spark, Flink, REST catalog, and SDX integration for security and governance. Commercial.
- [Upsolver](https://www.upsolver.com/) - Real-time streaming ingestion platform with native Iceberg support, Adaptive Iceberg Optimizer, and CDC processing (acquired by Qlik January 2025). Commercial.
- [Confluent](https://www.confluent.io/) - Enterprise Kafka platform with Tableflow for automatic Iceberg table creation, managed Kafka Connect with Iceberg sink, and Flink integration. Commercial.

## Development Tools

### Command Line Tools

- [PyIceberg CLI](https://py.iceberg.apache.org/cli/) - Official CLI for describing, listing, managing Iceberg tables with commands for schema, properties, snapshots, and table operations. Python. Open source (Apache 2.0).
- [Iceberg Go CLI](https://go.iceberg.apache.org/cli.html) - Go implementation similar to PyIceberg CLI for table and namespace operations. Go 1.23+. Open source (Apache 2.0).
- [Upsolver Iceberg Diagnostic CLI](https://docs.upsolver.com/content/how-to-guides-1/apache-iceberg/analyze-your-iceberg-tables-using-the-upsolver-cli) - Evaluates Iceberg tables for optimization opportunities with side-by-side comparison of current vs optimized metrics. Install via Brew/PIP. Commercial.
- [Iceberg Catalog Migrator CLI](https://github.com/projectnessie/iceberg-catalog-migrator) - Bulk migrate Iceberg tables between catalogs with migrate and register commands. Java 21+. Open source (Apache 2.0).

### Development Environments

- [Spark Iceberg Docker Image](https://iceberg.apache.org/spark-quickstart/) - Official tabulario/spark-iceberg Docker image with pre-configured Spark cluster, Iceberg catalog, and Jupyter notebook environment for local development. Open source (Apache 2.0).
- [Iceberg REST API Test](https://github.com/transformatek/test-apache-iceberg) - Example project testing Iceberg REST API with PyIceberg for namespace and table operations. Open source.
- [AWS Iceberg Streaming Examples](https://github.com/aws-samples/iceberg-streaming-examples) - High-throughput IoT and CDC examples with best practices for Spark + Iceberg streaming, deployable to EMR Serverless and AWS Glue. Open source samples.

## Testing

- [TestHiveMetastore](https://medium.com/@dpaani/running-scalatest-with-apache-iceberg-and-spark-using-maven-ebbfbde889c5) - JUnit testing with local Thrift service and Derby databases for isolated Iceberg testing from iceberg-hive-metastore module. Open source (Apache 2.0).
- [TestContainers](https://github.com/apache/iceberg) - Docker-based integration testing framework used in official Iceberg repository for testing catalog implementations and engine integrations. Open source (Apache 2.0).

## Community

### Events and Conferences

- [Iceberg Summit 2025](https://www.icebergsummit2025.com/) - Second annual ASF-sanctioned event, hybrid format (San Francisco April 8, virtual April 9), organized by AWS, Dremio, Microsoft, Snowflake with 500+ expected attendees. Official.
- [Apache Iceberg Talks](https://iceberg.apache.org/talks/) - Curated list of talks and videos related to Iceberg, updated regularly with conference presentations and technical deep-dives. Official.

### Discussion Channels

- [Apache Iceberg Slack](https://apache-iceberg.slack.com/) - Active community workspace with channels for meetups, vendors, jobs, and technical discussions. [Join here](https://join.slack.com/t/apache-iceberg/shared_invite/...). Official.
- [Mailing Lists](https://iceberg.apache.org/community/) - dev@, commits@, and private@ lists for development discussions, commit notifications, and PMC discussions. Subscribe at dev-subscribe@iceberg.apache.org. Official (ASF).
- [GitHub Discussions](https://github.com/apache/iceberg) - Issue tracking, pull requests, and community discussions on specific features and bugs. Official (ASF).

### Meetups

- [Iceberg Community Meetups](https://icebergcommunity.com/) - Platform for starting and joining local Apache Iceberg meetups with Slack channels like #meetup-seattle, #meetup-atlanta for regional communities. Community-organized.

### Social Media

- [@IcebergDevs Twitter](https://twitter.com/IcebergDevs) - Developer-focused Twitter account for latest announcements, blogs, and project updates. Community advocacy.

## Learning Resources

### Official Documentation

- [Apache Iceberg Documentation](https://iceberg.apache.org/docs/latest/) - Comprehensive official documentation covering schema evolution, partitioning, time travel, performance tuning, and multi-engine support. Official (ASF).
- [API Documentation](https://iceberg.apache.org/docs/latest/api/) - Java API reference for core Iceberg interfaces and implementations. Official (ASF).

### Books

- [Apache Iceberg: The Definitive Guide](https://www.oreilly.com/library/view/apache-iceberg-the/9781098148614/) - Comprehensive O'Reilly guide by Tomer Shiran, Jason Hughes, and Alex Merced covering architecture, features, WAP, CDC, and streaming. [Free PDF](https://www.dremio.com/wp-content/uploads/2023/02/apache-iceberg-TDG_ER1.pdf). Official O'Reilly publication.

### Online Courses

- [Apache Iceberg 101 (Dremio University)](https://university.dremio.com/course/apache-iceberg) - Free 12-part video course by Alex Merced covering architecture, transactions, catalogs, time-travel, and maintenance. Free.
- [Apache Iceberg: The Complete Masterclass (Udemy)](https://www.udemy.com/course/apache-iceberg-end-to-end-data-lakehouse-masterclass/) - Hands-on practical course with schema evolution, hidden partitioning, Spark integration, and production best practices. Paid.
- [Getting Started with Apache Iceberg (O'Reilly)](https://www.oreilly.com/live-events/getting-started-with-apache-iceberg/) - Live training with interactive exercises covering ACID guarantees, table creation, migration, and time-travel. Paid.
- [Apache Iceberg Courses (Class Central)](https://www.classcentral.com/subject/apache-iceberg) - Aggregator of 100+ Apache Iceberg courses covering Kafka, Spark, Impala, and AWS integrations. Mixed free/paid.

### Tutorials and Guides

- [Spark Iceberg Quickstart](https://iceberg.apache.org/spark-quickstart/) - Official Docker-based quick start with tabulario/spark-iceberg image and sample code for table operations. Official (ASF).
- [Apache Iceberg Tutorial (DataCamp)](https://www.datacamp.com/tutorial/apache-iceberg) - Complete beginner's guide with hands-on setup instructions and optimization techniques. Third-party.
- [Mastering Apache Iceberg (DigitalOcean)](https://www.digitalocean.com/community/tutorials/mastering-apache-iceberg) - Scalable data lake management guide with prerequisites, architecture, and practical implementation. Third-party.
- [Introduction to Apache Iceberg (Baeldung)](https://www.baeldung.com/apache-iceberg-intro) - Practical deployment tutorial with Minio, Trino, Docker, and code examples. Third-party.
- [Dremio Apache Iceberg 101](https://www.dremio.com/blog/apache-iceberg-101-your-guide-to-learning-apache-iceberg-concepts-and-practices/) - Comprehensive resource hub with 100+ links organized by core concepts, features, hands-on exercises, and production usage. Third-party.

### Best Practices

- [AWS Prescriptive Guidance for Iceberg](https://docs.aws.amazon.com/prescriptive-guidance/latest/apache-iceberg-on-aws/best-practices.html) - Optimization for cost, performance, and data retention with configuration trade-offs. AWS official.
- [Snowflake Iceberg Best Practices](https://docs.snowflake.com/en/user-guide/tables-iceberg-best-practices) - Refresh schedules, storage serialization, and query optimization guidance. Snowflake official.
- [Cloudera Iceberg Best Practices](https://docs.cloudera.com/runtime/7.2.17/iceberg-how-to/topics/iceberg-best-practices.html) - Format version 2, parallelism, positional deletes, and drop table performance optimization. Cloudera official.
- [7 Apache Iceberg Best Practices (Monte Carlo)](https://www.montecarlodata.com/blog-apache-iceberg-best-practices/) - Schema evolution, metadata management, catalog choice, and integration patterns with dbt, Snowflake, Databricks, Kafka. Third-party.
- [Optimize Iceberg Performance (Upsolver)](https://www.upsolver.com/blog/optimize-iceberg-performance) - 10 tips for partitioning, compaction, file sizes, z-ordering with webinar and advanced techniques. Third-party.

### Blogs and Articles

- [Dremio Blog](https://www.dremio.com/blog/) - Extensive collection of Iceberg articles, tutorials, comparisons, and feature announcements with regular updates. Vendor.
- [Tabular Blog](https://www.tabular.io/blog/) - Monthly Iceberg community news (2023-2024), technical deep-dives, Apache Iceberg Cookbook with 30+ recipes. Vendor.
- [2025 Guide to Architecting an Iceberg Lakehouse](https://blog.datalakehouse.help/posts/2024-12-2025-guide-architecting-an-iceberg-lakehouse/) - Comprehensive architecture guide with self-audit questions, tool selection, and best practices (December 2024). Community.
- [What's New in Apache Iceberg V3?](https://opensource.googleblog.com/2025/08/whats-new-in-iceberg-v3.html) - Binary deletion vectors with Roaring bitmaps, default column values, and V3 specification ratification (2025). Google official.
- [10 Future Iceberg Developments for 2025](https://medium.com/data-engineering-with-dremio/10-future-apache-iceberg-developments-to-look-forward-to-in-2025-7292a2a2101d) - Scan Planning endpoint, interoperable views, streaming support, and Hybrid Catalog GA (January 2025). Community.

### Video Resources

- [Apache Iceberg YouTube Channel](https://www.youtube.com/@ApacheIceberg) - Official talks, tutorials, conference recordings, and Iceberg Summit 2024 playlist with 32 talks. Official (ASF).
- [Gnarly Data Waves Podcast](https://www.youtube.com/@gnarlydatawaves) - Apache Iceberg Office Hours recordings and dedicated episodes on Iceberg topics, available on YouTube and Spotify. Community.

### Example Projects

- [Iceberg Spark S3 Examples](https://github.com/ismailsimsek/iceberg-examples) - Spark SQL examples with Iceberg on S3 and Java API usage demonstrations. Community.
- [Iceberg Streaming Examples (AWS)](https://github.com/aws-samples/iceberg-streaming-examples) - High-throughput IoT and CDC scenarios with Spark + Iceberg streaming best practices and local development environment. AWS samples.
- [Iceberg Demo (Flink + Trino)](https://github.com/tj---/iceberg-demo) - Stream writes to Iceberg on GCS using Flink and reading with Trino via Iceberg connector. Community.
- [Iceberg in Production](https://github.com/dipankarmazumdar/iceberg-in-production) - Curated blogs and videos showing real-world Iceberg production usage from various organizations. Community.

---

## Contributing

Contributions welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first. Submit a pull request with your suggestions following the awesome-x format.

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work.
