# Business Model & Go-To-Market

## 1. Monetization thesis

Ads mogu finansirati acquisition sloj, ali **ne treba da budu glavni business model**. Najvredniji trenutak je kad korisnik upravo odlučuje o projektu od nekoliko hiljada ili desetina hiljada evra.

## 2. Revenue stack

### A. Display ads — pomoćni prihod
- samo na SEO/editorial/calculator stranicama;
- ne stavljati agresivne oglase unutar quote reporta ili project dashboarda;
- dobra zaštita: projekat može praviti mali prihod i pre marketplace-a.

### B. One-time Project Pro — preferirani consumer model
Renoviranje je episodic use-case; mesečna pretplata često nije prirodna. HouseLog koristi jednokratni premium po projektu, što potvrđuje model kao tržišno razumljiv. [S10]

Testirati price points, npr.:
- Free: estimate + osnovni benchmark + 1 quote preview.
- Decision Report: jednokratna naplata za detaljan quote compare/export.
- Project Pro: jednokratno po projektu za više ponuda, budget control, change orders, dokumente i actuals.

Ne zaključavati cenu bez willingness-to-pay testa.

### C. Qualified contractor leads
Tek kada platforma zna scope i budžet, lead je kvalitetniji od generičkog „treba mi majstor“.

Modeli za test:
- pay-per-qualified-lead;
- contractor credits;
- contractor subscription za slanje više ponuda / CRM-lite.

Ne Radi Sam već koristi besplatno za korisnika i plaćene mogućnosti za majstore, bez provizije po poslu. [S9] To je dokaz da je contractor-paid model lokalno razumljiv.

### D. Materials commerce
- shopping list;
- retailer partnerships;
- affiliate/deep links;
- sponsored bundles jasno označeni.

Neutralni benchmark nikad ne sme biti promenjen zbog partnera.

### E. B2B insights — kasnije
Anonimizovani trendovi realnih cena, bez prodaje ličnih podataka. Tek uz dovoljan sample i pravnu proveru.

## 3. Neutrality policy — kritična

Ako platforma zarađuje od leadova i prodavaca, postoji konflikt interesa. Zato:
- paid partner badge;
- sponsored placement jasno označen;
- paid status ne utiče na market benchmark;
- paid status ne povećava quote clarity score;
- eventualni sorting po „recommended“ mora biti transparentan i ne zasnovan samo na komercijalnom odnosu.

## 4. Go-to-market sequence

### Stage 1 — SEO acquisition
Fokus na queries gde korisnik već ima problem:
- renoviranje kupatila cena Beograd;
- koliko košta kupatilo 5m2;
- keramičar cena m2;
- hidroizolacija cena;
- kompletna adaptacija kupatila;
- koliko materijala za pločice/krečenje;
- ponuda majstora kako proveriti;
- šta treba da sadrži ponuda za renoviranje.

Svaka SEO stranica vodi u **interactive scope/estimate**, ne samo članak.

### Stage 2 — Quote checker hook
Shareable poruka:
„Dobio si ponudu za renoviranje? Uploaduj i vidi šta nedostaje pre nego što platiš avans.“

Ovo je bolji social/word-of-mouth hook od kalkulatora.

### Stage 3 — Data contributor loop
Korisnik koji potvrdi stvarni final cost dobija npr. dodatnu analizu/izvoz/benchmark update. Nagrada ne sme biti vezana za visinu prijavljene cene.

### Stage 4 — Partners
- interior designers;
- real-estate agents za kupce starijih stanova;
- property managers;
- contractor associations/individual teams;
- retailers.

## 5. Build vs partner marketplace

Ne graditi supply marketplace dok ne znamo da imamo homeowner demand. Testirati:
1. ručno prosleđivanje 10–20 quality leadova;
2. partnerstvo sa postojećim platformama;
3. tek onda sopstveni contractor acquisition.

Ne Radi Sam i Daibau već imaju supply/marketplace sloj. [S9][S8]

## 6. Revenue unit model — scenario, ne prognoza

Za internu ekonomiju pratiti **revenue per 1,000 qualified sessions**, a ne samo page RPM.

Primer monetizacije na 10.000 relevantnih mesečnih sesija:
- display ads: mali osnovni prihod;
- 10–30 plaćenih decision/project unlocks;
- 10–40 monetizovanih quality leadova;
- nekoliko material referrals.

Tačne stope treba validirati eksperimentom; ne zaključavati business case na AdSense pretpostavci.

## 7. Moat

Najslabiji moat: kalkulator formula.
Srednji moat: UX + quote parser.
Najjači moat:
1. canonical scope taxonomy;
2. normalized local quote dataset;
3. verified actual price observations;
4. longitudinal project budget/changes;
5. partner network i repeatable acquisition.

## 8. Key business risks

- nedovoljno SEO traffic-a;
- korisnici ne žele da uploaduju finansijske dokumente;
- premalo evidence-backed actuals;
- contractor supply previše fragmentisan;
- konflikt interesa kroz leads/sponsorship;
- users koriste samo free estimate i nikad ne pređu na high-value features.

Za svaki rizik postoji gate u Validation dokumentu.

## 9. GTM refresh — 2026-09-24

### Acquisition channel A — high-intent SEO
Keep, but center pages around decisions, not generic articles:
- proveri ponudu za renoviranje;
- renoviranje kupatila cena + interactive scope;
- šta mora da sadrži ponuda majstora;
- predmer/predračun vs ponuda;
- dodatni radovi i promene budžeta.

### Acquisition channel B — recent property buyers
RGZ H1 2026 shows a large apartment transaction flow and strong Belgrade concentration. [S20]

Potential partnerships:
- buyer agents / real-estate agencies;
- mortgage brokers;
- home-inspection / architecture services;
- post-purchase email/checklist partnerships.

Offer: `Renovation Readiness Report`, not a property valuation.

### Acquisition channel C — professionals
Architects/interior designers/property managers may distribute branded/co-branded Decision Reports to clients. This channel reuses the core capability and can monetize before a marketplace exists.

### Revenue F — professional review / financing readiness (later)
Banks already have renovation/adaptation products and documentation requirements. [S29][S30]

Potential revenue:
- paid structured export/review pack;
- referral to licensed professional;
- qualified finance lead, where compliant and transparently disclosed.

Do not position the platform as a lender or licensed estimator unless those capabilities actually exist.

### Revenue G — energy-renovation context (later)
Do not build a generic subsidy directory: an active Serbian product already targets that job. [S32]

Potential value instead:
- detect when scope includes windows/insulation/heating/solar;
- surface official programme link/status;
- scenario: gross cost vs illustrative subsidy effect;
- partner handoff only after eligibility is verified by official rules.

## 10. Monetization order

Preferred sequence:
1. free estimate / limited quote check;
2. one-time Decision Report / Project Pro;
3. professional/co-branded reports;
4. qualified contractor leads;
5. materials commerce;
6. finance/professional-review referral;
7. aggregate B2B intelligence only after privacy/sample thresholds.

This order maximizes trust and minimizes two-sided marketplace risk.
