# Roadmap

## Roadmap princip

Roadmap je **problem/data-first**, ne feature-count-first. Najveći rizik nije da ne umemo da napravimo UI, već da lokalni benchmark nema dovoljno kvalitetnih podataka ili da quote normalization nije pouzdana.

## Phase 0 — Evidence & taxonomy pilot

**Cilj:** pre ozbiljnog razvoja dokazati da možemo normalizovati realne ponude i napraviti razumljiv report.

### Deliverables
- Bathroom Work Item Taxonomy v1 (40–70 standardnih stavki).
- 30–50 anonimizovanih realnih ponuda/predračuna/računa iz Beograda, gde je moguće.
- Manual normalization worksheet/prototype.
- Price Observation schema i trust tiers.
- 5–10 razgovora sa izvođačima/keramičarima/vodoinstalaterima.
- 15–20 razgovora sa homeownerima koji su skoro renovirali.
- Landing stranica + demo report.

### Gate za nastavak
- najmanje 80% line itema iz uzorka može da se mapira u taksonomiju bez stvaranja „ostalo“ kategorije;
- homeowneri razumeju standardizovano poređenje bez stručnog prevodioca;
- najmanje nekoliko korisnika kaže da bi uploadovalo sopstvenu ponudu za ovakav report;
- nalazimo dovoljno jasan način da prikažemo uncertainty.

## Phase 1 — Public Estimate MVP (Bathroom, Belgrade)

**Cilj:** SEO/acquisition alat koji istovremeno gradi standardizovan scope.

### Features
- no-login scope wizard za renoviranje kupatila;
- dimensions / stanje / radovi / materijal tier / logistika;
- deterministic estimate engine v1;
- local pricebook Beograd;
- low / typical / high ranges;
- contingency/risk model;
- breakdown: labor / material / logistics / contingency;
- confidence + source freshness;
- shareable result URL bez ličnih podataka;
- analytics events.

### Ne uključuje
AI chat, marketplace, profile majstora, payment, full apartment.

### Gate
- calculator completion rate i user tests pokazuju da wizard nije predugačak;
- korisnik razume zašto postoji raspon;
- najmanje 90% estimate line itema ima source/confidence metadata;
- nema kritičnih formula bez testova.

## Phase 2 — Quote Intelligence MVP

**Cilj:** prva funkcija koju ChatGPT/generički kalkulator ne zamenjuje lako.

### Features
- upload PDF/JPG/PNG;
- text extraction → OCR samo kada je potrebno;
- AI-assisted line item extraction;
- standard taxonomy mapping;
- user confirmation/editor;
- scope coverage matrix;
- missing/unclear item detection;
- unit-price normalization;
- benchmark deviation with sample/confidence;
- clarification questions;
- quote report export/share.

### Važno
Ne prikazivati „Contractor score 72/100“. Prikazivati **Quote completeness/clarity** i konkretne razloge.

### Gate
- extraction accuracy na test setu dovoljno visoka da korisnik ne mora ručno popravljati većinu redova;
- false missing-item alerts su pod kontrolom;
- benchmark se nikad ne prikazuje kao lokalni ako nema minimum sample-a.

## Phase 3 — Compare 2–3 Quotes

**Cilj:** standardizovati ponude pre poređenja.

### Features
- side-by-side normalized scope;
- uključeno / nije uključeno / nejasno;
- rad vs materijal;
- PDV status;
- payment schedule;
- start/end or duration;
- warranty/exclusions;
- comparable total (uz jasno prikazane pretpostavke);
- delta vs independent estimate;
- „questions to ask each contractor“.

### Gate
Korisnici donose odluku lakše i više ne biraju samo najniži total.

## Phase 4 — Project Control

**Cilj:** zadržati korisnika tokom radova i dobiti kvalitetne actual podatke.

### Features
- project dashboard;
- Budget / Estimated / Committed / Invoiced / Paid / Forecast;
- accepted quote → committed lines;
- invoices/receipts;
- payment milestones;
- change orders with approval evidence;
- project phases/status;
- document vault;
- warranty records;
- actual-vs-estimate by work item;
- export project report.

### Gate
- korisnici dodaju najmanje jednu stvarnu uplatu/change-order nakon početnog estimate-a;
- forecast koristi realne commitments umesto procenta potrošenog budžeta.

## Phase 5 — Verified Actual Price Flywheel

**Cilj:** izgraditi lokalni dataset koji je teži za kopiranje od UI-a.

### Features
- completed-project confirmation;
- evidence tiers;
- dedupe/fraud detection;
- percentile benchmarks;
- recency weighting;
- locality roll-up (opština samo kada n dozvoljava; inače grad/region);
- benchmark history;
- „based on N comparable observations“;
- contributor rewards (npr. dodatni quote scan/report), bez plaćanja koje podstiče lažne podatke.

## Phase 6 — Full Apartment + Novi Sad/Niš

Kompozicija postojećih modules: kupatilo, zidovi/boja, podovi, elektro, vodovod, stolarija, vrata, rušenje/logistika. Full apartment nije poseban kalkulator nego orchestration više standardnih scopes.

## Phase 7 — Leads (carefully)

### Model
- korisnik eksplicitno bira „želim ponude“;
- scope iz platforme postaje kvalitetan brief;
- partneri dobijaju isti standardizovan brief;
- leads se naplaćuju izvođačima ili kroz paket/pretplatu;
- plaćanje ne utiče na quote benchmark ni na organsko rangiranje.

### Build vs partner
Pre izrade sopstvenog marketplace-a testirati partnerstvo/integraciju sa postojećim platformama. Ne Radi Sam i Daibau već rešavaju supply acquisition. [S9][S8]

## Phase 8 — Materials / Commerce

### Prvo
- shopping list;
- generički recommended quantity;
- reference price bands.

### Zatim
- retailer feeds/partnerships;
- konkretne korpe;
- availability/delivery;
- affiliate/sponsored offers, jasno označene.

Ne raditi neovlašćeno scraping preuzimanje. Partner feed ili dozvoljeni API je preferiran.

## Phase 9 — B2B / Market Intelligence

Tek kada dataset postane dovoljan:
- trendovi realnih cena po trade/category;
- anonymized benchmark reports;
- supplier demand insights;
- portfolio view za male investitore.

## Predloženi release redosled

R0 Research → R1 Bathroom Estimate → R2 Quote Analyzer → R3 Quote Compare → R4 Project Control → R5 Actuals → R6 Apartment/Regions → R7 Leads → R8 Commerce → R9 B2B.

**Najvažnija disciplina:** ne prelaziti na R6–R9 ako R2–R5 nisu stvorili data flywheel.

## Roadmap refresh — 2026-09-24

### R0A — Evidence corpus and taxonomy (blocks product code)
Target:
- 30–50 real bathroom documents from Belgrade;
- >=10 with accepted/not-accepted outcome where possible;
- >=10 with final/actual evidence where possible;
- canonical taxonomy with explicit inclusions/exclusions;
- manual normalization benchmark.

Pass candidate:
- >=80% of economically material line-item value mapped with medium/high confidence;
- unresolved economically material value <=20%;
- median manual cleanup <=20 min/typical quote after taxonomy stabilizes.

### R0B — Manual Decision Report (blocks automated quote AI)
Deliver 5–10 manual reports to target users.

Pass candidate:
- >=60% report users discover at least one material omission/difference they did not identify themselves;
- >=40% would use it again for another quote/project;
- >=3 credible willingness-to-pay signals.

### R0C — Landing/acquisition smoke test
Before building broad SEO content, test three propositions:
1. “Proveri ponudu majstora.”
2. “Uporedi dve ponude na istom scope-u.”
3. “Koliko će renoviranje stvarno završiti?”

Measure qualified upload/start intent, not vanity traffic.

### R2.5 — Scope Gap Library
Promote recurring omissions/ambiguities from normalized quotes into a versioned project-type checklist. This becomes a core quote-analysis input before statistical benchmark density is mature.

### Discovery track D1 — Post-purchase Readiness
After quote intelligence proves value, test with recent apartment buyers / agents. Do not integrate property listings or build a valuation product before demand evidence.

### Discovery track D2 — Professional Decision Reports
Test architects/interior designers/property managers as a B2B distribution channel before building a contractor marketplace.

### Discovery track D3 — Financing / subsidy context
Test documentation-readiness and official-link assistance only after core project budgets are reliable.

### Explicit sequencing rule
Do not start broad leads/commerce while benchmark density is weak. A biased or low-confidence benchmark destroys the core trust asset faster than early lead revenue can compensate.
