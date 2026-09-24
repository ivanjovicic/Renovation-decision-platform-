# Data, Pricing & Estimate Plan

## 1. Data moat

Najvrednija imovina proizvoda nije formula već **normalizovana baza lokalnih observations** sa poznatim scope-om i dokazom. Javni cenovnici služe za bootstrapping, ne kao jedini truth source.

## 2. Zašto javni cenovnik nije dovoljan

Javni izvori koriste različite definicije „kompletnog renoviranja“. Čak isti portal može u različitim tekstovima dati veoma različite raspone za slično kupatilo. [S6][S7] Bez scope normalizacije ne znamo da li cena uključuje sanitarije, instalacije, odvoz, PDV, pripremu podloge, dizajn ili premium materijal.

Zato je primary key benchmarka praktično:

`WorkItem + ScopeVariant + Unit + LocationLevel + DateBucket + MaterialResponsibility + VATStatus + EvidenceTier`

## 3. Canonical work taxonomy

Primer work itema:
- DEMO_TILE_WALL
- DEMO_TILE_FLOOR
- DEBRIS_REMOVE
- PLUMBING_WATER_POINT_NEW
- PLUMBING_DRAIN_MOVE
- ELECTRICAL_POINT_NEW
- WATERPROOFING_FLOOR
- WATERPROOFING_SHOWER_ZONE
- TILE_INSTALL_STANDARD
- TILE_INSTALL_LARGE_FORMAT
- SCREED_REPAIR
- WALL_LEVELING
- SANITARY_WC_INSTALL
- SHOWER_INSTALL
- PAINT_WET_ROOM

Svaki ima:
- unit (m², m, kom, point, fixed);
- quantity rule;
- prerequisites/dependencies;
- typical exclusions;
- material rule;
- labor price model;
- risk modifiers.

## 4. Source types / evidence tiers

### Tier A — Verified actual
Plaćeni račun/faktura + potvrda da je rad završen + strukturisan scope. Najviša težina.

### Tier B — Accepted / signed quote
Ponuda koju je korisnik stvarno prihvatio; dobra za committed market price, nije isto što i final actual.

### Tier C — Submitted quote
Stvarna ponuda izvođača, ali nije potvrđeno da je posao ugovoren.

### Tier D — Public retailer/product price
Javno objavljena cena konkretnog SKU-a, sa timestampom i izvorom.

### Tier E — Editorial/public market guide
Daibau, Ne Radi Sam i slični javni rasponi. Korisni za bootstrap i sanity check, ali niska težina u local actual benchmarku. [S6][S9]

### Tier F — User self-report without proof
Najniža težina; koristi se samo kada sample size i anti-fraud pravila dozvoljavaju.

## 5. Required provenance fields

Svaki observation:
- source_type;
- source_reference/document_id;
- collected_at;
- effective_date;
- city / municipality granularity;
- raw description;
- normalized_work_item;
- quantity;
- unit;
- total;
- labor_total;
- material_total;
- VAT_included (true/false/unknown);
- material_by_contractor / material_by_homeowner;
- included_items/excluded_items;
- evidence_tier;
- normalization_confidence;
- anomaly_flags.

## 6. Local benchmark methodology

### Ne koristiti prost prosek.
Predlog:
1. ukloni/umanji duplikate;
2. odvoji različite scope varijante;
3. recency weight;
4. robust outlier handling;
5. izračunaj P25 / median / P75;
6. objavi sample size N;
7. confidence = funkcija N + evidence quality + recency + dispersion.

### Granularity fallback
- opština: samo uz dovoljan N;
- inače grad;
- inače region/Srbija;
- nikad izmišljena „lokalna cena“ iz premalog uzorka.

Primer:
`Keramika standard, rad, Beograd: P25 18, Median 22, P75 27 €/m²; N=43; 71% Tier A/B/C; poslednjih 180 dana; Confidence=High.`

## 7. Anti-manipulation

- jedan contractor ne sme dominirati sample-om;
- limit observations po istom subjektu/projektu;
- detect identical quote templates/amounts;
- contractor self-entered cene odvojiti od homeowner evidence;
- retailer sponsored prices nikad ne ulaze u „market benchmark“ bez oznake;
- outlier se ne briše automatski ako ima dokaz — može predstavljati premium/complexity variant;
- audit log svih benchmark rebuild-a.

## 8. Estimate Engine v1

Pipeline:
1. Scope input.
2. Quantity derivation.
3. Waste/normatives.
4. Labor estimate per work item.
5. Material estimate by class/SKU references.
6. Logistics modifiers.
7. Building/condition risk modifiers.
8. Known add-ons.
9. Contingency.
10. Aggregate low/typical/high.

### AI boundary
AI sme da:
- prevede slobodan opis u proposed work items;
- izvuče line iteme iz ponude;
- predloži mapping;
- napiše razumljivo objašnjenje.

AI ne sme da:
- izmisli tržišnu cenu;
- samostalno promeni quantity rule;
- pretvori jedan self-report u lokalni benchmark;
- dodeli contractor quality score bez eksplicitnog, dokazivog modela.

## 9. Material pricebook

### V1
- generička klasa: economy/standard/premium;
- standard package sizes;
- manufacturer normatives gde su javni i dozvoljeni;
- ručno kurirani javni reference prices sa timestampom.

Javni izvori pokazuju da je moguće naći m²/pakovanje cene za pločice i laminat. [S17][S18] Koristiti ih kao reference, ne graditi sistem na krhkom scraping-u.

### V2
Partner feeds, CSV/API, supplier agreements.

## 10. Data refresh SLA

Predlog:
- actual labor benchmark: rolling 180–365 dana;
- volatile material price: 30–60 dana;
- slow-changing normative: 12 meseci ili po promeni proizvoda;
- editorial source: quarterly review;
- stale badge ako je SLA probijen.

## 11. Data quality dashboard

Interno:
- coverage po work itemu/lokaciji;
- sample size;
- evidence tier mix;
- stale observations;
- mapping confidence;
- high-dispersion benchmarks;
- suspicious contributor clusters;
- benchmark drift.

## 12. Privacy and aggregation

Ponude mogu sadržati ime, telefon, adresu, PIB/MB i druge lične/poslovne podatke. Primeniti data minimization, privatni raw-document storage, deletion/export i jasno odvojiti dokument od anonimizovanog observation seta. [S14]

Pre korišćenja uploaded document data za aggregate benchmark, pravni osnov i korisnička obaveštenja moraju biti eksplicitno definisani.

## 13. 2026-09-24 data refinements

### Separate benchmark dimensions
Never collapse these dimensions unless sample size forces a documented fallback:
- labor-only vs labor+material;
- VAT included/excluded/unknown;
- standard vs complex geometry/format;
- demolition/substrate preparation included/excluded;
- transport/debris/floor/lift included/excluded;
- homeowner-supplied vs contractor-supplied materials;
- apartment age/condition where materially relevant.

### Recency / volatility
Public 2026 material-price reporting notes frequent changes, in some categories weekly. [S33] Therefore:
- material observations use stronger recency weighting than relatively stable labor items;
- benchmark output records effective date/window;
- stale material-heavy estimates show a re-quote warning;
- quoted material validity/expiry is captured where present.

### Scope Gap Dataset
In addition to `PriceObservation`, keep `ScopeExpectation` / `ScopeGapObservation`:
- project type;
- expected canonical item;
- present / absent / ambiguous;
- quote/document type;
- location/date;
- confidence.

This dataset can become useful before price samples are large enough for fine-grained local percentiles.

### Contribution bias controls
User-contributed actuals can be selection-biased. Record source channel, completion state and evidence quality. Do not present a small self-selected sample as representative of the whole market.

### Benchmark publication fallback
When local evidence is too sparse:
1. show no precise percentile if minimum evidence is not met;
2. fall back to wider geography/time window only with visible label;
3. optionally show a lower-confidence editorial/public-guide context separately;
4. never blend low-confidence guide values invisibly into verified-actual statistics.
