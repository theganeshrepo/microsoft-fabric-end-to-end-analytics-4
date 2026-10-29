# Fabric Warehouse

## Warehouse

The project uses a Microsoft Fabric Warehouse to maintain the control information required for incremental data loading.

## Watermark / Control Table

The Warehouse contains a maintain/control table that stores the latest successfully processed `LastModifiedDate` for each configured source entity.

This allows the pipeline to determine which records need to be processed during the next execution.

## Incremental Loading Flow

```text id="a4nq7x"
Fabric Warehouse
      ↓
Read Previous Watermark
      ↓
Filter Source Data
      ↓
Load New / Modified Records
      ↓
Successful Load
      ↓
Update Watermark
```

## Purpose

Using a Warehouse control table provides:

- Centralized watermark management
- Incremental processing
- Reduced unnecessary data movement
- Reliable tracking of successful processing
- Support for repeatable pipeline executions

The Warehouse is used as the control layer for the project's incremental ingestion process.