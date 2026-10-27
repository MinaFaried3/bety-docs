---
name: dash-system-architect
description: Senior Principal Architecture skill for designing backend APIs (.NET 8+ Monolith), Flutter frontend architectures, real-time location streaming (SSE/WebSockets), H3 geospatial dispatch, pricing engines, and cancellation logic for Dash.
---

# Dash System Architecture & API Design Skill

This skill governs architectural decisions and code implementation standards across the Dash Ride-Sharing and Package Delivery platform.

## 🔗 GitHub Relative Hyperlink Rule (MANDATORY)
All cross-document references in markdown files MUST use relative file paths (e.g. `[headers.md](./headers.md)` or `[headers.md](../headers.md)`). Never use `file:///...` URIs.

## 🗣️ Architectural Pre-Flight Rule (MANDATORY)
Every week's Architectural Discussion & Technical Decision Points (Section 🗣️) MUST be pre-discussed and documented in the preceding week's implementation plan (Week N-1) to ensure Week N is ready for immediate, direct code implementation without blocking decision delays.

## 🏗️ Technology Stack Standards

### 1. Backend (.NET 8+ Monolithic Architecture)
- **Framework:** ASP.NET Core Web API, Single Modular Monolith codebase.
- **Module Boundaries:** Isolated by namespace (`src/Modules/Identity`, `src/Modules/Trips`, `src/Modules/Drivers`, `src/Modules/Pricing`, `src/Modules/Delivery`, `src/Modules/Dashboard`).
- **Data Stores:** SQL Server (relational entities, transactions, spatial columns) + Redis (location caches, H3 driver index, pub/sub, distributed locks).
- **Communication:** MediatR / System.Threading.Channels internal event bus. Monolithic WebSockets for Driver GPS/Offer streams, Server-Sent Events (SSE) for Rider live trip updates.

### 2. Frontend (Flutter Mobile & Web Dashboard)
- **Targets:** Android & iOS (Rider/Driver Mobile Apps), Web (Admin Dashboard).
- **State Management:** Cubit (`flutter_bloc`) using sealed classes for states.
- **Dependency Injection:** `get_it`.
- **API Client:** `Dio` + `Retrofit`, returning `Dartz` `Either<Failure, T>`.
- **Localization:** `easy_localization` (en-US and ar-SA ONLY).

---

## 📋 API Contract Rules

1. **Request Rules ([base_request.md](./base_request.md)):**
   - GET parameters flat & static: `page`, `perPage`, `search`, `sortBy`, `sortOrder`.
   - Operators: `Neq`, `Gt`, `Gte`, `Lt`, `Lte`, `Like`, `In`, `Nin`, `From`/`To`, `IsNull`, `IsNotNull`.
   - Update mutations: Form-only (flat object), List-only (`UpdateListObject` containing `created`, `updated`, `deleted`), Composite (unmodified lists = `null`).

2. **Response Rules ([base_response.md](./base_response.md)):**
   - Root wrapper: `meta` (code, success, message, version, timestamp), `data`, `cache`, `error`.
   - Single list endpoints (Case A): `items` and `meta` directly under `data`.
   - Multi-resource / Composite endpoints (Case B): Paginated lists nested under descriptive keys (e.g. `active_rides`).
   - Caching: Controlled via `X-Request-General-Cache` and `X-Request-Personal-Cache`.

3. **Header Rules ([headers.md](./headers.md)):**
   - Dio client headers including app context (`fcm-token`, `env`, `appName`, `packageName`, `version`, `buildNumber`, `deviceId`, `platform`).

4. **Dashboard Screens Tree Schema Standard:**
   - Screens tree payload returned in Auth Login or User Info MUST conform to: `id` (int), `name` (single localized string resolved from `Accept-Language`), `icon` (string), `route` (string for leaf screens, `null` for parent modules), `is_module` (boolean), `permission` (object `{ view: bool, add: bool, update: bool, delete: bool }`), and `children` (array `[...]` for parent modules, `null` for leaf screens). Must be synchronized with [dashboard_screens_seed.json](./dashboard_screens_seed.json).
