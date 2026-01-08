# NEXUS AI – Enterprise Transit System

## Overview

NEXUS AI is an **enterprise-grade, AI-driven public transit intelligence platform**. It combines real-time transit data, geospatial analysis, and explainable AI decision-making into a professional, scalable system.

This project is designed **from day one** for production use: modular architecture, clear data contracts, and separation of concerns.

---

## Core Goals

* Replace passive timetable apps with **decision-making intelligence**
* Use **real transit APIs** (Digitransit / GTFS Realtime)
* Provide a **clear, professional UI** suitable for enterprise and pilot deployments
* Be scalable to multi-city, multi-agency environments

---

## System Architecture

```
┌────────────┐
│  Frontend  │  UI, Map, User Interaction
└─────┬──────┘
      │ REST / JSON
┌─────▼──────┐
│ Edge API   │  Validation, caching, normalization
└─────┬──────┘
      │ Internal contracts
┌─────▼──────┐
│ AI Core    │  Decision logic, predictions
└─────┬──────┘
      │
┌─────▼──────┐
│ Services   │  Digitransit, GTFS Realtime
└────────────┘
```

---

## Repository Structure

```
nexus-ai/
├─ frontend/
│  ├─ index.html
│  ├─ styles/
│  │  └─ theme.css
│  ├─ ui/
│  │  ├─ topbar.js
│  │  ├─ sidepanel.js
│  │  └─ stops.js
│  ├─ map/
│  │  ├─ map-init.js
│  │  └─ vehicle-layer.js
│  └─ state/
│     └─ store.js
│
├─ ai-core/
│  ├─ walk-decision.js
│  ├─ delay-prediction.js
│  ├─ route-choice.js
│  └─ early-warning.js
│
├─ services/
│  ├─ digitransit-graphql.js
│  ├─ gtfs-realtime.js
│  └─ stops-service.js
│
├─ api/
│  ├─ edge-handler.js
│  └─ routes.js
│
├─ docs/
│  ├─ architecture.md
│  └─ decisions.md
│
├─ README.md
└─ package.json
```

---

## AI Decision Philosophy

NEXUS AI does **not** try to be a black box.

Every decision is:

* Deterministic
* Explainable
* Auditable

Example decisions:

* *Should the user walk faster or wait?*
* *Is switching to another line safer?*
* *Should the user be warned **before** movement starts?*

---

## Data Sources

* **Digitransit GraphQL** – routes, stops, departures
* **GTFS Realtime** – vehicle positions, delays
* **Geolocation API** – user movement

---

## Deployment Targets

* Frontend: Static hosting (Vercel, Netlify)
* Edge / API: Cloudflare Workers or Node.js
* AI Core: Shared logic, testable in isolation

---

## Project Status

**Phase:** Architecture locked ✅

Next phases:

1. Implement frontend modules
2. Implement backend services
3. Connect AI Core
4. End-to-end testing

---

## Guiding Principle

> *"This system should make better decisions than the user, and explain them clearly."*

---

© NEXUS AI – Enterprise Transit Intelligence
