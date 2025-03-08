# Ignition Edge Docker Compose Setup

This repository contains a Docker Compose configuration for running [Ignition Edge](https://inductiveautomation.com/) from Inductive Automation using Docker.

## Website

Visit the [Inductive Automation website](https://inductiveautomation.com/) for detailed information, documentation, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/inductiveautomation/ignition).

## Environment Variables

The following environment variables are used in this Compose file:

- **IGNITION_TAG**  
  Specifies the version tag of the Ignition Docker image.  
  *Default*: `latest`

- **IGNITION_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `ignition-edge`

- **IGNITION_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `ignition-edge`

- **IGNITION_PORT**  
  Maps the host port to the container port.  
  *Default*: Host port `8078` maps to container port `8088`

- **TZ**  
  Sets the timezone for the container.  
  *Default*: `America/Chicago`

- **ACCEPT_IGNITION_EULA**  
  Accepts the Ignition End User License Agreement.  
  *Default*: `Y`

- **GATEWAY_ADMIN_USERNAME**  
  Specifies the username for gateway administration.  
  *Default*: `admin`

- **GATEWAY_ADMIN_PASSWORD**  
  Specifies the password for gateway administration.  
  *Default*: `password`

- **IGNITION_EDITION**  
  Specifies which edition of Ignition to run.  
  *Default*: `edge`

- **IGNITION_LICENSE_KEY**  
  Sets the license key for Ignition, if applicable.  
  *Default*: `_empty_`

## Volumes and Networks

- **Volume:**
  - `ignition-edge-data` (mounted at `/var/lib/ignition`)

- **Network:**
  - `portainer-network` (external)
