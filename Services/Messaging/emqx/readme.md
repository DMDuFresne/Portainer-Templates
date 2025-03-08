# EMQX Docker Compose Setup

This repository contains a Docker Compose configuration for running [EMQX](https://www.emqx.io/), a scalable and distributed MQTT broker, using Docker.

## Website

Visit the [EMQX website](https://www.emqx.io/) for detailed information on features, documentation, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/emqx/emqx).

## Environment Variables

The following environment variables are defined in the Compose file:

- **EMQX_TAG**:  
  Specifies the version tag of the EMQX image.  
  *Default*: `latest`

- **EMQX_CONTAINER_NAME**:  
  Sets the name of the Docker container.  
  *Default*: `broker`

- **EMQX_HOSTNAME**:  
  Sets the hostname for the container.  
  *Default*: `broker`

- **EMQX_MQTT_PORT**:  
  Maps the host port to MQTT port `1883` in the container.  
  *Default*: `1883`

- **EMQX_WS_PORT**:  
  Maps the host port to WebSocket port `8083` in the container.  
  *Default*: `8083`

- **EMQX_DASHBOARD_PORT**:  
  Maps the host port to the EMQX Dashboard port `18083` in the container.  
  *Default*: `18083`

- **EMQX_ALLOW_ANONYMOUS**:  
  Configures whether anonymous connections are allowed.  
  *Default*: `true`

## Additional Configuration

This setup also defines persistent volumes and uses an external network for proper data management and network isolation:

- **Volumes:**
  - `emqx-data`
  - `emqx-etc`
  - `emqx-log`

- **Networks:**
  - `portainer-network` (external)
