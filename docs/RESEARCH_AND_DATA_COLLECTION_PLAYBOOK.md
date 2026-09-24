# Research & Data Collection Playbook

## 1. R0 objective

Before software MVP, prove that real renovation documents can be normalized into a common scope and that the normalized comparison materially helps homeowners.

### Minimum evidence target

- 30–50 real bathroom quotes / pro-forma invoices / invoices from Belgrade;
- at least 10 with known accepted/not-accepted outcome where possible;
- at least 10 with some final/actual cost evidence where possible;
- 15–20 homeowner interviews;
- 5–10 contractor / architect / project-manager interviews;
- 5–10 manual Decision Reports shown to target users.

No single source should dominate the sample.

## 2. Recruiting channels

Prioritize:
- personal network / recent renovators;
- local homeowner and neighborhood groups;
- architects/interior designers willing to share anonymized examples with permission;
- small contractors willing to share templates or redacted quotes;
- recent property buyers;
- publicly available examples only as low-confidence seed evidence.

Never ingest private documents without permission.

## 3. Consent and anonymization

Before using an uploaded/shared document for benchmark research:
- explain intended use;
- remove name, phone, exact address, bank account, signature and unrelated identifiers;
- preserve broad location only when allowed and necessary;
- store original private documents separately from derived observations;
- allow withdrawal/deletion of personal source documents subject to legal obligations.

Benchmark datasets should store derived facts, not unnecessary personal data.

## 4. Manual normalization procedure

For each document:
1. identify project type and known project metadata;
2. split document into raw line items;
3. map each item to canonical work-item code(s);
4. record original text verbatim internally for audit;
5. capture quantity, unit, unit price, total price;
6. tag labor/material split and responsibility;
7. tag VAT state as included/excluded/unknown;
8. tag inclusions/exclusions and logistics;
9. tag ambiguity / missing information;
10. assign evidence tier;
11. record normalization confidence;
12. exclude observations that cannot be made comparable.

## 5. Evidence tiers

Suggested hierarchy:

- **A — Verified actual:** final invoice/receipt/payment evidence + known scope.
- **B — Accepted quote / contracted:** known selected quote/contract with sufficiently clear scope.
- **C — Real market quote:** real contractor quote, outcome unknown.
- **D — Public project/market evidence:** public lead/price examples, useful for context but not treated as actual transaction truth.
- **E — Editorial/public guide:** lowest benchmark weight; bootstrap/reference only.

Evidence tier must never be hidden from benchmark logic.

## 6. Quality metrics for R0

Track:
- taxonomy coverage: % raw line items mapped confidently;
- split rate: % raw lines requiring mapping to multiple canonical items;
- unresolved rate;
- unit normalization success;
- material/labor/VAT known rate;
- inter-reviewer agreement on a 10-document subset;
- minutes of manual work per quote;
- % of Decision Reports where user says at least one important omission/difference was newly revealed;
- % users willing to upload another quote;
- % willing to pay or refer a friend.

### Candidate pass gates

Proceed toward MVP if roughly:
- >=80% of economically material line-item value can be normalized with medium/high confidence;
- <=20 minutes median manual cleanup per standard quote after taxonomy stabilizes;
- >=60% of report users identify at least one useful/new decision insight;
- >=40% say they would use the tool for another quote/project;
- at least 3 users show credible willingness to pay for the full report/project layer.

These are internal decision thresholds, not market benchmarks.

## 7. Decision Report template

Manual report should include:
- project/scope summary;
- missing/unclear expected items;
- normalized quote breakdown;
- benchmark range only where evidence is sufficient;
- deviations with confidence;
- payment/term/warranty/VAT clarity;
- questions to ask contractor;
- budget impact and contingency;
- explicit limitations.

Never call a quote fraudulent or a contractor dishonest.

## 8. Actual-price contribution loop

At project completion, ask user to confirm:
- final paid amount;
- accepted quote amount;
- approved changes;
- final quantities where known;
- material purchases paid directly by homeowner;
- final invoice/receipt evidence if willing.

Incentives may include:
- free/discounted project report;
- extended document storage;
- benchmark access;
- contribution badge/status.

Never pay in a way that rewards a particular price or negative review.

## 9. Research backlog

After bathroom R0:
- apartment renovation taxonomy transfer test;
- Belgrade -> Novi Sad price fallback test;
- post-purchase readiness interviews;
- architect/property-manager B2B report test;
- financing-document workflow interviews with authorized professionals;
- lead-routing pilot only after demand side proves repeatable.
