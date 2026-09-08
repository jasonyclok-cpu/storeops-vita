# StoreOps × Ghost Demand — Locked Product Boundary

**Status:** product-boundary guardrail  
**Applies to:** StoreOps payment validation and future Ghost Demand productization  
**Purpose:** prevent both products from collapsing into a generic “AI Shopify growth audit”.

## Core distinction

**Ghost Demand** answers:

> What do customers want that the market or this merchant is not satisfying yet?

**StoreOps** answers:

> A customer already wants to buy. Can the live Shopify purchase path actually complete as expected?

Short form:

> Ghost Demand finds unmet demand before the product wins. StoreOps verifies the purchase path after demand arrives.

Traditional Chinese:

> Ghost Demand 搵「有需求但未被滿足」；StoreOps 驗證「有購買意圖之後，網站係咪真係買得到」。

## Ghost Demand owns

- unmet-demand discovery;
- public/self-volunteered demand signal mining;
- category and product-gap discovery;
- buyer-question / complaint / request clustering;
- evidence that a product or offer opportunity may exist;
- opportunity validation before recommending product creation or assortment expansion;
- “what should this merchant consider selling or testing?” questions.

Ghost Demand must not diagnose cart/checkout/payment-path failures as its core product.

## StoreOps owns

- live storefront reachability;
- product and available-variant verification;
- Add to Cart execution;
- cart read-back;
- variant, quantity and base-price integrity;
- checkout handoff verification;
- real desktop/mobile reproduction in the paid verification scope;
- screenshot / reproduction evidence;
- Expected vs Observed findings;
- Developer-ready Fix Brief;
- one post-fix retest where included by the current offer;
- “customers want to buy — is the buying path working?” questions.

StoreOps must not become a product-opportunity, category-demand, SEO, GEO, AEO or broad growth-advice platform during payment validation.

## Shared infrastructure is allowed

The products may reuse infrastructure without merging their customer promise. Shared layers may later include:

- merchant/store identity and Shopify URL intake;
- public storefront fetching and safe URL validation;
- evidence envelopes and durable verification IDs;
- report rendering;
- bilingual EN / Traditional Chinese presentation;
- email delivery;
- payment/account infrastructure;
- shared safety, provenance and retention rules.

Shared infrastructure does **not** mean shared scoring or a single generic audit report.

## Routing rule

Use this deterministic routing rule when scope is ambiguous:

- “What should I sell / what demand is missing?” → **Ghost Demand**
- “Why can interested shoppers not complete the purchase path?” → **StoreOps**

If a request contains both, keep two findings/modules rather than blending them into one vague recommendation.

## Future platform shape

Only after each wedge is independently validated may they be presented under a broader commerce-intelligence platform, for example:

- Demand Layer — Ghost Demand
- Transaction Layer — StoreOps

Do not build a combined platform merely because the infrastructure can be shared. Each module must first prove its own willingness-to-pay gate.

## Anti-overlap test

Before adding a StoreOps feature, ask:

> Does this feature verify an observed purchase-path behavior on a live store?

If **no**, it probably does not belong in StoreOps payment validation.

Before adding a Ghost Demand feature, ask:

> Does this feature identify or validate unmet demand or a product/offer opportunity?

If **no**, it probably does not belong in Ghost Demand.
