# 📈 Real-Time Stock Market Data Pipeline

<img width="5889" height="3500" alt="487893098-6b49eb4d-4bf7-473d-9281-50c20b241760" src="https://github.com/user-attachments/assets/ecdd574d-9070-432c-90ca-147075d874ef" />


## 🚀 Business Context & Strategy
In today’s fast-paced financial markets, stale data leads to poor decision-making. The goal of this project was to engineer a **highly reliable, low-latency data pipeline** that captures live stock market movements and transforms them into actionable business intelligence. 

By leveraging the **Modern Data Stack**, this architecture ensures that Data Scientists and Business Analysts always have access to clean, real-time data for trend analysis, KPI monitoring, and strategic forecasting.

## 🛠️ Tech Stack
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apache-kafka&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=for-the-badge&logo=snowflake&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Apache_Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=for-the-badge&logo=dbt&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

## 🏗️ Technical Architecture & Pipeline Flow

* **Engineered** a robust Python Producer that connects to the Finnhub API, pulling live stock quotes and publishing them to an Apache Kafka streaming topic.
* **Built** a resilient Kafka Consumer to subscribe to the live stream, reliably writing raw JSON payloads into MinIO (S3-compatible) storage to act as our foundational Data Lake.
* **Orchestrated** automated ELT workflows using Apache Airflow, scheduling DAGs to ingest raw data from MinIO into the Snowflake Bronze layer every 60 seconds.
* **Driven** by the Medallion Architecture, applied DBT (Data Build Tool) models to transform raw data:
  * *Silver Layer:* Cleansed, deduplicated, and standardized stock quotes.
  * *Gold Layer:* Modeled into analytics-ready tables for Candlestick charts, KPIs, and Tree Maps.
* **Led** the final visualization phase by connecting Power BI directly to the Snowflake Gold layer via Direct Query, delivering real-time dashboards for business stakeholders.

## 📊 Final Deliverables

🔥 **Live Interactive Dashboard:** [Click here to view the real-time Power BI Dashboard!](https://app.powerbi.com/view?r=eyJrIjoiOGU3Zjg5OTQtZTA2Yi00ODg4LTlhM2YtOWYwNzA3MzRlZDI5IiwidCI6ImE1MTVlN2M0LThjZjctNGY5Ny1iMjNiLTk2NDkxNjQ1ZjdmMCIsImMiOjEwfQ%3D%3D)

<img width="1725" height="940" alt="Screenshot 2026-07-05 115428" src="https://github.com/user-attachments/assets/ec68cd6a-600c-4c04-a6aa-716b648c8c74" />


## ⚙️ How to Run Locally
1. Clone this repository.
2. Spin up the infrastructure using Docker: `docker-compose up -d`
3. Execute the Kafka Producer and Consumer scripts.
4. Enable the Airflow DAG to automate Snowflake ingestion.
5. Run `dbt run` to build the Silver and Gold models in Snowflake.

---
*Note: This project was executed following the architectural framework designed by [Data with Jay](https://github.com/Jay61616/real-time-stocks-mds). It served as a practical implementation to master streaming data and modern cloud data warehouse technologies.*
