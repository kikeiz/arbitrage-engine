# Arbitrage Engine

> Marketplace research and integration platform for supplier catalog analysis, product matching, pricing intelligence, and commerce workflow automation.

## Overview

Arbitrage Engine is a backend platform currently under active development.

The project is designed to connect supplier catalogs with online marketplaces through official APIs in order to analyze product availability, pricing, fees, stock, and potential commercial opportunities.

The long-term goal is to provide a modular integration layer capable of working with multiple suppliers and marketplaces without coupling the core business logic to any specific external platform.

## Current Status

**Development / MVP**

The current version focuses on read-only marketplace research and supplier catalog integration.

Implemented capabilities include:

- Supplier catalog ingestion
- Product and variant normalization
- Supplier price and stock retrieval
- Multi-currency support
- Exchange-rate normalization
- Marketplace price analysis
- Marketplace fee abstraction
- Opportunity evaluation
- Concurrent asynchronous API integrations
- Extensible supplier and marketplace adapters

Transactional operations such as automated listing creation, order placement, and fulfillment are not enabled in the current MVP.

## Architecture

The project follows Domain-Driven Design and Hexagonal Architecture principles.

```text
External Suppliers
        │
        ▼
Supplier Adapters
        │
        ▼
Supplier Catalog
        │
        ├──────────────┐
        │              │
        ▼              ▼
    Products     Supplier Offers
        │              │
        └──────┬───────┘
               │
               ▼
       Marketplace Adapters
               │
               ▼
      Marketplace Snapshots
               │
               ▼
      Opportunity Evaluation
               │
               ▼
         Ranked Results
