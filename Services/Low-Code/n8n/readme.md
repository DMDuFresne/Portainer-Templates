# n8n Docker Compose Setup

This repository contains a Docker Compose configuration for running [n8n](https://n8n.io/), an open-source workflow automation tool, using Docker.

## Website

Visit the [n8n website](https://n8n.io/) for detailed information, documentation, and support.

## Docker Hub

The official n8n Docker image is available on [Docker Hub](https://hub.docker.com/r/n8nio/n8n).

## Environment Variables

The following environment variables are used in the Compose file:

- **N8N_TAG**  
  Specifies the version tag of the n8n image.  
  *Default*: `latest`

- **N8N_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `n8n`

- **N8N_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `n8n`

- **N8N_PORT**  
  Maps the host port to the n8n port (`5678`) in the container.  
  *Default*: `5678`

- **TZ**  
  Sets the timezone for the container.  
  *Default*: `UTC`

- **N8N_BASIC_AUTH_ACTIVE**  
  Enables or disables basic authentication.  
  *Default*: `false`

- **N8N_BASIC_AUTH_USER**  
  Defines the username for basic authentication.  
  *Default*: `admin`

- **N8N_BASIC_AUTH_PASSWORD**  
  Defines the password for basic authentication.  
  *Default*: `password`

- **N8N_SECURE_COOKIE**  
  Enables secure cookies for authentication.  
  *Default*: `false`

## Volumes and Networks

The Compose file defines a persistent volume and uses an external network for container connectivity:

- **Volume:**
  - `n8n-data` (mounted at `/home/node/.n8n`)

- **Network:**
  - `portainer-network` (external)
