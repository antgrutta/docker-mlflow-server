# MLFlow Server Docker Deployments

This repository contains a Docker Compose file for MLFlow Server. The compose file will deploy Minio as the S3 storage backend and configure MLFlow to use SQLite as the tracking database. All data will be stored in the `./data` directory.

## Prerquisites

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Customize the environment

The `.env.sample` file contains the sample environment variables for the MLFlow server. It is recommended that you copy the `.env.sample` file to `.env` and customize the environment variables. The following variables are available:

| Variable              | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| AWS_ACCESS_KEY_ID     | AWS access key ID which Minio will set                       |
| AWS_SECRET_ACCESS_KEY | AWS secret access key which Minio will set                   |
| AWS_BUCKET            | AWS S3 bucket name, the bucket will be auto-created by Minio |

## Run the MLFlow server using Docker Compose

```base
docker-compose up --env-file .env up
```

## Access the MLFlow server UI

The MLFlow server UI is available at `http://localhost:5000`

## References

- [Deploy MLflow with docker compose](https://towardsdatascience.com/deploy-mlflow-with-docker-compose-8059f16b6039)
