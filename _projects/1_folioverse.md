---
layout: page
title: FolioVerse
description: Creating a TCG Portfolio Tracker
img: assets/img/dkbxtcg_logo.ico
importance: 1
category: work
related_publications: false
---

What started as a high-fidelity prototype for collectors is evolving into a comprehensive infrastructure platform for the live events industry. This project represents a journey from a single-user tool ("FolioVerse") to a multi-tenant SaaS ecosystem ("VenueGrid").

### Live Application

You can explore the current functional prototype here:  
**[Launch FolioVerse Web App](https://folioverse.streamlit.app/)**

---

### Phase 1: The Prototype (FolioVerse)

The initial concept, **FolioVerse**, was built to solve a specific problem in the Trading Card Game (TCG) community: the disconnect between physical collections and digital valuation. Most collectors rely on static spreadsheets or disconnected marketplaces. I wanted to create an immersive, "game-like" interface for portfolio management.

Built as a rapid prototype using **Python** and **Streamlit**, the current application features:

- **Immersive Binder:** A skeuomorphic "drag-and-drop" interface that allows users to organize digital cards exactly as they would in a physical binder.
- **Market Data Engine:** Real-time integration with the Pokemon TCG API to track historical pricing and market movers.
- **Portfolio Analytics:** A financial dashboard calculating ROI, win/loss metrics, and set completion percentages.
- **Cloud Database:** Migrated from local storage to **PostgreSQL (Neon)** to support persistent user accounts and global access.

### Phase 2: The Engineering Pivot

While the Streamlit prototype demonstrated valuable UX concepts, scaling it to support thousands of concurrent users required a fundamental architectural shift. I am currently migrating the project from a monolithic script to a **Cloud-Native Microservices Architecture**.

This migration addresses critical production constraints:

- **Concurrency:** Utilizing **PostgreSQL** to handle simultaneous writes and ACID transactions, moving away from local file-based storage.
- **Performance:** Decoupling the frontend from the logic by implementing a **FastAPI** backend. This separates the "View" layer from heavy data processing.
- **Scalability:** Containerizing services with **Docker** and **Kubernetes** to allow independent scaling of the Inventory Service versus the Analytics Engine.

This project showcases full-stack capability: from intuitive frontend UX design to complex, distributed backend systems engineering.
