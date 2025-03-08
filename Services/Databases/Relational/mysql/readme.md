# MySQL Docker Compose Setup

This repository contains a Docker Compose configuration for running [MySQL](https://www.mysql.com/), a popular open-source relational database, using Docker.

## Website

Visit the [MySQL website](https://www.mysql.com/) for documentation, downloads, and community resources.

## Docker Hub

The official MySQL Docker image is available on [Docker Hub](https://hub.docker.com/_/mysql).

## Environment Variables

The following environment variables are used in this Compose file:

- **MYSQL_TAG**  
  Specifies the version tag of the MySQL image.  
  *Default*: `latest`

- **MYSQL_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `mysql`

- **MYSQL_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `mysql`

- **MYSQL_PORT**  
  Maps the host port to the MySQL port (`3306`) in the container.  
  *Default*: `3306`

- **MYSQL_ROOT_PASSWORD**  
  Specifies the root password for MySQL.  
  *Default*: `rootpassword`

- **MYSQL_DATABASE**  
  Defines the default database to be created.  
  *Default*: `exampledb`

- **MYSQL_USER**  
  Specifies the name of a non-root user to be created.  
  *Default*: `user`

- **MYSQL_PASSWORD**  
  Sets the password for the non-root user.  
  *Default*: `password`

## Volumes and Networks

The Compose file also defines a persistent volume and an external network for container connectivity:

- **Volume:**
  - `mysql-data` (mounted at `/var/lib/mysql`)

- **Network:**
  - `portainer-network` (external)
