# Notebooks

This directory contains all Databricks notebooks used to build the Azure Databricks Retail Lakehouse project.

The notebooks are organized according to the Medallion Architecture (Bronze → Silver → Gold) and grouped by business domain.

## Folder Structure

```text
notebooks/
│
├── aggregates/
│   └── daily_order_summary
│
├── dimensions/
│   ├── dim_bronze
│   ├── dim_silver
│   └── dim_gold
│
├── facts/
│   ├── fact_order_items_bronze
│   ├── fact_order_items_silver
│   └── fact_order_items_gold
│
├── monthly_facts/
│   ├── returns_shipment_fact_bronze
│   ├── returns_shipment_fact_silver
│   ├── returns_shipment_fact_gold
│
└── setup/
    ├── setup_catalog
    └── setup_raw_external_volume
```

---

## Setup

The setup notebooks configure the environment required for the project.

### Setup Catalog

Creates and configures the catalog, schemas, and storage locations used throughout the lakehouse.

### Setup Raw External Volume

Registers external storage locations and enables access to source files stored in Azure Data Lake Storage Gen2.

---

## Dimensions

Processes master data entities through Bronze, Silver, and Gold layers.

### Bronze Layer

Ingests raw dimension data from ADLS using Auto Loader and stores it as Delta tables.

Dimension tables:

* Brands
* Categories
* Products
* Customers
* Calendar

### Silver Layer

Applies data cleansing and standardization rules including:

* Duplicate removal
* Data type corrections
* Text standardization
* Null handling
* Business rule validation

### Gold Layer

Creates business-ready dimension tables for reporting and analytics.

Gold dimensions:

* Product Dimension
* Customer Dimension
* Date Dimension

---

## Facts

Contains the primary transactional sales pipeline.

### Order Items Bronze

Loads raw order item transactions using Auto Loader with checkpointing and schema evolution.

### Order Items Silver

Performs cleansing, standardization, deduplication, and incremental upserts using Delta MERGE.

### Order Items Gold

Creates analytics-ready sales facts and business KPIs including:

* Gross Amount
* Discount Amount
* Net Amount
* Coupon Flag
* Date ID

---

## Monthly Facts

Contains pipelines that process datasets received on a monthly basis.

### Returns Pipeline

Processes return transactions through Bronze, Silver, and Gold layers.

Business metrics include:

* Return Days
* Within Policy Flag
* Late Return Flag

### Shipments Pipeline

Processes shipment transactions through Bronze, Silver, and Gold layers.

Business metrics include:

* Carrier Group
* Weekend Shipment Flag
* Date ID

---

## Aggregates

### Daily Order Summary

Creates a business-facing aggregate table used for reporting and dashboarding.

Metrics include:

* Total Quantity
* Total Gross Amount
* Total Discount Amount
* Total Tax Amount
* Total Amount

The aggregation uses a rolling 30-day incremental recalculation strategy to improve processing efficiency.

---

## Key Technologies Used

* Azure Databricks
* Delta Lake
* Unity Catalog
* Auto Loader (CloudFiles)
* Structured Streaming
* Delta MERGE
* Change Data Feed (CDF)
* ADLS Gen2
* Spark SQL
* Checkpointing
* AvailableNow Trigger
* Schema Evolution

