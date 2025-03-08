# PostgreSQL Docker Compose Setup

This repository contains a Docker Compose configuration for running [PostgreSQL](https://www.postgresql.org/), a robust open-source relational database, using Docker.

## Website

Visit the [PostgreSQL website](https://www.postgresql.org/) for detailed documentation, downloads, and community resources.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/postgres).

## Environment Variables

The following environment variables are used in this Compose file:

- **POSTGRES_TAG**  
  Specifies the version tag of the PostgreSQL image.  
  *Default*: `latest`

- **POSTGRES_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `postgres`

- **POSTGRES_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `postgres`

- **POSTGRES_PORT**  
  Maps the host port to the PostgreSQL port (`5432`) in the container.  
  *Default*: `5432`

- **POSTGRES_USER**  
  Specifies the username for PostgreSQL.  
  *Default*: `user`

- **POSTGRES_PASSWORD**  
  Sets the password for the PostgreSQL user.  
  *Default*: `password`

- **POSTGRES_DB**  
  Defines the default database to be created.  
  *Default*: `db`

## Volumes and Networks

The Compose file also defines a persistent volume and uses an external network for container connectivity:

- **Volume:**
  - `postgres-data` (mounted at `/var/lib/postgresql/data`)

- **Network:**
  - `portainer-network` (external)
