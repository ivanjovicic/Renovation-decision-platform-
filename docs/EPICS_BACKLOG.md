# Epics & Prioritized Backlog

Priorities: P0 = required for next release; P1 = high-value next; P2 = later.

## EPIC E0 — Taxonomy & Pricebook Foundation (P0)
- E0.1 Define bathroom canonical work items.
- E0.2 Units, dependencies, exclusions and quantity rules.
- E0.3 PriceObservation schema + evidence tiers.
- E0.4 Location hierarchy Serbia → city → municipality.
- E0.5 Source/provenance registry.
- E0.6 Benchmark builder v0 manual/import.
- E0.7 Data quality dashboard skeleton.

**Acceptance:** every displayed price can answer „odakle, kada, za koji scope i sa kojim confidence-om?“

## EPIC E1 — Bathroom Scope Builder (P0)
- wizard UX;
- room dimensions/openings;
- condition/building age questions;
- demolition;
- plumbing/electrical;
- waterproofing;
- tiling;
- sanitary fixtures;
- logistics;
- material tier;
- scope summary/edit.

## EPIC E2 — Estimate Engine (P0)
- deterministic quantity engine;
- labor/material ranges;
- risk modifiers;
- contingency;
- low/base/high result;
- source/confidence display;
- immutable EstimateSnapshot;
- golden fixtures and tests.

## EPIC E3 — SEO/Public Results (P0)
- indexable landing pages;
- structured metadata;
- calculator deep links;
- shareable estimate;
- content/source update timestamps;
- analytics events;
- Search Console integration.

## EPIC E4 — Quote Upload & Extraction (P0/P1)
- secure upload;
- native PDF text extraction;
- OCR fallback;
- structured AI extraction;
- schema validation;
- taxonomy mapping;
- user correction UI;
- extraction regression set.

## EPIC E5 — Quote Intelligence (P1)
- coverage matrix;
- missing/unclear items;
- benchmark deviation;
- Quote Clarity metrics;
- clarification questions;
- quote report export/share.

## EPIC E6 — Compare Quotes (P1)
- 2–3 quote side-by-side;
- normalized units;
- material/labor split;
- exclusions;
- VAT/payment/term/warranty fields;
- comparable coverage summary;
- no automatic contractor winner.

## EPIC E7 — Project Budget Control (P1)
- Budget ceiling;
- Estimated;
- Committed;
- Invoiced;
- Paid;
- Remaining estimate;
- Forecast at completion;
- cash/payment milestones.

## EPIC E8 — Change Orders (P1)
- proposed/approved/rejected/done;
- delta price/timeline;
- approval evidence;
- forecast recalculation;
- audit trail.

## EPIC E9 — Documents & Evidence (P1)
- quotes/contracts;
- invoices/receipts;
- payments;
- photos;
- warranties;
- retention/delete/export;
- evidence pack PDF/export.

## EPIC E10 — Actual Price Flywheel (P1)
- project completion confirmation;
- actual cost capture;
- evidence classification;
- anonymization;
- contributor dedupe;
- benchmark rebuild;
- sample/confidence UI.

## EPIC E11 — Contractor Context (P2)
- manual contractor records;
- business ID;
- APR verification workflow compliant with terms;
- verified-job review;
- contractor quote history within user project.

## EPIC E12 — Leads (P2)
- „želim ponude“ opt-in;
- standardized brief;
- partner routing;
- lead status;
- monetization rules;
- neutrality/sponsored controls.

## EPIC E13 — Materials Commerce (P2)
- shopping list;
- reference product mapping;
- partner feed ingestion;
- product availability/pricing;
- sponsored/affiliate disclosure;
- basket comparison.

## EPIC E14 — Full Apartment (P2)
Compose modules rather than new monolith:
- bathroom;
- painting;
- flooring;
- electrical;
- plumbing;
- demolition;
- doors/joinery;
- logistics.

## EPIC E15 — Regional Scale (P2)
- Novi Sad;
- Niš;
- locality fallback rules;
- regional pricebooks;
- market-specific SEO.

## First 20 implementation tickets
1. WorkItemDefinition schema.
2. PriceObservation schema.
3. Source/evidence taxonomy.
4. Location hierarchy.
5. Bathroom scope template.
6. Demolition quantity rules.
7. Tiling quantity rules.
8. Waterproofing rules.
9. Plumbing work items.
10. Electrical work items.
11. Labor benchmark import v0.
12. Material reference import v0.
13. Estimate engine interfaces.
14. Estimate snapshot/versioning.
15. Bathroom wizard UI.
16. Estimate result breakdown UI.
17. Confidence/provenance component.
18. Golden estimate test fixtures.
19. Analytics event schema.
20. SEO landing template.

**Do not start quote AI before tickets 1–4 and taxonomy quality are stable enough.**

## Backlog refresh — 2026-09-24

### EPIC E0A — Evidence Corpus & Normalization Tooling (P0, before product MVP)
- redaction/anonymization checklist/tooling;
- raw line-item capture;
- manual taxonomy mapping UI/spreadsheet schema;
- evidence tiering;
- normalization-confidence field;
- reviewer disagreement capture;
- R0 metrics export.

### EPIC E0B — Scope Gap Library (P0)
- project-type expected item model;
- required / conditional / optional classification;
- present/absent/ambiguous observation capture;
- top omitted items report;
- versioning.

### EPIC E0C — Manual Decision Report Generator (P0)
- report template;
- quote coverage section;
- comparable total section;
- benchmark section with sample/confidence;
- clarification questions;
- limitations/disclaimer;
- export/share.

### Priority correction
`E4 Quote Upload & Extraction` must remain behind a successful manual R0 workflow. Do not automate a normalization process that has not yet become repeatable by humans.

### EPIC E16 — Renovation Readiness (Discovery/P2)
- purchase + renovation total-cost scenario;
- building-age/condition input;
- high-risk unknown checklist;
- partner/referral experiment;
- no structural inspection claims.

### EPIC E17 — Professional Report Channel (Discovery/P1-P2)
- co-branded report;
- client share link;
- professional notes/override;
- per-report/project pricing experiment.

### EPIC E18 — Financing Readiness (P2)
- documentation checklist;
- structured export;
- authorized-professional handoff;
- finance lead only after compliance review.

### EPIC E19 — Energy Efficiency Context (P2)
- detect relevant scope measures;
- official-call deep links;
- last-checked timestamp;
- no independent eligibility promise.
