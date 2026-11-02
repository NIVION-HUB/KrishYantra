# KrishYantra — Engineering Rules

These rules supplement the repository's root `AGENTS.md`. If a rule conflicts with a documented safety requirement or an existing repository convention, stop and resolve the conflict before implementation.

## 1. Non-negotiable product rules

1. Preserve the existing KrishYantra visual identity.
2. Do not invent agronomic facts, product labels, market prices, model outputs or user data.
3. Treat model outputs as estimates, not ground truth.
4. Fail safely when critical weather / biological readiness inputs are absent, stale or invalid.
5. Explain consequential recommendations in simple language and expose the main reasons.
6. Do not claim a feature, integration or test is complete unless it has been verified.

## 2. Design-system preservation

The root `AGENTS.md` requires preserving the established `design-md-stripe` aesthetic:

- Deep forest: `#1b4332`
- Emerald: `#2d6a4f`
- Ivory / sage surfaces: `#fbfcf8`, `#f8faf7`
- Crisp border: `#e8ede4`
- Elegant, readable typography

Tokens may be refined, but do not replace the theme with an unrelated visual language. Follow existing component patterns before introducing new ones.

## 3. Code quality

- Prefer small, cohesive modules with clear ownership.
- Use descriptive names and explicit types at API boundaries.
- Validate external input before domain logic.
- Keep deterministic domain calculations out of UI components.
- Avoid duplicated business rules across frontend, backend and bots.
- Handle loading, empty, error, stale-data and partial-data states.
- Remove dead code and unused dependencies introduced by a change.
- Do not add abstractions without a concrete use case.

## 4. Frontend rules

- Follow the existing Next.js App Router structure and conventions.
- Reuse established design tokens and shared components.
- Keep layouts responsive and mobile-first.
- Provide accessible labels, keyboard operation, visible focus and sufficient contrast.
- Use loading and error states for network-backed views.
- Do not hardcode secrets, production URLs or user-specific data.
- Keep API response types synchronized with backend contracts.

## 5. Backend and API rules

- Validate request bodies, query parameters and external responses.
- Use consistent response and error shapes.
- Apply timeouts and bounded retries to external calls.
- Keep credentials in environment variables / secret stores.
- Enforce authentication and role authorization for protected operations.
- Verify WhatsApp webhook signatures/tokens according to provider requirements.
- Never expose stack traces, secrets or internal endpoint credentials to clients.

## 6. ML and agronomic rules

- Version models and record the version used for each consequential inference.
- Track input schema, units, source and timestamp.
- Validate feature ranges and missing-value behavior.
- Evaluate models on held-out and region/crop-relevant data.
- Report uncertainty / confidence only when the model supports it.
- Do not use a low-confidence classification as a definitive diagnosis.
- Keep safety gates deterministic, reviewable and conservative.
- Product rankings do not override label instructions or local regulations.
- Dosage calculations require validated label concentration, crop, target, area and carrier-volume assumptions.
- Economic estimates must disclose benchmark source/date and assumptions.

## 7. Data and privacy rules

- Collect only data needed for the stated feature.
- Do not commit real farmer records, personal images, tokens or credentials.
- Use synthetic or anonymized data in tests and examples.
- Define retention and deletion behavior for uploaded images and chat records.
- Restrict admin access and audit sensitive actions.
- Treat third-party data licensing and attribution as implementation requirements.

## 8. Git and change management

- Make focused commits with clear messages.
- Do not commit generated build output, virtual environments, caches or local secrets.
- Update relevant documentation when architecture, APIs, environment variables or workflows change.
- Avoid unrelated formatting churn.
- Review the diff before committing.

## 9. Required verification before declaring done

Run the relevant checks for the changed subsystem:

- Frontend: lint/type checks available in package scripts and `npm run build`.
- Backend: unit tests, import/startup check and API contract tests available in the repository.
- PS-02: deterministic tests for formula boundaries, units, missing values and time windows.
- ML: schema checks and model evaluation appropriate to the change.
- WhatsApp: webhook validation and mocked provider interaction tests.
- Admin: build and role-access checks.

Record commands run and actual outcomes. Do not report skipped checks as passed.

## 10. Deployment rule

The root `AGENTS.md` states that Vercel production deployment must be verified whenever updates are fetched and merged. Verify deployment status and smoke-test key routes after relevant merges; record the deployment URL and verification time.
