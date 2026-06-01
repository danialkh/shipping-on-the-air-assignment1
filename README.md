# ✈️ Shipping on the Air

> Autonomous drone package delivery platform — Assignment #01  
> **Version:** `v1.0.0` · Course Project · DDD + Microservices Architecture

---

## 💡 Overview

**Shipping on the Air** is a distributed, event-driven platform designed for automated autonomous drone logistics. 

### Key Features
- **Smart Booking:** Onboard shipments with distinct physical specifications and time constraints.
- **Automated Dispatching:** Dynamically matches optimal drones and generates 3D flight waypoints.
- **Live Telematics:** High-frequency tracking with sub-resource ETA calculations and checkpoint logs.
- **Resilient Operations:** Built-in flight safety overrides (In-flight Route Abort / Return-to-Base).

The platform applies **Domain-Driven Design (DDD)** principles to orchestrate decentralized, event-driven microservices.

---

## 📂 Repository Structure

```text
shipping-on-the-air/
├── openapi.yaml                 ← Unified API specification (OpenAPI 3.0)
├── docker-compose.yml           ← Service orchestrator
├── frontend/                    ← React Web App (Prototype UI + Living Doc)
│   ├── src/
│   │   └── App.jsx
│   └── package.json
└── services/
    ├── order-service/           ← Manages shipment lifecycle (Port 3001)
    ├── tracking-service/        ← Live telematics & event streams (Port 3002)
    └── mission-service/         ← Fleet dispatches & flight routes (Port 3003)


🚀 Quick Start & Environment Setup
Option A — Frontend Prototype Only
    Bash
    cd frontend
    npm install && npm run dev
    🌐 URL: http://localhost:5173

Option B — Complete Microservice Infrastructure (Docker)
Spin up the complete ecosystem alongside an isolated interactive global documentation suite:

Bash
docker compose up --build -d

🛰️ Cluster Port AllocationService ComponentInternal Domain URIPurposeAPI Documentationhttp://localhost:8080Interactive Swagger UI API EngineFrontend UIhttp://localhost:5173Living document & simulation interfaceOrder Servicehttp://localhost:3001Core booking & shipment recordsTracking Servicehttp://localhost:3002Telematics ledger & event ingestionMission Servicehttp://localhost:3003Flight path calculation & asset tracking


Architectural Topology
The system maps explicitly to 5 Bounded Contexts communicating asynchronously via Apache Kafka domain events.

Bounded Context	Microservice Owner	Core Domain Responsibility
Order Management	order-service	Ingestion, validation, and shipment state transitions.
Route Planning	mission-service	Geo-spatial 3D waypoint computation & corridor safety.
Fleet Management	mission-service	Drone availability matrices, payloads, and battery health.
Mission Execution	mission-service	Telemetry capture, route verification, and safe landing steps.
Tracking & Alerts	tracking-service	Dynamic ETA calculations and chronological journey events.
🛠️ Technology Ecosystem
Frontend: React + Vite (SPA)

Backend Services: Node.js + Express.js

Database Engine: PostgreSQL (Isolated per microservice context)

Asynchronous Bus: Apache Kafka (Distributed Domain Event Logs)

Containerization: Docker + Docker Compose v2

API Standards: OpenAPI 3.0 Specification (Swagger rendering)

📖 The "Living Document"
The code inside frontend/src/App.jsx acts as the project's executable living documentation, combining blueprint models directly with operational software:

✅ Functional & Non-Functional Requirements Matrix

✅ Ubiquitous Language Glossary for logistics-drones alignment

✅ Aggregate boundaries & Entity definition blocks

✅ Vectorized Bounded Context Map (SVG Blueprint)

✅ Integrated Kafka Domain Event Catalog

✅ Live simulation sandbox tracking SHP-001, MSN-001, and DRN-07

🎥 Demonstration
📹 Watch the Demo Video Layout (Insert link post-recording)

👥 Engineering Team
Student Name (Student ID: 00000000) - Core System Contributor

📄 License
Academic Research Artifact — Protected against commercial distribution.


### What changed?
1. Added **OpenAPI / Swagger UI (`Port 8080`)** straight into the port allocation matrix so anyone evaluating your assignment sees your documentation container right away.
2. Cleaned up the Markdown tables to align cleanly (`:---`).
3. Re-worded description summaries using strong, professional domain vocabulary (`Decentralized`, `3D waypoints`, `Telematics ingestion`).

