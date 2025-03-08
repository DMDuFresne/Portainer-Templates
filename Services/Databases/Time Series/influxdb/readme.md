# InfluxDB Docker Compose Setup

This repository contains a Docker Compose configuration for running [InfluxDB](https://www.influxdata.com/products/influxdb/), a time series database, using Docker.

## Website

Visit the [InfluxDB website](https://www.influxdata.com/products/influxdb/) for documentation, features, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/influxdb).

## Environment Variables

The following environment variables are used in the Compose file:

- **INFLUXDB_TAG**  
  Specifies the version tag of the InfluxDB image.  
  *Default*: `2`

- **INFLUXDB_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `influxdb`

- **INFLUXDB_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `influxdb`

- **INFLUXDB_PORT**  
  Maps the host port to the InfluxDB port (`8086`) in the container.  
  *Default*: `8086`

- **DOCKER_INFLUXDB_INIT_MODE**  
  Determines the initialization mode for InfluxDB.  
  *Default*: `setup`

- **DOCKER_INFLUXDB_INIT_USERNAME**  
  Specifies the admin username for InfluxDB.  
  *Default*: `admin`

- **DOCKER_INFLUXDB_INIT_PASSWORD**  
  Specifies the admin password for InfluxDB.  
  *Default*: `StrongPassw0rd`

- **DOCKER_INFLUXDB_INIT_ORG**  
  Sets the organization name for InfluxDB.  
  *Default*: `myorg`

- **DOCKER_INFLUXDB_INIT_BUCKET**  
  Sets the initial bucket name for InfluxDB.  
  *Default*: `mybucket`

## Volumes and Networks

The Compose file also defines a persistent volume and an external network for container connectivity:

- **Volume:**
  - `influxdb-data` (mounted at `/var/lib/influxdb2`)

- **Network:**
  - `portainer-network` (external)
