# Eclipse Mosquitto Docker Compose Setup

This repository contains a Docker Compose configuration for running [Eclipse Mosquitto](https://mosquitto.org/), an open-source MQTT broker, using Docker.

## Website

Visit the [Eclipse Mosquitto website](https://mosquitto.org/) for more information, documentation, and support.

## Docker Hub

The official Docker image is available on [Docker Hub](https://hub.docker.com/_/eclipse-mosquitto).

## Environment Variables

The following environment variables are used in the Compose file:

- **MOSQUITTO_TAG**  
  Specifies the version tag of the Eclipse Mosquitto image.  
  *Default*: `latest`

- **MOSQUITTO_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `broker`

- **MOSQUITTO_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `broker`

- **MOSQUITTO_MQTT_PORT**  
  Maps the host port to the MQTT port (`1883`) in the container.  
  *Default*: `1883`

## Volumes and Networks

The Compose file also defines persistent volumes and an external network for data storage and connectivity:

- **Volumes:**
  - `mosquitto-data`
  - `mosquitto-log`

- **Network:**
  - `portainer-network` (external)

## Additional Configuration

On startup, the container runs a shell command to generate a custom Mosquitto configuration file at `/mosquitto/config/mosquitto.conf` before starting the broker with the specified settings.
