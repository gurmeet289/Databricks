# Databricks

## 📊 Databricks Overview

---

## What is Databricks?

Databricks is a cloud-based unified data and AI platform built on **Apache Spark**, designed for processing big data and enabling collaborative data science, engineering, and machine learning. It was founded by the creators of Apache Spark and is available on major cloud platforms like **AWS**, **Azure**, and **Google Cloud**.

---

## Why is Databricks Used?

Databricks is used to:

- **Handle Big Data**: Process petabytes of structured, semi-structured, and unstructured data at scale.
- **Collaborate on Data Projects**: Enable data scientists, engineers, and analysts to work together in shared notebooks.
- **Simplify Data Pipelines**: Build ETL/ELT pipelines with ease using Spark or SQL.
- **Run Machine Learning Workflows**: Train, deploy, and track ML models with built-in MLflow.
- **Unify Data Lakes and Warehouses**: Implement a **Lakehouse** architecture combining the best of both worlds.

---

## Similar Tools / Platforms Like Databricks

| Platform                    | Key Features                                                              |
|-----------------------------|---------------------------------------------------------------------------|
| **Snowflake**               | Cloud data warehouse optimized for SQL & BI workloads                     |
| **Google BigQuery**         | Fully-managed serverless data warehouse (SQL-based)                      |
| **Azure Synapse**           | Unified analytics with data warehouse and Spark                          |
| **Amazon EMR**              | Managed Hadoop/Spark cluster for big data workloads                      |
| **Cloudera Data Platform**  | Hybrid data platform with Hadoop & Spark                                 |
| **Apache Spark (Standalone)** | Open-source, distributed big data engine                                |

---

## Key Features / Uniqueness of Databricks

| Feature                   | Uniqueness / Advantage                                                                 |
|---------------------------|----------------------------------------------------------------------------------------|
| **Lakehouse Architecture** | Combines flexibility of data lakes with ACID transactions via Delta Lake             |
| **Collaborative Notebooks**| Real-time co-authoring, version control, supports SQL, Python, R, Scala              |
| **Auto-scaling Clusters** | Automatically adjusts compute resources based on workload                            |
| **MLflow Integration**    | Built-in tool for managing ML lifecycle (tracking, packaging, deployment)            |
| **Delta Lake**            | Open-source storage layer for ACID transactions and schema enforcement                |
| **Serverless and Managed**| No infrastructure management, fast setup                                              |
| **Unity Catalog**         | Centralized governance, access control, and lineage tracking across data assets       |

---

## Why Databricks Came Into the Picture: Problem It Solves

### 🚨 Problems Before Databricks:
- Data lakes were **cheap but unreliable** (no ACID compliance, weak governance).
- Data warehouses were **reliable but expensive**, and struggled with unstructured data.
- Data engineers, scientists, and analysts worked in **silos using separate tools**.
- Managing Spark and distributed computing environments was **complex and error-prone**.

---

### Databricks Solved This By:
- Creating the **Lakehouse architecture** via Delta Lake.
- Providing a **unified platform** for all data roles.
- Offering **managed Spark** with notebooks and collaborative workflows.
- Enabling **enterprise-grade governance** using Unity Catalog.
- Simplifying **AI/ML development** with tools like MLflow and AutoML.

---
# 🧱 Databricks Architecture Diagram
## 📘 Explanation

### 1. External Data Sources
This layer represents all possible sources of data that feed into Databricks.

- **RDBMS**: MySQL, Oracle, PostgreSQL, etc.
- **REST APIs**: Interfaces over HTTP.
- **Event Streams**: Real-time data via Apache Kafka.
- **IoT/Logs/Flat Files**: CSVs, JSON, device logs.
- **ERP/CRM Systems**: SAP, Salesforce.
- **SaaS Platforms**: Google Analytics, Workday, etc.

---

### 2. Ingestion Layer
This is where raw data enters Databricks from external sources.

- **Auto Loader**: Automatic data ingestion in batch/streaming.
- **Spark Structured Streaming**: Real-time processing framework.
- **COPY INTO**: SQL command to load into Delta Lake.
- **Partner Tools**: Fivetran, Informatica.
- **Messaging Systems**:
  - Kafka
  - Azure Event Hubs
  - Google Pub/Sub

---

### 3. Storage Layer + Medallion Architecture (Delta Lake)

Implements a structured, tiered data lake.

- **Delta Lake**: Adds ACID transactions and schema enforcement to data lakes.
- **Medallion Architecture**:
  - **Bronze**: Raw data (unfiltered).
  - **Silver**: Cleaned and joined data.
  - **Gold**: Aggregated, curated data.
- **Cloud Storage**:
  - Amazon S3
  - Azure ADLS
  - Google Cloud Storage (GCS)

---

### 4. Data Processing & Engineering Layer

Transforms and enriches data for analytics and ML.

- **Apache Spark**: Core engine for distributed compute.
- **PySpark**: Python API for Spark.
- **Delta Live Tables (DLT)**: Declarative ETL pipelines.
- **MLlib / XGBoost**: Machine learning libraries.
- **Workflows**: Job orchestration.

---

### 5. Compute / Runtime Environment

Executes queries, notebooks, and models.

- **Databricks Clusters**:
  - Interactive Clusters (development)
  - Job Clusters (production)
- **Photon Runtime**: High-speed SQL engine.
- **Serverless SQL Warehouses**: Auto-managed compute.

---

### 6. Governance & Catalog Layer

Manages security, metadata, and access control.

- **Unity Catalog**:
  - RBAC
  - Lineage tracking
  - Tagging
  - Audit logs
- **IAM Integration**: With Azure AD, Okta, etc.

---

### 7. Consumption & Interface Layer

How users and systems access and consume data.

- **Notebooks**: Python, SQL, R, Scala.
- **SQL Editor**
- **BI Tools**:
  - Power BI
  - Tableau
- **Job Scheduler**
- **APIs & SDKs**:
  - REST APIs
  - dbx CLI
  - Python/Scala SDKs

---

### 8. Cloud Infrastructure Platform

Where Databricks is hosted and scaled.

- **Cloud Platforms**: AWS, Azure, GCP.
- **Object Storage**: S3, ADLS, GCS.
- **Cluster Provisioning**: Kubernetes or Virtual Machines.

---

## 🔄 Summary: How It All Connects

- Data flows from external sources into the Ingestion Layer.
- Stored in Delta Lake using the Medallion Architecture (Bronze → Silver → Gold).
- Transformed via Spark and ML in the Processing Layer.
- Executed on managed compute environments.
- Governed via Unity Catalog for secure access and auditing.
- Consumed by analysts and apps via notebooks, BI tools, and APIs.
- Entire stack runs on cloud platforms like AWS, Azure, or GCP.

---

✨ Built for scalability, governance, and real-time intelligence.

