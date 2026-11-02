# KrishYantra — Project Memory

This file is the compact, durable context for contributors and AI coding assistants. Keep it factual, current and concise. Update it when a decision is made or a milestone is verified.

## 1. Project identity

- **Name:** KrishYantra (कृषियंत्र)
- **Purpose:** Autonomous precision-agriculture intelligence, biophysical weather gating and crop-health decision support.
- **Product promise:** “Saath Har Kisan Ke Liye” — practical, explainable, science-backed support for farmers.
- **Primary experience:** Farmer-facing Next.js web app / PWA, with admin and WhatsApp access paths.

## 2. Repository map

- `frontend/` — Next.js farmer application.
- `backend/` — FastAPI orchestration/API service.
- `ps02-engine/` — climate-stress and biological-readiness engine.
- `vertex_ai/` — six model definitions / deployment assets.
- `admin/` — operations and extension-officer portal.
- `whatsapp-bot/` — WhatsApp Cloud API integration.
- `bot/` — standalone bot utilities.
- `docs/` — research, architecture and ML documentation.
- `AGENTS.md` — root-level contributor constraints.

## 3. Known architecture baseline

The repository's published guide describes a six-stage pipeline:

1. Model 1 — climate stress / risk classification.
2. Model 2 — biological readiness and spray-safety gating.
3. Model 3 — biological intervention ranking.
4. Model 4 — crop recovery trajectory.
5. Model 5 — yield baseline regression.
6. Model 6 — causal uplift / ROBI estimation.

Documented stack: Next.js 16, Python FastAPI, Python PS-02 engine, Vertex AI model services, Meta WhatsApp Cloud API and Vercel deployment.

## 4. Decisions that must remain true

- Preserve the existing `design-md-stripe` visual direction.
- Core colors: forest `#1b4332`, emerald `#2d6a4f`, ivory/sage `#fbfcf8` / `#f8faf7`, border `#e8ede4`.
- Keep safety/readiness rules conservative and explainable.
- Missing or stale critical data must not be interpreted as safe conditions.
- Separate deterministic agronomic rules from probabilistic model predictions.
- Display data source, timestamp, units and assumptions for consequential outputs.
- Never claim guaranteed diagnosis, yield or financial returns.
- Verify Vercel production after relevant updates are fetched and merged, as required by `AGENTS.md`.

## 5. Important paths named by the repository guide

- `backend/app/main.py` — FastAPI entry point.
- `backend/app/routers/pipeline.py` — model pipeline orchestration.
- `backend/tunnel_bridge.py` — local Vertex AI bridge.
- `backend/check_vertex_status.py` — Vertex endpoint health check.
- `frontend/src/app/plant-intelligence/prescription/page.tsx` — prescription UI.
- `frontend/src/app/impact/page.tsx` — impact / ROBI UI.
- `frontend/src/app/plant-intelligence/recovery/page.tsx` — recovery workflow.
- `frontend/src/lib/farmerAdvisoryEngine.ts` — advisory language / transformation.
- `frontend/src/lib/usePipelinePrediction.ts` — prediction coordination hook.

Paths and implementation may change. Confirm they exist before editing.

## 6. Local development reference

Root commands documented in `package.json`:

```bash
npm install
npm run dev
```

The root development command runs backend, frontend and PS-02 concurrently. Individual service commands are documented in `ARCHITECTURE.md`. Check the actual package scripts and requirements before running them.

## 7. External data / integrations mentioned

- Weather / microclimate: Open-Meteo and Meteoblue references.
- Soil / crop context: soil series and agronomic reference data.
- Market: APMC / Agmarknet benchmarks.
- Model inference: Google Vertex AI.
- Messaging: Meta WhatsApp Cloud API.
- Image diagnosis: vision-model integration.

For each source, maintain ownership, license, units, refresh cadence, timestamp and fallback documentation. Do not put credentials in this file.

## 8. Current verified state

**This section is intentionally not pre-filled with assumed progress.** Update it only after checking the working tree and running the relevant verification.

- Current branch / commit:
- Last verified local startup:
- Last frontend build:
- Last backend test run:
- Last PS-02 test run:
- Last model evaluation:
- Last production deployment / smoke test:
- Known blockers:

## 9. Update protocol

When changing this file:

1. Keep durable decisions; do not store temporary debugging noise.
2. Add dates to important decisions and verification results.
3. Mark assumptions as assumptions until verified in source or tests.
4. Remove obsolete details rather than accumulating contradictory notes.
5. Never store API keys, passwords, private farmer data or personal image content.
