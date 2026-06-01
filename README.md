# ✈️ Shipping on the Air

> Drone-based package delivery platform — Assignment #01  
> Version: `v1.0.0` · Course project · DDD + Microservices

---

## What is this?

**Shipping on the Air** is an online system for delivering packages via autonomous drones. A customer can:

- Place a shipment request (origin, destination, weight, time window)
- Get a drone automatically assigned and a route planned
- Track the package in real time on a map
- Receive notifications at key delivery milestones

The project is built following **Domain-Driven Design (DDD)** as the methodological approach and **Microservices** as the architectural style.

---

## Repository Structure

```
shipping-on-the-air/
├── README.md
├── CHANGELOG.md
├── docker-compose.yml          ← runs all services together
├── frontend/                   ← React app (living doc + prototype UI)
│   ├── src/
│   │   └── App.jsx
│   └── package.json
└── services/
    ├── order-service/          ← manages shipment lifecycle
    ├── tracking-service/       ← real-time tracking & events
    └── mission-service/        ← drone mission orchestration
```

---

## How to Run

### Option A — Frontend only (prototype UI)

```bash
cd frontend
npm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

### Option B — Full stack with Docker (all microservices)

Make sure you have [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed, then:

```bash
docker-compose up --build
```

| Service            | URL                          |
|--------------------|------------------------------|
| Frontend           | http://localhost:5173        |
| Order Service      | http://localhost:3001        |
| Tracking Service   | http://localhost:3002        |
| Mission Service    | http://localhost:3003        |

---

## Architecture Overview

The system is decomposed into 5 bounded contexts following DDD:

| Bounded Context          | Responsibility                              |
|--------------------------|---------------------------------------------|
| Order Management         | Shipment lifecycle, customer orders         |
| Route Planning           | Geo-spatial route computation, no-fly zones |
| Fleet Management         | Drone availability and maintenance          |
| Mission Execution        | Drone mission orchestration, telemetry      |
| Tracking & Notifications | Real-time tracking, ETA, push alerts        |

Services communicate asynchronously via **Apache Kafka** domain events.

---

## Tech Stack

| Layer         | Technology                          |
|---------------|-------------------------------------|
| Frontend      | React + Vite                        |
| Order Service | Node.js + Express + PostgreSQL      |
| Tracking Svc  | Node.js + Express + PostgreSQL      |
| Mission Svc   | Node.js + Express + PostgreSQL      |
| Message Bus   | Apache Kafka                        |
| Container     | Docker + Docker Compose             |

---

## Living Document

The `frontend/src/App.jsx` file is the **living document** for this assignment. It contains:

- ✅ Functional & Non-Functional Requirements
- ✅ Ubiquitous Language glossary
- ✅ DDD Aggregate design
- ✅ Bounded Context map (with SVG diagram)
- ✅ Microservices architecture diagram
- ✅ Kafka event catalog
- ✅ Interactive prototype (shipment tracking demo)

---

## Demo Video

> 📹 [Link to demo video — add after recording]

---

## Authors

> Add your name / student ID here

---

## License

Academic project — not for commercial use.
# shipping-on-the-air-assignment1
