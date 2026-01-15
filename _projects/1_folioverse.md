---
layout: page
title: FolioVerse to VenueGrid
description: Evolving a TCG Portfolio Tracker into a Live Event Infrastructure Platform
img: 
importance: 1
category: work
related_publications: false
---

What started as a high-fidelity prototype for collectors is evolving into a comprehensive infrastructure platform for the live events industry. This project represents a journey from a single-user tool ("FolioVerse") to a multi-tenant SaaS ecosystem ("VenueGrid").

### Phase 1: The Prototype (FolioVerse)

The initial concept, **FolioVerse**, was built to solve a specific problem in the Trading Card Game (TCG) community: the disconnect between physical collections and digital valuation. Most collectors rely on static spreadsheets or disconnected marketplaces. I wanted to create an immersive, "game-like" interface for portfolio management.

Built as a rapid prototype using **Python 3.10** and **Streamlit**, the current application features:
*   **Immersive Binder:** A skeuomorphic "drag-and-drop" interface that allows users to organize digital cards exactly as they would in a physical binder.
*   **Market Data Engine:** Real-time integration with the Pokemon TCG API to track historical pricing and market movers.
*   **Portfolio Analytics:** A financial dashboard calculating ROI, win/loss metrics, and set completion percentages.

### Phase 2: The Engineering Pivot

While the Streamlit prototype demonstrated valuable UX concepts, scaling it to support thousands of concurrent users required a fundamental architectural shift. I am currently migrating the project from a monolithic script to a **Cloud-Native Microservices Architecture**.

This migration addresses critical production constraints:
*   **Concurrency:** Moving from local file-based storage (JSON) to **PostgreSQL** to handle simultaneous writes and ACID transactions.
*   **Performance:** Decoupling the frontend from the logic by implementing a **FastAPI** backend. This separates the "View" layer from heavy data processing.
*   **Scalability:** Containerizing services with **Docker** and **Kubernetes** to allow independent scaling of the Inventory Service versus the Analytics Engine.

### Phase 3: The Platform Vision (VenueGrid)

The ultimate goal of this project is **VenueGrid**, a platform designed to compete with legacy event management systems like Ticketmaster, specifically tailored for the collectibles industry.

The TCG industry suffers from a "Data Desert" at physical events—vendors have inventory that attendees can't see until they walk up to the booth, and organizers lack real-time data on floor activity. VenueGrid acts as the "Operating System" for the convention floor.

**Key Technical & Product Pillars:**

**1. The "Reverse Marketplace" (Bounty Board)**
Instead of forcing vendors to upload thousands of items, VenueGrid utilizes a "Pull" model. Attendees broadcast "Wants" (e.g., "Looking for Gold Star Rayquaza") to the network. Vendors receive real-time alerts and can "Claim" the bounty, driving foot traffic to their specific booth.

**2. Dynamic Ticketing & Identity**
To combat scalping and fraud, the platform utilizes a **Context-Aware Identity System**. Users have distinct roles (Organizer, Vendor, Attendee) depending on the event context. Tickets are generated using time-based rotating QR codes (TOTP), preventing static screenshot sharing.

**3. The Financial Ledger**
Moving beyond simple payment processing, the backend implements an immutable **Double-Entry Ledger**. This ensures perfect financial tracking for split payments (e.g., Platform Fees vs. Organizer Payouts) and enables robust auditing for high-volume transactions via Stripe Connect.

This project showcases full-stack capability: from intuitive frontend UX design to complex, distributed backend systems engineering.
