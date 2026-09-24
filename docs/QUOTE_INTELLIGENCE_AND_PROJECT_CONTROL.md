# Quote Intelligence & Project Control

## 1. Quote intelligence je srce proizvoda

Prava diferencijacija nije OCR. OCR/LLM ekstrakciju mogu svi. Vrednost je u **normalizaciji na isti scope i lokalnom benchmarku**.

## 2. Quote ingestion pipeline

1. Upload PDF/image.
2. Malware/file validation.
3. Native text extraction ako postoji.
4. OCR samo za sken/fotografiju.
5. AI structured extraction u strogi schema format.
6. Normalize units/currency/VAT.
7. Map to work taxonomy.
8. Confidence per line.
9. User review — obavezna potvrda spornih redova.
10. Frozen quote version.

## 3. Normalized line item schema

- raw_text
- normalized_work_item_id
- quantity
- unit
- unit_price
- line_total
- labor/material/both/unknown
- material_spec
- VAT_status
- included/excluded
- mapping_confidence
- user_confirmed

## 4. Scope Coverage Matrix

Za svaki expected work item:
- Included explicit
- Included likely (needs confirmation)
- Excluded explicit
- Missing
- Not applicable

Primer za kupatilo:
- demontaža: included
- odvoz: missing
- hidroizolacija: missing
- nivelacija: unclear
- fugovanje/silikon: included
- test instalacija: unclear

Ovo korisniku daje mnogo više vrednosti od „Ponuda A je 12% jeftinija“.

## 5. Quote Clarity & Coverage — dokument, ne izvođač

Score može biti 0–100 ali samo za **quality of quote document**:
- scope coverage 35%;
- price transparency 20%;
- quantity/unit clarity 15%;
- payment terms 10%;
- timeline 10%;
- warranty/exclusions 10%.

Naziv: `Quote Clarity` ili `Ponuda: nivo jasnoće`, nikad „Majstor 72/100“.

## 6. Compare Quotes

### Comparable total
Ponude se ne porede po raw total-u. Sistem prikazuje:
- raw total;
- known excluded scope adjustment (informativno, sa jasnim pretpostavkama);
- missing-item estimated exposure;
- comparable coverage total.

Ne praviti veštačku „tačnu“ cenu. Ako nedostaje više bitnih stavki, reći da ponude nisu još dovoljno uporedive.

## 7. Clarification Assistant

Automatski generiše pitanja na osnovu nedostataka:
- Da li je odvoz šuta uključen?
- Da li cena keramike uključuje nivelaciju podloge?
- Ko nabavlja lepak/hidroizolaciju?
- Da li je PDV uključen?
- Da li se dodatni radovi odobravaju pisanim putem?
- Koliki je avans i koje milestone uplate slede?
- Koji je rok i šta se dešava kod kašnjenja?

## 8. Change Orders

Zakon o zaštiti potrošača uređuje saglasnost za dodatne radove; zato feature nije samo „nice to have“. [S13]

Workflow:
`Proposed → User Review → Approved/Rejected → Committed → Invoiced → Paid`.

Svaka promena prikazuje:
- originalni budget/forecast;
- delta cene;
- delta roka;
- razlog;
- dokaz (poruka/dokument/fotografija);
- ko je odobrio i kada.

## 9. Budget lifecycle

### Required totals
- Budget ceiling
- Baseline estimate
- Current estimate
- Committed
- Invoiced
- Paid
- Approved changes
- Remaining uncommitted estimate
- Contingency remaining
- Forecast at completion

### Formula
`Forecast = Paid + Unpaid committed + Approved changes not included + Remaining estimate + expected contingency usage`

Prikazati i „best/base/worst“ forecast, ne samo jednu cifru.

## 10. Evidence vault

Za svaki contractor/work item:
- quotes;
- accepted quote/contract;
- change orders;
- invoices;
- payment proof;
- before/after photos;
- warranties;
- product receipts/manuals.

Kasnije „Project Evidence Pack“ za reklamaciju, prodaju stana ili garanciju.

## 11. Contractor comparison

Ne nuditi algoritamski „winner“ samo na osnovu cene. Prikazati:
- verified business status (kada dostupno i dozvoljeno);
- quote clarity;
- scope coverage;
- price position vs benchmark;
- schedule;
- payment profile;
- warranty;
- verified-job reviews;
- broj završenih poslova kroz platformu.

User odlučuje.

## 12. Review integrity

Recenzija je „verified“ samo ako je povezana sa realnim project/accepted quote/payment signalom. Ostale recenzije jasno razdvojiti ili ih uopšte ne koristiti u ranoj fazi.

## 13. Project control scope

Ne praviti Buildertrend. Homeowneru treba minimum:
- faza;
- sledeći milestone;
- ko radi;
- planirano/commitovano/plaćeno;
- otvorena odluka;
- otvoren change order;
- dokument koji nedostaje.

Gantt i kompleksno resource planning tek ako usage dokaže potrebu.

## 14. Scope Gap Library integration

Quote analysis should output three different concepts, never one blended score:

1. **Coverage:** expected canonical scope items present / absent / ambiguous.
2. **Clarity:** quantity/unit/material/VAT/payment/warranty/exclusion clarity.
3. **Benchmark context:** only for comparable normalized items with sufficient evidence.

An item can be expensive but clear; cheap but incomplete; or impossible to benchmark. Keep these distinctions visible.

## 15. Decision Report v1 output

The first paid/manual report should fit on a small number of screens/pages:
- normalized scope summary;
- top 5 missing/unclear items;
- comparable price total where possible;
- benchmark deviations with sample/confidence;
- payment schedule / VAT / warranty / deadline clarity;
- questions to send contractor;
- contingency and forecast impact;
- limitations.

Do not generate a contractor winner. Users decide.

## 16. Financing handoff — later

Where a bank or other institution requires an authorized predmer/predračun, the platform can export structured scope/data for review by a licensed professional. It must explicitly distinguish:
- platform estimate / quote analysis;
- professional signed estimate;
- bank-accepted documentation.
