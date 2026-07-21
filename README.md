## Cryptocurrency Volatility Data Pipeline

This project is an automated, end-to-end data engineering pipeline built in Databricks. It extracts live cryptocurrency market data from the CoinGecko API, processes it through a Medallion Architecture (Bronze, Silver, Gold) using PySpark and Spark SQL, and generates a live volatility leaderboard for financial analysis.

## Architecture & Tech Stack

Language: Python, SQL
Data Processing: Apache Spark (PySpark), Spark SQL
Storage: Delta Lake
Orchestration: Databricks Workflows (Job Scheduler)
Data Source: CoinGecko REST API

<img width="1321" height="1155" alt="image" src="https://github.com/user-attachments/assets/9e9a2518-38f5-4f6a-99e8-98ebebc1a0af" />

In this project, I leveraged Apache Spark (via PySpark and Spark SQL) as the core distributed processing engine to handle complex data transformations. Using PySpark's DataFrame API in the Silver layer, I efficiently performed data cleansing, type casting, and feature engineering such as dynamically categorizing coins into market cap tiers using when/otherwise logic and calculating exact price spreads.
Spark SQL was then used in the Gold layer to rapidly aggregate this cleansed data into business-ready metrics, such as Market Dominance and custom Volatility Indexes.

To elevate this pipeline from a static script to a live tracking system, I implemented the Databricks Job Scheduler (Workflows). I orchestrated the notebooks to execute sequentially (Bronze $\rightarrow$ Silver $\rightarrow$ Gold) on an automated, two-minute continuous trigger. This seamless orchestration ensured that fresh API payload data was constantly ingested, transformed, and merged into the Delta Lake, providing near real-time updates to the downstream analytics tables and dashboards without any manual intervention.
