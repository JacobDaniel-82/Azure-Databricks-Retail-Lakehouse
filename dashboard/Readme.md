# Dashboards

This folder contains the reporting layer for the Azure Databricks Retail Lakehouse project.

The dashboard was built using Power BI and consumes analytics-ready datasets generated from the Gold layer of the lakehouse architecture.

![](/screenshots/dashboard.png)

## Dashboard Overview

The Power BI dashboard provides business insights based on curated dimension and fact tables, including:

* Product Analysis
* Customer Analysis
* Sales Performance
* Returns Analysis
* Shipment Analysis
* Daily Order Metrics

The dashboard is designed to demonstrate how data flows from raw source files through the Bronze, Silver, and Gold layers before being consumed by business users.

## Data Source

The dashboard is built on top of the Gold layer tables:

* gld_dim_products
* gld_dim_customers
* gld_dim_date
* gld_fact_order_items
* gld_fact_order_returns
* gld_fact_order_shipments
* gld_fact_daily_orders_summary

These tables contain cleansed, standardized, and business-ready data optimized for reporting and analytics.

## Power BI File

The original Power BI (.pbix) file is not included in this repository due to GitHub file size limitations.

Dashboard screenshots can be found in the `screenshots` folder.

## Purpose

The dashboard represents the final consumption layer of the project and demonstrates how the Azure Databricks Retail Lakehouse supports business reporting and decision-making through curated analytical datasets.
