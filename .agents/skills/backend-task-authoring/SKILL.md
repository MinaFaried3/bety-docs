---
name: backend-task-authoring
description: Draft and maintain implementation-ready Dash backend tasks, including API contracts, business scenarios, localized responses, and acceptance criteria. Use when a backend task is requested, revised, approved, or saved under tasks/backend.
---

# Backend Task Authoring

Create concise tasks that a backend engineer can implement without another requirements meeting.

## Workflow

1. Inspect `[base_request.md](../../../base_request.md)`, `[base_response.md](../../../base_response.md)`, and `[headers.md](../../../headers.md)` when the task changes an API.
2. Draft the task in chat until the user explicitly approves it.
3. After approval, save it to `tasks/backend/<lowercase-kebab-name>.md` with `Status: Approved` and the approval date.
4. Preserve the approved scope exactly. Treat later changes as revisions requiring fresh approval before replacing the saved specification.

## Required Task Shape

- Title and objective.
- Endpoint and required headers.
- Request and full base-wrapped response contracts.
- Business and eligibility rules.
- Concrete response scenarios covering all materially different outcomes.
- Stable enums, reason codes, localization behavior, and entity identifiers.
- Error cases using `meta.success: false`, `data: null`, and populated `error.errors` when applicable.
- Acceptance criteria and required backend tests.

## Contract Rules

- Every response example uses `meta`, `data`, `cache`, and `error` exactly as defined by `[base_response.md](../../../base_response.md)`.
- Return only the language selected by `Accept-Language: en-US | ar-SA`; do not return `titleEn`/`titleAr` pairs.
- Separate machine-readable codes from localized text.
- For lists inside composite responses, use descriptive list keys. Add pagination only when the endpoint actually paginates.
- Make blocking versus non-blocking effects explicit.
- Model aggregate rejection at the entity level when product requirements do not expose field-level rejection.
- Include enough active workflow state for client recovery, but do not duplicate transport configuration already known by the client.

## Scope Boundary

Saving an approved task does not authorize implementation or automatic edits to architecture documents. Perform those only when the user requests implementation or documentation promotion.
