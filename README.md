# Inventory Platform

A production-grade Inventory Management Platform built twice, independently, in two different backend ecosystems — Django/Python and Spring Boot/Java — as a long-term engineering apprenticeship. This is not a tutorial project. The goal is to build real, correctness-sensitive software (inventory, stock, reservations, orders) and a genuinely production-shaped AI/RAG chatbot on top of it, deeply enough to reason about the engineering tradeoffs myself rather than just following steps.

## Learning Objective

Build independent capability across programming fundamentals (DSA), backend engineering (Django and Spring Boot), databases (PostgreSQL), security, testing, DevOps, and applied AI (RAG, tool calling, agentic workflows) — using one continuous, realistic domain instead of scattered demos.

## Current Status

- **Day:** 1
- **Phase:** Environment setup
- **Track:** Common (machine audit, both ecosystems)

- **Day 2:** VS Code environment configured for Python + Java; known limitation documented (Java extension Run/Debug fails on unmanaged/loose .java files without a Maven project — resolves once Spring Boot project exists).

- **Day 3:** Practicing Git fundamentals on a dedicated branch (day/03-git-fundamentals) — staging, diffing, and committing deliberately.

## Technology Tracks

This project has two deliberately separate backend implementations of the same domain:

- **`backend-django/`** — Python + Django + Django REST Framework + PostgreSQL + Redis + RAG stack (pgvector, Neo4j)
- **`backend-spring/`** — Java + Spring Boot + Spring Data/JPA + PostgreSQL + Redis + Kafka + Spring Security + Spring AI + RAG stack

They are not merged. Each is built and evaluated on its own merits, and compared only after both are substantially built.

## Repository Structure

    inventory-platform/

├── docs/ # environment records, architecture notes, ADRs
├── backend-django/ # Track 1: Django implementation
├── backend-spring/ # Track 2: Spring Boot implementation
├── scripts/ # automation/setup scripts
└── README.md

## Verifying the Environment

See `docs/environment/day-01-environment.md` for the verified toolchain versions and how to reproduce this setup on a new machine.

## Development Principles

- Verify before changing — don't reinstall or reconfigure something that already works.
- Make the environment observable — if you can't measure a version, you don't know the environment.
- Make setup reproducible — another developer should be able to recreate it from `docs/`.
- Don't add complexity before it's needed — no Kafka, Kubernetes, Neo4j, microservices, or RAG infrastructure until a real problem justifies it.
