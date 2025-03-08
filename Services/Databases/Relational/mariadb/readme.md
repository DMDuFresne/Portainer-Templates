# MariaDB Docker Compose Setup

This repository contains a Docker Compose configuration for running [MariaDB](https://mariadb.org/), a popular open-source relational database, using Docker.

## Website

Visit the [MariaDB website](https://mariadb.org/) for documentation, downloads, and community resources.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/mariadb).

## Environment Variables

The following environment variables are used in the Compose file:

- **MARIADB_TAG**  
  Specifies the version tag of the MariaDB image.  
  *Default*: `latest`

- **MARIADB_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `mariadb`

- **MARIADB_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `mariadb`

- **MARIADB_PORT**  
  Maps the host port to the MariaDB port (`3306`) in the container.  
  *Default*: `3306`

- **MYSQL_ROOT_PASSWORD**  
  Specifies the root password for the MariaDB instance.  
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
  - `mariadb-data` (mounted at `/var/lib/mysql`)

- **Network:**
  - `portainer-network` (external)
