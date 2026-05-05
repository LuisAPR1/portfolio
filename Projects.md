# Projects

Short reference of every public project on [github.com/LuisAPR1](https://github.com/LuisAPR1), grouped by area. Stack and a one-paragraph summary for each.

---

## Distributed Systems & Backend

### Distributed Key-Value Storage System
*Python · FastAPI · Redis · RabbitMQ · CockroachDB · Docker · Kubernetes* — [repo](https://github.com/LuisAPR1/Distributed-Key-Value-Storage-System)

Fault-tolerant distributed key-value store with strong consistency and high availability. Multi-tier architecture (FastAPI + Redis + RabbitMQ + CockroachDB) deployed cloud-native on Kubernetes with Horizontal Pod Autoscaling, Prometheus/Grafana monitoring, and continuous health checks.

### DepChain — Permissioned Blockchain with BFT Consensus
*Java · Hyperledger Besu · Solidity · UDP · BLS · Ed25519* — [repo](https://github.com/LuisAPR1/Permissioned-Blockchain-with-BFT-Consensus)

Permissioned blockchain implementing the **Basic HotStuff** BFT consensus over UDP, with a layered link stack (FairLoss → Stubborn → Authenticated Perfect Links via X25519 DH + HMAC), BLS threshold-signed Quorum Certificates, EVM execution via Hyperledger Besu, and a frontrunning-resistant ERC-20 token. Tolerates `f = ⌊(n−1)/3⌋` Byzantine replicas.

---

## Data Engineering & Machine Learning

### ETL & OLAP Data Warehouse Pipeline
*SQL · Pentaho (PDI/PRD) · Mondrian · MySQL · MDX · Saiku · Docker* — [repo](https://github.com/LuisAPR1/ETL-OLAP-DataWarehouse-Pipeline)

End-to-end Business Intelligence pipeline over ~1.3M UK real-estate transaction records (HM Land Registry Price Paid Data). Includes a Kimball star schema, dual ETL implementation (Pentaho + idempotent pure SQL with recursive CTEs), Mondrian OLAP cube consumed via Saiku/MDX, and pixel-perfect PDF reports — fully Dockerized for reproducibility.

### ML Prediction Pipeline
*Python · FastAPI · Scikit-learn · Pandas* — [repo](https://github.com/LuisAPR1/ML-Prediction-Pipeline)

End-to-end Data Science web app for **flight cancellation prediction**. Includes a preprocessing pipeline (cyclic temporal encoding, ordinal encoding, MinMax scaling), six classification models (Naïve Bayes, KNN, Logistic Regression, Decision Tree, MLP, Random Forest), and FastAPI endpoints for single-flight inference and batch model evaluation.

### MNIST Digit Recognition — V2
*Java · JavaScript · HTML/CSS · MNIST* — [repo](https://github.com/LuisAPR1/Digit-Recognition-NN-V2) · [live](https://luisapr1.github.io/Digit-Recognition-NN-V2/)

From-scratch Java MLP (256 → 128, ReLU + Softmax) trained with mini-batch SGD and cross-entropy loss on MNIST, with no external ML libraries. Paired with a responsive web playground for live in-browser sketching, real-time inference, and top-5 prediction visualization.

### MNIST Digit Recognition — V1
*Java* — [repo](https://github.com/LuisAPR1/Digit-Recognition-NN)

Earlier educational feedforward neural network in pure Java (sigmoid activations + backpropagation) with MSE convergence checking and CSV weight serialization. Built without any external ML library, focused on the core mechanics of training and inference.

---

## Compilers & Programming Languages

### Tuga Compiler & Virtual Machine
*Java · ANTLR 4* — [repo](https://github.com/LuisAPR1/Compiler-For-Tuga-Language)

Full compilation pipeline for **Tuga**, an imperative language with Portuguese-based keywords. Includes ANTLR-generated lexer/parser, two-phase semantic analysis (scoped symbol table + type checking), bytecode generation, and a custom stack-based virtual machine (S-VM) supporting functions, locals, control flow, and forward references.

### Prototype-Based Object System for Julia
*Julia · Metaprogramming* — [repo](https://github.com/LuisAPR1/Prototype-Based-Julia)

Implementation of a prototype-based object system in Julia (in the spirit of JavaScript/Self), exploring metaprogramming and dynamic delegation as an alternative to Julia's native multiple-dispatch model.

---

## Full-Stack & Web

### CineByte — Movie & TV Discovery App
*React · TypeScript · Node.js · Express · NeDB · TMDb API · JWT* — [repo](https://github.com/LuisAPR1/React-Ts-REST-API-Movie-App)

Full-stack web app for movie and TV show discovery, with a React + TypeScript frontend and an Express + TypeScript backend. Integrates the TMDb API for browsing, search, and metadata, plus JWT authentication with bcrypt password hashing, SMTP-based account verification, and a per-user favorites system.

### Digital Banking System
*PHP · MySQL · JavaScript · Chart.js · Bootstrap* — [repo](https://github.com/LuisAPR1/Coinky)

Web banking platform built on a custom PHP MVC architecture (no external framework). Manages three account types (Main, Savings, Reserve) with inter-account transfers, transaction history, real-time balance charts (Chart.js), an administrative panel, and security via `password_hash` and prepared statements.

### Personal Portfolio
*Hugo · Markdown · GitHub Pages* — [repo](https://github.com/LuisAPR1/portfolio) · [live](https://luisapr1.tech)

Personal portfolio website built with Hugo and deployed automatically via GitHub Pages on every push to `main`. Showcases projects, blog posts, and CV at [luisapr1.tech](https://luisapr1.tech).

---

## Games & Graphics

### Snake Game Remix
*Java · Swing · JUnit* — [repo](https://github.com/LuisAPR1/OOP-Remix-of-Snake-Game)

OOP remake of classic Snake with both graphical (Swing) and textual (CLI) interfaces. Features manual and automatic (pathfinding) play modes, customizable arena and food types, dynamic rotating obstacles, and a leaderboard — built with OOP patterns (Singleton, Abstract Factory, Strategy) and JUnit-tested.

### 2D Physics Engine
*JavaScript · p5.js* — [repo](https://github.com/LuisAPR1/PhysicsEngine) · [live](https://luisapr1.github.io/PhysicsEngine/)

Interactive 2D physics simulation built from scratch with p5.js. Implements rigid body dynamics, AABB collision detection, friction/restitution control, and **Verlet integration** for energy-stable long-running simulations, with real-time control over body parameters.

### 3D First-Person Mini-Game
*Computer Graphics · 3D Rendering · Shading* — [repo](https://github.com/LuisAPR1/3D-1st-Person-Mini-Game)

First-person 3D mini-game built to practice real-time rendering, shading, and texturing techniques. Computer Graphics university coursework.
