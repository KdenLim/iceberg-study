# Directions

To start up the different containers individually.

spark 3.3 with jupyter notebook

The notebook image builds locally for your machine's architecture, including
ARM64 on Apple Silicon. It uses Spark 3.3.1, Python 3.10, and Java 11.

```
docker compose up --build notebook
```

To print the notebook URL and login token:

```
docker compose exec notebook jupyter notebook list
```

minio (s3-compatible storage layer)

```
docker-compose up minio
```

nessie (transactional catalog for Apache Iceberg)

```
docker-compose up nessie
```

Dremio (data lakehouse platform (query engine, access layer, more))

```
docker-compose up dremio
```

There are three folders in this repo mapped specifically to the spark/notebook container which are:

- `datasets` use this for any sample datasets
- `notebooks` for storing notebooks
- `warehouse` to be used as a warehouse for written data

[Find Guides and Tutorials Here](https://github.com/developer-advocacy-dremio/quick-guides-from-dremio)
