# Azure Data Factory Assignment

## Overview
This project demonstrates an end-to-end data engineering pipeline using Azure Data Factory, Azure Data Lake Storage Gen2, and Azure Databricks.

The project involves ingesting, transforming, and integrating customer, product, store, and sales data using the Medallion Architecture.

## Technologies Used
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- PySpark
- SQL
- Delta Lake
- Unity Catalog

## Project Structure

```text
ADF-Assignment/
│
├── src/
│   └── ADF_Assignment - Sadanand.pdf
└── README.md
```

## Implementation

**1. Azure Data Factory**
- Created a parameterized pipeline.
- Identified the latest modified files using Get Metadata and ForEach.
- Copied files into the Bronze layer.

**2. Bronze Layer**
- Stored raw customer, product, store, and sales data.

**3. Silver Layer**
- Applied data cleaning and transformations using PySpark.
- Standardized column names.
- Implemented business transformations.
- Used SQL MERGE for upsert operations.

**4. Gold Layer**
- Integrated Product, Store, and Customer Sales data.
- Applied UDF functions.
- Created the final `StoreProductSalesAnalysis` Delta dataset using overwrite mode.

## Databricks Notebooks
- `bronze_to_silver` – Data transformation and Silver layer loading.
- `silver_to_gold` – Data integration and Gold layer creation.

## Final Output

```text
gold/sales_view/StoreProductSalesAnalysis
```

The final output is a consolidated sales analysis dataset stored in Delta format.
