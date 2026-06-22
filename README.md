# Green Taxi Data Engineering Pipeline on Microsoft Azure

## Project Overview

This project demonstrates an end-to-end Azure Data Engineering solution built using Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, Delta Lake, Azure Key Vault, and Microsoft Entra ID.

The solution follows the Medallion Architecture (Bronze, Silver, Gold) to ingest, transform, and serve Green Taxi trip data from an external API source. A scalable and parameterized ingestion framework was implemented using Azure Data Factory, while Azure Databricks and PySpark were used to perform data cleansing, validation, and business transformations. The final curated data was stored as Delta Tables to leverage advanced Delta Lake features such as ACID transactions, schema enforcement, versioning, and time travel.

---

## Solution Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/6b82630b-cd52-4f05-a15b-e59387b1eade" />

---

## Goal of the Project

The primary objective of this project is to design and implement a cloud-native data engineering pipeline capable of handling large-scale transportation data using Azure services.

### Key Objectives

* Build an automated data ingestion framework using Azure Data Factory.
* Implement parameterized and dynamic pipelines for scalability.
* Design a Medallion Architecture using Bronze, Silver, and Gold layers.
* Perform large-scale data transformations using PySpark.
* Implement Delta Lake for reliable and optimized data storage.
* Demonstrate advanced Delta Lake capabilities such as Versioning and Time Travel.
* Apply security best practices using Azure Key Vault and Microsoft Entra ID.

---

## Technology Stack

### Cloud Services

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure Databricks
* Azure Key Vault
* Microsoft Entra ID

### Data Engineering Tools

* PySpark
* Delta Lake
* Parquet
* REST API

### Programming Languages

* Python
* SQL

---

# Part 1: Data Ingestion

The ingestion layer was developed using Azure Data Factory to extract Green Taxi trip data from an external API source and load it into Azure Data Lake Storage Gen2.

Rather than creating separate pipelines for each dataset, a parameterized and metadata-driven framework was implemented. Dynamic pipelines enable ingestion of multiple datasets while minimizing development effort and improving maintainability.

### Key Highlights

* API-based data ingestion using Azure Data Factory.
* Parameterized pipeline design.
* Dynamic ingestion using pipeline expressions and parameters.
* Metadata-driven architecture.
* Automated extraction from source APIs.
* Raw data landing in Bronze layer.
* Data stored in Parquet format.
* Scheduled and on-demand execution support.
* Reusable ingestion framework for future datasets.

### Business Value

The ingestion framework enables scalable onboarding of new datasets without redesigning pipelines, making the solution suitable for enterprise-scale data operations.

<img width="1847" height="594" alt="1000193880" src="https://github.com/user-attachments/assets/4a1e6bfe-541b-4e45-a914-2a99176a3d96" />

Dynamic Pipeline Configuration

<img width="1846" height="639" alt="1000193879" src="https://github.com/user-attachments/assets/0311358f-ae53-41f7-9f12-39dd92dc478f" />
<img width="1546" height="848" alt="1000193881" src="https://github.com/user-attachments/assets/2dadc48e-88a2-483d-a9bd-54ed87920cee" />

Successful Pipeline Run

<img width="1591" height="915" alt="1000193882" src="https://github.com/user-attachments/assets/fde74c63-afa1-43aa-859b-03165e459d37" />
Data Ingestion
img width="1593" height="783" alt="image" src="https://github.com/user-attachments/assets/602d5bac-16b4-4dc8-b207-cfb9f72de7ac" />


---

# Part 2: Data Transformation

Azure Databricks and PySpark were used to process and transform raw data following Medallion Architecture best practices.

The transformation process was divided into Bronze-to-Silver and Silver-to-Gold stages to ensure data quality, consistency, and analytical readiness.

## Bronze to Silver

The raw data was validated, cleaned, and standardized.

### Activities Performed

* Schema validation
* Data type conversions
* Null handling
* Duplicate removal
* Data quality checks
* Standardization of columns

## Silver to Gold

Business transformations were applied to prepare datasets for analytics and reporting.



### Business Value

The layered transformation approach improves data quality, governance, maintainability, and analytical reliability.



Databricks Workspace
<img width="1666" height="957" alt="1000193898" src="https://github.com/user-attachments/assets/e9b2f690-f7e2-4496-ba1d-00de8f310f4e" />

Service Principle
<img width="1666" height="826" alt="1000193899" src="https://github.com/user-attachments/assets/e3defef7-f0e8-4e7b-b7c0-65c1fcbe3b18" />

Bronze to Silver Notebook Writing data
<img width="1902" height="607" alt="1000193900" src="https://github.com/user-attachments/assets/b6b0530a-2987-4780-b80d-03d13a60feb9" />


Transformation Results
<img width="1603" height="815" alt="1000193901" src="https://github.com/user-attachments/assets/a476bdff-9cb4-4fc7-9d1d-4b886cbb06af" />


---

# Part 3: Serving Layer (Delta Lake)

The Gold layer was implemented using Delta Lake to provide a reliable and analytics-ready serving layer.

Delta Lake enhances traditional data lake architectures by adding transactional consistency, schema management, and historical tracking capabilities.

### Key Highlights

* Creation of Delta Tables.
* ACID-compliant transactions.
* Schema enforcement.
* Schema evolution support.
* Delta transaction logs.
* Historical data versioning.
* Time Travel functionality.
* Optimized analytical querying.

### Advanced Concepts Demonstrated

* Managed Delta Tables
* External Delta Tables
* Delta Logs
* Data Versioning
* Time Travel Queries
* Historical Data Recovery

### Business Value

Delta Lake enables enterprise-grade reliability while maintaining the flexibility and scalability of a modern data lake architecture.

📷 **Attach Screenshots**

* Delta Table Creation
* Delta Log Structure
* Delta Version History
* Time Travel Query Results
* Gold Layer Storage

---

# Security and Governance

Security and access management were implemented using Azure-native services.

### Components Used

* Microsoft Entra ID
* Azure Key Vault

### Security Features

* Secure authentication and authorization.
* Secret management through Key Vault.
* Access control and governance.
* Secure service connectivity.



---

# Pipeline Automation and Monitoring

The solution supports automated execution and monitoring capabilities through Azure Data Factory.

### Features

* Scheduled pipeline execution.
* On-demand execution.
* Pipeline monitoring.
* Logging and troubleshooting.
* Automated orchestration.

📷 **Attach Screenshots**

* Trigger Configuration
* Monitoring Dashboard
* Successful Pipeline Execution

---

# Conclusion

This project demonstrates the implementation of a modern Azure Data Engineering solution using industry-standard cloud services and architectural patterns. By combining Azure Data Factory, Azure Databricks, Delta Lake, and Azure Data Lake Storage Gen2, the solution provides a scalable, secure, and analytics-ready platform for processing Green Taxi trip data.
