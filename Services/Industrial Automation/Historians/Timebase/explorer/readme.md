# Timebase Explorer Docker Compose Setup

This repository contains a Docker Compose configuration for running [Timebase Explorer](https://www.timebase.com/), a component of the Timebase ecosystem designed for exploring time series data, using Docker.

## Website

Visit the [Timebase website](https://www.timebase.com/) for detailed documentation, features, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/timebase/explorer).

## Environment Variables

The following environment variables are used in this Compose file:

- **EXPLORER_TAG**  
  Specifies the version tag of the Timebase Explorer image.  
  *Default*: `latest`

- **EXPLORER_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `timebase-explorer`

- **EXPLORER_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `timebase-explorer`

- **EXPLORER_PORT**  
  Maps the host port to the container's port (`4531`).  
  *Default*: `4531`

## Volumes and Networks

- **Volumes:**
  - `explorer-config` (mounted at `/timebase/config`)
  - `explorer-logs` (mounted at `/timebase/logs`)

- **Network:**
  - `portainer-network` (external)
