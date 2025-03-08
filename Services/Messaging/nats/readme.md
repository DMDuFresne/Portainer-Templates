# NATS Docker Compose Setup

This repository contains a Docker Compose configuration for running [NATS](https://nats.io/), a high-performance messaging system, using Docker.

## Website

Visit the [NATS website](https://nats.io/) for documentation, features, and community support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/nats).

## Environment Variables

The following environment variables are used in this Compose file:

- **NATS_TAG**  
  Specifies the version tag of the NATS image.  
  *Default*: `latest`

- **NATS_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `nats`

- **NATS_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `nats`

- **NATS_CLIENT_PORT**  
  Maps the host port to the NATS client port (`4222`) in the container.  
  *Default*: `4222`

- **NATS_CLUSTER_PORT**  
  Maps the host port to the NATS cluster port (`6222`) in the container.  
  *Default*: `6222`

- **NATS_MONITOR_PORT**  
  Maps the host port to the NATS monitor port (`8222`) in the container.  
  *Default*: `8222`

## Volumes and Networks

The Compose file also defines a persistent volume and uses an external network for container connectivity:

- **Volume:**
  - `nats-data`

- **Network:**
  - `portainer-network` (external)
