> [!NOTE]
> Disclaimer: This project is an unofficial community-driven effort and is not affiliated with, endorsed by, or supported by Redpanda. While we strive to provide useful tools and documentation, please note that this repository is maintained independently and does not receive any official support or guarantees from Redpanda or its team. For official documentation and support, please refer to Redpanda's official resources.

# Redpanda AI Quickstart - README

This README provides an overview of the services included in the `redpanda-ai-quickstart` docker-compose setup. Each service's functionality, ports exposed, and links to web user interfaces are described for easier management.

- [Getting Started](#getting-started)
- [Deployed Services](#deployed-services)
  - [PostgreSQL (EnterpriseDB)](#postgresql-enterprisedb)
    - [pgAdmin 4](#pgadmin-4)
  - [Qdrant](#qdrant)
  - [Neo4j](#neo4j)
  - [Ollama](#ollama)
    - [Open WebUI](#open-webui)
  - [Redpanda](#redpanda)
    - [Redpanda Console](#redpanda-console)
    - [Redpanda Connect](#redpanda-connect)
- [Port Overview](#port-overview)

# Getting Started

To get started with the `redpanda-ai-quickstart`, follow these steps:

1. **Prerequisites**: Ensure you have the following installed:
   - [Docker](https://www.docker.com/get-started)
   - [Docker Compose](https://docs.docker.com/compose/install/)

2. **Clone the Repository**:
   Open a terminal and run the following command to clone the repository:
   ```
   git clone https://github.com/yourusername/redpanda-ai-quickstart.git
   ```

3. **Navigate to the Project Directory**:
   Change into the project directory:
   ```
   cd redpanda-ai-quickstart
   ```

4. **Start the Services**:
   Use Docker Compose to start all the services defined in the `docker-compose.yml` file:
   ```
   docker-compose up
   ```

5. **Access the Services**:
   Once the services are up and running, you can access their web interfaces through your browser using the following URLs:
   - PostgreSQL: [http://localhost:5050](http://localhost:5050) (pgAdmin)
   - Qdrant: [http://localhost:6333/dashboard](http://localhost:6333/dashboard)
   - Neo4j: [http://localhost:7474](http://localhost:7474)
   - Ollama Open WebUI: [http://localhost:3000](http://localhost:3000)
   - Redpanda Console: [http://localhost:8080](http://localhost:8080)

# Deployed Services

This project includes several services essential for building AI-driven applications. The following services are deployed in this setup:

1. **PostgreSQL** - A powerful relational database for data management.
2. **PgAdmin 4** - A web-based management tool for PostgreSQL.
3. **Qdrant** - A vector search engine optimized for AI workloads.
4. **Neo4j** - A graph database for managing complex data relationships.
5. **Ollama** - A service for efficient model inference for machine learning.
6. **Redpanda** - A high-performance streaming platform supporting Kafka APIs.

## PostgreSQL (EnterpriseDB)

PostgreSQL is a powerful, open-source object-relational database system used for various data management applications. This deployment uses EnterpriseDB's PostgreSQL image.

- **Service**: PostgreSQL
- **Exposed Port**: `5432` (Postgres wire protocol)
- **Login**: 
  - **Username**: `postgres`
  - **Password**: `postgres`

### PgAdmin 4

PgAdmin 4 is a web-based UI management tool for PostgreSQL databases, allowing you to easily visualize and manage PostgreSQL instances.

> [!NOTE]
> On the first time connecting to the default postgres database you may be prompted to enter a password. This is `postgres`.

- **Service**: PgAdmin 4
- **Exposed Port**: `5050` (Web UI)
- **Web UI**: [http://localhost:5050](http://localhost:5050)

## Qdrant

Qdrant is a vector search engine optimized for AI-driven use cases, enabling search over high-dimensional vector spaces such as embeddings.

- **Service**: Qdrant
- **Exposed Port**: `6333`
- **Web UI**: [http://localhost:6333/dashboard](http://localhost:6333/dashboard)

## Neo4j

Neo4j is a graph database management system designed to store and query complex relationships between data points. It is optimal for graph-like structures.

- **Service**: Neo4j
- **Exposed Ports**: 
  - `7474` (Web Interface)
  - `7687` (Bolt Protocol for driver connections)
- **Web UI**: [http://localhost:7474](http://localhost:7474)

## Ollama

Ollama provides model inference capabilities, designed to run machine learning models efficiently. It is especially useful for AI-based workloads utilizing GPUs.

- **Service**: Ollama
- **Exposed Port**: `11434` (HTTP API)

### Open WebUI

Open WebUI serves as a frontend interface to interact with the Ollama service, providing an easy way to manage and test AI models.

- **Service**: Open WebUI
- **Exposed Port**: `3000` (Web UI)
- **Web UI**: [http://localhost:3000](http://localhost:3000)

## Redpanda

> [!NOTE]
> [Redpanda Connect](https://www.redpanda.com/connect) requires an Enterprise agreement to use AI functionality. Please ensure you have an active Connect entitlement with Redpanda Data, Inc. before using it in a production capacity.

Redpanda is a high-performance streaming platform that supports Kafka APIs, allowing you to build streaming architectures without the complexity of managing ZooKeeper.

- **Service**: Redpanda
- **Exposed Ports**:
  - `19092` (Kafka External)
  - `18082` (Pandaproxy External)
  - `18081` (Schema Registry External)
  - `9644` (Admin API)

### Redpanda Console

Redpanda Console provides a web-based UI for managing Redpanda clusters. You can monitor brokers, topics, partitions, and messages.

- **Service**: Redpanda Console
- **Exposed Port**: `8080` (Web UI)
- **Web UI**: [http://localhost:8080](http://localhost:8080)

### Redpanda Connect

Redpanda Connect features a huge collection of sources, sinks, and processors to power any real-time data and AI pipelines. Create new connectors with ease, with multiple plug-in strategies, including native Go and your favorite Wasm-supported language. Use in Redpanda Cloud, run the Apache 2.0 licensed connectors for free, or pay for expert support.

- **Service**: Redpanda Connect
- **Exposed Port**: `8080` (Web UI)
- **Web UI**: [http://localhost:8080](http://localhost:8080)

---

## Port Overview

| Service         | Exposed Port | Service Port | Description                                 |
|-----------------|--------------|--------------|---------------------------------------------|
| PostgreSQL      | 5432         | 5432         | PostgreSQL database                         |
| PgAdmin 4       | 5050         | 80           | Web UI for PostgreSQL management            |
| Qdrant          | 6333         | 6333         | Vector search engine                        |
| Neo4j           | 7474         | 7474         | Web Interface for Neo4j                     |
| Neo4j           | 7687         | 7687         | Bolt Protocol for Neo4j connections         |
| Ollama          | 11434        | 11434        | AI model inference service                  |
| Open WebUI      | 3000         | 8080         | Web interface for AI model management       |
| Redpanda        | 9092         | 9092         | Kafka API (External)                        |
| Redpanda        | 8082         | 8082         | Pandaproxy API (External)                   |
| Redpanda        | 8081         | 8081         | Schema Registry (External)                  |
| Redpanda        | 9644         | 9644         | Admin API for Redpanda                     |
| Redpanda Console| 8080         | 8080         | Web UI for Redpanda Console                 |
