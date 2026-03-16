# 🚀 Microsoft Fabric API Data Pipeline

This project demonstrates an **end-to-end data engineering pipeline built using Microsoft Fabric**. The pipeline extracts data from a public REST API, stores raw data in the **Lakehouse Bronze layer**, and processes the data through **Silver and Gold layers** using Fabric notebooks.

The solution follows the **Medallion Architecture (Bronze → Silver → Gold)** to enable scalable and structured data processing for analytics.

---

# 🔄 Pipeline Overview

The pipeline consists of **three main stages**.

---

## 1️⃣ Extract_from_API

This stage uses a **Copy Activity** in Microsoft Fabric Data Pipeline to fetch data from a **REST API** using an HTTP GET request.

The API response is retrieved in **JSON format** and stored directly in the **Lakehouse Bronze layer** as raw data.

**Raw Data Path**

```
API_data/bronze/posts/Raw_API_DATA.json
```

The Bronze layer stores the **unprocessed source data exactly as received**, ensuring traceability and reproducibility.

---

## 2️⃣ Bronze_to_Silver

Once the raw data is ingested, a **Microsoft Fabric Notebook** processes the Bronze data and transforms it into a structured dataset suitable for analytics.

Typical transformations include:

* Removing invalid or duplicate records
* Flattening nested JSON structures
* Standardizing column names
* Performing data type conversions
* Applying basic data validation rules

The processed dataset is then stored in the **Silver layer** as structured tables.

The Silver layer contains **clean and reliable datasets ready for further transformation**.

---

## 3️⃣ Silver_to_Gold

In the final stage, another Fabric notebook processes the **Silver layer tables** to create **analytics-ready datasets**.

The Gold layer contains **curated and aggregated tables** optimized for reporting and business intelligence.

Typical operations include:

* Data aggregation
* Business metric calculations
* Data enrichment
* Preparing datasets for analytics

These datasets can be consumed by:

* Power BI dashboards
* reporting tools
* downstream analytics systems

---

# 🏗 Architecture Flow

```
API Source
      ↓
Fabric Data Pipeline (Copy Activity)
      ↓
Bronze Layer (Raw JSON Files in Lakehouse)
      ↓
Notebook Transformation (Bronze → Silver)
      ↓
Silver Layer (Clean Structured Data)
      ↓
Notebook Aggregation (Silver → Gold)
      ↓
Gold Layer (Analytics Ready Data)
```

---

# 🧰 Technologies Used

* Microsoft Fabric
* Fabric Data Pipelines
* Lakehouse Architecture
* REST API Data Ingestion
* PySpark / Fabric Notebooks
* JSON Data Processing
* Git for Version Control

---

# 🎯 Purpose of the Project

This project demonstrates how to design and implement a **scalable data pipeline using Microsoft Fabric**.

It highlights key data engineering practices including:

* ingesting data from external APIs
* implementing Medallion Architecture
* notebook-based data transformations
* layered data modeling for analytics
* building analytics-ready datasets for reporting and dashboards
