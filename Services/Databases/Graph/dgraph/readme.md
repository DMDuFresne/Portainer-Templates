# Dgraph Docker Compose Setup

This repository contains a Docker Compose configuration for running [Dgraph](https://dgraph.io/), a distributed graph database, using Docker.

## Website

Visit the [Dgraph website](https://dgraph.io/) for detailed information, documentation, and support.

## Docker Hub

The official Dgraph Docker images are available on [Docker Hub](https://hub.docker.com/r/dgraph/dgraph).

## Environment Variables

The following environment variables are used in the Compose file:

- **DGRAPH_TAG**  
  Specifies the version tag of the Dgraph image.  
  *Default*: `latest`

- **DGRAPH_ZERO_CONTAINER_NAME**  
  Sets the name of the Dgraph Zero container.  
  *Default*: `dgraph-zero`

- **DGRAPH_ZERO_HOSTNAME**  
  Sets the hostname for the Dgraph Zero container.  
  *Default*: `zero`

- **ZERO_RPC_PORT**  
  Maps the host port to the Dgraph Zero RPC port (`5080`).  
  *Default*: `5080`

- **ZERO_HTTP_PORT**  
  Maps the host port to the Dgraph Zero HTTP port (`6080`).  
  *Default*: `6080`

- **DGRAPH_ALPHA_CONTAINER_NAME**  
  Sets the name of the Dgraph Alpha container.  
  *Default*: `dgraph-alpha`

- **DGRAPH_ALPHA_HOSTNAME**  
  Sets the hostname for the Dgraph Alpha container.  
  *Default*: `alpha`

- **ALPHA_HTTP_PORT**  
  Maps the host port to the Dgraph Alpha HTTP port (`8080`).  
  *Default*: `8080`

- **ALPHA_ADMIN_PORT**  
  Maps the host port to the Dgraph Alpha Admin port (`9080`).  
  *Default*: `9080`

- **DGRAPH_RATEL_CONTAINER_NAME**  
  Sets the name of the Dgraph Ratel container.  
  *Default*: `dgraph-ratel`

- **DGRAPH_RATEL_HOSTNAME**  
  Sets the hostname for the Dgraph Ratel container.  
  *Default*: `ratel`

- **RATEL_HTTP_PORT**  
  Maps the host port to the Dgraph Ratel UI port (`8000`).  
  *Default*: `8000`

## Volumes and Networks

The Compose file defines persistent volumes and uses an external network for container connectivity:

- **Volumes:**
  - `dgraph-zero-data` (mounted at `/dgraph` for Zero)
  - `dgraph-alpha-data` (mounted at `/dgraph` for Alpha)

- **Network:**
  - `portainer-network` (external)
