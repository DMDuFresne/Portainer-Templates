# QuestDB Docker Compose Setup

This repository contains a Docker Compose configuration for running [QuestDB](https://questdb.io/), a high-performance SQL database designed for time series data, using Docker.

## Website

Visit the [QuestDB website](https://questdb.io/) for detailed documentation, features, and community resources.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/questdb/questdb).

## Environment Variables

The following environment variables are used in this Compose file:

- **QUESTDB_TAG**  
  Specifies the version tag of the QuestDB image.  
  *Default*: `latest`

- **QUESTDB_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `questdb`

- **QUESTDB_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `questdb`

- **QUESTDB_WEB_PORT**  
  Maps the host port to the QuestDB web interface port (`9000`) in the container.  
  *Default*: `9000`

- **QUESTDB_INGEST_PORT**  
  Maps the host port to the QuestDB ingest port (`9009`) in the container.  
  *Default*: `9009`

- **QUESTDB_POSTGRES_PORT**  
  Maps the host port to the QuestDB PostgreSQL wire protocol port (`8812`) in the container.  
  *Default*: `8812`

## Volumes and Networks

The Compose file also defines a persistent volume and uses an external network for container connectivity:

- **Volume:**
  - `questdb-data` (mounted at `/root/.questdb`)

- **Network:**
  - `portainer-network` (external)
