---
title: "Snake Game Remix"
description: "OOP remake of classic Snake with both graphical (Swing) and textual (CLI) interfaces. Features manual and automatic (pathfinding) play modes, customizable arena and food types, dynamic rotating obstacles, and a leaderboard — built with OOP patterns (Singleton, Abstract Factory, Strategy) and JUnit-tested."
tech_stack:
  - "Java"
  - "Swing"
  - "JUnit"
live_url: "https://github.com/LuisAPR1/OOP-Remix-of-Snake-Game"
live_label: "View on GitHub"
group: "Games & Graphics"
weight: 120
---

<div>

A remake of Snake built for the **Object-Oriented Programming** course, with a deliberate emphasis on clean OOP structure: separate `Core/`, `Geometry/`, and `UI/` packages, JUnit tests for both the core game logic and the geometry primitives.

## What it does

### Two interfaces, same engine

| Interface | Tech | Use case |
|---|---|---|
| Graphical | Java Swing GUI | Modern visual rendering |
| Textual | Console | Terminal enthusiasts |

Both share the exact same core engine — the UI is a thin presentation layer over `Arena`, `Snake`, `AbstractFood`, and `Obstacle`.

### Two play modes

- **Manual**: WASD or arrow keys.
- **Automatic**: an AI pathfinding algorithm steers the snake toward food while avoiding obstacles and itself.

### Customization

| Option | Effect |
|---|---|
| Arena dimensions | Custom width and height |
| Snake head size | Difficulty knob |
| Food type | Circle or square |
| Rasterization | Filled or outlined |
| Obstacles | Static or **dynamic** (rotating around a custom pivot point) |
| Scoring | Configurable points per food item |

Dynamic obstacles rotate around custom pivots — the collision system has to handle moving geometry, which made the AABB / point-in-polygon checks in `Geometry/` worth thinking about properly.

### Leaderboard

Player scores persist to `rank.txt` and are displayed at the end of each session, so high scores survive restarts.

### Test coverage

The project ships with JUnit 5 tests for both the core (`POOSnake/Core/CoreTests/`) and the geometry primitives (`POOSnake/Geometry/GeometryTests/`) — runnable via the bundled `junit-platform-console-standalone` jar.

## Why it matters

This was the project where I really internalized **separation of concerns** and the **factory / strategy / abstract-base-class** patterns: the core engine doesn't know whether it's being rendered to a JFrame or to stdout, food types are swappable through a common abstract base, and the AI mode plugs into the same `Snake` movement interface as a human player. Built in collaboration with José Lima and Pedro Ferreira.

</div>
