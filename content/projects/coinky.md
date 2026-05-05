---
title: "Digital Banking System"
description: "Web banking platform built on a custom PHP MVC architecture (no external framework). Manages three account types (Main, Savings, Reserve) with inter-account transfers, transaction history, real-time balance charts (Chart.js), an administrative panel, and security via password_hash and prepared statements."
tech_stack:
  - "PHP"
  - "MySQL"
  - "JavaScript"
  - "Chart.js"
  - "Bootstrap"
live_url: "https://github.com/LuisAPR1/Coinky"
live_label: "View on GitHub"
group: "Full-Stack & Web"
weight: 100
---

<div>

A complete digital banking experience in PHP, built end-to-end on top of a hand-rolled MVC core (no Laravel, no Symfony — just routing, controllers, models, and views I wrote myself).

## What it does

- **Three account types per customer**: a Main account for daily transactions, Savings for long-term goals, and a Reserve for emergencies.
- **Inter-account transfers** with intuitive sliders and balance validation in real time.
- **Transaction history** per account, with pagination and filtering.
- **Balance evolution charts** powered by Chart.js — see your account trends over time.
- **Currency converter** built in for quick cross-currency lookups.
- **Profile management**: edit personal data, change password, upload a profile photo.

## Admin panel

A separate administrative surface (`/admin/`) for:

- Listing all registered customers.
- Activating / deactivating accounts.
- Monitoring system-wide transactions.

## Architecture

- **MVC built from scratch** in PHP — controllers, models, views, layouts, and a custom routing system (`rotas.php` / `rotas_admin.php`). No external framework.
- **MySQL** persistence with prepared statements throughout (no string-built SQL).
- **Composer** for the autoloader and a small set of helpers.
- **`password_hash()`** for credentials; sessions guard every authenticated page; permission checks gate the admin area.

## Frontend stack

- **Chart.js** for the balance trend lines.
- **Circle Progress** for the dashboard's circular balance visualization.
- **FontAwesome** for iconography.
- **jQuery** for DOM and AJAX glue.
- Modern responsive CSS — works on phones and desktops.

</div>
