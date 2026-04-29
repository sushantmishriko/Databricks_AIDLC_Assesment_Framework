# Auto Loader

**Category:** Data Ingestion  
**Generated:** 2026-04-28 12:00:00  
**Environment:** prod

---

## Overview

Auto Loader incrementally and efficiently loads new data from cloud storage with automatic schema evolution.

## When to Use This Skill

* Ingest files from S3/ADLS/GCS cloud storage
* Handle schema evolution automatically
* Process JSON, CSV, Parquet, Avro files incrementally
* Build bronze layer ingestion in medallion architecture

## Code Examples

### Python Auto Loader with Schema Evolution

```python
from pyspark.sql import functions as F

df = (spark.readStream
    .format("cloudFiles")
    .option("cloudFiles.format", "json")
    .option("cloudFiles.schemaLocation", "/checkpoints/schema")
    .option("cloudFiles.inferColumnTypes", "true")
    .load("s3://bucket/data/")
    .withColumn("ingestion_timestamp", F.current_timestamp())
)

df.writeStream.table("main.bronze.raw_events")
```

### SQL Auto Loader

```sql
CREATE OR REFRESH STREAMING TABLE main.bronze.raw_events
AS SELECT *, current_timestamp() as ingestion_timestamp
FROM cloud_files("s3://bucket/data/", "json")
```

## Best Practices

* Always specify schemaLocation for schema evolution tracking
* Add metadata columns for audit trail
* Use inferColumnTypes for better type inference
* Monitor schema evolution events
* Enable rescue column for malformed records

## SDLC Considerations

### Development
* Use small sample datasets
* Test schema evolution scenarios
* Validate rescue column behavior

### Production
* Enable monitoring and alerting
* Configure cloud notifications for low latency
* Set appropriate retention policies

## Related Skills

* medallion-architecture
* streaming-processing
* error-handling-recovery
