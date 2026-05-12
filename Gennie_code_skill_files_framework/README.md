# Data Engineering Skill File Generator Framework

## Overview

This framework provides a **reusable, enterprise-grade system** for generating Genie Code skill files tailored to professional data engineering needs. It covers the complete spectrum of data engineering capabilities with **special emphasis on Medallion Architecture (Bronze/Silver/Gold)** and real-world enterprise workflows.

### Core Capabilities

- **Medallion Architecture** - Complete Bronze/Silver/Gold layer patterns and best practices
- **Project Planning** - Requirements discovery, table analysis, architecture design
- **Pipeline Creation** - Lakeflow Spark Declarative Pipelines, streaming, batch processing
- **Data Ingestion** - Auto Loader, CDC, advanced file format readers (including STTM)
- **Data Quality** - Expectations, validation, monitoring
- **Performance** - Delta optimization, query tuning, caching
- **Governance** - Unity Catalog, access control, lineage
- **Operations** - End-to-end observability, monitoring, error handling
- **Deployment** - Databricks Asset Bundles (DABs), CI/CD, multi-environment management
- **Applications** - Lakehouse Apps, common notebooks, reusable utilities

## Framework Components

### 1. Skill_File_Generator Notebook
Interactive notebook with user-friendly widgets for:
- Selecting DE features to generate skill files for
- Configuring target environments (dev/test/prod/SDLC)
- Specifying catalog and schema for code examples
- **Medallion layer selection** (Bronze/Silver/Gold specific patterns)
- Customizing output with additional context
- Controlling inclusion of code examples and best practices

### 2. DE Feature Catalog (de_feature_catalog.json)
Comprehensive JSON metadata for **22 data engineering features**:
- Feature descriptions and use cases
- Configuration parameters
- Code templates (Python & SQL)
- Best practices
- SDLC considerations
- Medallion layer integration
- Related features for cross-referencing

### 3. SkillFileGenerator Class
Python class that generates professional SKILL.md files with:
- Feature overview and purpose
- When to use this skill
- Prerequisites checklist
- **Layer-specific patterns** (Bronze/Silver/Gold)
- Code examples (Python/SQL)
- Configuration parameters table
- Best practices guidance
- Common patterns
- Troubleshooting tips
- SDLC-specific considerations
- References and related skills

## Getting Started

### Quick Start Guide

1. **Open the Generator Notebook**
   ```
   /Users/sushant.mishriko@tigeranalytics.com/Databricks_AIDLC_Assesment_Framework/Gennie_code_skill_files_framework/Skill_File_Generator
   ```

2. **Run Cells 1-4** to initialize the framework and create widgets

3. **Configure Your Requirements** using the widgets:
   - **Feature**: Select from 22 available DE features
   - **Environment**: Choose dev, test, prod, or all_sdlc
   - **Catalog/Schema**: Specify your Unity Catalog target
   - **Layer Context**: Bronze/Silver/Gold context for medallion patterns
   - **Output Path**: Where to save generated skill files
   - **Options**: Include code examples and best practices

4. **Run Cell 6** to generate and save the skill file

5. **Review Output**: The generated SKILL.md file is created at:
   ```
   <output_path>/<feature-name>/SKILL.md
   ```

### Example Workflow

```python
# Widget Configuration Example
de_feature = "medallion-layer-patterns"
environment = "prod"
target_catalog = "prod_catalog"
target_schema = "bronze"  # or silver, gold
output_path = "/Users/your_name@company.com/.assistant/skills"
include_code_examples = "true"
include_best_practices = "true"
```

Result: Generates comprehensive Bronze/Silver/Gold pattern skill file at:
```
/Users/your_name@company.com/.assistant/skills/medallion-layer-patterns/SKILL.md
```

## Available Data Engineering Features (22 Total)

### 🏗️ Architecture & Planning (2 features)
1. **Requirements & Discovery** ⭐ NEW
   - Understand business requirements
   - Discover and analyze existing tables/schemas
   - Map requirements to technical architecture
   - Create data flow diagrams
   
2. **Medallion Layer Patterns (Bronze/Silver/Gold)** ⭐ ENHANCED
   - Bronze layer raw ingestion patterns
   - Silver layer cleansing and conforming
   - Gold layer business metrics
   - Layer-to-layer best practices
   - End-to-end medallion implementation

### 🔄 Pipeline & Processing (3 features)
3. **Lakeflow Spark Declarative Pipelines (SDP)**
   - Streaming tables and materialized views
   - Data quality expectations
   - Multi-hop architecture support
   
4. **Streaming Data Processing**
   - Real-time analytics with Structured Streaming
   - Windowing and watermarks
   - Stateful transformations
   
5. **Batch Data Processing**
   - Scheduled batch jobs
   - Incremental processing patterns
   - Partition-based processing

### 📥 Data Ingestion (4 features)
6. **Auto Loader**
   - Cloud storage ingestion (S3/ADLS/GCS)
   - Automatic schema evolution
   - Multi-format support

7. **Advanced File Format Readers** ⭐ NEW
   - Custom/proprietary format parsing
   - STTM file reader patterns
   - Multi-line JSON/XML handling
   - Complex nested structures

8. **Change Data Capture (CDC)**
   - Apply changes API
   - SCD Type 1 & 2 support
   - Real-time data synchronization

9. **Incremental Processing Patterns**
   - Timestamp-based incremental loads
   - Change Data Feed
   - Partition-based strategies

### ✅ Data Quality & Governance (2 features)
10. **Data Quality & Expectations**
    - Validation rules and data contracts
    - Quality metrics tracking
    - Failed records handling

11. **Unity Catalog Governance**
    - Fine-grained access control
    - Row filters and column masks
    - Tag-based policies (ABAC)
    - Data lineage tracking

### ⚡ Performance & Optimization (2 features)
12. **Delta Lake Optimization**
    - OPTIMIZE with Z-ORDER
    - VACUUM for storage reclamation
    - Auto-optimize configuration

13. **Performance Tuning**
    - Query optimization techniques
    - Caching strategies
    - Cluster right-sizing

### 📊 Operations & Observability (2 features)
14. **Monitoring & Observability**
    - Pipeline event logs
    - Data quality metrics
    - System tables queries
    - Alerting integration

15. **End-to-End Observability** ⭐ NEW
    - Complete pipeline visibility
    - Cross-layer monitoring
    - Cost and performance tracking
    - Data lineage visualization
    - Real-time dashboards

### 🔧 SDLC & Deployment (4 features)
16. **Testing Framework**
    - Unit and integration tests
    - Pytest fixtures
    - Pipeline testing patterns

17. **Databricks Asset Bundles (DABs)** ⭐ NEW
    - Infrastructure as Code
    - Multi-environment deployment
    - Configuration management
    - Version control integration

18. **CI/CD Deployment**
    - GitHub Actions / Azure DevOps
    - Automated deployment pipelines
    - Environment promotion

19. **Dev/Test/Prod Workflow**
    - Multi-environment management
    - Configuration parameterization
    - Environment promotion strategies

### 📱 Application Development (1 feature)
20. **Lakehouse Apps & Common Notebooks** ⭐ NEW
    - Streamlit/Dash app development
    - Reusable utility notebooks
    - Common DE libraries
    - Shared functions and patterns

### 🛠️ Error Handling & Reliability (2 features)
21. **Error Handling & Recovery**
    - Rescue columns for bad data
    - Retry logic with exponential backoff
    - Quarantine patterns
    - Circuit breakers

22. **Incremental Processing** (duplicate removed in count)

## 🏗️ Medallion Architecture Guide

### Why Bronze/Silver/Gold?

The medallion architecture provides a **structured approach** to data refinement:

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│    BRONZE    │ ──> │    SILVER    │ ──> │     GOLD     │
│  (Raw Data)  │     │  (Cleansed)  │     │ (Aggregated) │
└──────────────┘     └──────────────┘     └──────────────┘
```

### Bronze Layer (Landing Zone)
**Purpose**: Raw data ingestion with minimal transformation

**Patterns**:
- Auto Loader for cloud storage ingestion
- Preserve all source data including bad records
- Add metadata: ingestion_timestamp, source_file
- Schema evolution handling
- Append-only or snapshot strategies

**Example Use Cases**:
- Ingest JSON files from S3
- Stream data from Kafka
- Load CSV files from ADLS
- Capture database CDC feeds

### Silver Layer (Cleaned & Conformed)
**Purpose**: Validated, cleaned, and conformed data

**Patterns**:
- Type conversions and data cleansing
- Deduplication and filtering
- Data quality expectations (drop/quarantine invalid)
- Schema standardization
- Enrichment and joins

**Example Use Cases**:
- Clean and validate bronze data
- Apply business rules
- Merge multiple sources
- Implement SCD Type 2

### Gold Layer (Business Metrics)
**Purpose**: Business-level aggregations and KPIs

**Patterns**:
- Pre-computed aggregations
- Business metrics and KPIs
- Denormalized for reporting
- Optimized for BI tools
- Materialized views

**Example Use Cases**:
- Daily/monthly aggregations
- Customer 360 views
- Executive dashboards
- ML feature stores

### Layer-Specific Best Practices

| Aspect | Bronze | Silver | Gold |
|--------|--------|--------|------|
| **Schema** | Flexible, evolving | Standardized, enforced | Denormalized |
| **Quality** | Relaxed (warnings) | Strict (drop invalid) | Pre-validated |
| **Processing** | Append-only | Upserts/Merges | Aggregations |
| **Retention** | Long-term archive | Medium-term | Short-term cache |
| **Updates** | Immutable | Mutable (CDC) | Recomputed |
| **Consumers** | Internal pipelines | Data engineers | Business users |

## Professional Workflows

### Workflow 1: Complete Medallion Implementation

```
Day 1 - Planning & Discovery:
  ✓ Requirements & Discovery → Document requirements
  ✓ Unity Catalog Governance → Set up catalogs/schemas
  ✓ DABs → Initialize project structure

Day 2 - Bronze Layer:
  ✓ Auto Loader → Raw ingestion from S3/ADLS
  ✓ File Format Readers → Handle custom formats
  ✓ Error Handling → Rescue column setup
  ✓ Monitoring → Bronze layer metrics

Day 3 - Silver Layer:
  ✓ Data Quality → Define expectations
  ✓ CDC → Apply changes for updates
  ✓ Incremental Processing → Efficient processing
  ✓ Testing → Unit tests for transformations

Day 4 - Gold Layer:
  ✓ Batch Processing → Business aggregations
  ✓ Performance Tuning → Optimize queries
  ✓ Delta Optimization → OPTIMIZE and Z-ORDER

Day 5 - Operations:
  ✓ End-to-End Observability → Complete monitoring
  ✓ CI/CD → Automated deployment
  ✓ Lakehouse Apps → Build dashboards
```

### Workflow 2: Enterprise SDLC Setup

```
Setup Phase:
  ✓ DABs → Infrastructure as Code
  ✓ Dev/Test/Prod → Environment separation
  ✓ Unity Catalog → Catalog per environment
  ✓ Testing Framework → Test infrastructure

Development:
  ✓ Requirements Discovery → Gather requirements
  ✓ Medallion Patterns → Design layers
  ✓ Common Notebooks → Build utilities
  ✓ Local testing with sample data

Testing:
  ✓ Integration testing
  ✓ Data quality validation
  ✓ Performance benchmarking
  ✓ CI/CD automation

Production:
  ✓ Deployment via DABs
  ✓ End-to-End Observability
  ✓ SLA monitoring
  ✓ Incident response
```

## SDLC Integration Guide

### Development Environment (dev)
**Purpose**: Rapid iteration and feature development

**Configuration**:
```yaml
environment: dev
catalog: dev_catalog
schemas:
  bronze: dev_catalog.bronze
  silver: dev_catalog.silver
  gold: dev_catalog.gold
data_volume: sample datasets (< 100k records)
expectations: relaxed (warnings only)
monitoring: basic logging
```

**Best Practices**:
- Use small sample datasets for fast iteration
- Test all three layers (bronze/silver/gold)
- Relaxed data quality rules
- Frequent testing with quick feedback
- Local debugging and troubleshooting

### Test Environment (test)
**Purpose**: Integration testing and validation

**Configuration**:
```yaml
environment: test
catalog: test_catalog
schemas:
  bronze: test_catalog.bronze
  silver: test_catalog.silver
  gold: test_catalog.gold
data_volume: realistic (production-like)
expectations: enforced (drop invalid)
monitoring: comprehensive metrics
```

**Best Practices**:
- Full integration testing through all layers
- Realistic data volumes
- Performance benchmarking
- Data quality validation
- Failure scenario testing

### Production Environment (prod)
**Purpose**: Live production workloads

**Configuration**:
```yaml
environment: prod
catalog: prod_catalog
schemas:
  bronze: prod_catalog.bronze
  silver: prod_catalog.silver
  gold: prod_catalog.gold
data_volume: full production data
expectations: strict (fail on violations)
monitoring: real-time + alerting + observability
```

**Best Practices**:
- Strict data quality enforcement per layer
- Full end-to-end observability
- SLA tracking and alerting per layer
- Incident response procedures
- Change control processes
- DAB-based deployments

## Customization & Extension

### Adding New Features

1. **Update DE_FEATURE_CATALOG** in the notebook (Cell 3):
```python
DE_FEATURE_CATALOG["your-new-feature"] = {
    "name": "Your New Feature",
    "description": "Feature description",
    "category": "Category Name",
    "use_cases": [...],
    "parameters": {...},
    "code_templates": {...},
    "best_practices": [...],
    "sdlc_considerations": {...}
}
```

2. **Update de_feature_catalog.json** with the same structure

3. **Run the generator** to create skill files for your custom feature

### Modifying Templates

Edit the `SkillFileGenerator` class (Cell 5) to customize:
- Section structure
- Markdown formatting
- Code example presentation
- Best practices layout
- Medallion layer integration

### Environment-Specific Customization

Generate different skill files for each environment:
```python
# For development
environment = "dev"  # Includes dev-specific guidance

# For production  
environment = "prod"  # Includes prod-specific best practices

# For complete SDLC
environment = "all_sdlc"  # Includes guidance for all environments
```

## Integration with Genie Code

### Using Generated Skill Files

1. **Place skill files** in your Genie Code skills directory:
   ```
   ~/.assistant/skills/<feature-name>/SKILL.md
   ```

2. **Reference in Genie Code** conversations:
   ```
   "Load the medallion-layer-patterns skill for bronze layer ingestion"
   "Use the databricks-asset-bundles skill to deploy this pipeline"
   "Load requirements-discovery to analyze these tables"
   ```

3. **Genie Code automatically**:
   - Reads the SKILL.md file
   - Applies best practices
   - Uses code templates
   - Follows SDLC guidance
   - Implements layer-appropriate patterns

### Skill File Best Practices

- **One feature per skill file** - Keep skills focused
- **Include complete code examples** - Make them copy-paste ready
- **Add layer context** - Specify Bronze/Silver/Gold when relevant
- **Add SDLC considerations** - Environment-specific guidance
- **Update regularly** - Keep skills current with Databricks updates
- **Test generated skills** - Validate they work with Genie Code

## Troubleshooting

### Common Issues

**Issue**: Widget not showing all 22 features
**Solution**: Re-run Cell 3 to reload the feature catalog

**Issue**: Generated file is empty
**Solution**: Check output path permissions and verify catalog exists

**Issue**: Code examples have placeholder values
**Solution**: Ensure target_catalog and target_schema are set in widgets

**Issue**: Missing medallion layer patterns
**Solution**: Use "medallion-layer-patterns" feature for layer-specific guidance

**Issue**: DAB deployment fails
**Solution**: Validate databricks.yml syntax, check permissions

## Support & Contribution

### Getting Help
- Review generated skill files for examples
- Check de_feature_catalog.json for available features
- Consult Databricks documentation for feature details
- Review QUICKSTART.md for step-by-step guidance

### Contributing New Features
1. Fork the framework
2. Add new feature to DE_FEATURE_CATALOG
3. Include medallion layer context if applicable
4. Test skill file generation
5. Submit for team review

## License & Usage

This framework is designed for **internal company use** for generating data engineering skill files. Customize and extend as needed for your organization's requirements.

---

**Framework Version**: 2.0.0 (Enhanced with Medallion Architecture & Professional Workflows)  
**Last Updated**: 2026-04-28  
**Total Features**: 22 (6 new professional features)  
**Maintained By**: Tiger Analytics Team  
**Contact**: sushant.mishriko@tigeranalytics.com
