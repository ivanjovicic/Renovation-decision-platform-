# Agent instructions — Renovation Decision Platform

## Canonical strategy

Read `README.md`, `docs/PRODUCT_STRATEGY_AND_PRD.md`, `docs/ROADMAP.md`, and `docs/DECISION_LOG.md` before proposing implementation.

The repository is validation-first. Do not turn it into a generic construction super-app.

## Product boundary

The core product is:

`scope -> evidence-backed benchmark -> quote normalization -> comparison -> committed budget -> changes/actuals -> better benchmark`

Do not treat AI-generated prices as truth. Price outputs must come from deterministic rules and versioned evidence-backed observations.

## Before coding

Production MVP work remains blocked until R0 gates in `docs/VALIDATION_KPI_RISK_PLAN.md` pass. Research/data tooling, prototypes, schemas and manual-report support are allowed when they directly help those gates.

## Data rules

Every market-price observation must preserve:

- canonical work item;
- location granularity;
- observation date;
- unit / quantity;
- labor/material/VAT inclusion when known;
- source/evidence tier;
- normalization notes;
- confidence / exclusion reasons.

Never silently combine incomparable scopes.

## AI rules

AI may:
- extract line items;
- propose taxonomy mappings;
- detect ambiguous text;
- summarize differences;
- draft clarification questions.

AI must not:
- invent benchmark prices;
- claim a contractor is dishonest;
- make structural, electrical, gas or other licensed-engineering safety judgments;
- automatically choose the “best contractor” based on an opaque score.

## Marketplace / commerce boundary

Leads, contractor supply, financing, subsidies and material commerce are expansion layers. They must not distort the independent benchmark or quote analysis.

Paid/sponsored partners must be clearly separated from benchmark methodology.

## Documentation discipline

When evidence changes the thesis, update:
1. `docs/MARKET_AND_OPPORTUNITY_RESEARCH.md`
2. `docs/DECISION_LOG.md`
3. affected canonical plan(s)
4. `docs/SOURCE_REGISTER.md`

Avoid duplicate strategy documents.
