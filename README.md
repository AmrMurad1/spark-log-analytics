# Web Log Analytics Pipeline
**Medallion Architecture | Databricks | Spark**

## Executive Summary
An end-to-end data pipeline processing **3.3GB of raw web logs** into a structured **Star Schema**. This project demonstrates scalable ETL/ELT practices using Delta Lake to provide actionable DevOps insights.

<img width="2701" height="2525" alt="image" src="https://github.com/user-attachments/assets/0e9a5523-440c-49eb-8e1c-12e9ade31362" />

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
