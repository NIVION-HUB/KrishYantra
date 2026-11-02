# KrishYantra — Development Tasks and Roadmap

**Purpose:** A working execution board for rebuilding, stabilizing and extending the application.  
**Status convention:** `[ ]` not verified / pending · `[x]` verified complete · `[!]` blocked or needs investigation.

> Initial task states are intentionally unchecked. Confirm each item against the current codebase before marking it complete.

## Phase 0 — Repository recovery and baseline

- [ ] Clone / open the repository and confirm the active branch and commit.
- [ ] Read `README.md`, `AGENTS.md`, existing docs and environment examples.
- [ ] Inventory all services, entry points, ports and dependency manifests.
- [ ] Identify required environment variables without copying secret values into docs.
- [ ] Install dependencies using the repository's supported commands.
- [ ] Start frontend, backend and PS-02 engine independently.
- [ ] Record current build, test and runtime failures.
- [ ] Confirm which features are live, experimental, mocked or incomplete.

**Exit criteria:** A reproducible local setup and a written baseline of working / failing services.

## Phase 1 — Contracts and core reliability

- [ ] Document API routes, request/response schemas and error formats.
- [ ] Define canonical units and validation ranges for weather, soil, crop and acreage inputs.
- [ ] Add request IDs and structured service logs.
- [ ] Add timeouts and bounded retry behavior for external APIs and model calls.
- [ ] Define stale-data and unavailable-provider behavior.
- [ ] Add health checks for frontend dependencies, backend and PS-02.
- [ ] Verify CORS, authentication, authorization and webhook security.

**Exit criteria:** Services fail predictably and expose diagnosable health / error states.

## Phase 2 — Farmer experience

- [ ] Verify onboarding and farm / field profile flow.
- [ ] Verify crop, growth-stage, soil and acreage capture.
- [ ] Verify weather and crop-risk dashboard.
- [ ] Verify “Why” explanation and source/freshness display.
- [ ] Verify biological readiness states: suitable, not suitable, insufficient data.
- [ ] Verify recommendation steps and label-aligned safety notes.
- [ ] Verify cultural advisory content.
- [ ] Test mobile layouts and Hindi/English content.
- [ ] Test empty, loading, error and offline/poor-network states.

**Exit criteria:** A farmer can complete the primary field-risk and advisory journey on mobile.

## Phase 3 — Intelligence pipeline and models

- [ ] Inventory Models 1–6: code, artifact, schema, version, endpoint and owner.
- [ ] Document feature definitions, units, source and missing-value behavior.
- [ ] Validate Model 1 risk outputs against held-out data.
- [ ] Validate Model 2 readiness formulas and boundary conditions with domain experts.
- [ ] Validate Model 3 ranking data and product catalogue freshness.
- [ ] Validate Model 4 recovery assumptions and escalation thresholds.
- [ ] Validate Model 5 yield baseline calibration by crop / region.
- [ ] Validate Model 6 causal assumptions, treatment definition and uncertainty.
- [ ] Add regression tests and model-version traceability.
- [ ] Verify cloud endpoint health and safe fallback behavior.

**Exit criteria:** Each model has a documented contract, evaluation evidence and safe failure behavior.

## Phase 4 — Diagnosis, messaging and follow-up

- [ ] Verify image upload, storage and deletion/retention behavior.
- [ ] Verify crop symptom questionnaire and diagnostic response contract.
- [ ] Add low-confidence and severe-case escalation.
- [ ] Verify WhatsApp webhook verification and message lifecycle.
- [ ] Verify Hindi/English bot responses and provider failure handling.
- [ ] Verify 48-hour follow-up / spray audit scheduling.
- [ ] Ensure duplicate webhook deliveries are idempotent.

**Exit criteria:** A farmer can submit a case, receive a bounded response and complete a follow-up.

## Phase 5 — Admin, impact and operations

- [ ] Verify admin authentication and role-based permissions.
- [ ] Verify farmer / case / advisory monitoring views.
- [ ] Verify yield and ROBI assumptions, benchmark provenance and dates.
- [ ] Add operational metrics for API latency, error rate and model availability.
- [ ] Add audit trail for consequential admin actions.
- [ ] Confirm privacy and data-retention policies.

**Exit criteria:** Authorized staff can review operational status without exposing unnecessary farmer data.

## Phase 6 — Release readiness

- [ ] Run frontend lint/type checks and production build.
- [ ] Run backend and PS-02 automated tests.
- [ ] Run API contract and integration tests.
- [ ] Run model evaluation checks for changed models.
- [ ] Run security and dependency checks.
- [ ] Test key routes on mobile and desktop.
- [ ] Verify production environment variables and secret configuration.
- [ ] Deploy and smoke-test Vercel production routes.
- [ ] Record release version, commit, deployment URL and known limitations.

**Exit criteria:** Release checks pass or remaining exceptions are documented and explicitly accepted.

## Priority guide

- **P0:** Data safety, service startup, primary farmer journey, readiness gating, provenance.
- **P1:** Diagnosis, ranking, follow-up, admin workflows and economic estimates.
- **P2:** Additional languages, advanced analytics and quality-of-life improvements.

## Work item template

```text
### [ ] Short task title
- Owner:
- Priority: P0 / P1 / P2
- Area: frontend / backend / PS-02 / ML / admin / WhatsApp / infra
- Context:
- Acceptance criteria:
- Dependencies:
- Verification command(s):
- Notes / decision:
```

## Progress log

| Date | Area | Change / verification | Result | Owner |
|---|---|---|---|---|
| YYYY-MM-DD | — | Initialize this roadmap | Pending review | — |
