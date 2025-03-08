# Timebase Collector Docker Compose Setup

This repository contains a Docker Compose configuration for running [Timebase Collector](https://www.timebase.com/), a tool for collecting time series data as part of the Timebase ecosystem, using Docker.

## Website

Visit the [Timebase website](https://www.timebase.com/) for detailed documentation, features, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/timebase/collector).

## Environment Variables

The following environment variables are used in this Compose file:

- **COLLECTOR_TAG**  
  Specifies the version tag of the Timebase Collector image.  
  *Default*: `latest`

- **COLLECTOR_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `timebase-collector`

- **COLLECTOR_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `timebase-collector`

- **COLLECTOR_PORT**  
  Maps the host port to the collector’s port (`4521`) in the container.  
  *Default*: `4521`

- **COLLECTOR_ACTIVE**  
  Determines whether the collector is active.  
  *Default*: `false`

## Volumes and Networks

- **Volumes:**
  - `collector-config` (mounted at `/timebase/config`)
  - `collector-data` (mounted at `/timebase/data`)
  - `collector-logs` (mounted at `/timebase/logs`)

- **Network:**
  - `portainer-network` (external)
