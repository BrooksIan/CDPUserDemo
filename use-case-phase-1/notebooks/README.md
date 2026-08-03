# Phase 1 Notebooks

Jupyter notebooks for the Phase 1 CDP deduplication lab. Run them in a Cloudera AI Workbench session, in order.

![Notebooks in CAI session](../images/NoteBooksInSession.png)

## Run order

| Order | Notebook | Purpose |
|------:|----------|---------|
| 0 | [`00_Getting_Started.ipynb`](./00_Getting_Started.ipynb) | Install deps, local Spark, `kinit`, copy sample CSV to HDFS `/tmp` |
| 1 | [`01_Basic_Deduplication.ipynb`](./01_Basic_Deduplication.ipynb) | Exact record-level dedup; write results under `/tmp` |
| 2 | [`02_Iceberg_REST_Catalog.ipynb`](./02_Iceberg_REST_Catalog.ipynb) | Optional local Iceberg + publish shared table for Hue |

## Before you start

1. Create a JupyterLab session from the project (see the [Phase 1 README](../README.md) screenshots).
2. Open this `notebooks/` folder in the session file browser.
3. For Exercise 2 shared publish: copy the CDW Hive JDBC URL and optionally generate a Knox/CDP JWT, then complete Step 0 in `02_Iceberg_REST_Catalog.ipynb`.

## After the notebooks

Verify HDFS and shared tables in Hue with [`../hueview.md`](../hueview.md).
