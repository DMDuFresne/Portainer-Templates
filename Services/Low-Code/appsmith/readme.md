# Appsmith Docker Compose Setup

This repository contains a Docker Compose configuration for running [Appsmith](https://www.appsmith.com/), an open source platform to build internal tools quickly, using Docker.

## Website

Visit the [Appsmith website](https://www.appsmith.com/) for detailed documentation, features, and community support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/appsmith/appsmith-ee).

## Environment Variables

The following environment variables are used or available in this Compose file:

- **APPSMITH_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `appsmith`

- **APPSMITH_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `appsmith`

- **APPSMITH_PORT**  
  Maps the host ports to the container's ports.  
  *Defaults*:  
  - `8080` for HTTP (mapped to container port `80`)
  - `8443` for HTTPS (mapped to container port `443`)  
  > **Note:** Both mappings use the same environment variable. Adjust as needed.

### Optional Environment Variables

The following optional environment variables can be configured for additional customization:

- **APPSMITH_DB_URL**  
  Sets the database URL for Appsmith.  
  *Example*: `mongodb+srv://{username}:{password}@{mongo.host.name}/{db_name}`

- **APPSMITH_REDIS_URL**  
  Specifies the Redis URL for Appsmith.  
  *Example*: `redis://{redis.instance.hostname}:{port}`

- **APPSMITH_KEYCLOAK_DB_URL**  
  Defines the Keycloak database URL for integrated identity management.  
  *Example*: `postgresql://appsmith:password@appsmith.postgres.database.azure.com:5432/keycloak`

- **APPSMITH_GOOGLE_MAPS_API_KEY**  
  Specifies the Google Maps API key for use with Appsmith.  
  *Example*: `YOUR_API_KEY`

## Volumes and Networks

- **Volume:**
  - `appsmith-stacks` (mounted at `/appsmith-stacks`)

- **Network:**
  - `portainer-network` (external)
