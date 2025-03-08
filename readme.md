# Portainer Template Examples

This repository contains a collection of Docker Compose examples packaged as Portainer Templates. These examples span various categories—from databases and industrial automation to low-code platforms, messaging systems, and big data solutions. The goal is to provide ready-to-use templates that can be easily imported into Portainer to deploy these services quickly and reliably.

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
  - [Services](#services)
    - [Databases](#databases)
    - [Industrial Automation](#industrial-automation)
    - [Low Code](#low-code)
    - [Messaging](#messaging)
  - [Stacks](#stacks)
- [How to Use These Templates](#how-to-use-these-templates)
  - [Deploying Portainer Stacks from Git](#deploying-portainer-stacks-from-git)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository is organized into two main sections:

1. **Services** – Contains categorized folders with Docker Compose examples for different technologies.
2. **Stacks** – A separate directory containing pre-configured Docker Compose stacks for Portainer.

## Repository Structure

### Services

#### Databases

- **Document**
  - **MongoDB** – Document-based NoSQL database.
- **Graph**
  - **Dgraph** – Distributed graph database.
  - **Neo4j** – Graph database optimized for connected data.
- **Relational**
  - **MariaDB** – Community-developed fork of MySQL.
  - **MSSQL** – Microsoft's relational database system.
  - **MySQL** – Widely used open-source SQL database.
  - **Postgres** – Advanced open-source relational database.
- **Time Series**
  - **InfluxDB** – Purpose-built time series database.
  - **QuestDB** – High-performance time series database.
  - **TimescaleDB** – Time series extension built on PostgreSQL.

#### Industrial Automation

- **Data Ops**  
  - *(Include any additional data operations templates as needed)*
- **Historians**
  - **Timebase Historian** – Historian for storing and querying time series data.
- **Platforms**
  - **Ignition** – SCADA/industrial application platform.
  - **Ignition Edge** – Edge computing variant of the Ignition platform.
- **Simulation**
  - **PackML Simulator** – Tool for simulating packaging machine logic.

#### Low Code

- **Appsmith** – Framework for building internal tools.
- **Grafana** – Analytics and monitoring platform.
- **n8n** – Workflow automation tool.
- **Node-RED** – Flow-based programming tool for wiring together devices and APIs.

#### Messaging

- **EMQX** – High-performance MQTT broker.
- **HiveMQ Edge** – Lightweight MQTT broker for edge environments.
- **Mosquitto** – Simple and efficient MQTT broker.
- **NATS** – Cloud-native messaging system.

### Stacks

This repository includes a `Stacks` directory that contains additional Docker Compose stacks designed for use with Portainer. More stacks will be added over time to expand the available deployment options.

## How to Use These Templates

### Deploying Portainer Stacks from Git

Instead of manually copying Compose files, you can configure Portainer to pull and deploy them directly from this Git repository.

#### **Steps to Use Git for Portainer Stacks:**

1. **Navigate to Stacks in Portainer**
   - Log into your Portainer instance.
   - Go to **Stacks** and click **Add Stack**.

2. **Select Git Repository as the Deployment Method**
   - Instead of pasting Compose YAML, select **Git Repository**.

3. **Enter Your Repository Details**
   - **Repository URL**:  

     ```bash
     https://github.com/DMDuFresne/Portainer-Templates.git
     ```

   - **Compose Path**:  
     Enter the relative path to the specific Compose file within the repo.  
     Example:  

     ```bash
     Services/Databases/Document/mongodb/docker-compose.yml
     ```

4. **Enable Automatic Sync (Optional)**
   - Check the **Automatic Updates** option if you want Portainer to periodically pull updates from the Git repo.

5. **Deploy the Stack**
   - Click **Deploy the Stack** to start the service.

### Alternative: Importing Templates into Portainer

If you prefer to use Portainer Templates:

1. **Go to Settings > Templates**.
2. Click **Add Template** and enter the necessary details (name, description, and link to the compose file in this repository).
3. Save the template and deploy from the Templates view.

### Customizing Deployments

- Each template includes comments and configuration options. Modify environment variables, volume mappings, and network settings as required by your deployment environment.

## Contributing

Contributions are welcome! If you have improvements, additional Docker Compose examples, or new service templates to add, please open an issue or submit a pull request. Follow the repository's coding and documentation guidelines.

## License

This project is licensed under the [MIT License](LICENSE).
