# Dash Platform — AI Architectural Rules & System Standards

> **Role & Persona:** Senior Principal System Architect & AI Technical Lead.
> **Scope:** Dash Ride-Sharing & Package Delivery Platform (Competitor to Uber, inDrive, and DiDi).
> **AI Engine Compatibility:** Antigravity (Gemini 3.6 Flash / 3.5 Flash), Claude (3.5 / 3.7 Sonnet & Opus), OpenAI (GPT-4o / o1 / o3), Grok 3, DeepSeek (V3 / R1 / V4), Nemotron, HY3, Mimo V3, Codex.
> **Supported IDEs:** Antigravity, Cursor, OpenCode, Composer, VSCode.

---

## 1. Core Architectural Principles & System Design

1. **System Architecture:**
   - **Backend:** ASP.NET Core (.NET 8+) Modular Monolith. Clean Architecture with explicit module boundaries (`src/Modules/Identity`, `src/Modules/Trips`, `src/Modules/Drivers`, `src/Modules/Pricing`, `src/Modules/Delivery`, `src/Modules/Dashboard`).
   - **Database Storage:** SQL Server (relational, transactional data, spatial indexes) + Redis (in-memory geospatial caching, driver location streams, distributed locks, pub/sub).
   - **Real-Time Protocols:** Monolithic WebSockets (Driver location & trip offer streams) + Server-Sent Events (Rider & Admin Dashboard live tracking streams).
   - **Geospatial Indexing:** Uber H3 hexagonal spatial indexing for driver proximity queries and dynamic surge cell calculation.
   - **Frontend:** Flutter (Android, iOS, Admin Web). Clean Architecture + Cubit (`flutter_bloc`) with sealed state classes (`BaseState`). Network layer using `Dio` + `Retrofit` with `Dartz` (`Either<Failure, T>`). Dual localization (`easy_localization`) for **English (en-US)** and **Arabic (ar-SA)** ONLY.

---

## 2. Multi-Document Cascading & Cross-Sync Matrix (CRITICAL RULE)

Whenever modifying any documentation or specification file, you **MUST** strictly enforce the following 7 document synchronization rules:

| Source File Modified | Trigger Event | Mandatory Cascading Updates Required |
| :--- | :--- | :--- |
| `dashboard-screen-plan.md` | Any modification to Admin Dashboard UI, screens, widgets, or workflows. | **MUST** mirror the change immediately in [dashboard-screen-plan-ar.md](./dashboard-screen-plan-ar.md) preserving complete Arabic translation integrity. |
| **Dashboard Side Menu / Screens Tree** | Any modification to side menu structure or screens tree in `dashboard-screen-plan.md`. | **MUST** immediately update [dashboard_screens_seed.json](./dashboard_screens_seed.json), [dashboard-api-flow.md](./dashboard-api-flow.md), and [implementation-plan/week-02.md](./implementation-plan/week-02.md) preserving schema rules (`id: int`, `route`, `permission: {}`, single localized `name`, `children: null` for leaves). |
| `dashboard-screen-plan-ar.md` | Any modification to Arabic Dashboard screens or localized copy. | **MUST** mirror the change immediately in [dashboard-screen-plan.md](./dashboard-screen-plan.md) preserving English design integrity. |
| **Dashboard Triad** (`dashboard-api-flow.md` OR `dashboard-screen-plan.md` OR `dashboard-screen-plan-ar.md`) | Any change in admin APIs, screens, or dashboard data flows. | **MUST** synchronize across all three files: [dashboard-api-flow.md](./dashboard-api-flow.md), [dashboard-screen-plan.md](./dashboard-screen-plan.md), and [dashboard-screen-plan-ar.md](./dashboard-screen-plan-ar.md). |
| `system-design-ride-sharing.md` | Any core system functionality, architecture, or business logic change. | **MUST** propagate changes to: [dashboard-api-flow.md](./dashboard-api-flow.md), [dashboard-screen-plan.md](./dashboard-screen-plan.md), [rider-api-flow.md](./rider-api-flow.md), and [driver-api-flow.md](./driver-api-flow.md). |
| `cancellation-pricing-guide.md` | Any pricing rule, dynamic surge, commission tier, or cancellation fee rule update. | **MUST** update [cancellation-pricing-guide.md](./cancellation-pricing-guide.md) and refactor: [system-design-ride-sharing.md](./system-design-ride-sharing.md), [driver-api-flow.md](./driver-api-flow.md), [rider-api-flow.md](./rider-api-flow.md), [dashboard-api-flow.md](./dashboard-api-flow.md), and [dashboard-screen-plan.md](./dashboard-screen-plan.md). |
| `matching_system_design.md` | Any matching algorithm, dispatch radius, H3 ring, or driver offer timeout change. | **MUST** update [matching_system_design.md](./matching_system_design.md) and cascade to: [system-design-ride-sharing.md](./system-design-ride-sharing.md), [driver-api-flow.md](./driver-api-flow.md), [rider-api-flow.md](./rider-api-flow.md), [dashboard-api-flow.md](./dashboard-api-flow.md), and [dashboard-screen-plan.md](./dashboard-screen-plan.md). |
| **API Endpoints Addition/Modification** | Any new or updated API endpoint. | **MUST** register the endpoint in [driver-api-flow.md](./driver-api-flow.md), [rider-api-flow.md](./rider-api-flow.md), or [dashboard-api-flow.md](./dashboard-api-flow.md) AND ensure complete compliance with [base_request.md](./base_request.md), [base_response.md](./base_response.md), and [headers.md](./headers.md). |

---

## 3. Strict API Contract Standards

All API requests and responses across the Dash platform **MUST** follow these exact schemas:

1. **Request Standards ([base_request.md](./base_request.md)):**
   - **Listing/Query Endpoints:** Mandatory HTTP `GET`. Flat static parameters (`page`, `perPage`, `search`, `sortBy`, `sortOrder`). Filter suffixes: `Neq`, `Gt`, `Gte`, `Lt`, `Lte`, `Like`, `In`, `Nin`, `From`/`To`, `IsNull`, `IsNotNull`. Multi-pagination requests are strictly prohibited.
   - **Mutations (Update Payloads):**
     - *Form-Only:* Flat JSON object.
     - *List-Only:* Root key matching collection name with `created` (array of objects), `updated` (array of full objects), `deleted` (array of ID objects `{ "id", "status" }`).
     - *Composite (Form + Lists):* Unmodified lists MUST be set to `null` for selective dirty tracking.

2. **Response Standards ([base_response.md](./base_response.md)):**
   - Standard wrapper structure:
     ```json
     {
       "meta": { "code": 200, "success": true, "message": "...", "version": ["v1.0.0"], "timestamp": "2026-07-23T12:00:00Z" },
       "data": { ... },
       "cache": null,
       "error": null
     }
     ```
   - **Direct Pagination (Case A):** If payload contains ONLY a single list resource, `items` and `meta` reside at `data` root.
   - **Nested Pagination (Case B):** If payload contains multiple keys, paginated lists must be nested under descriptive keys (e.g. `active_rides: { items: [...], meta: {...} }`).
   - **Cache Header Evaluation:** Controlled by `X-Request-General-Cache` and `X-Request-Personal-Cache` headers.

3. **Header Standards ([headers.md](./headers.md)):**
   - `Accept`, `Content-Type`, `Authorization: Bearer <JWT>`, `Accept-Language: en-US | ar-SA`, `X-Idempotency-Key` (for mutations), `X-App-Version`, `X-Platform`.
   - Device context injected by Dio interceptor (`fcm-token`, `env`, `appName`, `packageName`, `version`, `buildNumber`, `deviceId`, `platform`).
   - Real-time headers: `Accept: text/event-stream` & `Last-Event-ID` for SSE; query parameter `token` & `trip` for WebSockets.

4. **Media & Image Upload Standards:**
   - Any image or binary file upload (e.g., driver documents, vehicle images, color assets, payment receipts, avatars) **MUST** be sent as `multipart/form-data` with explicit boundary handling.
   - For entity creation/updating requiring image references, the image binary is uploaded via `multipart/form-data` to the dedicated media upload endpoint (`POST /api/v1/dashboard/media/upload` or `/api/v1/media/upload`), and the resulting URL/key string is passed in JSON payloads. Binary files must never be directly embedded into JSON request bodies.

---

## 4. 12-Week Roadmap & Relative Hyperlinks Governance

1. **Strict 12-Week Roadmap Cap:** The implementation plan in `implementation-plan/` is capped at exactly 12 weeks (6 sprints). No Week 13+ allowed.
2. **8-Week MVP Boundary:** Weeks 1 through 8 focus strictly on the **Passenger Transport Ride Scenario (RIDE)**. Advanced capabilities (Package Delivery, Wallet Top-ups, Driver Balance Limits, SOS Alerts, Marketing Campaigns, Ads, and Sponsorships) are post-MVP (Weeks 9-12).
3. **GitHub Relative Hyperlink Rule (MANDATORY):**
   - **NEVER** use absolute `file:///...` URIs when writing markdown hyperlinks anywhere in the workspace.
   - **ALWAYS** use relative markdown paths (e.g., `[headers.md](../headers.md)`, `[system-design-ride-sharing.md](../system-design-ride-sharing.md)`) so links work seamlessly when pushed to GitHub repositories or opened in different environments.
   - Every weekly plan file (`week-01.md` through `week-12.md`) and `README.md` **MUST** include direct relative markdown hyperlinks pointing to the corresponding main design documents (`system-design-ride-sharing.md`, `driver-api-flow.md`, `rider-api-flow.md`, `dashboard-api-flow.md`, `dashboard-screen-plan.md`, `matching_system_design.md`, `cancellation-pricing-guide.md`, `base_request.md`, `base_response.md`, `headers.md`).
4. **Architectural Pre-Flight Rule (MANDATORY):**
   - Every week's Architectural Discussion & Technical Decision Points (Section 🗣️) **MUST** be pre-discussed and documented in the preceding week's implementation plan (Week N-1).
   - This ensures that when Week N starts, all technical decisions are already resolved, enabling immediate, direct code implementation without blocking decision delays.
