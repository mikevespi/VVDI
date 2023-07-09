# VVDI

A testing playground for verified, versioned data ingestion.

## Tools

### LakeFS

https://lakefs.io/
A git-like version control system for data.

port-forward 8000

### Postgres

https://www.postgresql.org/
LakeFS uses a postgres database to store it's working data (branching data etc.).

### MinIO

https://min.io/
MinIO provides S3 compatible local storage to act as the data store lakefs is managing. To point this demo at an existing S3 instance, simply change the `blockstore` values the lakefs config found in `helm/lakefs-ecosystem/values.yaml` `lakefs-instance.lakefsConfig`.

To port-forward this, sometimes you need to restart it quickly so run `while true; do kubectl port-forward pod/minio 9000 9090; done` and if it gets hung up logging in, just ctrl-c the port forward and it'll restart.

### duckDB

https://duckdb.org/
DuckDB is an in-process. SQL OLAP database management system.

The bundle used in this repo was found [here](https://abcabhishek.substack.com/p/duckdb-bundle-on-kubernetes).
