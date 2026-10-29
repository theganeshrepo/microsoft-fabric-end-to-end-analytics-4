# E-Commerce End-to-End Analytics | Microsoft Fabric

## Project Overview

End-to-end E-Commerce analytics solution built using Microsoft Fabric to ingest, transform, model, and analyze customer, order, payment, support, and web activity data.

The solution uses Microsoft Fabric components including Lakehouse, Data Factory Pipelines, PySpark, Fabric Warehouse, SQL Analytics Endpoint, and Power BI Semantic Models.

## Architecture

**Source Data → Incremental Pipeline → Lakehouse → PySpark Transformations → Curated Data → Warehouse / SQL → Power BI Semantic Models → Reports**

### Microsoft Fabric Components

- **Data Factory Pipeline** – orchestrates data ingestion and incremental loading.
- **Fabric Lakehouse** – stores Bronze, Silver, and Gold data layers.
- **PySpark Notebook** – performs data cleansing, validation, transformation, and business logic.
- **Fabric Warehouse** – maintains incremental-load watermark/control information.
- **SQL Analytics Endpoint** – enables SQL-based analysis of Lakehouse data.
- **Power BI Semantic Models** – Customer 360 and Customer Life Cycle analytical models.

## Incremental Loading

Incremental ingestion is implemented using `LastModifiedDate` as the watermark column.

The pipeline:

1. Reads the previous watermark from the control table in Fabric Warehouse.
2. Identifies new or modified source records.
3. Processes the required entities through the pipeline.
4. Loads the data into the Fabric Lakehouse.
5. Updates the watermark after successful processing.

## Lakehouse Data Layers

The project uses a single Fabric Lakehouse with logical Medallion Architecture layers:

- **Bronze** – raw/source data
- **Silver** – cleansed and transformed data
- **Gold** – curated business-ready data

### Key Tables

- Customers
- Orders
- Payments
- Support Tickets
- Web Activities
- Silver customer/order/payment/support/web activity tables
- Gold Customer 360 table

## Power BI

Two semantic models are developed for analytics:

- **Customer 360**
- **Customer Life Cycle**

These models provide business-ready data for customer analysis, behavior analysis, and lifecycle reporting.

## Repository Structure

```text
├── README.md
├── docs/
│   ├── architecture/
│   ├── data-model/
│   └── incremental-loading/
├── fabric/
│   ├── lakehouse/
│   ├── pipelines/
│   ├── notebooks/
│   └── warehouse/
├── powerbi/
│   └── semantic-models/
│       ├── customer-360/
│       └── customer-life-cycle/
├── sql/
└── screenshots/
```

## Key Skills Demonstrated

**Microsoft Fabric | Lakehouse | Medallion Architecture | Data Factory | Incremental Loading | PySpark | Fabric Warehouse | SQL | SQL Analytics Endpoint | Power BI | Semantic Modeling | Customer 360 | Customer Lifecycle Analytics**