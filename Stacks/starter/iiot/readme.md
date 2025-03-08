# IIoT Edge Docker Compose Setup

This repository contains a Docker Compose configuration for running a complete IIoT (Industrial Internet of Things) Edge solution. The setup includes multiple services such as HiveMQ Edge, PostgreSQL, Timebase components (Collector, Historian, Explorer), Node-RED, Grafana, and Appsmith. All services connect to a dedicated Docker network (`iiot-edge-network`) and use persistent volumes for data storage.

## Services Overview

Below is a detailed overview of each service included in this Compose file.

---

## 1. HiveMQ Edge Broker

**Description:**  
A lightweight MQTT broker optimized for IIoT edge environments.

- **Image:** `hivemq/hivemq-edge:${HIVEMQ_EDGE_TAG:-latest}`  
- **Container Name:** `iiot-edge-broker`  
- **Hostname:** `broker`  
- **Ports:**  
  - MQTT: `${HIVEMQ_EDGE_MQTT_PORT:-1883}:1883`  
  - UI: `${HIVEMQ_EDGE_UI_PORT:-8080}:8080`  
- **Environment Variables:**  
  - `HIVEMQ_LOG_LEVEL` (Default: `INFO`)
- **Volumes:**  
  - `iiot-edge-hivemq-edge-logs` mounted at `/opt/hivemq/log`  
  - `iiot-edge-hivemq-edge-conf` mounted at `/opt/hivemq/conf`  
  - `iiot-edge-hivemq-edge-data` mounted at `/opt/hivemq/data`  
  - `iiot-edge-hivemq-edge-extensions` mounted at `/opt/hivemq/extensions`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [HiveMQ Edge](https://www.hivemq.com/hivemq-edge/)  
**Docker Hub:** [hivemq/hivemq-edge](https://hub.docker.com/r/hivemq/hivemq-edge)

---

## 2. PostgreSQL

**Description:**  
A popular open-source relational database.

- **Image:** `postgres:${POSTGRES_TAG:-latest}`  
- **Container Name:** `iiot-edge-postgres`  
- **Hostname:** `postgres`  
- **Ports:**  
  - `${POSTGRES_PORT:-5432}:5432`  
- **Environment Variables:**  
  - `POSTGRES_USER` (Default: `user`)  
  - `POSTGRES_PASSWORD` (Default: `password`)  
  - `POSTGRES_DB` (Default: `db`)  
- **Volumes:**  
  - `iiot-edge-postgres-data` mounted at `/var/lib/postgresql/data`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [PostgreSQL](https://www.postgresql.org/)  
**Docker Hub:** [postgres](https://hub.docker.com/_/postgres)

---

## 3. Timebase Collector

**Description:**  
A component of the Timebase ecosystem for collecting time series data.

- **Image:** `timebase/collector:${COLLECTOR_TAG:-latest}`  
- **Container Name:** `iiot-edge-timebase-collector`  
- **Hostname:** `timebase-collector`  
- **Ports:**  
  - `${COLLECTOR_PORT:-4521}:4521`  
- **Environment Variables:**  
  - `ACTIVE` (sourced from `COLLECTOR_ACTIVE`, Default: `false`)  
- **Volumes:**  
  - `iiot-edge-collector-config` mounted at `/timebase/config`  
  - `iiot-edge-collector-data` mounted at `/timebase/data`  
  - `iiot-edge-collector-logs` mounted at `/timebase/logs`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [Timebase](https://timebase.io/)  
**Docker Hub:** [timebase/collector](https://hub.docker.com/r/timebase/collector)

---

## 4. Timebase Historian

**Description:**  
Stores and manages historical time series data as part of the Timebase ecosystem.

- **Image:** `timebase/historian:${HISTORIAN_TAG:-latest}`  
- **Container Name:** `iiot-edge-timebase-historian`  
- **Hostname:** `timebase-historian`  
- **Ports:**  
  - `${HISTORIAN_PORT:-4511}:4511`  
- **Volumes:**  
  - `iiot-edge-historian-data` mounted at `/timebase/data`  
  - `iiot-edge-historian-logs` mounted at `/timebase/logs`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [Timebase](https://timebase.io/)  
**Docker Hub:** [timebase/historian](https://hub.docker.com/r/timebase/historian)

---

## 5. Timebase Explorer

**Description:**  
A tool for exploring and visualizing time series data within the Timebase ecosystem.

- **Image:** `timebase/explorer:${EXPLORER_TAG:-latest}`  
- **Container Name:** `iiot-edge-timebase-explorer`  
- **Hostname:** `timebase-explorer`  
- **Ports:**  
  - `${EXPLORER_PORT:-4531}:4531`  
- **Volumes:**  
  - `iiot-edge-explorer-config` mounted at `/timebase/config`  
  - `iiot-edge-explorer-logs` mounted at `/timebase/logs`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [Timebase](https://timebase.io/)  
**Docker Hub:** [timebase/explorer](https://hub.docker.com/r/timebase/explorer)

---

## 6. Node-RED

**Description:**  
A flow-based programming tool for wiring together hardware devices, APIs, and online services.

- **Image:** `nodered/node-red:${NODE_RED_TAG:-latest}`  
- **Container Name:** `iiot-edge-nodered`  
- **Hostname:** `nodered`  
- **Ports:**  
  - `${NODE_RED_PORT:-1880}:1880`  
- **Volumes:**  
  - `iiot-edge-nodered-data` mounted at `/data`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [Node-RED](https://nodered.org/)  
**Docker Hub:** [nodered/node-red](https://hub.docker.com/r/nodered/node-red)

---

## 7. Grafana

**Description:**  
An open-source analytics and monitoring platform.

- **Image:** `grafana/grafana:${GRAFANA_TAG:-latest}`  
- **Container Name:** `iiot-edge-grafana`  
- **Hostname:** `grafana`  
- **Ports:**  
  - `${GRAFANA_PORT:-3000}:3000`  
- **Environment Variables:**  
  - `GF_SECURITY_ADMIN_PASSWORD` (sourced from `GRAFANA_ADMIN_PASSWORD`, Default: `admin`)  
  - `GF_USERS_ALLOW_SIGN_UP` (Default: `false`)  
- **Volumes:**  
  - `iiot-edge-grafana-data` mounted at `/var/lib/grafana`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [Grafana](https://grafana.com/)  
**Docker Hub:** [grafana/grafana](https://hub.docker.com/r/grafana/grafana)

---

## 8. Appsmith

**Description:**  
An open-source platform to build internal tools quickly.

- **Image:** `index.docker.io/appsmith/appsmith-ee`  
- **Container Name:** `iiot-edge-appsmith`  
- **Hostname:** `appsmith`  
- **Ports:**  
  - `${APPSMITH_PORT:-8888}:80`  
- **Volumes:**  
  - `iiot-edge-appsmith-stacks` mounted at `/appsmith-stacks`  
- **Networks:**  
  - `iiot-edge-network`  

**Website:** [Appsmith](https://www.appsmith.com/)  
**Docker Hub:** [appsmith/appsmith-ee](https://hub.docker.com/r/appsmith/appsmith-ee)

---

## Volumes

The following persistent volumes are defined for data storage:

- `iiot-edge-hivemq-edge-logs`
- `iiot-edge-hivemq-edge-conf`
- `iiot-edge-hivemq-edge-data`
- `iiot-edge-hivemq-edge-extensions`
- `iiot-edge-postgres-data`
- `iiot-edge-collector-config`
- `iiot-edge-collector-data`
- `iiot-edge-collector-logs`
- `iiot-edge-historian-data`
- `iiot-edge-historian-logs`
- `iiot-edge-explorer-config`
- `iiot-edge-explorer-logs`
- `iiot-edge-nodered-data`
- `iiot-edge-grafana-data`
- `iiot-edge-appsmith-stacks`

---

## Networks

All services connect to the external Docker network:

- **Network Name:** `iiot-edge-network`

---

## How to Use

1. **Clone the Repository:**
   Clone this repository to your local machine.

2. **Configure Environment Variables:**
   Create a `.env` file (or set environment variables directly) to override the defaults if needed.

3. **Deploy the Stack:**
   Run the following command in the directory containing your `docker-compose.yml`:

   ```bash
   docker-compose up -d
   ```
