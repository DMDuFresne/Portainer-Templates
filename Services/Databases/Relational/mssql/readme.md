# Microsoft SQL Server Docker Compose Setup

This repository contains a Docker Compose configuration for running [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server/) using Docker.

## Website

Visit the [Microsoft SQL Server website](https://www.microsoft.com/en-us/sql-server/) for detailed information, documentation, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/microsoft-mssql-server).

## Environment Variables

The following environment variables are used in this Compose file:

- **MSSQL_TAG**  
  Specifies the version tag of the Microsoft SQL Server image.  
  *Default*: `2022-latest`

- **MSSQL_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `mssql`

- **MSSQL_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `mssql`

- **MSSQL_PORT**  
  Maps the host port to the SQL Server port (`1433`) in the container.  
  *Default*: `1433`

- **ACCEPT_EULA**  
  Accepts the End User License Agreement required by Microsoft SQL Server.  
  *Default*: `Y`

- **SA_PASSWORD**  
  Sets the SA (system administrator) password for SQL Server.  
  *Default*: `Strong@Passw0rd`

## Volumes and Networks

The Compose file also defines a persistent volume and an external network for container connectivity:

- **Volume:**
  - `mssql-data` (mounted at `/var/opt/mssql`)

- **Network:**
  - `portainer-network` (external)
