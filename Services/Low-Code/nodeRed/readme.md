# Node-RED Docker Compose Setup

This repository contains a Docker Compose configuration for running [Node-RED](https://nodered.org/), a flow-based programming tool for wiring together hardware devices, APIs, and online services, using Docker.

## Website

Visit the [Node-RED website](https://nodered.org/) for detailed documentation, tutorials, and community support.

## Docker Hub

The official Node-RED Docker image is available on [Docker Hub](https://hub.docker.com/r/nodered/node-red).

## Environment Variables

The following environment variables are defined in this Compose file:

- **NODE_RED_TAG**  
  Specifies the version tag of the Node-RED Docker image.  
  *Default*: `latest`

- **NODE_RED_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `nodered`

- **NODE_RED_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `nodered`

- **NODE_RED_PORT**  
  Maps the host port to the Node-RED port (`1880`) in the container.  
  *Default*: `1880`

## Volumes and Networks

- **Volume:**
  - `nodered-data` (mounted at `/data`)

- **Network:**
  - `portainer-network` (external)
