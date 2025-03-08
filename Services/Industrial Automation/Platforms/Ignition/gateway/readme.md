# Ignition Gateway Docker Compose Setup

This repository contains a Docker Compose configuration for running [Ignition Gateway](https://inductiveautomation.com/), an industrial application platform from Inductive Automation, using Docker.

## Website

Visit the [Inductive Automation website](https://inductiveautomation.com/) for detailed information, documentation, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/inductiveautomation/ignition).

## Environment Variables

The following environment variables are defined in this Compose file:

- **IGNITION_TAG**  
  Specifies the version tag of the Ignition Docker image.  
  *Default*: `latest`

- **IGNITION_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `ignition-gateway`

- **IGNITION_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `ignition-gateway`

- **IGNITION_PORT**  
  Maps the host port to the container's port.  
  *Default*: Host port `8088` maps to container port `8088`

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
  *Default*: `standard`

- **IGNITION_LICENSE_KEY**  
  Sets the license key for Ignition, if applicable.  
  *Default*: `_empty_`

- **GATEWAY_MODULES_ENABLED**  
  Specifies a comma-separated list of modules to enable on the gateway.  
  *Default*: `opc-ua,perspective,web-developer`

## Volumes and Networks

- **Volume:**
  - `ignition-gateway-data` (mounted at `/var/lib/ignition`)

- **Network:**
  - `portainer-network` (external)
