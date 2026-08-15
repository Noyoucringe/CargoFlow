# CargoFlow — Cloud-Native Logistics Tracking Platform

CargoFlow is an enterprise-grade, cloud-native logistics tracking application built using **Service-Oriented Architecture (SOA)** and **Microservices**. It addresses real-world logistics tracking problems — real-time shipment visibility, intelligent search, and AI-powered insights — using a scalable, event-driven backend.

Built for the **SOA Programming and Microservices** course.

---

## Team

| Roll No | Name |
|---|---|
| 2410030030 | T.G.S.S. Rohit |
| 2410030128 | P. Anirudh |
| 2410030129 | P. Srirama Bharath |

**Instructor:** Mr. Chanda Raj Kumar

---

## Overview

Each business capability is built as an **independent Spring Boot microservice**, with its own MongoDB database. Services communicate via:

- **REST APIs** — synchronous, request/response communication
- **Apache Kafka** — asynchronous, event-driven communication

Cloud-native infrastructure is provided by **Spring Cloud Eureka** (service discovery), **Spring Cloud Gateway** (single entry point), and **Config Server** (centralized configuration).

---

## Microservices

| Service | Responsibility | Database |
|---|---|---|
| Authentication Service | Login, JWT issuance & access control | `auth_db` |
| Domain Service | Core logistics/business domain entities | `domain_db` |
| Workflow Service | Orchestrates shipment & tracking workflows | `workflow_db` |
| Notification Service | Real-time alerts & updates | `workflow_db` |
| Analytics Service | KPIs, dashboards & business insights | `analytics_db` |
| AI Assistant Service | Natural-language queries, semantic search & recommendations | `ai_db` |

---

## AI Features (Powered by MongoDB)

1. **Aggregation Pipeline** — dashboards, KPIs, reports and business insights
2. **Atlas Search** — intelligent full-text search across business entities
3. **Atlas Vector Search** — semantic search for natural-language discovery
4. **RAG with MongoDB** — retrieves relevant documents before generating AI responses
5. **AI Agent with MongoDB** — performs domain-specific tasks using enterprise data

---

## Tech Stack

**Backend:** Spring Boot, Spring Cloud Eureka, Spring Cloud Gateway, Config Server
**Database:** MongoDB Atlas
**Messaging:** Apache Kafka
**Security:** JWT
**Testing:** JUnit
**DevOps:** Docker, GitHub Actions
**Cloud:** AWS / Azure

---

## Architecture Flow

```
Client → Gateway → Eureka (service discovery) → Microservices (REST + Kafka) → Config Server
                                                          ↓
                                        JWT Security + Docker + CI/CD → AWS/Azure
```

1. **Gateway** — single entry point for all client requests
2. **Eureka** — service discovery & registration
3. **Microservices** — handle business logic, communicate via REST (sync) and Kafka (async)
4. **Config Server** — centralized configuration for all services
5. **Security & Delivery** — JWT auth, Dockerized services, CI/CD via GitHub Actions, deployed to AWS/Azure

---

## Getting Started

```bash
# Clone the repository
git clone https://github.com/<your-username>/cargoflow.git
cd cargoflow

# Build each microservice
./mvnw clean install

# Run with Docker Compose (if configured)
docker-compose up
```

> Update this section with actual setup steps once your local run/deploy process is finalized.

---

## Project Status

🚧 In development — built as part of the SOA Programming and Microservices course project (Review 1).
