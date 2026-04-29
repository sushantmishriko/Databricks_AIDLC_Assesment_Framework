# Quick Start Guide: DE Skill File Generator

## 5-Minute Quick Start

### Step 1: Open the Generator Notebook
Navigate to:
```
Databricks_AIDLC_Assesment_Framework/Gennie_code_skill_files_framework/Skill_File_Generator
```

### Step 2: Run Initialization Cells
Execute cells 1-4 in sequence:
- Cell 1: Framework overview (markdown)
- Cell 2: Load dependencies
- Cell 3: Load DE feature catalog (16 features)
- Cell 4: Create interactive widgets

### Step 3: Configure Your Skill File
Use the widgets that appear above the notebook to configure:

| Widget | Example Value | Description |
|--------|--------------|-------------|
| **1. Select DE Feature** | `auto-loader` | Choose from 16 DE features |
| **2. Target Environment** | `prod` | dev, test, prod, or all_sdlc |
| **3. Target Catalog** | `main` | Your Unity Catalog name |
| **4. Target Schema** | `bronze` | Schema for code examples |
| **5. Output Directory** | `/Users/you@company.com/.assistant/skills` | Where to save |
| **6. Additional Context** | `For AWS S3 ingestion` | Optional notes |
| **7. Include Code Examples** | `true` | Include code snippets |
| **8. Include Best Practices** | `true` | Include guidance |

### Step 4: Generate the Skill File
Run Cell 6 to generate and save the skill file.

**Output**: A complete SKILL.md file at:
```
<output_path>/<feature-name>/SKILL.md
```

### Step 5: Review and Use
1. Navigate to the output location
2. Review the generated SKILL.md file
3. Copy to your Genie Code skills directory
4. Use in Genie Code conversations!

---

## Example Use Cases

### Use Case 1: Generate Auto Loader Skill for Production

**Configuration**:
```
DE Feature: auto-loader
Environment: prod
Catalog: prod_catalog
Schema: bronze
Output: /Users/john.doe@company.com/.assistant/skills
```

**Result**: Production-ready Auto Loader skill with:
- S3/ADLS/GCS code examples
- Schema evolution handling
- Production monitoring guidance
- Error handling patterns

### Use Case 2: Create Complete SDLC Pipeline Skills

Generate skills for all environments:

1. **Bronze Layer - Auto Loader**
   - Feature: `auto-loader`
   - Environment: `all_sdlc`
   - Output: Bronze ingestion skill with dev/test/prod guidance

2. **Silver Layer - CDC**
   - Feature: `change-data-capture`
   - Environment: `all_sdlc`
   - Output: CDC processing skill for data cleansing

3. **Gold Layer - Batch Processing**
   - Feature: `batch-processing`
   - Environment: `all_sdlc`
   - Output: Aggregation skill for business metrics

### Use Case 3: Observability & Testing

Generate operational skills:

```
Feature: monitoring-observability
Environment: prod
→ Generates monitoring skill with alerting patterns

Feature: testing-framework
Environment: test
→ Generates testing skill with pytest examples

Feature: error-handling-recovery
Environment: prod
→ Generates error handling skill with retry logic
```

---

## Generated Skill File Preview

When you run the generator, here's what you get:

```markdown
# Auto Loader
**Category:** Ingestion
**Generated:** 2026-04-28 10:30:00
**Environment:** prod

## Overview
Incrementally and efficiently load new data from cloud storage with schema evolution

## When to Use This Skill
* Ingesting files from S3/ADLS/GCS
* Handling schema evolution automatically
* Processing JSON, CSV, Parquet, Avro files
* Incremental file processing
* Bronze layer ingestion in medallion architecture

## Code Examples

### Example 1: Python Auto Loader
```python
from pyspark.sql import functions as F

df = (spark.readStream
    .format("cloudFiles")
    .option("cloudFiles.format", "json")
    .option("cloudFiles.schemaLocation", "/checkpoints/schema")
    .load("s3://bucket/path")
)

df.writeStream.table("main.bronze.raw_events")
```

## Best Practices
* Always specify schemaLocation for schema evolution tracking
* Add metadata columns for audit trail
* Monitor schema evolution events
...
```

---

## Common Workflows

### Workflow 1: New Pipeline Development

1. **Generate base skills** (Day 1):
   ```
   auto-loader → Bronze ingestion
   change-data-capture → Silver transformation
   batch-processing → Gold aggregation
   ```

2. **Add quality & monitoring** (Day 2):
   ```
   data-quality → Validation rules
   monitoring-observability → Metrics & alerts
   ```

3. **Setup SDLC** (Day 3):
   ```
   dev-test-prod-workflow → Environment management
   cicd-deployment → Automated deployment
   testing-framework → Unit & integration tests
   ```

### Workflow 2: Performance Optimization

1. **Generate optimization skills**:
   ```
   delta-optimization → Table optimization
   performance-tuning → Query tuning
   incremental-processing → Efficient processing
   ```

2. **Apply to existing pipelines**
3. **Measure improvements**
4. **Update runbooks**

### Workflow 3: Governance & Compliance

1. **Generate governance skills**:
   ```
   unity-catalog-governance → Access control
   ```

2. **Implement policies**:
   - Row-level security
   - Column masking for PII
   - Tag-based access control

3. **Audit and monitor**

---

## Pro Tips

### Tip 1: Generate All Skills at Once
Create a script to generate all 16 skills:

```python
features = [
    "lakeflow-spark-declarative-pipelines",
    "auto-loader",
    "change-data-capture",
    "delta-optimization",
    "monitoring-observability",
    "testing-framework",
    "cicd-deployment",
    "streaming-processing",
    "batch-processing",
    "medallion-architecture",
    "unity-catalog-governance",
    "performance-tuning",
    "error-handling-recovery",
    "incremental-processing",
    "dev-test-prod-workflow"
]

for feature in features:
    # Set widget value
    dbutils.widgets.remove("de_feature")
    dbutils.widgets.dropdown("de_feature", feature, [feature])
    # Run generation cell
    # (Cell 6 code here)
```

### Tip 2: Customize for Your Tech Stack

Add your company-specific details:
- Cloud provider (AWS/Azure/GCP)
- Naming conventions
- Security requirements
- Team contacts

### Tip 3: Version Control Your Skills

```bash
git init
git add skills/
git commit -m "Generated DE skills v1.0"
```

### Tip 4: Regular Updates

Schedule quarterly reviews:
- Update for new Databricks features
- Incorporate team feedback
- Refresh code examples
- Update best practices

---

## Troubleshooting Quick Reference

| Issue | Solution |
|-------|----------|
| Widgets not appearing | Re-run Cell 4 |
| Empty output file | Check catalog/schema exist |
| Permission denied | Verify output path permissions |
| Feature not in dropdown | Re-run Cell 3 to reload catalog |
| Code has placeholders | Set catalog/schema widgets |

---

## Next Steps

After generating your first skill file:

1. ✅ Review the output SKILL.md file
2. ✅ Test code examples in a notebook
3. ✅ Copy to Genie Code skills directory
4. ✅ Use in Genie Code: "Load the auto-loader skill"
5. ✅ Iterate based on results

**Happy skill generation! 🚀**
