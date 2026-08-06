# Wind-Turbine-Data-Pipeline
Scalable PySpark data pipeline for processing wind turbine telemetry, performing statistical aggregations, detecting anomalies, and storing clean data in SQLite.

A scalable big data processing pipeline built using PySpark designed to ingest, clean, aggregate, and analyze multi-source telemetry data from 15 wind turbines. The project automates data extraction, performs rigorous data quality checks, handles missing and duplicate values, calculates statistical aggregations, detects anomalies using standard deviation thresholds, and exports the final insights into a structured SQLite database and compressed archive bundles.

An organization needed a reliable, high-performance data processing pipeline to ingest raw, distributed telemetry log datasets (`data_group_1.csv`, `data_group_2.csv`, `data_group_3.csv`) containing timestamped wind speed, direction, and power output metrics across 15 separate wind turbines.

In this project I developed an end-to-end automated big data workflow in Python utilizing PySpark to ingest compressed raw logs, validate schema structures, clean anomalies, compute daily and overall operational performance aggregates, and persist the processed outputs cleanly for downstream analytical platforms or relational databases.

Actions:
1. Infrastructural Setup & Ingestion: Configured a PySpark `SparkSession` environment, handling automated zip-file extraction and schema inference across multiple distributed CSV partitions.
2. Data Quality & Validation: Executed programmatic null-value checks, duplicate identification, and record validation across all 11,160 entries to secure data integrity.
3. Transformation & Aggregation: Utilized PySpark SQL and DataFrame APIs to build daily power production summaries (calculating minimum, maximum, average power output, and sample counts) and derive statistical baselines (mean and standard deviation per turbine).
4. Anomaly Detection & Persistence: Implemented statistical anomaly-filtering rules based on standard deviation boundaries, converted distributed data frames into Pandas for lightweight operations, and loaded the curated records into a relational SQLite database (`wind_turbine.db`) alongside compressed ZIP exports.

Result:
Successfully delivered a robust, fault-tolerant data pipeline that processed over 11,000 telemetry records without data loss. The solution automatically generated standardized operational summaries, isolated anomalies, and produced portable database and CSV bundle artifacts ready for reporting and maintenance teams.
