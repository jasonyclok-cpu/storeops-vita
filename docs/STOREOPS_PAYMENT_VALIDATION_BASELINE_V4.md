# StoreOps by Vita Pet System — Payment Validation Baseline v4

**Status:** LOCKED PAYMENT-VALIDATION BASELINE  
**Last updated:** 2026-09-07  
**Applies before:** full SaaS build, live self-service scanner platform, monitoring, subscriptions, AI explanation layer  
**Primary commercial gate:** a real external merchant pays **US$19.99**

---

## 0. Purpose

This document is the authoritative StoreOps execution baseline for the payment-validation stage.

Its purpose is to prevent the project from becoming a generic SEO/GEO/AEO audit SaaS, a large dashboard, or an overbuilt product before real merchant willingness-to-pay is proven.

The current job is simple:

1. Build the smallest trustworthy StoreOps experience.
2. Make the free output genuinely useful and evidence-backed.
3. Make the paid offer materially more valuable than generic ChatGPT/Claude advice.
4. Test the full experience with the owner first.
5. Only after owner acceptance, test with real external Shopify merchants.
6. If real payment demand does not appear after the defined test, stop product development.

This document supersedes broader implementation instructions where they conflict with the payment-validation scope.

---

## 1. Product identity

**Product name:** StoreOps by Vita Pet System  
**Primary category:** Shopify Purchase-Path Verification  
**Target user:** Shopify merchants, initially US / UK / AU; Traditional Chinese version also required for owner/HK/Chinese-speaking merchants.  
**Current price test:** US$19.99 one-time Founding Verification  
**Frontend repository:** `jasonyclok-cpu/storeops-vita`  
**Scanner repository:** `jasonyclok-cpu/gutsdogcom-ai-os`  
**Existing scanner core:** `src/revenue_leak_watchdog.py`

StoreOps is not positioned as an SEO, GEO, AEO, AIO or generic AI-analysis product.

---

## 2. Competitive scan — what already exists

A GitHub benchmark review found that the SEO/AEO/GEO space is already crowded with strong free/open-source projects. StoreOps should learn from their product strengths without copying their category.

### Claude SEO

Repository: `AgriciDaniel/claude-seo`

Observed strengths:

- broad technical SEO, content, E-E-A-T, schema, GEO, ecommerce and Google-data coverage;
- many parallel specialist skills/agents;
- evidence-led recommendations;
- recommendations designed to be falsifiable/testable rather than promotional;
- mature open-source traction.

**Lesson to adopt:** every StoreOps recommendation should state what was observed, what was expected, what evidence supports the finding, how to reproduce it, and how to know whether the issue is resolved.

**Do not copy:** the broad all-in-one SEO platform scope.

### GetCito

Repository: `ai-search-guru/getcito-worlds-first-open-source-aio-aeo-or-geo-tool`

Observed strengths:

- AI visibility tracking;
- prompt monitoring;
- citation/mention analysis;
- competitor benchmarking;
- background jobs and reports;
- REST API and white-label capability.

**Lesson to adopt:** turn raw technical output into a repeatable professional report artifact and, later, support before/after history.

**Do not copy:** AI-visibility monitoring as the current StoreOps wedge.

### GEO Optimizer / GeoReady

Repository: `Auriti-Labs/geo-optimizer-skill`

Observed strengths:

- strong free audit;
- clear technical categories;
- concrete fixes;
- history/regression concepts;
- free value first, recurring paid value later.

**Lesson to adopt:** the free StoreOps result must prove value before asking for payment; the paid product must add a new layer of work, not merely more prose.

**Do not copy:** arbitrary readiness scoring as StoreOps' main value proposition.

### shopify-geo-audit

Repository: `builtbyabs/shopify-geo-audit`

Observed strengths:

- Shopify-specific positioning;
- no account / no API key / low friction;
- outputs paste-ready fixes rather than only a report;
- clear priority list;
- SSRF-protected crawling.

**Lesson to adopt:** StoreOps should provide a developer-ready Fix Brief and clear next action, not vague advice.

**Do not copy:** Shopify + GEO as differentiation. That already exists.

### Mentha

Repository: `beenruuu/Mentha`

Observed strengths:

- real browser automation;
- captures what a real user sees;
- structured result processing;
- competitor and historical reporting.

**Lesson to adopt:** StoreOps' paid verification should use real desktop/mobile browser reproduction where appropriate and include screenshot evidence.

**Do not copy:** general AI-answer-engine monitoring.

### AI Visibility Audit

Repository: `syntropicsignal-ai/ai-visibility-audit`

Observed strengths:

- ecommerce-focused report productization;
- buyer-query framing;
- competitor share and client-ready outputs.

**Lesson to adopt:** the report must look like a professional merchant artifact that can be handed to a developer or stakeholder.

### Plyxo

Repository: `pixelfogg/Plyxo-CRO-SEO-AIO-AEO-GEO`

Observed strengths:

- CRO + SEO + GEO integration;
- screenshots and visual friction localization;
- code-fix framing;
- competitor intelligence.

**Lesson to adopt:** screenshot evidence and actionable remediation can materially improve perceived value.

**Explicitly do not adopt:** unsupported revenue-loss projections, artificial conversion-lift promises, or broad "everything optimizer" positioning.

---

## 3. StoreOps differentiation

The primary differentiator is not SEO, GEO, AI analysis, scoring or dashboards.

The differentiator is:

> **SEO helps people find your store. StoreOps verifies they can actually buy from it.**

Traditional Chinese:

> **SEO 幫客人搵到你；StoreOps 驗證客人嚟到之後，係咪真係買得到。**

Second positioning principle:

> **We don't guess what might be wrong. We reproduce what actually happens.**

Supporting line:

> **Real storefront. Real purchase path. Evidence included.**

Traditional Chinese:

> **我哋唔估問題可能喺邊；我哋重現實際發生嘅購買流程。**

> **真實店舖、真實購買路徑、附有證據。**

---

## 4. What StoreOps sells

StoreOps does **not** sell generic AI advice.

It sells:

**LIVE STOREFRONT VERIFICATION**  
+ **REPRODUCIBLE EVIDENCE**  
+ **DEVELOPER-READY NEXT STEPS**  
+ **ONE RETEST AFTER CHANGE**

General-purpose AI can suggest what might be wrong.

StoreOps must show what actually happened on the merchant's live storefront during a defined purchase-path verification.

If the output could be replaced by pasting a URL into ChatGPT or Claude and asking for generic advice, the StoreOps output is not good enough.

---

## 5. Existing technical advantage

The existing Revenue Leak Watchdog already performs deterministic public Shopify checks without Shopify Admin access, OAuth, app installation, customer data or payment submission.

Current verified path:

`Product page -> available variant -> Add to Cart -> cart read-back -> variant/quantity/price consistency -> checkout handoff -> STOP`

Existing safety boundary:

- no Shopify Admin API;
- no merchant login;
- no customer/order data;
- no payment details;
- no real order placement;
- no discount guessing/brute force;
- no fake revenue-loss calculation;
- unsupported or uncertain cases are WARN, not false FAIL.

This deterministic scanner is an asset. Do not replace it with generic LLM reasoning.

---

## 6. Locked validation strategy

Until real payment demand is proven, build only the **Payment Validation MVP**.

Locked funnel:

`Visit -> Store URL -> Email for free Evidence Snapshot -> real scan/review -> free report delivered -> US$19.99 Founding Verification -> Stripe payment`

Do not build the complete self-service SaaS first.

Do not build features merely to make the product look larger.

---

## 7. Bilingual requirement

StoreOps must have two complete customer-facing languages:

1. English
2. Traditional Chinese (`繁體中文`)

English is the default for US / UK / AU traffic.

Language control:

`EN | 繁中`

Both languages must have full content and functional parity.

Required bilingual coverage includes:

- landing page;
- navigation;
- hero;
- URL input;
- email capture;
- confirmation;
- sample report;
- real free Evidence Snapshot;
- PASS/WARN/FAIL explanation;
- Founding Verification offer;
- refund wording;
- trust/safety;
- FAQ;
- error states;
- transactional report email;
- Privacy / Terms customer-facing text;
- future results/report screen.

Internal codes remain:

- PASS
- WARN
- FAIL

Recommended Traditional Chinese labels:

- `PASS｜通過`
- `WARN｜需進一步驗證`
- `FAIL｜確認異常`

Do not translate internal API state names.

---

## 8. Free product — Evidence Snapshot

Do not call the free product a generic "AI audit".

Preferred name:

**StoreOps Purchase Path Evidence Snapshot**

Traditional Chinese:

**StoreOps 購買流程證據快照**

The free output must already be useful enough to establish trust.

Required content:

1. Store identity / domain.
2. Verification timestamp.
3. Verification ID.
4. Scope tested.
5. Actual product URL tested.
6. Actual variant tested where supported.
7. Purchase-path sequence.
8. PASS / WARN / FAIL by check.
9. Evidence summary.
10. Explicit limitations.
11. What was not verified automatically.
12. Recommended next step.

The free report must be based on real scanner execution, not generic generated advice.

---

## 9. Proof-of-Work standard

Every report should visibly prove that StoreOps actually performed work.

Include where supported:

- Verification ID, e.g. `SO-2026-XXXX`;
- verification timestamp;
- tested storefront;
- tested product;
- tested variant;
- test path;
- environment/method where appropriate;
- Evidence IDs;
- retest status when applicable.

This should make the artifact feel closer to a QA verification report than an AI chat transcript.

Do not expose sensitive session tokens, checkout tokens, customer data or credentials.

---

## 10. Finding schema

Every material finding must answer:

### WHAT WE TESTED

Exactly which purchase-path step was exercised.

### EXPECTED

What should normally happen.

### OBSERVED

What actually happened.

### EVIDENCE

What concrete observation supports the result.

### CONFIDENCE

One of:

- Verified
- Inconclusive

### IMPACT CATEGORY

Use only evidence-backed categories:

- **BLOCKING** — customer cannot continue the verified purchase path.
- **INTEGRITY** — variant, quantity, price or cart state does not match expectation.
- **FRICTION** — purchase remains possible but a verified interaction creates purchase friction.
- **INCONCLUSIVE** — available evidence is insufficient.

### PRIORITY

Only if evidence supports prioritization:

- **P1** — purchase blocked.
- **P2** — purchase-path integrity risk.
- **P3** — verified purchase friction.
- **P4** — observation/lower-priority item.

### NEXT STEP

A concrete next action.

### RETEST CONDITION

What change or condition should be rechecked to determine whether the problem is resolved.

Never exaggerate severity to make the paid service look more valuable.

---

## 11. PASS / WARN / FAIL semantics

### PASS

The tested path completed successfully and no supported critical failure was found in that tested scope.

PASS does not mean the entire store is leak-free.

### WARN

The system does not have enough reliable evidence to declare PASS or FAIL.

WARN is not a confirmed revenue leak.

### FAIL

A reproducible critical failure was detected with sufficient evidence.

Critical rule:

> **UNCERTAIN OR UNSUPPORTED CASES MUST BE WARN.**

Never convert a timeout, bot block, unsupported storefront pattern or synthetic-runner limitation into a fake merchant FAIL.

---

## 12. What the free Evidence Snapshot must not do

Do not include:

- arbitrary health score;
- invented conversion score;
- invented monthly revenue loss;
- invented potential uplift;
- fake customer urgency;
- unsupported root cause;
- generic 1,000-word AI essay;
- sample data represented as the merchant's actual data.

Sample/demo content must be labelled clearly as:

- `Sample Report`
- `Example Finding`

---

## 13. Paid product — Founding Verification

Product:

**StoreOps Founding Verification**

Price test:

**US$19.99 one-time**

The paid product must offer materially more value than the free Evidence Snapshot.

Required paid deliverables:

1. Real desktop browser verification.
2. Real mobile browser/viewport verification.
3. Manual reproduction of the reported or scanner-flagged issue.
4. Screenshot evidence where useful and safe.
5. Exact reproduction steps.
6. Expected vs Observed.
7. Verified vs Inconclusive distinction.
8. Evidence-backed impact category.
9. Priority where supported.
10. Developer-ready Fix Brief.
11. One verification retest after the merchant makes the recommended change.

Refund promise:

> **If no actionable issue can be verified, you can request a full refund.**

Do not promise guaranteed revenue, guaranteed issue discovery or guaranteed conversion improvement.

---

## 14. Developer-ready Fix Brief

The paid output should be useful to a merchant's developer, theme developer, app developer or Shopify expert.

A Fix Brief should include where supported:

- affected purchase-path step;
- exact reproduction path;
- Expected vs Observed;
- screenshots/evidence references;
- likely technical area to inspect, without pretending certainty;
- relevant theme/app/cart component context if visibly supported;
- specific checks to perform;
- what not to change prematurely;
- retest condition.

Avoid vague wording such as:

> "Check your Shopify settings."

Prefer actionable wording such as:

> "Reproduce on the live theme, isolate the cart-drawer behavior, confirm the checkout CTA receives the expected Shopify checkout destination, then retest the same path on mobile."

Only state a root cause when evidence supports it.

---

## 15. Retest as a paid-value differentiator

One retest after the merchant makes a recommended change is included in the US$19.99 Founding Verification.

This changes the perceived product from:

> "Buy a report"

into:

> "Reproduce -> prove -> fix brief -> change -> verify again"

The retest should compare:

- original finding;
- merchant-reported change;
- same purchase path;
- new observed result;
- final status.

Future productization may store before/after history, but that is not required before payment validation.

---

## 16. Landing-page positioning

Primary direction:

> **Is your Shopify store quietly losing sales?**

Supporting statement:

> **SEO helps people find your store. StoreOps verifies they can actually buy from it.**

Proof line:

> **We don't guess what might be wrong. We reproduce what actually happens.**

Trust strip:

- No Shopify app
- No login
- No order placed

Primary action:

**Check my store**

The first ask must be the Store URL, not email.

---

## 17. Landing-page information architecture

Recommended sequence:

1. Navigation + `EN | 繁中`.
2. Hero + Store URL field.
3. Trust strip.
4. Visual Sample Evidence Snapshot.
5. "What StoreOps actually tests".
6. PASS/WARN/FAIL semantics.
7. "Evidence, not guesses" differentiation.
8. Free Evidence Snapshot explanation.
9. Founding Verification comparison.
10. Developer-ready Fix Brief example.
11. One-retest value.
12. Refund reassurance.
13. Trust & Safety.
14. FAQ.
15. Support / Privacy / Terms footer.

Do not make it look like a generic SEO dashboard SaaS.

---

## 18. Design direction

Use the repo-local `frontend-app-builder` skill.

Desired visual identity:

- premium;
- technical;
- trustworthy;
- evidence-led;
- modern SaaS quality without generic template feeling.

Palette direction:

- deep ink / navy foundation;
- premium emerald primary;
- warm coral/orange brand accent;
- subtle blue/lavender highlights.

Semantic status colors:

- PASS = green;
- WARN = amber;
- FAIL = deep red.

FAIL red must remain visually separate from brand coral/orange.

Avoid:

- monochrome green;
- bento-grid overload;
- fake metrics;
- excessive pills/cards;
- fake testimonials;
- crypto/neon aesthetics;
- made-up "revenue lost" widgets.

---

## 19. Phase A — minimum truthful product

Before the live self-service scan API exists, the merchant flow is:

`Store URL -> email for report delivery -> secure lead capture -> existing scanner run/review -> Evidence Snapshot emailed within approximately 1 business day -> US$19.99 Founding Verification`

Truthfulness rules:

- no fake loading percentage;
- no fake "scanning now" animation if no backend scan is running;
- no sample data shown as the merchant's result;
- clearly say the report will be emailed.

Suggested copy:

> **We'll verify your store and email the Evidence Snapshot.**

> **Your verification will normally arrive within 1 business day.**

---

## 20. Phase A minimum backend

GitHub Pages must never connect directly to PostgreSQL.

Minimum server endpoint:

`POST /api/leads`

Input:

```json
{
  "store_url": "https://example.com",
  "email": "merchant@example.com",
  "locale": "en"
}
```

Responsibilities:

- URL validation/normalization;
- email validation;
- rate limiting;
- secure server-side persistence;
- timestamp;
- locale;
- generic confirmation response.

No database credentials or email-service secrets may be exposed to browser JavaScript.

The minimum backend should remain small and should be designed so `/api/scan` can be added later without rewriting the frontend architecture.

---

## 21. Full live scanner API is explicitly deferred

Do **not** build before payment validation unless owner explicitly changes the gate:

- full `/api/scan` job system;
- live progress engine;
- large worker/queue architecture;
- self-service merchant account;
- merchant dashboard;
- subscriptions;
- persistent monitoring;
- AI explanation layer;
- automated store mutations;
- broad shipping/promotion automation;
- broad CRO/SEO/GEO suite.

Existing scanner code should still be reused to produce Phase A reports.

---

## 22. Email capture

Email must not be the first ask.

Phase A:

- email required only after Store URL submission because the free report is delivered by email.

Allowed use without separate marketing consent:

- report delivery;
- necessary service/status communication.

Do not automatically treat report-delivery email as newsletter/general marketing consent.

If StoreOps later wants promotional follow-up, use a separate optional unchecked consent control.

---

## 23. Transactional email quality

Email deliverability is part of product quality.

Before external testing:

- choose one transactional email provider;
- configure SPF;
- configure DKIM;
- configure DMARC;
- verify sender domain;
- test Gmail inbox placement;
- test Outlook inbox placement;
- set support/reply behavior clearly.

Suggested sender:

`StoreOps by Vita Pet System <noreply@vitapetsystem.com>`

Reply-To:

`support@vitapetsystem.com`

---

## 24. Payment

Target paid product:

**StoreOps Founding Verification**

Price:

**US$19.99 one-time**

A real Stripe LIVE Payment Link must be supplied/approved by the owner before real payment CTA activation.

Never invent a Stripe URL.

Do not treat Stripe test mode as live.

---

## 25. Analytics

Use one lightweight provider for MVP:

**GA4**

Minimum funnel events:

- `page_view`
- `hero_url_submitted`
- `phase_a_email_captured`
- `phase_a_confirmation_viewed`
- `sample_report_viewed`
- `pricing_section_viewed`
- `founding_verification_cta_viewed`
- `founding_verification_cta_clicked`
- `payment_link_visited` where measurable

Do not send to GA4:

- email;
- full store URL;
- scan evidence;
- job evidence;
- customer/order/payment data.

Analytics failure must never break StoreOps functionality.

---

## 26. Owner Acceptance Gate — mandatory before external launch

The owner is the first customer-quality gate.

Use a real Shopify store, preferably GutsDogCom, and test the complete Payment Validation MVP.

Owner must experience:

- English version;
- Traditional Chinese version;
- language switching;
- landing page;
- Store URL input;
- email capture;
- confirmation;
- free Evidence Snapshot;
- evidence quality;
- paid Founding Verification offer;
- desktop layout;
- mobile layout;
- refund/trust copy.

Owner must answer:

> **If this belonged to a company I did not know, after seeing this free Evidence Snapshot, would I personally pay US$19.99 for the Founding Verification?**

Possible results:

### YES

Owner Acceptance = PASS. External payment validation may begin.

### MAYBE

Owner Acceptance = FAIL. Improve only the core value proposition, report, trust, offer or UX. Retest owner.

### NO

Owner Acceptance = FAIL. Do not launch externally. Do not build Phase B. Fix the product value first.

Functional QA alone does not count as owner acceptance.

---

## 27. Owner report-value checklist

Before external launch, owner should be able to answer YES to the following:

- Does the report prove StoreOps actually ran a test?
- Does the report contain evidence rather than generic prose?
- Is Expected vs Observed clear?
- Is WARN clearly different from FAIL?
- Does it avoid unsupported revenue claims?
- Could a developer act on the Fix Brief?
- Is the paid product materially more valuable than the free report?
- Does one retest make the US$19.99 offer feel complete?
- Does the product feel harder to replace with a single ChatGPT/Claude prompt?
- Would I personally pay if this were not my own product?

If multiple answers are NO, do not launch.

---

## 28. External payment-validation test

Only after Owner Acceptance PASS:

Test with real external Shopify merchants who do not personally know the owner.

Initial target:

**approximately 20–30 qualified prospects**

Prefer signal-led prospects with explicit purchase-path pain, such as public reports of:

- checkout failure;
- cart failure;
- conversion drop with checkout symptoms;
- payment/shipping/promotion problems;
- mobile purchase friction;
- broken-store symptoms.

Do not rely on broad random-store scanning as the primary lead strategy.

Track:

`Prospects contacted -> Visits -> Store URL submissions -> Evidence Snapshots delivered -> Founding Verification CTA clicks -> Payment-link visits -> Actual payments`

---

## 29. Commercial success gate

The key event is:

> **A real external merchant who does not personally know the owner pays US$19.99.**

At least one payment = initial payment-validation PASS.

Prefer 2–3 real paid verifications before assuming repeatable demand.

After 2–3 payments, test US$29 before considering US$39/49.

---

## 30. Stop rule

If merchants submit stores and consume the free report but nobody pays:

- do not add product features;
- run one controlled improvement round focused only on report value, trust, positioning, CTA, offer and pricing presentation;
- test again.

If two meaningful external tests with qualified prospects produce **0 real payments** despite report consumption:

> **STOP STOREOPS PRODUCT DEVELOPMENT.**

Do not continue adding features in the hope that another feature will create demand.

---

## 31. What unlocks after payment validation

Only after payment-validation PASS may the broader StoreOps roadmap unlock, including:

- live `/api/scan`;
- real queued/running/done state;
- instant on-screen PASS/WARN/FAIL;
- worker/job persistence;
- richer report automation;
- before/after history;
- persistent monitoring;
- alerting;
- broader browser automation;
- future Shopify app/OAuth if justified;
- future higher-priced plans;
- future optional AI explanation layer.

The existing v3 architecture remains a future implementation reference, not a pre-validation requirement.

---

## 32. Security and trust boundaries

Never:

- place real orders;
- submit payment details;
- bypass login or access controls;
- stress test stores;
- brute-force discount codes;
- commit customer PII;
- commit secrets;
- fabricate evidence;
- claim unsupported root cause;
- invent lost-revenue numbers;
- make automated high-risk merchant writes.

Use least privilege.

---

## 33. Report design standard

The report must look like a professional verification artifact, not an AI chat transcript.

Prefer:

- concise findings;
- timestamp;
- Verification ID;
- tested path;
- evidence references;
- screenshots where appropriate;
- Expected vs Observed;
- exact reproduction steps;
- clear status semantics;
- concrete Fix Brief;
- retest state.

Avoid:

- long generic paragraphs;
- vague Shopify advice;
- fake scores;
- unsupported statistics;
- decorative dashboards with no product value.

---

## 34. Value-replacement test

Before any report is delivered, ask:

> **Could the merchant get essentially the same value by pasting their store URL into a generic ChatGPT or Claude conversation?**

If YES, the report is not good enough.

StoreOps must add value through:

- execution;
- reproducible verification;
- real purchase-path testing;
- evidence;
- screenshots where relevant;
- developer-ready next steps;
- retesting.

Not through more generic prose.

---

## 35. Immediate Codex scope

Codex must use the repo-local:

`.agents/skills/frontend-app-builder/SKILL.md`

Immediate task is **design first**.

Required bilingual concepts/states:

- EN / 繁中 language selector;
- hero;
- Store URL entry;
- trust strip;
- Phase A email step;
- confirmation;
- Sample Evidence Snapshot;
- real-report presentation language;
- PASS/WARN/FAIL;
- Proof-of-Work metadata;
- Expected / Observed / Evidence / Confidence / Next Step;
- US$19.99 Founding Verification;
- free vs paid comparison;
- Developer-ready Fix Brief;
- one-retest value;
- refund reassurance;
- Trust & Safety;
- FAQ;
- mobile concept;
- desktop concept.

The design must make StoreOps feel materially different from a generic SEO/GEO audit SaaS.

Do not deploy until owner visually approves the design.

---

## 36. Immediate Codex instruction

Use this instruction after reading this file:

```text
Read docs/STOREOPS_PAYMENT_VALIDATION_BASELINE_V4.md in full.
Treat it as the locked StoreOps payment-validation baseline.

Use the repo-local frontend-app-builder skill.

Do not build the full SaaS.
Do not build the live /api/scan platform yet.
Do not build SEO/GEO/AEO features.
Do not add generic AI analysis.

First create the complete bilingual English + Traditional Chinese visual concept for the Payment Validation MVP.

The product must be positioned as Shopify Purchase-Path Verification, not a generic audit SaaS.

Core message:
SEO helps people find your store. StoreOps verifies they can actually buy from it.

Core proof principle:
We don't guess what might be wrong. We reproduce what actually happens.

The free product is a StoreOps Purchase Path Evidence Snapshot.
The paid product is a US$19.99 Founding Verification with desktop/mobile reproduction, screenshot evidence where useful, exact reproduction steps, Expected vs Observed, developer-ready Fix Brief, and one retest after change.

Create desktop and mobile concepts including the report artifact itself.

Do not deploy.
Do not change production.
Do not invent evidence, revenue loss, fake scores or Stripe URLs.

Stop and present the complete visual concept for owner approval.
```

---

## 37. Definition of Done for the validation MVP

The Payment Validation MVP is not DONE because code exists or a deployment succeeds.

Required sequence:

`design -> owner visual approval -> implementation -> live/staging deployment -> read-back -> functional QA -> owner end-to-end test -> owner willingness-to-pay YES -> external test`

Commercial validation requires:

`real external merchant -> real US$19.99 payment`

---

## 38. Final principle

StoreOps should remain:

- deterministic first;
- evidence first;
- truthful first;
- low-cost first;
- simple first;
- payment-validation first.

The project must not win by having more features than SEO/GEO tools.

It must win by doing one merchant-critical job more credibly:

> **Prove whether the buying path actually works, show the evidence, explain what to fix, and verify the change.**
