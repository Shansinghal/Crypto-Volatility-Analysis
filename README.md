## Cryptocurrency Volatility Data Pipeline

This project is an automated, end-to-end data engineering pipeline built in Databricks. It extracts live cryptocurrency market data from the CoinGecko API, processes it through a Medallion Architecture (Bronze, Silver, Gold) using PySpark and Spark SQL, and generates a live volatility leaderboard for financial analysis.

## Architecture & Tech Stack

Language: Python, SQL
Data Processing: Apache Spark (PySpark), Spark SQL
Storage: Delta Lake
Orchestration: Databricks Workflows (Job Scheduler)
Data Source: CoinGecko REST API
