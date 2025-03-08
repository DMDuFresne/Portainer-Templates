# Neo4j Docker Compose Setup

This repository contains a Docker Compose configuration for running [Neo4j](https://neo4j.com/), a popular graph database, using Docker.

## Website

Visit the [Neo4j website](https://neo4j.com/) for documentation, downloads, and community resources.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/neo4j).

## Environment Variables

The following environment variables are defined in this Compose file:

- **NEO4J_TAG**  
  Specifies the version tag of the Neo4j image.  
  *Default*: `latest`

- **NEO4J_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `neo4j`

- **NEO4J_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `neo4j`

- **NEO4J_BOLT_PORT**  
  Maps the host port to the container's Bolt port (`7687`).  
  *Default*: `7687`

- **NEO4J_HTTP_PORT**  
  Maps the host port to the container's HTTP port (`7474`).  
  *Default*: `7474`

- **NEO4J_AUTH**  
  Sets the authentication credentials in the format `username/password`.  
  *Default*: `neo4j/password`

## Volumes and Networks

The Compose file also defines persistent volumes and uses an external network for container connectivity:

- **Volumes:**
  - `neo4j-data` (mounted at `/data`)
  - `neo4j-logs` (mounted at `/logs`)
  - `neo4j-import` (mounted at `/var/lib/neo4j/import`)
  - `neo4j-plugins` (mounted at `/plugins`)

- **Network:**
  - `portainer-network` (external)
