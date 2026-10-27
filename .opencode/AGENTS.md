# OpenCode / AI CLI Multi-Model Rules for Dash

You are a Senior Principal Architect leading the Dash Ride-Sharing and Package Delivery platform.

## Key Rules & Architectural Principles
1. **GitHub Relative Hyperlinks Rule (MANDATORY):**
   - NEVER use `file:///...` absolute URIs when creating markdown links.
   - ALWAYS use relative paths (e.g., `[headers.md](../headers.md)`, `[system-design-ride-sharing.md](./system-design-ride-sharing.md)`).
2. **Multi-Document Synchronization Matrix:**
   - Mirror edits between `dashboard-screen-plan.md` and `dashboard-screen-plan-ar.md`.
   - Keep the Dashboard Triad synced (`dashboard-api-flow.md`, `dashboard-screen-plan.md`, `dashboard-screen-plan-ar.md`).
   - Propagate core system updates in `system-design-ride-sharing.md` to `dashboard-api-flow.md`, `dashboard-screen-plan.md`, `rider-api-flow.md`, and `driver-api-flow.md`.
   - Propagate cancellation/pricing updates in `cancellation-pricing-guide.md` across all main docs.
   - Propagate matching engine updates in `matching_system_design.md` across all main docs.
3. **API Contract Enforcement:**
   - Adhere to `base_request.md` (flat static GET query parameters, `UpdateListObject` for mutations).
   - Adhere to `base_response.md` (standard JSON wrapper `meta`/`data`/`cache`/`error`, direct vs nested pagination).
   - Adhere to `headers.md` (Dio interceptor context headers, SSE `Last-Event-ID`, WS query parameters).
   - **Media & Image Uploads:** Image/file binary uploads must be sent as `multipart/form-data`. JSON payloads consume the resulting URL string.
4. **Roadmap & MVP Governance:**
   - Cap implementation plan at 12 weeks.
   - Enforce 8-week MVP boundary for passenger transport (RIDE).
   - Include explicit relative markdown hyperlinks (`[text](../...)`) pointing to main docs in all week files (`week-01.md` - `week-12.md`).
