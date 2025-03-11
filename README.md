# Data-Pipeline-for-Customer-Account-Analysis

## 📌 Project Overview
This project aims to design and implement a scalable **Data Pipeline** for processing customer account data. The pipeline efficiently ingests, transforms, and loads data from an **Azure Data Lake Storage (ADLS) GOLD Storage** into an **Azure Synapse Analytics dedicated SQL pool** for downstream analytics and reporting.

## 🔥 Key Features
- **Data Ingestion:** Copy data from backend storage to the raw (bronze) container.
- **Incremental Processing with Databricks:** Clean and transform data in **Databricks Notebooks**.
- **ETL Processing:** Perform business logic transformations and aggregate customer balances.
- **Delta Table Processing:** Store curated data in **Parquet/Delta format** in ADLS GOLD storage.
- **Synapse Integration:** Create external tables in Azure Synapse Analytics and enable upsert functionality.
- **End-to-End Automation:** Utilize **Azure Data Factory (ADF)** for automation.

## 🛠️ Technologies Used
- **Azure Data Lake Storage (ADLS)**
- **Azure Data Factory (ADF)**
- **Databricks (PySpark & Delta Lake)**
- **Azure Synapse Analytics (Dedicated SQL Pool)**
- **Parquet & Delta Formats**
- **Azure IAM for Authentication**

## 📂 Project Steps
### **Step 1: Data Ingestion**
- Configured **Azure Data Factory (ADF)** to copy data from backend storage to the raw (bronze) container.
- Files copied:
  - `accounts.csv`
  - `customers.csv`
  - `loan_payments.csv`
  - `loans.csv`
  - `transactions.csv`

### **Step 2: Incremental Processing with Databricks**
- Read data from bronze container using Databricks.
- Cleaned and transformed raw data, ensuring schema correctness.
- Converted raw data into **Parquet/Delta format** before loading into the **silver** container.

### **Step 3: ETL Processing**
- Read **Curated (Silver) Data** from ADLS.
- Implemented **business logic** to calculate customer balances.
- Wrote transformed data to the **Refined (Gold) Container**.

### **Step 4: Loading Data into Azure Synapse Analytics**
- Created **External Tables** in Synapse Analytics for Gold Data.
- Configured **Data Pipeline** in ADF to load gold data into Synapse SQL tables.
- Used **MERGE (Upsert) logic** to handle existing records.

## ✅ Project Deliverables
- **Databricks Notebooks:** Contains all data transformation logic.
- **ADF Pipelines:** Automates data ingestion & loading into Synapse.
- **SQL Scripts:** To create external tables and validate data.
- **Screenshots & Logs:** Documented execution steps for reference.
