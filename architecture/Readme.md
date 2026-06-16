# Architecture

This folder contains the architecture diagrams used to illustrate the design, data flow, and processing layers of the Azure Databricks Retail Lakehouse project.

## Diagrams

### architecture.png

(architecture)[architecture.png]

Provides a high-level overview of the end-to-end solution architecture.

The diagram shows how raw e-commerce data is ingested from source files stored in Azure Data Lake Storage Gen2 (ADLS Gen2), processed through Azure Databricks using the Medallion Architecture, and delivered to Power BI for analytics and reporting.

Key components include:

* Data Sources
* Azure Data Lake Storage Gen2
* Azure Databricks
* Bronze Layer
* Silver Layer
* Gold Layer
* Power BI

---

### medallion_architecture.png

Illustrates the Medallion Architecture implemented in the project.

The diagram highlights the flow of data through the three processing layers:

#### Bronze Layer

* Raw data ingestion
* Metadata tracking
* Historical and incremental file processing

#### Silver Layer

* Data cleansing
* Standardization
* Deduplication
* Data quality validation

#### Gold Layer

* Business-ready dimensions
* Analytics-ready fact tables
* KPI generation
* Reporting datasets

This architecture enables scalable and maintainable data processing while preserving data lineage across the platform.

---

### dataflow.png

Provides a business-oriented view of the data pipeline.

The diagram demonstrates how operational e-commerce datasets such as products, customers, orders, shipments, and returns are transformed into curated analytical datasets and business insights.

The flow covers:

* Source Data
* Data Processing
* Business Data Models
* Reporting Layer
* Analytics & Insights

This view helps connect the technical implementation to the business outcomes delivered by the platform.

---

## Purpose

These diagrams collectively provide three perspectives of the project:

1. **Solution Architecture** – What was built.
2. **Medallion Architecture** – How the data is processed.
3. **Business Data Flow** – How raw data becomes actionable insights.

Together they provide a complete overview of the platform's design and data engineering workflow.
