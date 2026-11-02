# KrishYantra — Product Design Guide

## 1. Design intent

Design for farmers and field operators who need to understand a decision quickly, often on a mobile device and under variable network conditions.

The experience should feel:

- Trustworthy and calm, not alarmist.
- Practical and action-oriented.
- Scientific without being difficult to understand.
- Consistent across web, admin and conversational entry points.
- Readable in Hindi and English.

## 2. Existing visual direction

The repository's `AGENTS.md` and README establish a `design-md-stripe` direction. Preserve it.

| Token | Value | Usage |
|---|---|---|
| Deep forest | `#1b4332` | Primary brand, navigation, strong headings |
| Emerald | `#2d6a4f` | Primary actions and positive emphasis |
| Ivory | `#fbfcf8` | Main page background |
| Sage neutral | `#f8faf7` | Secondary surfaces |
| Border | `#e8ede4` | Dividers, cards and input boundaries |

Use semantic tokens in code rather than scattering raw hex values. Confirm the actual token file before adding or changing tokens.

## 3. Information hierarchy

A farmer-facing advisory should answer, in order:

1. **What is the situation?** — crop, field, risk and time window.
2. **Why is this happening?** — a short explanation using relevant signals.
3. **What should I do?** — prioritized practical steps.
4. **When should I do it?** — safe timing / readiness window.
5. **How do I do it?** — validated quantity, dilution and precautions when applicable.
6. **What if it does not improve?** — follow-up and escalation path.

Do not bury the action behind charts or technical model terminology.

## 4. Core interface patterns

### Risk summary

- Show risk level with both text and a visual indicator; never rely on color alone.
- State the forecast / observation time window.
- Show freshness and source status.
- Provide a short “Why this risk?” explanation.

### Biological readiness gate

- Clearly distinguish **Suitable**, **Not suitable**, and **Insufficient data**.
- List the blocking or supporting conditions (e.g. relevant temperature, humidity/VPD, wind or rain constraints when available).
- Never style “unknown” as “safe”.
- Include a next reassessment time only when it can be calculated from available data.

### Recommendation / prescription

- Separate the reason (“Why”) from the steps (“How”).
- Use numbered steps and familiar units.
- Show the field area and assumptions used in calculations.
- Include product-label and local-guidance caveats.
- Offer a non-chemical / cultural advisory when scientifically appropriate and validated.

### Crop image diagnosis

- Make image capture/upload instructions clear.
- Ask for the crop and growth stage if not already known.
- Present likely causes with uncertainty and verification steps.
- Offer human review for uncertain or severe cases.

### Yield / ROBI

- Separate measured values, external benchmarks and model estimates.
- Show the benchmark source and date.
- Display assumptions and uncertainty near the headline result.
- Avoid implying guaranteed returns.

## 5. Components and interaction

Prefer reusable components for:

- Page header and field selector.
- Risk / status summary.
- Metric card with unit and timestamp.
- Explanation / “Why” panel.
- Step-by-step action card.
- Data provenance and freshness label.
- Empty, loading, error and stale-data states.
- Follow-up timeline / recovery status.
- Accessible charts with text summaries.

Use consistent spacing, border radius, elevation and typography from the existing component system. Avoid introducing a second component library without a clear need.

## 6. Responsive and accessibility requirements

- Design mobile-first; support narrow screens without horizontal scrolling.
- Use touch targets large enough for outdoor/mobile use.
- Keep important actions visible and labels explicit.
- Maintain keyboard navigation and visible focus.
- Ensure text contrast and do not encode status by color alone.
- Support long translated labels and variable text expansion.
- Use plain language and explain uncommon terms.
- Provide text equivalents for charts and icons.

## 7. Localization and content

- Hindi and English are first-class content paths.
- Avoid concatenating translated fragments; use complete localized messages.
- Keep units explicit and consistent.
- Prefer locally familiar agricultural terminology, reviewed by domain experts.
- Do not translate product-label language in a way that changes its legal or safety meaning.

## 8. Design review checklist

- [ ] Existing forest / emerald / ivory / sage theme preserved.
- [ ] Primary action and decision are obvious.
- [ ] Risk and readiness states include text labels.
- [ ] Freshness, source and uncertainty are visible.
- [ ] Mobile layout works at narrow widths.
- [ ] Empty, loading, error and insufficient-data states exist.
- [ ] Hindi and English layouts have been checked.
- [ ] Keyboard focus and contrast are acceptable.
- [ ] Agronomic language and calculations have been reviewed.
