# StoreOps Codex Working Rules

These rules apply to all Codex work in this repository unless a task explicitly overrides them.

## 1. Locked product baseline

Before product/design work, read:

- `docs/STOREOPS_PAYMENT_VALIDATION_BASELINE_V4.md`
- `.agents/skills/frontend-app-builder/SKILL.md` for frontend/design work

When older prompts conflict with the v4 payment-validation baseline, v4 wins.

## 2. Review Artifact Gate — mandatory

Any task whose result must be visually or substantively reviewed by the owner must produce reviewable artifacts in the **same execution pass**. Do not stop at a text-only statement such as “design complete”, “report ready”, or “tests passed” when the actual output can be exported.

Examples include:

- visual/UI concepts;
- desktop/mobile layouts;
- bilingual customer-facing screens;
- reports and evidence summaries;
- test/QA result packages;
- before/after comparisons;
- owner-approval material.

### Default artifact formats

- Visual/UI work: export readable PNGs **plus one combined PDF**.
- Reports: export PDF and/or self-contained HTML when appropriate.
- QA/testing: export a human-readable report with the supporting evidence needed to review the result.
- Desktop/mobile work: include both desktop and mobile artifacts.
- EN/繁中 work: include enough artifacts in both languages to verify content parity.

Always provide the exact local file paths at handoff.

### Artifact quality

Artifacts must be readable at normal review size. Do not rely on tiny full-page screenshots when section-level detail is needed. Preserve the approved concept faithfully; do not generate unrelated alternatives merely to satisfy the export requirement.

## 3. Owner approval gate

When the task requires owner approval:

1. complete the requested work;
2. export the review artifacts in the same pass;
3. verify the files exist and are readable;
4. provide their paths;
5. STOP for owner review.

Do not implement the next gated phase, deploy, connect billing, change DNS, or modify production unless the owner has explicitly approved that step.

## 4. No fake completion

Never claim completion based only on planned output. For artifact-producing tasks, completion means the actual artifact files exist and are inspectable.

For code/runtime tasks, completion means execution plus target-environment read-back/validation where applicable.

## 5. Human-action batching

Continue autonomously through non-destructive work. If multiple owner/manual actions become necessary, collect them into one concise blocker list rather than interrupting the owner one item at a time, unless one blocker prevents all remaining useful work.

## 6. Safety and product boundaries

For the current StoreOps payment-validation stage:

- do not turn StoreOps into an SEO/GEO/AEO/AIO audit SaaS;
- do not fabricate findings, revenue-loss estimates, health scores, testimonials, or customer logos;
- uncertainty is WARN, not FAIL;
- do not require an OpenAI API key;
- do not deploy or modify the live GitHub Pages site during design-only tasks;
- do not build Phase B before the owner gate and external payment-validation gate are passed.
