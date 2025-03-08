# MongoDB Docker Compose Setup

This repository contains a Docker Compose configuration for running [MongoDB](https://www.mongodb.com/), a popular NoSQL database, using Docker.

## Website

Visit the [MongoDB website](https://www.mongodb.com/) for detailed information, documentation, and support.

## Docker Hub

The official MongoDB Docker image is available on [Docker Hub](https://hub.docker.com/_/mongo).

## Environment Variables

The following environment variables are used in the Compose file:

- **MONGO_TAG**  
  Specifies the version tag of the MongoDB image.  
  *Default*: `latest`

- **MONGO_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `mongodb`

- **MONGO_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `mongodb`

- **MONGO_PORT**  
  Maps the host port to the MongoDB port (`27017`) in the container.  
  *Default*: `27017`

- **MONGO_INITDB_ROOT_USERNAME**  
  Specifies the root username for MongoDB initialization.  
  *Default*: `root`

- **MONGO_INITDB_ROOT_PASSWORD**  
  Specifies the root password for MongoDB initialization.  
  *Default*: `root`

## Volumes and Networks

The Compose file defines a persistent volume and uses an external network for container connectivity:

- **Volume:**
  - `mongodb-data` (mounted at `/data/db`)

- **Network:**
  - `portainer-network` (external)
