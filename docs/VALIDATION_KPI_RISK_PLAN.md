# Validation, KPIs & Risk Plan

## 1. Biggest assumptions to validate

A1. Homeowner wants an independent benchmark, not only free marketplace quotes.
A2. User will upload contractor quote if privacy/value proposition is clear.
A3. We can normalize Serbian quote formats with acceptable manual correction.
A4. Local actual-price dataset can reach useful density.
A5. User will return during renovation to track commitments/changes.
A6. Contractor/retailer monetization can coexist with perceived neutrality.

## 2. Pre-code validation

### Experiment 1 — Manual Decision Report
Collect 20+ anonymized offers from recent renovations. Manually produce our ideal report.
Measure:
- would user have changed decision?
- most valuable section;
- willingness to upload quote;
- willingness to pay a one-time small fee.

### Experiment 2 — Scope Builder prototype
Clickable bathroom flow. Target: user can complete without knowing construction jargon.

### Experiment 3 — Contractor interview
Ask what causes bad leads and disputes. Validate whether standardized scope makes leads more attractive.

### Experiment 4 — Data bootstrap
Test how many quote rows map cleanly to taxonomy and what percentage remain ambiguous.

## 3. Product KPIs

### Acquisition
- organic impressions/clicks;
- landing → scope start;
- calculator completion.

### Decision value
- quote upload rate;
- quote extraction completion;
- correction rate per line;
- second quote upload rate;
- compare report views;
- clarification checklist usage/export.

### Project control
- accepted quote imported to committed budget;
- invoice/payment entries;
- change orders created;
- 30-day project return rate;
- completed project confirmation.

### Data flywheel
- verified observations/month;
- % Tier A/B evidence;
- work-item benchmark coverage;
- city coverage;
- median benchmark age;
- N distribution;
- number of user corrections to normalized mappings.

### Business
- paid project conversion;
- revenue / 1,000 qualified sessions;
- lead acceptance rate;
- revenue per qualified lead;
- CAC only after paid acquisition begins.

## 4. Quality gates

### Benchmark publish rule
No „local market range“ unless:
- minimum N threshold is met;
- dispersion is within defined bounds or clearly flagged;
- evidence mix is acceptable;
- data is fresh enough.

Otherwise fallback to broader geography and show lower confidence.

### Quote AI release rule
Before release:
- regression dataset covers common scanned/native PDF formats;
- critical amounts/units are validated;
- low-confidence lines are surfaced;
- user can correct before final report.

## 5. Legal/product safety risks

### Personal data
Quotes can contain names, phones, addresses and business identifiers. Follow Serbian data-protection obligations and minimize collection. [S14]

### Consumer-service workflow
Consumer law regulates additional works and notification where service price is significantly higher than reasonably expected. [S13] Product should help document consent, but not claim to provide legal advice.

### Engineering/safety
Do not calculate structural adequacy, electrical safety certification, gas work safety or other licensed engineering judgments as a consumer estimate. Route to qualified professional.

### Reviews/defamation
Avoid unverified accusations. Quote comparison describes document/scope. Contractor reviews require moderation and verified-job status where possible.

## 6. Competitive risks

### Ne Radi Sam / Daibau add our features
Mitigation: focus on independent benchmark/data quality and integrations; data flywheel before marketplace expansion.

### HouseLog localizes to Serbia
Mitigation: local price dataset, SEO acquisition, actuals, material/contractor ecosystem.

### ChatGPT/AI improves
Mitigation: product owns local structured data, document lifecycle and project state. AI becomes interface/client, not the moat.

## 7. Kill/pivot criteria

Consider pivot if after validation:
- users do not upload quote even when report is free;
- quote formats are too unstructured to normalize affordably;
- actual-price contribution remains near zero;
- SEO intent is dominated purely by „give me a phone number“ marketplace behavior;
- data confidence cannot be made transparent enough.

Possible pivots:
- B2B quote-normalization tool for designers/property managers;
- data/API layer for existing marketplaces;
- pure quote-checker without long-term project control.

## 8. Success gates before marketplace

Do NOT build own broad contractor marketplace until:
- decision layer has meaningful organic/direct usage;
- users generate standardized scopes;
- at least one city/trade has useful benchmark density;
- quote upload/compare is used repeatedly;
- qualified leads can be manually matched successfully.

## 9. 2026-09-24 promotion gates

### Gate R0 — data comparability
Pass candidate:
- 30–50 real bathroom documents;
- >=80% economically material value normalized medium/high confidence;
- <=20 min median manual cleanup after taxonomy stabilizes;
- evidence from more than one acquisition/source channel.

### Gate R0-D — decision value
Pass candidate:
- 5–10 manual reports;
- >=60% users discover a material new omission/difference;
- >=40% repeat-use intent;
- >=3 credible willingness-to-pay signals.

If R0-D fails, do not build project-control breadth.

### Gate R1 — public estimate
Pass candidate:
- completion rate sufficient to collect structured scope (target >=40% from qualified starts);
- users understand range/confidence, not a fake precise price;
- no major systematic error in golden fixtures/manual review.

### Gate R2 — quote extraction
Release to users only when economically material line items are extracted/mapped reliably on a held-out real-document set. Measure value-weighted accuracy, not only row count.

### Gate R3 — benchmark publication
Require minimum sample/evidence criteria by work item/location. If not met, show wider/older/lower-confidence context transparently or suppress the precise local number.

## 10. New opportunity experiments

### Post-purchase readiness
Interview 10 recent apartment buyers and 5 buyer agents/agencies. Test whether renovation-adjusted acquisition cost changes purchase/renovation decisions.

### Professional report channel
Give 3–5 architects/designers a manual branded Decision Report workflow. Measure whether it saves explanation/admin time and whether they would pay per report/project.

### Financing readiness
Interview at least 2 authorized professionals and 2 lending/broker stakeholders before building any “bank-ready” feature. Validate exact document boundaries.

### Energy-subsidy context
No generic feature until official data freshness can be maintained cheaply. Prefer official deep-links over copied eligibility logic.

## 11. Additional kill signals

Narrow/pivot if:
- benchmark data remains too sparse after a focused city/trade collection effort;
- the majority of useful value comes from human expert interpretation that cannot be standardized;
- users want contractor discovery but do not value independent quote analysis;
- privacy/consent makes actual-data contribution impractical;
- partner monetization pressures the benchmark toward sponsored outcomes.
