# Web Log Analytics Pipeline
**Medallion Architecture | Databricks | Spark**

## Executive Summary
An end-to-end data pipeline processing **3.3GB of raw web logs** into a structured **Star Schema**. This project demonstrates scalable ETL/ELT practices using Delta Lake to provide actionable DevOps insights.



## Tech Stack
* **Engine:** PySpark (DataFrames & Spark SQL)
* **Storage:** Delta Lake (ACID, Time Travel, Schema Evolution)
* **Orchestration:** Databricks Workflows (Automated Jobs)

---

## Pipeline Architecture

| Layer | Type | Responsibility |
| :--- | :--- | :--- |
| **Bronze** | Raw | Ingestion of `.txt` logs into Delta tables (Source of Truth). |
| **Silver** | Cleansed | Regex parsing, data type casting, and null handling. |
| **Gold** | Analytics | **Star Schema** implementation (Fact & Dimension tables). |

## The Gold Layer (Star Schema)
To optimize analytical performance, the data is modeled into:
* **`fact_web_traffic`**: Transactional logs partitioned by `date`.
* **`dim_clients`**: Unique IP-to-Hostname mapping.
* **`dim_date`**: Temporal metadata (Day, Month, Weekends).
* **`vw_devops_dashboard`**: A unified semantic view for BI consumption.



## Key Insights Delivered
* **Error Rate Monitoring:** Real-time tracking of 4xx and 5xx status codes.
* **Traffic Heatmaps:** Identification of peak request periods via `dim_date`.
* **Resource Allocation:** Bandwidth consumption analysis per endpoint.

## Automation
The pipeline is fully automated via **Databricks Jobs**, utilizing **Job Clusters** for cost-efficient execution and **Partitioning** for high-speed querying.
