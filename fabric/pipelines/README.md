# Fabric Data Pipeline

## Pipeline

The project uses a Microsoft Fabric Data Factory pipeline named `E_Commerce`.

The pipeline is responsible for orchestrating **incremental data ingestion** from source systems into the Fabric Lakehouse.

## Pipeline Flow

```text
Source
  ↓
Get Metadata
  ↓
ForEach
  ↓
Copy Data
  ↓
Lakehouse
  ↓
Update Watermark
```

## Incremental Loading

The pipeline uses `LastModifiedDate` as the watermark column.

The previous successful watermark is maintained in a control table in the **Fabric Warehouse**.

During execution:

1. The pipeline reads the previous watermark.
2. Source records are filtered using `LastModifiedDate`.
3. New or modified records are processed.
4. Data is loaded into the Lakehouse.
5. The watermark is updated after successful processing.

This approach avoids reprocessing the complete source dataset during every pipeline execution.

## Pipeline Components

### Get Metadata

Used to retrieve metadata required for pipeline processing.

### ForEach

Iterates through the configured entities/tables and processes them dynamically.

### Copy Data

Transfers the required source data into the Fabric Lakehouse.

## Key Capability

The pipeline demonstrates:

- Incremental data loading
- Watermark-based processing
- Metadata-driven processing
- Pipeline orchestration
- Dynamic table processing
- Integration between Fabric Warehouse and Lakehouse