---
name: dash-roadmap-governance
description: Governs the 12-week implementation plan, 8-week MVP boundaries (Passenger Transport RIDE base scenarios), and markdown hyperlink linking to main documentation files across the Dash platform.
---

# Dash 12-Week Implementation Plan & MVP Governance Skill

This skill enforces strict roadmap boundaries and cross-linking standards for the Dash project.

## 📅 Roadmap Constraints

1. **Strict 12-Week Limit:**
   - The implementation plan in `implementation-plan/` must contain exactly 12 weekly files (`week-01.md` through `week-12.md`).
   - Under no circumstances should additional weeks (e.g., Week 13+) be added.

2. **8-Week MVP Milestone (Passenger Transport RIDE):**
   - Weeks 1 to 8 focus exclusively on the core **Passenger Transport Ride Scenario (RIDE)**.
   - Core MVP capabilities completed by end of Week 8:
     - Dashboard vehicle & service pricing configuration.
     - Driver onboarding, document upload & admin approval.
     - Driver online state & GPS streaming via Monolithic WebSockets.
     - Rider destination search, upfront pricing calculation, & trip request.
     - Uber H3 geospatial matching & sequential dispatch countdown timer (`offer_timeout_seconds`, default 15s).
     - Rider SSE tracking screen & driver turn-by-turn navigation.
     - Google Roads API map-matching, final fare settlement, and ratings.
   - Post-MVP features (Package Delivery, Wallet Top-ups, Driver Balance Limits, SOS Alerts, Marketing Campaigns, Ads, and Sponsorships) MUST NOT bleed into Weeks 1-8.

3. **GitHub Relative Hyperlink Standards (MANDATORY):**
   - All plan files (`README.md`, `week-01.md` - `week-12.md`) MUST contain relative markdown hyperlinks (`[text](../...)` or `[text](./...)`) pointing to main design documents. Never use `file:///...` URIs.
     - [system-design-ride-sharing.md](../system-design-ride-sharing.md)
     - [driver-api-flow.md](../driver-api-flow.md)
     - [rider-api-flow.md](../rider-api-flow.md)
     - [dashboard-api-flow.md](../dashboard-api-flow.md)
     - [dashboard-screen-plan.md](../dashboard-screen-plan.md)
     - [dashboard-screen-plan-ar.md](../dashboard-screen-plan-ar.md)
     - [matching_system_design.md](../matching_system_design.md)
     - [cancellation-pricing-guide.md](../cancellation-pricing-guide.md)
     - [base_request.md](../base_request.md)
     - [base_response.md](../base_response.md)
     - [headers.md](../headers.md)

4. **Architectural Pre-Flight Rule (MANDATORY):**
   - Every week's Architectural Discussion & Technical Decision Points (Section 🗣️) **MUST** be pre-discussed and documented in the preceding week's implementation plan (Week N-1).
   - This ensures that when Week N starts, all technical decisions are already resolved, enabling immediate, direct code implementation without blocking decision delays.
