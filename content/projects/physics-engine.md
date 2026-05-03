---
title: "2D Physics Engine"
description: "An interactive 2D physics sandbox built from scratch with p5.js — rigid body dynamics, AABB collision detection, and Verlet integration for stable, energy-conserving simulations. Live in the browser."
tech_stack:
  - "JavaScript"
  - "HTML"
  - "CSS"
live_url: "https://luisapr1.github.io/PhysicsEngine/"
live_label: "Try the live demo"
weight: 100
---

<div>

The interactive playground is **live**: <a href="https://luisapr1.github.io/PhysicsEngine/" target="_blank">luisapr1.github.io/PhysicsEngine</a>.

## What it does

- **Real-time control** over mass, friction, and restitution.
- **Predictive trajectory** visualization for projectile motion.
- **Custom environment builder** — drop blocks, set their properties, watch them interact.
- A modern dark-themed control panel.

## Technical decisions

### Verlet integration over Euler

The simulation uses **Verlet integration** instead of the simpler explicit Euler method. Euler integration (`position += velocity * dt`) is straightforward but suffers from **energy drift** — kinetic energy slowly grows or shrinks, and the simulation eventually destabilizes, especially under collision constraints.

Verlet integration gives you:

- **Energy conservation** — total system energy stays well-behaved over long simulations.
- **Numerical stability** — implicit velocity correction handles collision constraints far more robustly.

### Collision system

| Component | Implementation |
|---|---|
| Detection | AABB (Axis-Aligned Bounding Box) for cheap overlap testing |
| Resolution | Position projection to resolve penetration |
| Bounce | Reflection of the previous-step position across the collision normal |
| Friction | Continuous force application based on normal force × combined friction coefficients |

Reflecting the *previous position* (rather than negating velocity) is the natural way to bounce in Verlet — there is no explicit velocity vector to flip.

## Why it matters

Building a physics engine from scratch is a great forcing function for the parts of game-like programming you usually take for granted: numerical stability, fixed-vs-variable time steps, the difference between "looks right at 60 fps" and "stable under load". And p5.js makes the rendering side disappear so you can focus on the math.

</div>
