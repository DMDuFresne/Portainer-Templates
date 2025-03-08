# Timebase Historian Docker Compose Setup

This repository contains a Docker Compose configuration for running [Timebase Historian](https://www.timebase.com/), a component of the Timebase ecosystem designed for storing and managing historical time series data, using Docker.

## Website

Visit the [Timebase website](https://www.timebase.com/) for detailed documentation, features, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/timebase/historian).

## Environment Variables

The following environment variables are used in this Compose file:

- **HISTORIAN_TAG**  
  Specifies the version tag of the Timebase Historian image.  
  *Default*: `latest`

- **HISTORIAN_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `timebase-historian`

- **HISTORIAN_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `timebase-historian`

- **HISTORIAN_PORT**  
  Maps the host port to the container's port (`4511`).  
  *Default*: `4511`

## Volumes and Networks

- **Volumes:**
  - `historian-data` (mounted at `/timebase/data`)
  - `historian-logs` (mounted at `/timebase/logs`)

- **Network:**
  - `portainer-network` (external)
