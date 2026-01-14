---
layout: page
title: FolioVerse
description: From Interactive Binder to Event Infrastructure Platform
img: assets/img/dkbxtcg_logo.ico
importance: 1
category: work
related_publications: false
---

FolioVerse began as a high-fidelity prototype designed to solve a specific problem in the Trading Card Game (TCG) community: the disconnect between physical collections and digital valuation. While most collectors rely on static spreadsheets or disconnected marketplaces, FolioVerse introduces an immersive, "game-like" interface for portfolio management.

Currently built as a rapid-prototype using **Streamlit** and **Python 3.10**, the application features a skeuomorphic "Drag-and-Drop" binder system, real-time market data integration via the Pokemon TCG API, and a financial analytics dashboard.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/folio_binder.jpg" title="The Interactive Binder" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/folio_analytics.jpg" title="Market Analytics" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/folio_search.jpg" title="Card Catalog" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: The interactive "Pro Binder" allowing custom slot organization. Middle: Financial ROI tracking using real-time market data. Right: The comprehensive card search engine.
</div>

### The Engineering Challenge

While the current version demonstrates the UX potential, scaling this to support thousands of concurrent users required a fundamental architectural pivot. I am currently migrating the project from a monolithic Streamlit script to a **Microservices Architecture**.

The new backend separates concerns using **FastAPI** for high-performance REST endpoints, **PostgreSQL** with **TimescaleDB** for time-series price history, and **Docker** for containerized deployment. This shift ensures data integrity (ACID compliance) and eliminates the race conditions inherent in local file-based storage.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/architecture_diagram.jpg" title="System Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/code_snippet.jpg" title="FastAPI Code" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The Roadmap: Transitioning to a containerized microservices architecture with dedicated Identity, Inventory, and Analytics services.
</div>

The platform expansion includes three innovative pillars:

1.  **The Live Bounty Board:** A reverse-marketplace where attendees broadcast "Wants" (e.g., "Looking for Gold Star Rayquaza") to vendors in the room, solving the liquidity problem at shows.
2.  **Geo-Fenced Inventory:** Utilizing **PostGIS**, the app connects buyers with verified inventory located physically nearby, creating a digital layer over the convention floor.
3.  **Tiered Verification:** Implementing a "Proof of Stock" system where vendors gain trust badges by uploading real-time photos of high-ticket items, verified by computer vision models.

By bridging the gap between the physical excitement of a card show and the efficiency of database engineering, this project moves beyond simple tracking to become critical infrastructure for the collectibles economy.
