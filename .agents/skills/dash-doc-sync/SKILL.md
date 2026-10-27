---
name: dash-doc-sync
description: Orchestrates multi-document cascading updates, EN/AR translation synchronization, and API contract validation across the Dash system architecture. Use whenever modifying any documentation, screen plans, API flows, pricing rules, or matching logic.
---

# Dash Multi-Document Synchronization & API Contract Skill

This skill enforces strict multi-document synchronization and contract validation whenever changes occur in system specifications.

## 🔗 GitHub Relative Hyperlink Rule (MANDATORY)

- **NEVER** use absolute `file:///...` URIs when writing markdown links.
- **ALWAYS** use relative markdown paths (e.g., `[headers.md](../headers.md)`, `[system-design-ride-sharing.md](./system-design-ride-sharing.md)`) so links work seamlessly on GitHub and across developer environments.

## 🔄 The 7 Document Cascading Principles

When making any change in the system documentation, evaluate and execute the required cascading edits:

1. **Dashboard Translation Mirroring:**
   - Source: [dashboard-screen-plan.md](./dashboard-screen-plan.md)
   - Target: [dashboard-screen-plan-ar.md](./dashboard-screen-plan-ar.md)
   - Rule: Any widget, screen layout, parameter, or flow updated in English MUST be updated in Arabic with natural, high-quality technical Arabic terms, keeping screen keys and structure identical.

2. **Reverse Dashboard Translation Mirroring:**
   - Source: [dashboard-screen-plan-ar.md](./dashboard-screen-plan-ar.md)
   - Target: [dashboard-screen-plan.md](./dashboard-screen-plan.md)
   - Rule: Any modification originating in Arabic must immediately reflect back in English.

3. **Dashboard Triad Synchronization:**
   - Files: [dashboard-api-flow.md](./dashboard-api-flow.md), [dashboard-screen-plan.md](./dashboard-screen-plan.md), [dashboard-screen-plan-ar.md](./dashboard-screen-plan-ar.md)
   - Rule: If a dashboard API endpoint changes, update screen documentation and localized components across all 3 files.

4. **Core System Architecture Propagation:**
   - Source: [system-design-ride-sharing.md](./system-design-ride-sharing.md)
   - Targets: [dashboard-api-flow.md](./dashboard-api-flow.md), [dashboard-screen-plan.md](./dashboard-screen-plan.md), [rider-api-flow.md](./rider-api-flow.md), [driver-api-flow.md](./driver-api-flow.md)
   - Rule: Fundamental core logic changes must ripple down to all API flows and UI screen plans.

5. **Cancellation & Pricing Refactoring:**
   - Source: [cancellation-pricing-guide.md](./cancellation-pricing-guide.md)
   - Targets: [system-design-ride-sharing.md](./system-design-ride-sharing.md), [driver-api-flow.md](./driver-api-flow.md), [rider-api-flow.md](./rider-api-flow.md), [dashboard-api-flow.md](./dashboard-api-flow.md), [dashboard-screen-plan.md](./dashboard-screen-plan.md)
   - Rule: Dynamic surge pricing, minimum fare rules, or cancellation penalty updates must be synchronized across all affected endpoints and core design docs.

6. **Matching System Cascading:**
   - Source: [matching_system_design.md](./matching_system_design.md)
   - Targets: [system-design-ride-sharing.md](./system-design-ride-sharing.md), [driver-api-flow.md](./driver-api-flow.md), [rider-api-flow.md](./rider-api-flow.md), [dashboard-api-flow.md](./dashboard-api-flow.md), [dashboard-screen-plan.md](./dashboard-screen-plan.md)
   - Rule: Algorithm modifications (H3 k-rings, offer timers, dispatch fallback logic) must update system design, driver push/socket flows, and rider tracking specs.

8. **Dashboard Side Menu & Screens Seed Synchronization:**
   - Source: [dashboard-screen-plan.md](./dashboard-screen-plan.md)
   - Targets: [dashboard_screens_seed.json](./dashboard_screens_seed.json), [dashboard-api-flow.md](./dashboard-api-flow.md), [implementation-plan/week-02.md](./implementation-plan/week-02.md)
   - Rule: Any modification to the side menu structure or screens tree must automatically update `dashboard_screens_seed.json`, `dashboard-api-flow.md`, and `week-02.md` enforcing `id: int`, `route` (string for leaves, `null` for modules), `permission: { view, add, update, delete }`, single localized `name`, and `children: null` for leaves.

---

## 🛠️ Verification Checklist
Before completing any documentation change task:
- [ ] Checked that all markdown links use relative paths, avoiding `file:///...` URIs.
- [ ] Checked if `dashboard-screen-plan.md` changes were duplicated to `dashboard-screen-plan-ar.md`.
- [ ] Checked if API changes were reflected in all 3 API flow files.
- [ ] Validated request/response payload against `base_request.md` and `base_response.md`.
