# TimescaleDB Docker Compose Setup

This repository contains a Docker Compose configuration for running [TimescaleDB](https://www.timescale.com/), a time-series database optimized for fast ingest and complex queries, built as an extension to PostgreSQL, using Docker.

## Website

Visit the [TimescaleDB website](https://www.timescale.com/) for detailed documentation, features, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/timescale/timescaledb).

## Environment Variables

The following environment variables are used in this Compose file:

- **TIMESCALE_TAG**  
  Specifies the version tag of the TimescaleDB image.  
  *Default*: `latest-pg16`

- **TIMESCALE_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `timescaledb`

- **TIMESCALE_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `timescaledb`

- **TIMESCALE_PORT**  
  Maps the host port to the TimescaleDB port (`5432`) in the container.  
  *Default*: `5432`

- **POSTGRES_USER**  
  Specifies the PostgreSQL user for TimescaleDB.  
  *Default*: `postgres`

- **POSTGRES_PASSWORD**  
  Sets the password for the PostgreSQL user.  
  *Default*: `StrongPassw0rd`

- **POSTGRES_DB**  
  Defines the default database to be created.  
  *Default*: `timescaledb`

## Volumes and Networks

The Compose file also defines a persistent volume and uses an external network for container connectivity:

- **Volume:**
  - `timescaledb-data` (mounted at `/var/lib/postgresql/data`)

- **Network:**
  - `portainer-network` (external)
