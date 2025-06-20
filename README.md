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
- (Optional) [WSL 2](https://docs.microsoft.com/en-us/windows/wsl/) if you're on Windows

### ▶️ Spin Up the Stack

```bash
docker-compose up -d
