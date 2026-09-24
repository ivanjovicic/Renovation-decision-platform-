# Technical Architecture

## 1. Principle

**Modular monolith, web-first, deterministic pricing core.** Nema potrebe za mikroservisima, event bus-om ili kompleksnim agent orkestracijama u ranoj fazi.

Predlog stacka koji odgovara postojećem iskustvu:
- Frontend: Next.js + TypeScript (SEO/SSR/SSG).
- Backend: .NET 10 Minimal API / modular monolith.
- DB: PostgreSQL (npr. Neon).
- Object storage: S3-compatible za private documents.
- Background jobs: jednostavan job runner/queue za parsing, OCR, benchmark rebuild.
- Analytics: privacy-aware product analytics + Search Console.

## 2. Bounded modules

### Catalog
WorkItemDefinition, MaterialDefinition, Unit, ScopeTemplate, RuleVersion.

### Pricing
PriceObservation, Benchmark, PriceSource, Location, ConfidenceModel.

### Estimation
Estimate, EstimateLine, EstimateSnapshot, RiskModifier, ContingencyPolicy.

### Quotes
Quote, QuoteDocument, QuoteLineRaw, QuoteLineNormalized, QuoteMappingReview, QuoteComparison.

### Projects
RenovationProject, Phase, BudgetLine, Commitment, Invoice, Payment, ChangeOrder, ForecastSnapshot.

### Contractors
ContractorReference, BusinessVerificationSnapshot, ProjectContractor, Review (later).

### Documents
PrivateDocument, EvidenceLink, Warranty, RetentionPolicy.

### Leads/Commerce
Lead, Partner, SponsoredOffer, MaterialBasket (later).

## 3. Key data model

### WorkItemDefinition
- id/code
- category
- unit
- default quantity rule
- dependencies
- common exclusions
- risk tags
- version

### PriceObservation
- work_item_id
- location_id
- date
- quantity/unit
- labor/material split
- total
- VAT status
- evidence tier
- contributor/project
- source metadata
- quality flags

### Benchmark
- cohort definition
- P25/median/P75
- sample count
- effective dates
- evidence mix
- confidence
- build version

### EstimateSnapshot
Immutable snapshot: inputs + rule version + benchmark ids + output. Korisnik mora moći da vidi zašto se kasnija procena promenila.

## 4. Quote processing architecture

`Upload → Secure store → Text extraction → OCR fallback → LLM extraction → Schema validation → Unit normalization → Taxonomy mapping → User confirmation → Freeze version → Compare`

### Rules
- files private by default;
- no quote is used for analytics/benchmark without defined policy/legal basis;
- PII redaction/anonymization before aggregate dataset;
- AI output always schema-validated;
- low-confidence mappings require human confirmation.

## 5. Estimate engine design

Pure deterministic library where possible.

Inputs:
- project scope;
- measurements;
- condition;
- location;
- material tier;
- logistics;
- rule/pricebook version.

Output:
- quantity lines;
- low/base/high labor;
- low/base/high material;
- risk/contingency;
- confidence;
- provenance list.

Unit test every formula. Golden test fixtures for common bathrooms.

## 6. Benchmark builder

Scheduled aggregation:
1. choose valid observations;
2. cohort by work item/scope/location/time;
3. anti-abuse filters;
4. weighted robust distribution;
5. fallback granularity;
6. publish immutable benchmark version;
7. anomaly report.

Never rebuild benchmark silently without versioning.

## 7. Security/privacy

Relevant because documents contain addresses, phones, names, bank/payment details. Serbia has a dedicated Personal Data Protection Law. [S14]

Minimum controls:
- encryption in transit/at rest;
- signed URLs;
- short-lived document access;
- strict per-project authorization;
- audit log for document access/deletion;
- user delete/export flow;
- configurable retention;
- redact PII from derived analytics;
- do not send entire unnecessary document context to AI providers;
- secrets management;
- malware/file type checks.

## 8. APR/business verification

APR allows public search and web services but warns against unauthorized automated scraping. [S15] Therefore:
- V1: user-provided business ID + link/manual verification;
- V2: approved web-service/contractual access if commercially justified.

## 9. AI governance

Model is not source of truth.

Track:
- model/provider/version;
- extraction prompt version;
- schema version;
- confidence;
- user corrections;
- regression dataset.

Create a fixed quote test set and run extraction regression before model/prompt changes.

## 10. Observability

Metrics:
- estimate errors/exceptions;
- quote extraction accuracy and correction rate;
- unclassified line rate;
- benchmark sample coverage;
- stale pricebook count;
- outlier rate;
- upload failures;
- cost per quote analysis;
- latency.

## 11. Deployment

Keep cheap:
- frontend CDN/edge hosting;
- one API service;
- managed Postgres;
- object storage;
- job worker only when quote analysis launches.

Do not add Redis/RabbitMQ/Kafka until an observed need exists.

## 12. Architecture refresh — 2026-09-24

### New bounded capability: Decision Intelligence
Keep a distinct domain/service layer for:
- scope expectations / gap library;
- coverage calculation;
- clarity calculation;
- comparable-total normalization;
- benchmark eligibility checks;
- clarification-question generation.

Do not bury this logic in UI or LLM prompts.

### Document pipeline states
A quote/document should move through explicit states:
`uploaded -> text_extracted -> ai_structured -> validation_required -> user_confirmed -> benchmark_eligible/not_eligible`.

Raw AI output is never treated as confirmed market data.

### Source-document vs benchmark separation
Private source document storage and derived benchmark observations must be separate. Deleting a personal source document should not require retaining unnecessary personal identifiers in the aggregate dataset.

### Scope taxonomy versioning
Every normalized quote and estimate stores the taxonomy version used. When taxonomy changes, historical documents are not silently rewritten; migrations/re-normalization are explicit and auditable.

### Public result caching
SEO/public estimate pages may be cached, but personalized quote/project data is private/no-store by default.

### Future professional export
Implement export schemas so an authorized professional can review/edit/sign a structured predmer/predračun later. Do not embed a fake “certified” status in the consumer engine.
