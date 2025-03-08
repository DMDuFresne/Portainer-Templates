# MING Docker Compose Setup

This repository contains a Docker Compose configuration for running a suite of IIoT services under the "MING" project. This stack includes:

- **Mosquitto** – an MQTT broker  
- **InfluxDB** – a time series database  
- **Node-RED** – a flow-based development tool for visual programming  
- **Grafana** – an open-source analytics and monitoring platform  

All services share a common Docker network (`ming-network`) and use persistent volumes for data storage.

---

## Services Overview

### 1. Mosquitto

**Description:**  
Eclipse Mosquitto is an open-source MQTT broker that implements the MQTT protocol version 3.1.1. This service is configured to allow anonymous connections and persist data to disk.

- **Image:** `eclipse-mosquitto:${MOSQUITTO_TAG:-latest}`  
- **Container Name:** `ming-broker`  
- **Hostname:** `broker`  
- **Ports:**  
  - MQTT: `${MOSQUITTO_MQTT_PORT:-1883}:1883`  
- **Command:**  
  The container runs a shell command that creates a custom configuration file at startup:

  ```sh
  echo 'listener 1883 0.0.0.0
  allow_anonymous true
  log_type error
  log_type warning
  log_type notice
  log_type information
  persistence true
  persistence_location /mosquitto/data/' > /mosquitto/config/mosquitto.conf && mosquitto -c /mosquitto/config/mosquitto.conf
  ```

- **Volumes:**  
  - `ming-mosquitto-data` mounted at `/mosquitto/data`  
  - `ming-mosquitto-log` mounted at `/mosquitto/log`  
- **Networks:**  
  - `ming-network`  

**Websites & References:**  

- [Mosquitto Website](https://mosquitto.org/)  
- [Docker Hub - Eclipse Mosquitto](https://hub.docker.com/_/eclipse-mosquitto)

---

### 2. InfluxDB

**Description:**  
InfluxDB is a high-performance time series database. This container initializes InfluxDB with a default setup using environment variables.

- **Image:** `influxdb:${INFLUXDB_TAG:-latest}`  
- **Container Name:** `ming-influxdb`  
- **Hostname:** `influxdb`  
- **Ports:**  
  - `${INFLUXDB_PORT:-8086}:8086`  
- **Environment Variables:**  
  - `DOCKER_INFLUXDB_INIT_MODE` (Default: `setup`)  
  - `DOCKER_INFLUXDB_INIT_USERNAME` (Default: `admin`)  
  - `DOCKER_INFLUXDB_INIT_PASSWORD` (Default: `StrongPassw0rd`)  
  - `DOCKER_INFLUXDB_INIT_ORG` (Default: `myorg`)  
  - `DOCKER_INFLUXDB_INIT_BUCKET` (Default: `mybucket`)  
- **Volumes:**  
  - `ming-influxdb-data` mounted at `/var/lib/influxdb2`  
- **Networks:**  
  - `ming-network`  

**Websites & References:**  

- [InfluxDB Website](https://www.influxdata.com/)  
- [Docker Hub - InfluxDB](https://hub.docker.com/_/influxdb)

---

### 3. Node-RED

**Description:**  
Node-RED is a flow-based development tool for wiring together hardware devices, APIs, and online services. This service provides a visual programming interface for creating automation workflows.

- **Image:** `nodered/node-red:${NODE_RED_TAG:-latest}`  
- **Container Name:** `ming-nodered`  
- **Hostname:** `nodered`  
- **Ports:**  
  - `${NODE_RED_PORT:-1880}:1880`  
- **Volumes:**  
  - `ming-nodered-data` mounted at `/data`  
- **Networks:**  
  - `ming-network`  

**Websites & References:**  

- [Node-RED Website](https://nodered.org/)  
- [Docker Hub - Node-RED](https://hub.docker.com/r/nodered/node-red)

---

### 4. Grafana

**Description:**  
Grafana is an open-source analytics and monitoring platform. In this configuration, it is set up with an administrator password and disabled sign-up by default.

- **Image:** `grafana/grafana:${GRAFANA_TAG:-latest}`  
- **Container Name:** `ming-grafana`  
- **Hostname:** `grafana`  
- **Ports:**  
  - `${GRAFANA_PORT:-3000}:3000`  
- **Environment Variables:**  
  - `GF_SECURITY_ADMIN_PASSWORD` (sourced from `GRAFANA_ADMIN_PASSWORD`, Default: `admin`)  
  - `GF_USERS_ALLOW_SIGN_UP` (Default: `false`)  
- **Volumes:**  
  - `ming-grafana-data` mounted at `/var/lib/grafana`  
- **Networks:**  
  - `ming-network`  

**Websites & References:**  

- [Grafana Website](https://grafana.com/)  
- [Docker Hub - Grafana](https://hub.docker.com/r/grafana/grafana)

---

## Volumes

The following persistent volumes are defined for data storage:

- `ming-mosquitto-data`
- `ming-mosquitto-log`
- `ming-influxdb-data`
- `ming-nodered-data`
- `ming-grafana-data`

---

## Networks

All services connect to the Docker network:

- **Network Name:** `ming-network`

---

## How to Use

1. **Clone the Repository:**  
   Clone this repository to your local machine.

2. **Configure Environment Variables (Optional):**  
   Create a `.env` file in the root directory to override the default values, if needed.

3. **Deploy the Stack:**  
   Run the following command in the directory containing your `docker-compose.yml`:

   ```bash
   docker-compose up -d
   ```

4. **Access the Services:**  
   - **Mosquitto:** MQTT clients can connect via port 1883.  
   - **InfluxDB:** Access the database on `http://localhost:8086`.  
   - **Node-RED:** Open the Node-RED editor at `http://localhost:1880`.  
   - **Grafana:** Open Grafana at `http://localhost:3000`.
