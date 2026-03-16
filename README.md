# Microsoft Fabric API Data Pipeline

This project demonstrates an end-to-end data engineering pipeline built using Microsoft Fabric. The pipeline extracts data from a public REST API, stores the raw data in a Lakehouse Bronze layer, and processes the data through Silver and Gold layers using notebooks.

## Pipeline Overview

The pipeline contains three main stages:

**1. Extract_from_API**

This step uses a Copy activity to fetch data from a REST API using an HTTP GET request. The API response is read as JSON and stored in the Fabric Lakehouse. The raw data is written to the Bronze layer as a JSON file.

Raw data path:
API_data/bronze/posts/Raw_API_DATA.json

This layer stores unprocessed data exactly as received from the source system.

**2. bronze_TO_Silver**

After the raw data is ingested, a Microsoft Fabric notebook processes the Bronze data. In this stage the data is cleaned, validated, and transformed into a structured format suitable for analytics.

Typical transformations include:

* Removing invalid records
* Flattening JSON structure
* Standardizing column names
* Data type conversions

The cleaned data is then stored in the Silver layer.

**3. Silver_to_Gold**

In the final stage, another notebook processes the Silver layer data to create analytics-ready datasets. The Gold layer contains curated and aggregated tables designed for reporting and business intelligence.

These datasets can be used by dashboards, reporting tools, or downstream analytics systems.

## Architecture Flow

API Source
↓
Copy Activity (Extract_from_API)
↓
Bronze Layer (Raw JSON in Lakehouse)
↓
Notebook Transformation (bronze_TO_Silver)
↓
Silver Layer (Clean Structured Data)
↓
Notebook Aggregation (Silver_to_Gold)
↓
Gold Layer (Business Ready Data)

## Technologies Used

* Microsoft Fabric
* Fabric Data Pipeline
* Lakehouse Architecture
* REST API Data Ingestion
* Notebook-based Data Transformation
* JSON Data Processing
* Git for version control

## Purpose of the Project

This project demonstrates how to design a scalable data pipeline using Microsoft Fabric and implement a Medallion Architecture for structured data processing. It highlights core data engineering concepts such as data ingestion, transformation pipelines, and layered data architecture.
