# Grafana Docker Compose Setup

This repository contains a Docker Compose configuration for running [Grafana](https://grafana.com/), an open-source analytics and monitoring platform, using Docker.

## Website

Visit the [Grafana website](https://grafana.com/) for detailed documentation, downloads, and support.

## Docker Hub

The official Grafana Docker image is available on [Docker Hub](https://hub.docker.com/r/grafana/grafana).

## Environment Variables

The following environment variables are used in this Compose file:

- **GRAFANA_TAG**  
  Specifies the version tag of the Grafana image.  
  *Default*: `latest`

- **GRAFANA_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `grafana`

- **GRAFANA_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `grafana`

- **GRAFANA_PORT**  
  Maps the host port to the container port (`3000`).  
  *Default*: `3000`

- **GRAFANA_ADMIN_PASSWORD**  
  Sets the Grafana admin password (mapped to `GF_SECURITY_ADMIN_PASSWORD`).  
  *Default*: `admin`

- **GF_USERS_ALLOW_SIGN_UP**  
  Determines whether user sign-ups are allowed.  
  *Default*: `false`

## Volumes and Networks

- **Volume:**
  - `grafana-data` (mounted at `/var/lib/grafana`)

- **Network:**
  - `portainer-network` (external)
