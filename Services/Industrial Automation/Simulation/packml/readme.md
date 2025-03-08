# PackML Simulator Docker Compose Setup

This repository contains a Docker Compose configuration for running the [PackML Simulator](https://github.com/libremfg/PackML-MQTT-Simulator), a tool designed to simulate PACKML-compliant production lines, using Docker.

## Website

For more information, visit the the [PackML Simulator GitHub page](https://github.com/libremfg/PackML-MQTT-Simulator).

## Image Repository

The official image is hosted on [GitHub Container Registry](https://ghcr.io/libremfg/packml-simulator).  
*(Note: This image is not available on Docker Hub.)*

## Environment Variables

The following environment variables are used in this Compose file:

- **PACKML_SIMULATOR_TAG**  
  Specifies the version tag of the PackML Simulator image.  
  *Default*: `latest`

- **PACKML_SIMULATOR_CONTAINER_NAME**  
  Sets the name of the Docker container.  
  *Default*: `packml-simulator`

- **PACKML_SIMULATOR_HOSTNAME**  
  Sets the hostname for the container.  
  *Default*: `packml-simulator`

- **SITE**  
  Defines the site name for the simulation.  
  *Default*: `Site`

- **AREA**  
  Defines the area name for the simulation.  
  *Default*: `Area`

- **LINE**  
  Defines the line name for the simulation.  
  *Default*: `Line`

- **MQTT_URL**  
  Specifies the MQTT broker URL.  
  *Default*: `mqtt://broker.hivemq.com`

- **MQTT_PORT**  
  Specifies the MQTT broker port.  
  *Default*: `1883`

- **MQTT_USERNAME**  
  Specifies the MQTT username (if required).  
  *Default*: `_empty_`

- **MQTT_PASSWORD**  
  Specifies the MQTT password (if required).  
  *Default*: `_empty_`

- **MQTT_CLIENT_ID**  
  Sets the MQTT client identifier.  
  *Default*: `packml-simulator`

- **CLIENT_TYPE**  
  Specifies the client type for communication.  
  *Default*: `mqtt`

- **SPARKPLUG_GROUP_ID**  
  Sets the Sparkplug group identifier.  
  *Default*: `Site`

- **SPARKPLUG_EDGE_NODE**  
  Sets the Sparkplug edge node identifier.  
  *Default*: `Area_Line`

- **TICK**  
  Defines the simulation tick interval in milliseconds.  
  *Default*: `1000`

## Resource Limits

This service is deployed with a memory limit of 30M.

## Networks

The PackML Simulator service connects to an external network named `portainer-network`.
