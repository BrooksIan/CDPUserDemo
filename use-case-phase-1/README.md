# Phase 1 Use Case — Data Deduplication Lab

CDP user demo materials for Phase 1: prepare sample customer data in Cloudera AI Workbench, deduplicate it with Spark, publish results to a shared CDW warehouse, and verify in Hue.

## Objective

Walk through an end-to-end deduplication flow:

1. Set up a local Spark session and copy sample data to HDFS
2. Remove exact duplicate records
3. Persist results (local Iceberg and/or shared Hive / CDW)
4. Confirm outputs in Hue (File Browser and Table Browser)

## Structure

```
use-case-phase-1/
├── README.md           # This overview
├── hueview.md          # Notebook → Hue verification guide
├── requirements.txt    # Python deps for CAI Workbench sessions
├── data/               # Sample CSVs (redundant customer rows)
├── hadoop-conf/        # Cluster client XML for hdfs dfs / kinit
└── notebooks/          # Lab notebooks (run in order)
```

| Path | Purpose |
|------|---------|
| [`notebooks/`](./notebooks/) | Getting Started, dedup, and Iceberg / Hue publish exercises |
| [`data/`](./data/) | Sample inputs (`redundant_data.csv`, larger variant) |
| [`hadoop-conf/`](./hadoop-conf/) | Hadoop / Kerberos client config for HDFS CLI |
| [`hueview.md`](./hueview.md) | Steps to verify notebook outputs in Hue |
| [`requirements.txt`](./requirements.txt) | Session package install list |

## Lab flow

| Order | Notebook / doc | What you do |
|------:|----------------|-------------|
| 0 | [`notebooks/00_Getting_Started.ipynb`](./notebooks/00_Getting_Started.ipynb) | Install deps, local Spark, `kinit`, copy CSV to HDFS `/tmp` |
| 1 | [`notebooks/01_Basic_Deduplication.ipynb`](./notebooks/01_Basic_Deduplication.ipynb) | Exact record-level dedup; write results under `/tmp` |
| 2 | [`notebooks/02_Iceberg_REST_Catalog.ipynb`](./notebooks/02_Iceberg_REST_Catalog.ipynb) | Local Iceberg (optional) + publish shared table for Hue |
| 3 | [`hueview.md`](./hueview.md) | Browse HDFS file and query `cdp_user_demo.*_shared` in Hue |

## Prerequisites

- Cloudera AI Workbench session with PySpark and `hdfs` / `kinit` client tools
- Project client XML in [`hadoop-conf/`](./hadoop-conf/) (see that folder’s README)
- Kerberos identity configured in the Getting Started environment cell
- Permission to write HDFS `/tmp`
- For Hue / shared tables: a running CDW Hive Virtual Warehouse and a working CAI Hive Data Connection

## Getting started

1. Open a CAI Workbench session in this project.
2. Run notebooks under [`notebooks/`](./notebooks/) in order, starting with `00_Getting_Started.ipynb`.
3. After HDFS copy and/or shared publish, follow [`hueview.md`](./hueview.md) to verify in Hue.

## Notes

- Local CAI `/tmp` Parquet and local Iceberg warehouses are **not** visible in Hue.
- Hue sees cluster HDFS (for example `/tmp/redundant_data.csv`) and tables registered in the shared Hive Metastore / CDW (for example `cdp_user_demo.deduped_customers_shared`).
