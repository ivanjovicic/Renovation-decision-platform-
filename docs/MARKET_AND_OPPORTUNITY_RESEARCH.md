# Market & Opportunity Research

Last refreshed: **2026-09-24**

## 1. Executive view

The Serbian renovation opportunity is attractive **not because calculators are missing**, but because the homeowner still lacks a neutral way to answer four linked questions:

1. What is the real scope?
2. Are contractor quotes comparable?
3. Is the quoted cost plausible for this location, date and scope?
4. What will the final project cost become after changes and omissions?

The market is fragmented enough that this decision layer remains open, but competition has moved quickly. A simple calculator, AI quote parser or contractor directory is not sufficient differentiation.

## 2. Structural demand signals

### Old and privately owned housing stock

RZS Census 2022 records **2,261,051 residential buildings** in Serbia. The single largest construction-age cohort is **1961–1980 with 745,485 buildings**. RZS also reports **3,536,885 privately owned dwellings**, representing 97.9% of the housing stock. [S1][S2]

This does not equal annual renovation demand, but it creates a large structural base of owner-controlled, aging housing.

### Active real-estate transaction channel

RGZ reports **61,343 real-estate purchase contracts in H1 2026** with a market value of about **€4.2bn**. Apartments represented **61% of transaction value (€2.5bn)**, while Belgrade accounted for **55% of apartment transaction value**. [S20]

This creates a valuable acquisition moment: shortly before or after apartment purchase, buyers have unusually high renovation intent and a concrete budget decision.

### Continuing construction / home-improvement ecosystem

RZS reports 2,751 building permits in July 2026 and 36,390 completed dwellings in 2025; broader construction output remains large. [S3][S21]

The product should nevertheless stay focused on homeowner renovation rather than general construction.

## 3. Competitive map — refreshed

### A. Material calculation / project planning

**LiczMat** is stronger than a basic calculator competitor: its current product includes 15 calculators, 161 materials, projects, estimates, and visible product areas for Pro, clients, offers and deadlines. Its Android app also exports estimates and monetizes through AdMob. [S4][S22]

**Implication:** “more calculators” and “PDF estimate” are commodity features.

**ProAdapt** provides material quantity calculations based on manufacturer norms and waste assumptions. [S5]

**Implication:** use manufacturer technical data for norms, but do not compete primarily on quantity formulas.

### B. Marketplace / contractor discovery

**Daibau** combines price content with demand capture and contractor leads; its public pages also expose many concrete project descriptions and broad estimate ranges. [S6][S8][S23]

**Ne Radi Sam** targets contractor discovery and written offers in Serbia. [S9]

**Implication:** a broad contractor marketplace is a poor first wedge. Leads should be an optional downstream monetization layer after decision demand exists.

### C. Closest regional decision/project benchmark

**HouseLog (Slovenia)** is the most important direct benchmark. It now offers project budgets, phases, contractor records, documents, receipts, warranties, AI quote extraction, quote comparison, 5 free AI scans and a one-time per-project Premium model. [S10][S24]

**Implication:** budget tracking + AI quote scanning alone is not defensible. Our local benchmark and evidence model must be materially better.

### D. Mature international workflow suites

**Houzz Pro** can generate estimates/proposals/invoices/change orders with AI, import external files, use location in pricing, track estimated/actual costs and connect change orders to project financials. [S25][S26]

**Buildertrend** treats change orders as a first-class workflow with scope, supporting files and digital owner approval. [S27]

**magicplan** calculates labor/material estimates from floor plans and maintains custom item libraries. [S28]

**Implication:** future roadmap can learn from these workflows, but building a full contractor ERP or floor-plan takeoff suite would destroy focus.

## 4. Key market gap

The strongest open gap is:

> **Independent homeowner-facing quote intelligence grounded in local, normalized, recent and evidence-weighted Serbian renovation data.**

The platform should know the difference between:
- a public editorial “price guide”;
- a real contractor quote;
- an accepted quote;
- a final invoice / paid actual;
- a quote where materials are included vs excluded;
- a simple tile job vs large-format / difficult substrate / demolition / logistics-heavy scope.

That distinction is the product.

## 5. New opportunity tracks

These are opportunities, not MVP commitments.

### Opportunity O1 — Post-purchase Renovation Readiness Report

**Why:** apartment transactions are large and concentrated in Belgrade. [S20]

A buyer can enter property size, building age, visible condition and intended works and receive:
- initial renovation budget range;
- high-risk unknowns to inspect;
- suggested contingency;
- “purchase price + expected renovation” total acquisition cost.

**Distribution:** real-estate agencies, mortgage brokers, buyer communities, property portals.

**Guardrail:** informational budgeting only; no structural/safety inspection claim.

**Priority:** discovery after bathroom MVP proof.

### Opportunity O2 — Financing readiness / bank-prep workflow

OTP and Banca Intesa currently offer renovation/adaptation loans. OTP explicitly requires a bill of quantities/cost estimate verified by an authorized person; Intesa disburses against pro-forma invoices for part of the loan. [S29][S30]

Potential product:
- financing scenario calculator;
- documentation checklist;
- export a structured project package;
- handoff to an authorized professional for a bank-valid predmer/predračun.

**Important:** our automatically generated estimate must never be marketed as a bank-valid professional estimate unless reviewed/signed by an appropriately authorized professional.

**Revenue potential:** qualified financing leads or professional-review fee.

### Opportunity O3 — Energy-renovation / subsidy context

The Ministry of Mining and Energy’s SURCE project continues to fund household energy-efficiency measures, with ordinary support up to 50% for individual measures, up to 65% for packages, and higher support for vulnerable groups; the programme covers many local governments. [S31]

However, **KojiDaBiram.rs already offers a 2026 municipality/status/subsidy experience and estimator**, so a generic subsidy portal is not a good standalone wedge. [S32]

Better integration later:
- flag when a planned measure may fall into an active public programme;
- deep-link to official/current municipal documentation;
- compare gross project cost vs indicative after-subsidy cost;
- never imply eligibility until official criteria are confirmed.

### Opportunity O4 — Scope Gap Library

Across normalized quotes, record which expected items are most often absent or ambiguous by project type, e.g.:
- debris removal;
- substrate preparation;
- waterproofing layers;
- electrical testing;
- VAT;
- transport / floor / lift surcharge;
- final cleanup;
- warranty.

This becomes both a useful homeowner checklist and a defensible data asset.

### Opportunity O5 — Price volatility / procurement-risk layer

Public material-price snapshots in 2026 note that some material prices can be adjusted weekly and vary by region and transport. [S16][S33]

Later, the project can surface:
- which parts of the estimate are stale/volatile;
- when to re-quote material-heavy items;
- price-lock / quote-expiry warnings;
- procurement lead times.

Do not build a national retail crawler in V1.

### Opportunity O6 — Professional “Decision Report” channel

Architects, interior designers, buyer agents and small property investors can use a branded report to explain scope/cost/quote differences to clients.

This may become an easier B2B monetization path than a broad contractor marketplace because it sells the existing decision layer rather than requiring supply-side liquidity.

## 6. Opportunity ranking

| Opportunity | Strategic value | Build difficulty | Partner dependence | Timing |
|---|---:|---:|---:|---|
| Local quote benchmark + normalization | 10/10 | 7/10 | low | Core now |
| Scope Gap Library | 9/10 | 4/10 | low | Core/early |
| Project forecast + change control | 9/10 | 6/10 | low | After quote proof |
| Post-purchase readiness | 8/10 | 5/10 | medium | Discovery |
| Professional Decision Reports | 8/10 | 5/10 | medium | Early monetization test |
| Contractor leads | 8/10 | 7/10 | high | Later |
| Financing readiness | 7.5/10 | 5/10 | medium/high | Later |
| Materials commerce | 7.5/10 | 7/10 | high | Later |
| Energy subsidy context | 6.5/10 | 5/10 | data-dependent | Supporting feature |
| Floor-plan takeoff / 3D | 6/10 | 9/10 | low | Do not build early |

## 7. Strategic conclusion

Proceed only with the narrow decision/data wedge. The market validates the workflow, but also proves that generic feature breadth is easy to copy.

The product wins if it becomes the best answer to:

> “I have this exact scope and these exact quotes in this part of Serbia, today. What is missing, what is comparable, what is plausible, and what will I probably end up paying?”
