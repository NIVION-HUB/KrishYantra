# KrishYantra — Product Requirements Document

**Document status:** Working baseline  
**Product:** KrishYantra (कृषियंत्र)  
**Category:** Precision-agriculture intelligence and farmer decision-support platform  
**Primary promise:** Help farmers make timely, explainable, field-specific crop-protection and crop-management decisions.

> “Saath Har Kisan Ke Liye” — move from reactive crisis management toward verifiable, science-backed harvest outcomes.

---

## 1. Product vision

KrishYantra is an agriculture intelligence platform that combines hyperlocal weather and microclimate signals, farm and crop context, image/voice-based observations, agronomic rules, and machine-learning predictions. It translates those signals into practical advisories that a farmer can understand and act on.

The product should not merely display predictions. It should explain **what is happening, why it matters, what action is appropriate, when it is safe to act, and how to follow up**.

## 2. Users and stakeholders

| User | Needs |
|---|---|
| Farmer / grower | Local-language, understandable, field-specific advice; low-friction access on a phone |
| Extension officer / agronomist | Reviewable farm context, risk indicators, recommendations, and follow-up status |
| Platform administrator | Operational visibility, user/content oversight, service health and configuration |
| Research / model team | Traceable inputs, model evaluation, versioning, and reproducible experiments |

## 3. Product scope

### In scope

- Farmer-facing web application / PWA.
- Farm profile and field context, including crop, growth stage, soil and acreage where available.
- Weather and microclimate risk intelligence.
- Biological readiness / spray-safety gating using relevant atmospheric conditions.
- Crop-health intelligence and image-assisted diagnosis workflows.
- Product or intervention ranking with understandable reasoning.
- Dosage and carrier-water calculations where supported by validated agronomic data.
- Yield and economic-impact estimates with visible assumptions.
- Follow-up and recovery workflows, including the documented 48-hour audit concept.
- Admin / extension-officer monitoring.
- WhatsApp-based conversational access and photo intake.
- Hindi and English experiences, with a path for additional vernacular languages.

### Out of scope unless explicitly approved

- Autonomous execution of farm operations or pesticide application.
- Guaranteed yield, disease diagnosis, or financial-return claims.
- Replacing qualified agronomists, local regulations, product labels, or official advisories.
- Presenting model estimates as measured facts.
- Adding new paid data providers or external integrations without documenting cost, licensing and fallback behavior.

## 4. Core user journeys

### Journey A — Understand field risk

1. Farmer selects or confirms a field.
2. Application obtains the available location, crop, growth-stage and weather context.
3. Risk engine evaluates relevant stress indicators and forecast horizon.
4. Farmer sees risk level, affected crop/stage, time window, and plain-language explanation.
5. Farmer can inspect the underlying signals and recommended next step.

### Journey B — Check whether an intervention is appropriate

1. Farmer opens plant intelligence for a crop/field.
2. System evaluates biological readiness and weather constraints.
3. If conditions are unsafe, the system explains the blocking factors and when to reassess.
4. If conditions are suitable, ranked options and application guidance are shown only when supported by trusted data.
5. Guidance includes label-aligned precautions and a clear disclaimer.

### Journey C — Report crop symptoms

1. Farmer submits a crop image and/or answers a short symptom questionnaire.
2. System records crop, stage, location/field context and capture time where available.
3. Diagnostic service returns likely issues, confidence/limitations and suggested verification steps.
4. High-risk or low-confidence cases are escalated to an agronomist / extension workflow.
5. Follow-up captures whether symptoms improved, worsened or remained unchanged.

### Journey D — Review expected impact

1. Farmer selects a crop/field and relevant baseline.
2. Yield / economic model produces an estimate with assumptions and uncertainty.
3. ROBI / return-on-biological-investment view separates baseline, estimated uplift, costs and market-price inputs.
4. Farmer can inspect the source and date of market benchmarks.

## 5. Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-01 | Support farmer onboarding and a persistent farm/field profile | P0 |
| FR-02 | Capture crop, growth stage, acreage and soil context where available | P0 |
| FR-03 | Display hyperlocal weather and crop-stress indicators with timestamps | P0 |
| FR-04 | Provide a biological readiness / spray-safety gate with reasons | P0 |
| FR-05 | Explain recommendations in plain Hindi/English | P0 |
| FR-06 | Show data provenance, freshness and unavailable-data states | P0 |
| FR-07 | Support crop image and questionnaire-based case intake | P1 |
| FR-08 | Provide ranked interventions with transparent rationale | P1 |
| FR-09 | Calculate application quantities only from verified product-label inputs | P1 |
| FR-10 | Provide recovery and follow-up workflow | P1 |
| FR-11 | Provide yield and causal ROBI estimates with assumptions | P1 |
| FR-12 | Provide admin / extension-officer review tools | P1 |
| FR-13 | Support WhatsApp entry points and webhook processing | P1 |
| FR-14 | Support multilingual voice workflows | P2 |

## 6. Non-functional requirements

- **Safety:** No unsupported treatment instruction; show label and local-regulation caveats.
- **Explainability:** Every consequential recommendation should expose its principal inputs and reasons.
- **Reliability:** Graceful degradation when weather, cloud inference, image analysis or messaging providers fail.
- **Performance:** Prioritize fast first render and progressively load heavy analytics.
- **Accessibility:** Mobile-first, readable typography, high contrast, large touch targets and low-bandwidth tolerance.
- **Privacy:** Collect only necessary personal/farm data; protect credentials and restrict access by role.
- **Traceability:** Record model version, input timestamp, output timestamp and relevant data sources.
- **Maintainability:** Keep UI, API orchestration, domain engines and model services separable.

## 7. Product success measures

Track these as measurable product metrics; do not claim targets until baselines are established.

- Farmer onboarding completion and repeat usage.
- Percentage of advisories with complete provenance and explanation.
- Weather / inference service availability and response latency.
- Recommendation acceptance and follow-up completion.
- Diagnostic escalation rate and agronomist review outcomes.
- Model precision/recall and calibration by crop, region and season.
- Percentage of estimates with complete assumptions and uncertainty.
- Farmer comprehension / usefulness feedback.

## 8. Trust, safety and agronomic guardrails

1. A model score is not a confirmed diagnosis.
2. Never invent missing weather, soil, crop-stage, product-label or market data.
3. If a safety gate cannot evaluate required inputs, return **insufficient data** rather than “safe”.
4. Product dosage must be grounded in the current approved label and applicable local guidance.
5. Show units, dilution basis, acreage basis and calculation assumptions.
6. Clearly distinguish forecast, model estimate, observation and user-entered data.
7. Provide escalation guidance for severe, uncertain or rapidly worsening cases.
8. Do not imply that an intervention guarantees yield improvement or profit.

## 9. Dependencies and open questions

- Confirm the authoritative source and refresh schedule for each weather, soil, market and product dataset.
- Confirm supported crops, regions, growth stages and language coverage.
- Confirm authentication, user roles and data-retention policy from the implementation.
- Confirm production model endpoints, versions, fallback behavior and service-level expectations.
- Validate all agronomic rules and product-label content with qualified domain experts.

## 10. Acceptance criteria

A release is acceptable when its implemented scope has tests, the primary farmer journey works on a mobile viewport, unavailable dependencies produce safe fallback states, recommendations expose reasons and provenance, and the frontend production build passes.
