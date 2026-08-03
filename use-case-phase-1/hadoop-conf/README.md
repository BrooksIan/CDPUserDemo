# Hadoop client configuration for CAI Workbench HDFS CLI

Place (or keep) the cluster client configs downloaded from Cloudera Manager here:

- `core-site.xml` (required)
- `hdfs-site.xml` (required)
- `ssl-client.xml` (recommended for TLS clusters)
- `log4j.properties` (optional; silences the incomplete-conf warning)

The Getting Started notebook sets `HADOOP_CONF_DIR` to this directory before running `hdfs dfs`.

Replace these files if you point at a different CDP environment.
