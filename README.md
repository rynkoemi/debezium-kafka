# 📦 Debezium + Kafka Docker Setup

This repository contains a Docker Compose configuration for running a local [Debezium](https://debezium.io/) + [Apache Kafka](https://kafka.apache.org/) stack, along with a sample JSON connector configuration to enable **Change Data Capture (CDC)** from a PostgreSQL database.

---

## 🧰 What's Included

- **`docker-compose.yaml`**  
  Defines and orchestrates containers for:
  - Apache Kafka
  - Zookeeper
  - Debezium Kafka Connect
  - PostgreSQL database

- **`debezium-connector.json`**  
  A sample configuration file used to register a PostgreSQL source connector with Debezium.

---

## 🚀 Getting Started

### 🔧 Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [WSL 2](https://docs.microsoft.com/en-us/windows/wsl/) if you're on Windows

### ▶️ Spin Up the Stack

```bash
docker-compose up -d
```

## 🔌 Register the Debezium Connector
Once the containers are up and running, register the connector using the included JSON file:

```bash
curl -X POST -H "Content-Type: application/json" \
     --data @debezium.json \
     http://localhost:8083/connectors
```
If successful, Debezium will begin streaming change events from the configured PostgreSQL database.

## 🛠️ Customization
To change the connector settings (e.g. database name, username, table include list), edit the debezium.json file before posting it to the Kafka Connect REST endpoint.
