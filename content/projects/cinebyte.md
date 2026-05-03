---
title: "CineByte — Movies & TV Discovery App"
description: "A full-stack web application for discovering movies and TV shows, with TMDb-powered browsing, advanced search, JWT authentication with email verification, and a personal favorites system. Built with React, TypeScript, and Express."
tech_stack:
  - "React"
  - "TypeScript"
  - "Node.js"
  - "JavaScript"
live_url: "https://github.com/LuisAPR1/web-api-integration-app"
live_label: "View on GitHub"
weight: 40
---

<div class="mt-8">

A complete two-tier movie discovery platform: a React + TypeScript frontend talking to a typed Express backend, with The Movie Database (TMDb) as the data source.

## Frontend

- **React 18 + TypeScript** for the UI, with **Material-UI** components and Styled Components for theming.
- **React Router DOM** for client-side routing across browse, search, detail, and account pages.
- **Axios** HTTP client with a typed API service layer.
- **Discovery surfaces**: popular, top-rated, now playing, and upcoming movies; popular, top-rated, and currently airing TV shows.
- **Real-time search** with debounced TMDb queries.
- **Filter bar**: filter by genre, certification, and year.
- **Movie detail view**: cast, crew, ratings, reviews.
- **Account features**: profile editing, favorites add/remove, persisted server-side per user.
- **Responsive design** that works on phones and desktops.

## Backend

- **Express + TypeScript** REST API.
- **JWT authentication** with bcrypt password hashing.
- **NeDB** lightweight document database for users and favorites.
- **Email verification** at registration via Nodemailer + SMTP, with an activation token round-trip.
- **UUID** for stable identifiers.
- **Input validation** at every endpoint.

## API surface

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/register` | Create a new user, send activation email |
| `GET` | `/activate?token=...` | Activate the account |
| `POST` | `/login` | Issue a JWT |
| `GET` / `PUT` | `/profile` | Read or update the authenticated profile |
| `GET` / `POST` / `DELETE` | `/favorites` | Manage the user's favorite movies and TV shows |

## Why it matters

CineByte is the project where I focused on **shipping a polished product end-to-end**: typed contracts on both sides of the wire, real authentication (not just a session cookie), real email verification (not a console log), and a UI that doesn't feel like a homework submission. It's also a clean reference for how I structure a TypeScript monorepo with separate `client/` and `server/` packages.

</div>
