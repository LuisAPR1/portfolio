---
title: "Prototype-Based Object System for Julia"
description: "Implementation of a prototype-based object system in Julia (in the spirit of JavaScript/Self), exploring metaprogramming and dynamic delegation as an alternative to Julia's native multiple-dispatch model."
tech_stack:
  - "Julia"
  - "Metaprogramming"
live_url: "https://github.com/LuisAPR1/Prototype-Based-Julia"
live_label: "View on GitHub"
group: "Compilers & Programming Languages"
weight: 80
---

<div>

A small object system implemented in Julia, exploring an object model that's deliberately *not* Julia's. Where Julia uses **multiple dispatch** as its central abstraction, this project leans into **prototype-based programming** in the tradition of Self and JavaScript — every object is a live, extensible bag of properties, and inheritance is just a runtime delegation chain.

## What it explores

- **Prototypes over classes.** There are no class definitions; new objects are built by cloning and extending existing ones.
- **Dynamic delegation.** Property and method lookups walk a parent-prototype chain, so behavior can be shared and overridden at runtime.
- **Metaprogramming.** The system is built using Julia's macro and reflection facilities, taking advantage of the language's homoiconic AST to make the object protocol feel natural at the call site.
- **An alternative dispatch model.** Comparing prototype-based dispatch against Julia's multiple-dispatch helped me think clearly about where each model excels — flexibility and runtime extension on one side, type-driven specialization on the other.

## Why it matters

Building this was less about shipping a feature and more about deeply understanding two competing approaches to OOP. Implementing a different paradigm *inside* a strongly opinionated language forces you to confront where the host language pushes back — and that's exactly where the interesting design questions live.

</div>
