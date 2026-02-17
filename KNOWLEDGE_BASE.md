# Enervit Retail Prezentace – Knowledge Base

## Brand Guidelines ENERVIT

- Logo ENERVIT musí byť vždy **biele na červenom obdĺžniku** (sharp corners, bez zaoblení)
- Padding okolo loga musí byť **proporcionálny** zo všetkých strán (nie veľký priestor dole)
- Na `<img>` v logo kontajneri pridať `display: block;` — odstraňuje extra whitespace pod obrázkom
- Intersport logo tiež v obdĺžniku so **sharp corners** (bez border-radius)
- Medzi logami Enervit a Intersport používať **separator "x"** (nie "+"), konzistentne na všetkých slidoch
- Väčší `gap` medzi logami v headeri: **12px** a CSS trieda `.logo-sep`
- Referenčný dokument: `Enervit Sport _ Logo Guidelines_03.2022.pdf`

## Produktové rady a farby

- **Enervit Sport** = červená rada (gely, tyčinky, nápoje, regenerácia)
- **C2:1 PRO** = červeno-čierna rada (patentovaná technológia 2:1, Carbo Gel/Bar/Jelly)
- **Pure-Pro** = tyrkysová/teal rada (proteíny, kreatín, aminokyseliny, elektrolyty)

## Cenové podmienky

- **35 % sleva z MOC** (doporučená maloobchodná cena s DPH)
- NC sa uvádza ako **"Vaše nákupní cena (bez DPH)"** — nie "Vaše cena"
- Pre potravinové doplnky je **DPH 12 %** (prepočet: `NC = MOC × 0.65 / 1.12`)
- Splatnosť **30 dní**
- Doprava zdarma nad **5 000 Kč**
- Bez minimálnej objednávky
- Expedícia do **5 pracovních dnů** (nie 3 dni!)
- Objednávky: **B2B portál / e-mail** — telefón vyškrtnúť (právne dôvody — objednávka musí byť písomná)

## Prezentačné pravidlá

- **Fullscreen mód** s popup odporučením (ako na Jiz50 reporte)
- Každý slide musí **fitovať bez scrollu** vo fullscreen
- Ak slide vyžaduje scroll → **rozdeliť na dva slidy** (napr. planogram split)
- Photo bannery v headeroch slidov → **odstrániť a presunúť do samostatných visual break slidov**
- Sidebar fotky na textových slidoch → zbytočne natiahujú layout, lepšie odstrániť
- Text o poskytovanej podpore formulovať opatrne: **"po vzájemné dohodě zajistíme podporu přizpůsobenou typu prodejny"**

## Práca s obrázkami

- **GPH série** (Enervit_PurePro_GPH_*.jpg) = výhradne Pure-Pro fotky (tyrkysové produkty)
- Pre Enervit Sport lifestyle: `sport-sinner.jpg` (Sinner s Liquid Gel na antuke) je najlepšia dostupná
- Pre C2:1 lifestyle: `enervit-homepage-block.jpg` (Pogačar s gelom), `c21-carbogel-lifestyle.jpg` (gel v drese)
- **Magic Cherry** (`magic-cherry-video-cover.jpg`) = product box shot, nie lifestyle — lepšie nahradiť
- `lifestyle-sport.jpg`, `lifestyle-running.jpg`, `lifestyle-cycling.jpg` = **broken** (404 stránky z enervit.cz, nie obrázky!)
- Slider obrázky zo stránky enervit.cz = tiež väčšinou **404 HTML stránky**
- Pri visual break slidoch dbať na **balans medzi 3 produktovými radami** (nie 4/5 z jednej)
- `object-fit: cover` + `object-position: center top` pre portréty (aby neboli orezané hlavy)

## Planogram

- Police 90 cm, 3 úrovne
- Rozloženie: **12 SKU Sport**, **8 SKU C2:1PRO**, **1 SKU Pure-Pro** = 21 celkom
- Doporučená hodnota prvního nákupu: **~15 000–25 000 Kč** na predajňu (v NC bez DPH)

## Ambasádori 2026

- **Jannik Sinner** (#1 ATP, tenis)
- **Tadej Pogačar** (4x TdF, cyklistika)
- **Federico Pellegrino** (bežecké lyžovanie)
- **Isaac Del Toro** (cyklistika, UAE Team Emirates)
- **Francesco Puppi** (trail running)
- Obnovené partnerstvo 2026 so Sinnerom i Pogačarom

## PIN ochrana a distribúcia

- Prezentácia je chránená **PIN gate stránkou** (client-side, sessionStorage)
- PIN pre Intersport: **intersport2026**
- Doménová stratégia: **[retailer].enervit.online** — každý partner má vlastnú subdoménu (napr. `intersport.enervit.online`, neskôr `decathlon.enervit.online`)
- Vercel stále deployuje z git repa, doména sa nastavuje cez DNS (enervit.online)

## Komunikácia s retailermi (emaily)

- Juraj píše **slovensky bez diakritiky** — to je štandard, nie čeština!
- **Žiadne emoji** v obchodných mailoch
- **Žiadny custom HTML font/styling** — čistý mail, štandardný rendering
- Oslovovať **krstným menom** (napr. "Dobry den, Lucie")
- Vyzdvihnúť **podmienky spolupráce** (splatnosť, SLA, doprava, závozy) — nie marketing/brand story
- Pridať vetu o flexibilite: "Vsetky body vieme spolocne prediskutovat a pripadne upravit podla potreby"
- V kópii vždy **Key Account Manager** (Karolína)
- Prvý kontakt Intersport: **Lucie Kuřičová** — `lucie.kuricova@intersport.cz` (stretnutie na JIZ50)

## Kontakty

- Key Account Manager: **Karolína Calda** — `calda.karolina@vitarsport.cz`, +420 724 963 739
- Intersport CZ: **Lucie Kuřičová** — `lucie.kuricova@intersport.cz`

## Technické workflow

- HTML prezentácia: `03_PREZENTACE_INTERSPORT_MANAGEMENT.html`
- Po každej zmene **syncovať do `index.html`** (Vercel deployuje index.html)
- Git repo: `github.com/jurajgiacko/enervitxintersport` → Vercel: `enervitxintersport.vercel.app` → Custom: `intersport.enervit.online`
- Pri renumberovaní slidov pracovať **odzadu** (od najvyššieho ID), aby nevznikli duplicity
- Pri merge conflictoch s Vercelom: `git checkout --ours` pre HTML súbory (lokálne zmeny majú prednosť)

## Chyby, ktorým sa vyhnúť

- **Nepoužívať `border-radius` na logá** — porušuje brand guidelines
- **Nekrčiť foto bannery do headerov slidov** — orezané hlavy, zlá vizuálna kvalita
- **Neodkazovať sa na slider obrázky z enervit.cz** — väčšina sú 404 stránky
- **Nepridávať telefón do objednávkových kanálov** — právne dôvody
- **Nekombovať obrázky len z jednej produktovej rady** na visual break slidoch

---
Posledná aktualizácia: 2026-02-17
