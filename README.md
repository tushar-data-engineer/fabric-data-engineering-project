# Microsoft Fabric Data Engineering Pipeline

This project demonstrates a simple data engineering pipeline built using Microsoft Fabric. The pipeline extracts data from a public REST API, processes it through different data layers, and stores it in a Lakehouse for analytics.

Since native Git integration is not available in free Microsoft Fabric workspaces, the pipeline definition is exported as JSON and stored in this repository to enable version control and project documentation.

## Architecture

The pipeline follows a Medallion Architecture pattern:

Bronze Layer
Raw data extracted from the API is stored without transformation.

Silver Layer
Data is cleaned and structured for analytical processing.

Gold Layer
Business-ready aggregated datasets are created for reporting and analytics.

## Pipeline Workflow

API Source
↓
Microsoft Fabric Data Pipeline
↓
Lakehouse Bronze Layer
↓
Data Transformation
↓
Silver Layer
↓
Gold Analytics Tables

## Repository Structure

pipelines/
Contains exported JSON definitions of Microsoft Fabric pipelines.

notebooks/
Contains data transformation notebooks.

sql/
Contains SQL scripts used for data modeling and aggregation.

architecture/
Contains architecture diagrams of the pipeline.

## Technologies Used

Microsoft Fabric
Lakehouse Architecture
REST API Data Extraction
Git Version Control

## Purpose of This Project

This repository demonstrates how data engineering pipelines can be built and documented using Microsoft Fabric while maintaining version control using Git.

It is designed as a portfolio project to showcase data engineering skills including data ingestion, pipeline orchestration, and lakehouse architecture.
