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
# 🧱 Databricks Architecture Block Flow Diagram

This diagram illustrates a typical Databricks-based Lakehouse architecture using layers. Each block represents a functional component of the data pipeline.


![image](https://github.com/user-attachments/assets/c906318c-4e76-4833-8dcd-0611c24c7fc0)
![image](https://github.com/user-attachments/assets/a6a6928e-0438-4717-a6ec-d3abce05ea3a)
![image](https://github.com/user-attachments/assets/22e4afb5-f8c2-4aa5-a4be-30861355ef83)

---

## 📘 Explanation

### 1. EXTERNAL DATA SOURCES
This layer represents all possible sources of data that feed into Databricks.
- **RDBMS (Relational Database Management System)**: Databases like MySQL, Oracle, PostgreSQL.
- **REST APIs**: Interfaces that allow applications to communicate over HTTP.
- **Event Streams (Kafka)**: Real-time data pipelines using tools like Apache Kafka.
- **IoT/Logs/Flat Files**: Machine-generated data, device data, CSVs, JSON, etc.
- **ERP/CRM Systems**: Enterprise systems like SAP (ERP) or Salesforce (CRM).
- **SaaS Platforms**: Cloud-based services such as Google Analytics, Salesforce, Workday.

---

### 2. INGESTION LAYER
This is where raw data enters Databricks from the external sources.
- **Auto Loader**: A Databricks utility for ingesting data in batch or streaming mode automatically.
- **Spark Structured Streaming**: Framework for processing streaming data.
- **COPY INTO**: SQL command for loading data into Delta Lake.
- **Partner Tools**: Tools like Fivetran, Informatica that offer prebuilt connectors.
- **Kafka / Event Hubs / PubSub**:
  - **Kafka**: Distributed event streaming platform.
  - **Event Hubs**: Azure’s event ingestion service.
  - **Pub/Sub**: Google Cloud’s messaging system.

---

### 3. STORAGE LAYER + MEDALLION ARCHITECTURE (Delta Lake)
This is the structured data lake using Delta Lake and implements the Medallion Architecture.
- **Delta Lake**: An open-source storage layer that brings ACID transactions to data lakes.
- **Medallion Architecture**: A 3-tier logical design to organize data:
  - **BRONZE**: Raw ingestion data (unfiltered, unvalidated).
  - **SILVER**: Cleaned and joined data (validated, deduplicated).
  - **GOLD**: Business-level curated data (aggregated, enriched).
- **Cloud Storage**:
  - **S3** – Amazon Simple Storage Service
  - **ADLS** – Azure Data Lake Storage
  - **GCS** – Google Cloud Storage

---

### 4. DATA PROCESSING & ENGINEERING LAYER
This layer transforms, enriches, and prepares the data for analytics or ML.
- **Apache Spark**: Distributed data processing engine (Databricks is built on this).
- **PySpark**: Python API for Apache Spark.
- **Delta Live Tables (DLT)**: Declarative pipelines that automate ETL workflows.
- **MLlib / XGBoost**: Built-in libraries for machine learning.
- **Databricks Workflows**: Orchestrates jobs, schedules, and dependencies.

---

### 5. COMPUTE / RUNTIME ENVIRONMENT
Resources used to execute queries, notebooks, pipelines, and ML models.
- **Databricks Clusters**:
  - **Interactive Cluster** – For development & notebooks.
  - **Job Cluster** – For production jobs.
- **Photon Runtime**: Highly performant SQL engine built by Databricks.
- **Serverless SQL Warehouses**: Auto-managed compute for SQL users.

---

### 6. GOVERNANCE & CATALOG LAYER
Handles access, security, metadata, and lineage.
- **Unity Catalog**:
  - **RBAC** – Role-Based Access Control
  - **Lineage** – Track data origin and transformation
  - **Tags** – Metadata labels
  - **Audits** – Logs for compliance and monitoring
- **IAM (Identity and Access Management)**: Integrated with providers like Azure Active Directory for user identity and permission control.

---

### 7. CONSUMPTION & INTERFACE LAYER
Interfaces and tools used to consume and interact with the data.
- **Notebooks**: Interactive environment for coding in Python, SQL, Scala, R.
- **SQL Editor**: GUI-based SQL editor in Databricks.
- **BI Dashboards**:
  - **Power BI** – Microsoft’s analytics dashboard tool.
  - **Tableau** – Popular data visualization platform.
- **Databricks Jobs**: Scheduler for notebooks, scripts, pipelines.
- **REST APIs / SDKs / dbx CLI**:
  - **REST API** – Allows programmatic access.
  - **SDK** – Software Development Kit for integration.
  - **dbx CLI** – CLI tool to manage jobs, repos, deployments.

---

### 8. CLOUD INFRASTRUCTURE PLATFORM
Underlying cloud services where Databricks is deployed.
- **AWS / Azure / GCP** – Cloud platforms supported by Databricks.
- **Cloud Object Storage**: Persistent storage used by Delta Lake.
- **Managed Kubernetes / VMs**:
  - **Kubernetes** – Container orchestration engine.
  - **VMs** – Virtual Machines provisioned for running Spark clusters.

---

### Summary: How It All Connects
- Data flows from external sources to the **Ingestion Layer**.
- The data is then stored in Delta Lake following the **Medallion Architecture** (Bronze → Silver → Gold).
- It’s processed using **Spark** and **ML** pipelines in the **Data Engineering Layer**.
- These transformations run on compute clusters managed by **Databricks**.
- **Governance** ensures secure and compliant data access.
- Finally, data is consumed via **notebooks**, **dashboards**, or **APIs**.
- All of this is built on cloud infrastructure like **AWS**, **Azure**, or **GCP**.
