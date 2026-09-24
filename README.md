# Renovation Decision Platform

**Status:** validation-first / pre-MVP  
**Market:** Serbia first, Belgrade first  
**Initial vertical:** complete bathroom renovation  
**Last strategy refresh:** 2026-09-24

## Product thesis

Renovation Decision Platform is **not** another material calculator and **not** another contractor marketplace.

It is an independent decision and control layer for homeowners:

```text
standardize scope
  -> estimate a local evidence-backed range
  -> normalize contractor quotes
  -> expose omissions and ambiguity
  -> compare like-for-like
  -> convert the selected quote into committed budget
  -> control change orders, invoices and payments
  -> collect verified actuals
  -> improve local benchmarks
```

### Core promise

> Before you sign or pay, understand what is included, what is missing, what a comparable local range looks like, and where the final project cost is likely to land.

## Why this position

The market already contains strong partial solutions:

- material/quantity calculators and project tools (LiczMat, ProAdapt);
- contractor marketplaces and rough price guides (Daibau, Ne Radi Sam);
- renovation project control and AI quote scanning (HouseLog);
- mature international contractor/project suites (Houzz Pro, Buildertrend, magicplan).

The defensible wedge is therefore **local price intelligence + canonical renovation taxonomy + quote normalization + verified actuals + auditable budget lifecycle**.

AI is an extraction and explanation layer. It is not the source of truth for prices.

## Current decision

**Do not build the full platform yet.**

The next investment gate is `R0 — Evidence & Taxonomy Pilot`:

1. collect 30–50 real, anonymizable bathroom renovation quotes / bills / final invoices from Belgrade;
2. define a canonical bathroom work-item taxonomy;
3. manually normalize the sample;
4. create 5–10 manual Decision Reports for recent/current renovators;
5. test whether the report changes a decision, reveals material omissions, or creates willingness to pay;
6. only then authorize the software MVP.

## Canonical documents

- [`docs/PRODUCT_STRATEGY_AND_PRD.md`](docs/PRODUCT_STRATEGY_AND_PRD.md)
- [`docs/MARKET_AND_OPPORTUNITY_RESEARCH.md`](docs/MARKET_AND_OPPORTUNITY_RESEARCH.md)
- [`docs/ROADMAP.md`](docs/ROADMAP.md)
- [`docs/DATA_PRICE_ESTIMATION_PLAN.md`](docs/DATA_PRICE_ESTIMATION_PLAN.md)
- [`docs/QUOTE_INTELLIGENCE_AND_PROJECT_CONTROL.md`](docs/QUOTE_INTELLIGENCE_AND_PROJECT_CONTROL.md)
- [`docs/BUSINESS_MODEL_GTM.md`](docs/BUSINESS_MODEL_GTM.md)
- [`docs/TECHNICAL_ARCHITECTURE.md`](docs/TECHNICAL_ARCHITECTURE.md)
- [`docs/VALIDATION_KPI_RISK_PLAN.md`](docs/VALIDATION_KPI_RISK_PLAN.md)
- [`docs/RESEARCH_AND_DATA_COLLECTION_PLAYBOOK.md`](docs/RESEARCH_AND_DATA_COLLECTION_PLAYBOOK.md)
- [`docs/EPICS_BACKLOG.md`](docs/EPICS_BACKLOG.md)
- [`docs/DECISION_LOG.md`](docs/DECISION_LOG.md)
- [`docs/SOURCE_REGISTER.md`](docs/SOURCE_REGISTER.md)

## Explicit non-goals before validation

No broad contractor marketplace, mobile app, nationwide live retail scraping, 3D design suite, automated structural/electrical engineering judgment, generic subsidy portal, or regional expansion is authorized before the core decision loop is validated.
