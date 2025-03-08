# HiveMQ Edge Docker Compose Setup

This repository contains a Docker Compose configuration for running [HiveMQ Edge](https://www.hivemq.com/hivemq-edge/), a lightweight and powerful MQTT broker for IoT applications, using Docker.

## Website

Visit the [HiveMQ Edge website](https://www.hivemq.com/hivemq-edge/) for detailed information on features, documentation, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/hivemq/hivemq-edge).

## Environment Variables

The following environment variables are used in this Compose file:

- **HIVEMQ_EDGE_TAG**  
  Specifies the version tag of the HiveMQ Edge image.  
  *Default*: `latest`

- **HIVEMQ_EDGE_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `hivemq-edge`

- **HIVEMQ_EDGE_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `hivemq-edge`

- **HIVEMQ_EDGE_MQTT_PORT**  
  Maps the host port to the MQTT port (`1883`) in the container.  
  *Default*: `1883`

- **HIVEMQ_EDGE_UI_PORT**  
  Maps the host port to the HiveMQ Edge UI port (`8080`) in the container.  
  *Default*: `8080`

- **HIVEMQ_LOG_LEVEL**  
  Configures the log level for HiveMQ Edge.  
  *Default*: `INFO`

## Volumes and Networks

The Compose file also defines persistent volumes for logs, configuration, data, and extensions, and uses an external network (`portainer-network`) for container connectivity:

- **Volumes:**
  - `hivemq-edge-logs`
  - `hivemq-edge-conf`
  - `hivemq-edge-data`
  - `hivemq-edge-extensions`

- **Network:**
  - `portainer-network` (external)
