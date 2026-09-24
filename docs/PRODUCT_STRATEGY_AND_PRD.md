# Product Strategy & PRD

## 1. Product thesis

Renoviranje je finansijski velika, ali informacijski neuređena odluka. Korisnik pre ugovaranja ne zna da li dve ponude pokrivaju isti scope, tokom radova ne zna koliko je već „commitovao“, a nakon dodatnih radova često gubi vezu između početnog budžeta i konačne cene.

Tržište je dovoljno veliko da opravda fokus: Popis 2022 beleži preko 2,26 miliona stambenih zgrada, a najveća grupa je iz perioda 1961–1980; 97,9% stanova je u privatnoj svojini. [S1][S2] To nije direktan TAM, ali pokazuje veliki, stariji i pretežno privatni fond nekretnina.

## 2. Problem koji rešavamo

Korisniku ne treba još jedan odgovor „renoviranje košta X €/m²“. Javni rasponi su preširoki i ponekad kontradiktorni. Daibau na cenovnoj stranici navodi jedan skup raspona, dok poseban vodič za 2026. navodi višestruko više ukupne iznose za tipično kupatilo. [S6][S7] To je signal da bez normalizacije scope-a, lokacije, datuma, uključenog materijala i kvaliteta podataka, jedna cifra nije pouzdana.

### Glavna jobs-to-be-done

1. **Pre planiranja:** Šta sve realno ulazi u moj projekat?
2. **Pre traženja ponuda:** Koji je razuman lokalni budžet i rizik?
3. **Kad stignu ponude:** Da li su ponude uopšte uporedive i šta nedostaje?
4. **Pre potpisivanja:** Koja pitanja moram postaviti izvođaču?
5. **Tokom radova:** Koliko je planned / committed / invoiced / paid i gde budžet odlazi?
6. **Kod dodatnih radova:** Koliko promena povećava forecast i da li je odobrena?
7. **Posle radova:** Koliko je stvarno koštalo i koji dokazi/garancije ostaju?

## 3. Konkurentska mapa

### Materijali i normativi
- **LiczMat**: 15 kalkulatora, 161 materijal, projekti i predračuni; aktuelni proizvod već izlaže Pro/klijente/ponude/rokove, pa je granica prema lakšem poslovnom alatu šira nego u prvobitnoj analizi. [S4][S22]
- **ProAdapt**: količine po normativima proizvođača, otpad, slojevi i tehničke pretpostavke. [S5]

Zaključak: ne pokušavati da pobedimo brojem formula.

### Cene i marketplace
- **Daibau**: cenovni vodiči, lead forma, ocenjeni izvođači i konkretni projektni zahtevi. [S6][S8]
- **Ne Radi Sam**: domaći marketplace sa pisanim ponudama, lokalnim majstorima, ocenama/verifikacijom i Pro modelom za majstore. [S9]

Zaključak: ne graditi marketplace kao prvu diferencijaciju.

### Decision/project-control benchmark
- **HouseLog**: vrlo blizak regionalni benchmark — projekti, faze, budžet, izvođači, dokumenti, računi/garancije, 5 besplatnih AI skenova, AI ekstrakcija i poređenje ponuda, uz one-time Premium po projektu. [S10][S24]
- **Trakvu**: AI poređenje contractor ponuda i otkrivanje nedostajućih stavki. [S11]
- **Scope/Budget My Reno**: homeowner-first budžet, actual vs estimate, contractors, change orders i dokumenti. [S12][S19]

Zaključak: globalno je problem validiran. Lokalni moat mora biti **srpski price intelligence + standardizovani scope + evidence-backed actuals**.

## 4. Pozicioniranje

### Ne govorimo
- „Nađi najjeftinijeg majstora.“
- „AI zna koliko renoviranje košta.“
- „Ova ponuda je prevara.“
- „Najbolji izvođač je X.“

### Govorimo
- „Ove dve ponude ne uključuju isti scope.“
- „Ova stavka je 24% iznad trenutno posmatranog raspona za uporedive radove; confidence: medium.“
- „U ponudi nije eksplicitno navedena hidroizolacija / odvoz / PDV / garancija.“
- „Forecast final cost je porastao zbog tri odobrena dodatna rada.“

## 5. Primarni segment

**Homeowner / kupac stana koji sam upravlja renoviranjem od približno nekoliko hiljada do nekoliko desetina hiljada evra.**

Početni slučaj: vlasnik stana u Beogradu, kompletno renoviranje kupatila. Kasnije: kompletan stan, Novi Sad, Niš.

Sekundarni segmenti kasnije:
- mali investitori koji renoviraju 1–5 stanova godišnje;
- arhitekte / project manageri koji žele homeowner report;
- izvođači koji žele strukturisan scope i manje sporova;
- prodavci materijala.

## 6. Core product loops

### Loop A — Plan
Scope Builder → Estimate → Risks → Budget scenarios.

### Loop B — Decide
Upload quote → Extract → Normalize → Missing items → Benchmark → Compare 2–3 offers → Clarification questions.

### Loop C — Control
Accept offer → Committed budget → Invoices → Payments → Change orders → Forecast at completion.

### Loop D — Learn
User confirms actual → evidence trust level → anonymized observation → benchmark refresh → better future estimates.

Ovaj poslednji loop je dugoročni moat.

## 7. Must-have functionality

### A. Scope Builder
Za kupatilo korisnik bira dimenzije, starost/stanje, rušenje, instalacije, pomeranje sanitarija, hidroizolaciju, keramiku, sanitarnu opremu, elektriku, ventilaciju, završne radove, logistiku (sprat/lift/odvoz) i nivo materijala.

Output nije samo lista radova već **standardizovani scope** sa jedinstvenim work-item kodovima.

### B. Deterministički Estimate Engine
Engine računa količine, normative, rad, materijal, logistiku, contingency i raspon. AI ne računa cenu. Svaki rezultat ima version, timestamp, location, confidence i izvore.

### C. Quote Import & Normalization
PDF/image/text → ekstrakcija line itema → mapiranje u standardnu taksonomiju → user confirmation → poređenje sa scope-om i benchmarkom.

### D. Scope Coverage / Quote Health
Umesto „ocena majstora“, prikazujemo objektivne metrike:
- coverage % očekivanih scope stavki;
- jasnoća količina/jedinica;
- jasnoća materijal vs rad;
- PDV status;
- rok i payment schedule;
- garancija;
- exclusions;
- potencijalno nejasne „ostalo/razno“ stavke.

### E. Quote Comparison
Ponude se prvo normalizuju na isti scope. Tek zatim se porede cena, rok, pokrivenost, uslovi plaćanja i dokumentaciona jasnoća.

### F. Budget Lifecycle — obavezno unapređenje
Ne samo Estimate vs Actual. Koristiti stanja:
1. **Budget ceiling** — koliko korisnik može da potroši.
2. **Estimated** — trenutna interna procena.
3. **Committed** — prihvaćene ponude/narudžbine.
4. **Invoiced** — fakturisano/obračunato.
5. **Paid** — stvarno plaćeno.
6. **Remaining estimate** — rad koji još nije ugovoren.
7. **Forecast at completion** = paid + unpaid commitments + remaining estimate + approved change orders + contingency remainder.

Ovo je mnogo korisnije od prostog „potrošeno 60%“.

### G. Change Order Manager — dodati rano
Zakon o zaštiti potrošača posebno uređuje dodatne radove i saglasnost potrošača. [S13] Zato svaki dodatni rad treba imati:
- opis razloga;
- izvođača;
- originalnu stavku;
- dodatnu cenu;
- uticaj na rok;
- status Proposed / Approved / Rejected / Done;
- dokaz saglasnosti.

To je i praktična i pravno relevantna funkcija.

### H. Realized Prices Dataset
Za svaki stvarno završen rad čuvamo anonimizovanu observation:
- work item;
- grad/šira zona;
- datum;
- quantity/unit;
- labor/material split;
- VAT status ako poznat;
- included/excluded scope;
- evidence tier;
- final price.

### I. Materials
U V1 ne pokušavati live price comparison celog tržišta. Koristiti:
- generičke klase (economy/standard/premium);
- normative;
- nekoliko ručno održavanih referentnih SKU primera;
- datum i izvor.

Kasnije partner feeds i konkretne korpe.

### J. Contractor Context
U početku korisnik ručno dodaje izvođača. Kasnije:
- business-status verification link / veb-servis gde je dozvoljeno;
- dokaz o poslovnom subjektu;
- relevantne licence samo gde su stvarno potrebne;
- verified-job reviews.

APR eksplicitno navodi da su podaci dostupni putem pretraga ili veb-servisa i da neovlašćeno scraping preuzimanje nije dozvoljeno. [S15]

## 8. Šta dodati u odnosu na početnu ideju

1. **Scope standardization** — bez ovoga quote comparison je lažno precizan.
2. **Committed/Invoiced/Paid model** — obavezno za stvarnu kontrolu budžeta.
3. **Change orders** — najveći izvor budžetskog drift-a i pravno relevantan.
4. **Evidence & warranties vault** — računi, ugovor, slike, garancije, potvrde plaćanja.
5. **Data confidence/provenance** — korisnik mora znati odakle broj dolazi.
6. **Price observation trust tiers** — stvarni račun nije isto što i self-report.
7. **Anti-manipulation** — contractor ili retailer ne sme moći da „nahrani“ benchmark sopstvenim cenama.
8. **Neutrality rules** — plaćeni partner ne sme automatski biti bolje rangiran.
9. **Risk flags** — building age, wet-room risks, logistics, hidden conditions.
10. **Dispute/export pack** — kasnije PDF sa scope-om, ponudom, promenama, plaćanjima i dokazima.

## 9. Šta NE graditi u prvoj godini

- univerzalni marketplace za sve majstore;
- social feed;
- generički AI chatbot;
- 3D dizajn enterijera;
- automatsko „rangiranje najboljeg majstora“ crnom kutijom;
- live scraping stotina prodavnica bez ugovora;
- neighborhood-level cene dok sample nije dovoljan;
- desetine kategorija radova pre kvaliteta kupatilo/stan taksonomije.

## 10. Product principles

1. **Independent by design** — benchmark nije pay-to-rank.
2. **Evidence over opinion** — prikazuj provenance i sample size.
3. **Range over false precision** — bez „4.037,42 €“ ako podaci ne opravdavaju preciznost.
4. **User confirmation before AI output becomes data** — ekstrakcija nije činjenica dok korisnik ne potvrdi.
5. **Version everything** — pricebook, rules, estimates i quote mappings.
6. **Private documents stay private by default** — analitički dataset dobija samo anonimizovane/izvučene podatke po jasnom pravnom osnovu.

## 11. Definition of product-market-fit signal

Pre nego što širimo kategorije, želimo dokaz da korisnici:
- završavaju scope;
- uploaduju ponude;
- vraćaju se da uporede novu ponudu;
- koriste forecast/change-order deo tokom radova;
- pristaju da potvrde stvarnu završnu cenu;
- deo korisnika plaća one-time Project Pro ili generiše monetizovan lead.

## 12. 2026-09-24 strategic refresh

### Strongest wedge
The strongest first product is no longer “estimate + project tracker”. It is:

> **Scope-first independent Quote Decision Report for a bathroom renovation in Belgrade.**

The report must standardize scope before showing any benchmark. Project control is the retention layer after the user accepts a quote.

### New high-value feature: Scope Gap Library
For each project type maintain a learned list of items that are frequently omitted or left ambiguous in real quotes. This should power:
- quote coverage checks;
- pre-quote homeowner checklists;
- clarification questions;
- contractor scope templates later.

This is easier to bootstrap than precise price intelligence and starts creating proprietary decision data immediately.

### New acquisition hypothesis: post-purchase renovation
RGZ reports 61,343 real-estate purchase contracts and €4.2bn market value in H1 2026; apartments are 61% of value and Belgrade dominates apartment value. [S20]

A later `Renovation Readiness Report` can target recent/near-term apartment buyers and calculate purchase price + likely renovation budget. Treat this as an acquisition/adjacency experiment, not MVP scope.

### New monetization hypothesis: financing readiness
Current Serbian renovation/adaptation loans can require pro-forma invoices and, in some cases, a bill of quantities/cost estimate verified by an authorized professional. [S29][S30]

The platform may later prepare a structured handoff package, but must never claim an automated estimate is bank-valid or professionally certified without required licensed review.

### Energy-efficiency context
State energy-renovation subsidies remain meaningful, but a generic subsidy finder is not a differentiation: KojiDaBiram.rs already has an active 2026 municipality/subsidy experience. [S31][S32]

Later feature: flag potentially relevant measures and link to official current calls; do not own eligibility truth.
