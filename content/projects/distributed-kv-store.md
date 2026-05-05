---
title: "Distributed Key-Value Storage System"
description: "Fault-tolerant distributed key-value store with strong consistency and high availability. Multi-tier architecture (FastAPI + Redis + RabbitMQ + CockroachDB) deployed cloud-native on Kubernetes with Horizontal Pod Autoscaling, Prometheus/Grafana monitoring, and continuous health checks."
tech_stack:
  - "Python"
  - "FastAPI"
  - "Redis"
  - "RabbitMQ"
  - "CockroachDB"
  - "Docker"
  - "Kubernetes"
live_url: "https://github.com/LuisAPR1/Distributed-Key-Value-Storage-System"
live_label: "View on GitHub"
group: "Distributed Systems & Backend"
weight: 10
---

<div class="mt-8">

A production-shaped distributed key-value store built for the **Parallel and Distributed Systems** course. The architecture explicitly addresses the four canonical distributed-systems concerns: **concurrency, scalability, fault tolerance, and consistency**.

## Architecture

```
                      ┌─────────┐
                      │ Client  │
                      └────┬────┘
                           ▼
                  ┌───────────────────┐
                  │ Nginx Load Balancer│
                  └──┬─────────────┬──┘
                     ▼             ▼
              ┌──────────┐  ┌──────────┐
              │ API Node │  │ API Node │
              └─────┬────┘  └────┬─────┘
                    │            │
        ┌───────────┴────────────┴────────────┐
        ▼                                     ▼
  ┌──────────┐                       ┌────────────────┐
  │  Redis   │                       │   RabbitMQ     │
  │ +Sentinel│                       │   (workers)    │
  └─────┬────┘                       └────────┬───────┘
        ▼                                     ▼
  ┌──────────────┐                    ┌──────────────┐
  │ CockroachDB  │                    │  Consumer    │
  │   cluster    │                    │   workers    │
  └──────────────┘                    └──────────────┘

   Prometheus + Grafana   |   Autoscaler   |   Health checks
```

## What I built

### REST API

A FastAPI service exposing `PUT(key, value)`, `GET(key)`, and `DELETE(key)`. Stateless API nodes sit behind Nginx so the system scales horizontally with zero changes to the application code.

### Caching layer with failover

Redis provides a hot-path cache; **Redis Sentinel** continuously monitors the master and performs automatic failover so an unhealthy primary doesn't take the system down.

### Persistent storage

**CockroachDB** stores the canonical data. It's a distributed SQL database with **ACID transactions**, automatic replication, and Raft-based consensus — meaning data survives node failures and remains strongly consistent.

### Async processing

Heavy or batched operations land on a **RabbitMQ** message queue and are processed by consumer workers. This decouples request latency from work latency and lets the system absorb traffic bursts gracefully.

### Observability

A **Prometheus + Grafana** stack scrapes metrics from every component (API latency, cache hit rate, queue depth, DB query times). I built dashboards for the four pillars: latency, errors, saturation, and traffic.

### Autoscaling and health checks

A custom autoscaler monitors load and brings additional API nodes / workers online (or removes them) automatically. Health checks at every layer trigger alerts before failures cascade.

### Reproducibility

The whole stack — Nginx, FastAPI, Redis, Sentinel, RabbitMQ, CockroachDB, Prometheus, Grafana, autoscaler — boots from a single `docker-compose up`. The repo also ships with a **cloud migration plan** (proposed AWS / Azure / GCP architecture, phased migration, security and cost analysis).

## Why it matters

This project is the inverse of DepChain: where DepChain is about correctness under Byzantine adversaries, this one is about staying online and fast as load and failures grow. Together they cover the two halves of dependable distributed systems.

</div>
