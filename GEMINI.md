# Dash Platform — Gemini & Antigravity AI Architectural Standards

> **Role & Persona:** Senior Principal System Architect & AI Technical Lead.  
> **Scope:** Dash Ride-Sharing & Package Delivery Platform.

---

## 1. System Architecture
- **Backend:** ASP.NET Core (.NET 8+) Modular Monolith (`src/Modules/*`). Clean Architecture with strict boundaries (`Identity`, `Trips`, `Drivers`, `Pricing`, `Delivery`, `Dashboard`). SQL Server + Redis caching/streams. Monolithic WebSockets + Server-Sent Events (SSE). Uber H3 hexagonal spatial indexing.
- **Frontend:** Flutter Clean Architecture + Cubit (`flutter_bloc`). Dio + Retrofit network layer with Dartz `Either<Failure, T>`. Localization (`easy_localization`) for **English (en-US)** and **Arabic (ar-SA)** only.

---

## 2. Media & Image Upload Standards (MANDATORY)
- **Multipart Form-Data Rule:** Any image or binary file upload (driver documents, vehicle images, color variants, payment receipts, user avatars) **MUST** be sent as `multipart/form-data` with explicit boundary handling.
- **Composite Payloads:** Entities that reference images must accept image URL/path strings in JSON request bodies produced by pre-uploading files to dedicated media upload endpoints (`POST /api/v1/dashboard/media/upload`). Binary files must never be directly embedded inside raw JSON request bodies.

---

## 3. Strict API Contracts
- **Requests ([base_request.md](./base_request.md)):** Flat static GET parameters (`page`, `perPage`, `search`, `sortBy`, `sortOrder`). Filter suffixes (`Neq`, `Gt`, `Gte`, `Lt`, `Lte`, `Like`, `In`, `Nin`, `From`/`To`, `IsNull`, `IsNotNull`).
- **Responses ([base_response.md](./base_response.md)):** Standard envelope `meta`, `data`, `cache`, `error`. Direct pagination for single list vs nested pagination for multiple keys.
- **Headers ([headers.md](./headers.md)):** `Authorization: Bearer <JWT>`, `Accept-Language: en-US | ar-SA`, `X-Idempotency-Key`, `X-App-Version`, `X-Platform`.

---

## 4. Multi-Document Cascading & Sync Matrix
- Mirror changes between `dashboard-screen-plan.md` and `dashboard-screen-plan-ar.md`.
- Keep the Dashboard Triad synchronized (`dashboard-api-flow.md`, `dashboard-screen-plan.md`, `dashboard-screen-plan-ar.md`).
- Propagate changes in `system-design-ride-sharing.md`, `cancellation-pricing-guide.md`, and `matching_system_design.md` across all documentation files.

---

## 5. Roadmap & Hyperlinks Governance
- 12-week implementation cap with an 8-week MVP milestone (Passenger Transport RIDE base scenarios).
- **NEVER** use absolute `file:///...` URIs in markdown links; **ALWAYS** use relative paths (e.g., `[headers.md](./headers.md)`).
