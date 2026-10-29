# PySpark Notebook

## Notebook

The project uses a Microsoft Fabric notebook named `E_Comm_Notebook`.

PySpark is used to process and transform data within the Lakehouse.

## Processing Flow

```text
Silver Data
    ↓
PySpark Transformations
    ↓
Data Cleansing & Validation
    ↓
Business Transformations
    ↓
Gold Data
```

## Key Processing Activities

- Data cleansing and validation
- Data type handling
- Transformation of source attributes
- Business-rule implementation
- Creation of curated analytical datasets
- Preparation of data for downstream semantic models

## Output

The notebook contributes to the curated Gold layer, including the:

- `gold_customer360` table

The transformed data is then consumed by downstream Power BI semantic models for customer analytics.