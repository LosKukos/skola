# Bezpečnost zdravotnických technologií
### Státnicová příprava – Biomedicínská technika 2026

---

# Otázka 59: Technické normy – systém ČSN, IEC 60601/80601, závaznost

## Co je technická norma?

Technická norma je **dokument stanovující požadavky, specifikace, směrnice nebo charakteristiky**, které lze konzistentně používat k zajištění, že materiály, výrobky, procesy a služby jsou vhodné pro svůj účel.

### Závaznost norem

| Typ | Závaznost | Popis |
|---|---|---|
| **Harmonizovaná norma** | De facto závazná | Norma citovaná v Úředním věstníku EU → splnění = presumpce shody s MDR požadavky |
| **Závazná norma** | Právně závazná | Odkaz v zákoně nebo vyhlášce → nutno splnit |
| **Dobrovolná norma** | Nezávazná | Použití je dobrovolné, ale splnění prokazuje dobrou praxi |

> **Presumpce shody**: Výrobce, který splní harmonizovanou normu, se předpokládá, že splnil odpovídající základní požadavek MDR – nemusí to dále dokazovat.

---

## Systém ČSN

**ČSN = Česká technická norma** – vydává **ÚNMZ (Úřad pro technickou normalizaci, metrologii a státní zkušebnictví)**.

### Označování norem

| Formát | Příklad | Popis |
|---|---|---|
| ČSN EN ISO XXXXX | ČSN EN ISO 13485 | Přejatá mezinárodní norma (ISO) jako evropská (EN) a česká (ČSN) |
| ČSN EN XXXXX | ČSN EN 60601-1 | Přejatá evropská norma (EN) jako česká |
| ČSN IEC XXXXX | ČSN IEC 60601-1 | Přejatá mezinárodní norma IEC jako česká |
| ČSN XXXXX | ČSN 33 2000 | Ryze česká norma (bez mezinárodního originálu) |

### Normalizační orgány

| Úroveň | Orgán | Zkratka |
|---|---|---|
| Mezinárodní – elektrotechnika | International Electrotechnical Commission | **IEC** |
| Mezinárodní – ostatní | International Organization for Standardization | **ISO** |
| Evropská | European Committee for Electrotechnical Standardization | **CENELEC** |
| Evropská | European Committee for Standardization | **CEN** |
| Česká | Úřad pro technickou normalizaci, metrologii a státní zkušebnictví | **ÚNMZ** |

---

## Systém norem IEC 60601 / IEC 80601

### IEC 60601 – Zdravotnické elektrické přístroje

Hierarchický systém norem pro bezpečnost a výkon ZEP (zdravotnických elektrických přístrojů):

```
IEC 60601-1 (Obecná norma)
        ├── IEC 60601-1-2 (Skupinová norma: EMC)
        ├── IEC 60601-1-6 (Skupinová norma: Použitelnost / Usability)
        ├── IEC 60601-1-8 (Skupinová norma: Alarmové systémy)
        ├── IEC 60601-1-9 (Skupinová norma: Ekologický návrh)
        ├── IEC 60601-1-10 (Skupinová norma: Fyziologické uzavřené smyčky)
        └── IEC 60601-1-11 (Skupinová norma: Domácí péče)

IEC 60601-2-xx (Zvláštní normy pro konkrétní typy ZP):
        ├── IEC 60601-2-2: ESU (elektrochirurgie)
        ├── IEC 60601-2-4: Defibrilátory
        ├── IEC 60601-2-25: Elektrokardiografy
        ├── IEC 60601-2-27: EKG monitory
        ├── IEC 60601-2-30: Automatické tlakoměry
        ├── IEC 60601-2-34: Invazivní tlakoměry
        ├── IEC 60601-2-49: Multiparametrické monitory
        └── IEC 60601-2-xx: ... (přes 80 zvláštních norem)
```

### IEC 80601 – Zdravotnické elektrické systémy
- Navazuje na IEC 60601-1
- Zahrnuje systémy složené z více ZEP (např. anesteziologická stanice)

### Trojice norem pro jeden ZP
Při certifikaci ZP se typicky aplikují:
1. **IEC 60601-1** – obecná norma (základ)
2. **Příslušné skupinové normy** (EMC, usability, alarmy...)
3. **Příslušná zvláštní norma** (specifická pro daný typ ZP)

---

## Základní bezpečnost a nezbytná funkčnost

| Pojem | Definice |
|---|---|
| **Základní bezpečnost (Basic Safety)** | Absence nepřijatelného rizika přímo způsobeného fyzikálními nebezpečími ZEP za normálních podmínek i za podmínek jediného selhání |
| **Nezbytná funkčnost (Essential Performance)** | Funkčnost ZEP, jejíž ztráta nebo degradace by vedla k nepřijatelnému riziku (nad rámec základní bezpečnosti) |

> Příklad: Monitor SpO₂ musí zobrazovat hodnoty správně (nezbytná funkčnost) a nesmí způsobit úraz elektrickým proudem (základní bezpečnost).

---

# Otázka 60: Obecné požadavky na bezpečnost elektrických ZP

## Ochrana před elektrickými nebezpečími

### Unikající proudy (Leakage Currents)

Unikající proud je proud, který teče mimo zamýšlenou cestu – přes pacienta, kryt nebo ochranný vodič.

| Typ unikajícího proudu | Definice | Limity (typ CF) |
|---|---|---|
| **Earth Leakage Current** | Proud tekoucí ochranným vodičem | ≤ 500 μA (norm.), ≤ 1 000 μA (SFC) |
| **Enclosure Leakage Current** | Proud tekoucí přes kryt přístroje | ≤ 100 μA (norm.) |
| **Patient Leakage Current** | Proud tekoucí přes AP část přes pacienta na zem | ≤ 10 μA (CF, norm.) |
| **Patient Auxiliary Current** | Proud tekoucí mezi AP částmi | ≤ 10 μA (CF, norm.) |

**SFC = Single Fault Condition** – podmínka jediného selhání (přerušení ochranného vodiče, zkrat AP části apod.)

### Třídy ochrany ZP

| Třída | Ochrana | Popis |
|---|---|---|
| **Třída I** | Ochranné uzemnění (PE) | Kovový kryt spojen s ochranným vodičem |
| **Třída II** | Dvojitá nebo zesílená izolace | Bez uzemnění – dvě nezávislé izolační bariéry |
| **Třída III (SELV)** | Bezpečné malé napětí | Napájení < 25 V AC nebo < 60 V DC |
| **Vnitřní napájení** | Baterie | Nejbezpečnější – bez síťového napájení |

---

## Ochrana před mechanickými nebezpečími

- **Pohyblivé části** – kryty, zámky (ochrana před zachycením)
- **Ostré hrany** – zaoblení, ochrany
- **Stabilita** – přístroj nesmí samovolně spadnout (tipover test)
- **Tlakové nádoby** – bezpečnostní ventily, tlakové testy
- **Ergonomie** – hmotnost, úchyty, manipulace

---

## Ochrana před nebezpečími z nežádoucího a nadměrného záření

| Typ záření | Nebezpečí | Ochrana |
|---|---|---|
| **Ionizující (RTG, gamma)** | Radiační poškození tkání | Stínění, kolimace, ALARA |
| **Laserové** | Poškození sítnice, kůže | Bezpečnostní třídy (1–4), ochranné brýle, interlocky |
| **UV záření** | Poškození kůže a očí | Kryty, filtry |
| **Infračervené (IR)** | Tepelné poškození | Kryty, varování |
| **Akustické (UZ)** | Poškození sluchu (UZ terapie) | Limity intenzity, expozičního času |
| **Elektromagnetické RF** | Tepelné poškození tkání (MRI SAR) | Limity SAR, monitoring |

---

## Ochrana před nadměrnými teplotami a jinými nebezpečími

### Tepelná nebezpečí
- **Povrchová teplota** – max. teplota povrchů přístupných pacientovi a obsluze
  - Kovové plochy: max. 51 °C (krátkodobý dotek), 43 °C (dlouhodobý)
  - Plastové plochy: max. 56 °C
- **Přehřátí** – tepelné pojistky, termostaty, ventilace
- **Požár** – materiály odolné vznícení, tepelné pojistky

### Biologická nebezpečí
- **Biokompatibilita** – materiály v kontaktu s pacientem dle ISO 10993
- **Sterilizovatelnost** – odolnost materiálů vůči sterilizačním procesům

---

## Ochrana před nebezpečným výstupem

- **Maximální výstupní energie** – defibrilátor, ESU, laserové systémy – hardwarové limity
- **Přesnost dávkování** – infuzní pumpy, radioterapie – software + hardware limity
- **Fail-safe design** – při selhání přístroj přejde do bezpečného stavu (ventilátory → odpojení od pacienta, ne nulový průtok)
- **Alarmy** – povinné pro ZP s kritickými výstupními parametry (IEC 60601-1-8)

---

## Poruchové stavy (Fault Conditions)

### Normální podmínky (NC – Normal Conditions)
Přístroj funguje dle specifikací výrobce, bez poruch.

### Podmínky jediného selhání (SFC – Single Fault Condition)
Přístroj musí zůstat bezpečný i při výskytu **jednoho selhání**:
- Přerušení ochranného vodiče (PE)
- Přerušení nebo zkrat jedné izolační vrstvy
- Zkrat AP části na napájení nebo zem
- Selhání jednoho chladicího prvku

> ZP musí splnit bezpečnostní limity i za SFC – to je klíčový požadavek IEC 60601-1!

---

## Elektromagnetická kompatibilita (EMC)

EMC = schopnost ZP fungovat správně v elektromagnetickém prostředí bez způsobení nepřijatelného rušení jiným zařízením.

### Dvě složky EMC

| Složka | Definice |
|---|---|
| **Emise (Emissions)** | ZP nesmí vyzařovat elektromagnetické rušení nad povolenou úroveň |
| **Imunita (Immunity/Susceptibility)** | ZP musí fungovat správně i při přítomnosti elektromagnetického rušení |

### Typy rušení a testy dle IEC 60601-1-2

| Typ rušení | Test |
|---|---|
| **Vedené emise** | Měření rušení na napájecím kabelu |
| **Vyzařované emise** | Měření vyzařovaného pole v bezodrazové komoře |
| **ESD (Electrostatic Discharge)** | Výboj statické elektřiny na kryt – 8 kV kontaktní, 15 kV vzduchový |
| **EFT (Electrical Fast Transient)** | Rychlé přechodové jevy na napájení |
| **Surge** | Přepěťové impulzy na napájení (blesk) |
| **RF imunita vedená** | Rušení zavedené přes napájení (0,15–80 MHz) |
| **RF imunita vyzařovaná** | Rušení ze vzdáleného zdroje (80–2700 MHz) |
| **Magnetické pole 50/60 Hz** | Vliv síťového magnetického pole |

### HEMP (Healthcare Environment – EMC profil nemocnice)
IEC 60601-1-2 edice 4 rozlišuje tři prostředí použití ZP:
- **Profesionální zdravotnické prostředí** (nemocnice, klinika)
- **Domácí péče**
- **Speciální prostředí** (blízkost HF chirurgie, MRI)

---

# Otázka 61: Zdravotnické napájecí jednotky

## Co je zdravotnická napájecí jednotka?

Zdravotnická napájecí jednotka (Medical IT system / Isolated Power System) je **soustava napájení** zajišťující bezpečné elektrické napájení zdravotnických přístrojů v prostorách s rizikem mikrošoku.

---

## Prostory dle míry rizika úrazu elektrickým proudem

Dle ČSN 33 2140 (EN 60364-7-710):

| Skupina | Popis | Příklady | Požadavky |
|---|---|---|---|
| **Skupina 0** | Bez speciálních požadavků | Ambulance, čekárny | Standardní instalace |
| **Skupina 1** | Riziko mikrošoku – omezené použití | Vyšetřovny, lůžková oddělení | IT systém nebo RCD |
| **Skupina 2** | Riziko mikrošoku – přímý kontakt se srdcem nebo život ohrožující výkony | Operační sály, ARO, katetrizační laboratoře, JIP | **Povinný IT systém (izolovaný napájecí systém)** |

---

## Izolovaný napájecí systém (IT systém)

### Princip
- Oddělovací transformátor (bezpečnostní izolační transformátor) odděluje spotřebiče od veřejné sítě
- Ani jeden vodič sekundárního okruhu není uzemněn
- **Izolační stav monitorován IMD (Insulation Monitoring Device)**
- První porucha izolace (zkrat na zem) **nevypne napájení** – pouze spustí alarm
- Teprve **druhá porucha** by způsobila zkrat → čas na řešení bez výpadku

### Výhody IT systému
- Kontinuita napájení (výpadek neohrozí pacienta při operaci)
- Minimalizace mikrošokového rizika (unikající proud < 1 mA)

### Komponenty IT systému

| Komponenta | Funkce |
|---|---|
| **Izolační transformátor** | Galvanické oddělení od sítě |
| **IMD** | Kontinuální monitoring izolačního stavu (alarm při R < 50 kΩ) |
| **Zobrazovací a alarmová jednotka (LIM)** | Signalizace stavu systému |
| **Přepěťová ochrana** | Ochrana před přepětím ze sítě |

---

## Medicinální plyny – napájení a rozvody

Viz **Otázka 50** – medicinální plyny jako součást technického vybavení nemocnice. Rozvody medicinálních plynů jsou součástí zdravotnické napájecí infrastruktury a podléhají VTZ legislativě.

---

## Záložní napájení (UPS a generátory)

Pro zdravotnická zařízení je kritická **kontinuita napájení**:

| Systém | Čas přepnutí | Výdrž | Použití |
|---|---|---|---|
| **UPS (Uninterruptible Power Supply)** | < 20 ms (online), < 5 ms (double conversion) | Minuty až hodiny | Operační sály, ICU, servery |
| **Dieselový generátor** | 10–30 s | Hodiny – dny | Záložní napájení celé nemocnice |
| **Kombinace UPS + generátor** | UPS překlene spuštění generátoru | Neomezeně (palivo) | Kritická infrastruktura |

Dle ČSN EN 60364-7-710 musí být definovány **kritické obvody** zásobované ze zálohy do 15 s.

---

# Otázka 62: Bezpečnostně-technické kontroly ZP

## Co je BTK?

Bezpečnostně-technická kontrola (BTK) je **pravidelná kontrola zdravotnického prostředku**, která ověřuje jeho bezpečnost, funkčnost a stav. Provádí ji biomedicínský technik nebo autorizovaný servis.

---

## Legislativní základ BTK

- **Zákon č. 375/2022 Sb.** – povinnost provozovatelů udržovat ZP v řádném technickém stavu
- **MDR 2017/745** – požadavek na PMS (postmarketingové sledování) zahrnuje i provozní bezpečnost
- **Návod výrobce** – výrobce definuje rozsah a frekvenci BTK (mandatory maintenance)

---

## Rozsah BTK

### 1. Vizuální kontrola
- Stav krytu (praskliny, deformace)
- Kabely a konektory (poškození, ohyby, koroze)
- Elektrody, senzory, příslušenství
- Štítky a označení (přítomnost, čitelnost)
- Čistota a hygiena

### 2. Elektrická bezpečnost
Měření dle IEC 60601-1 pomocí **elektrického bezpečnostního analyzátoru (ESA)**:

| Měřená veličina | Norma | Přístroj |
|---|---|---|
| Odpor ochranného uzemnění | < 0,1 Ω | ESA, miliohmetr |
| Earth leakage current | Dle třídy ZP | ESA |
| Patient leakage current | Dle typu AP (B/BF/CF) | ESA |
| Enclosure leakage current | Dle třídy ZP | ESA |

### 3. Funkční testy
- Ověření správnosti měření/zobrazení pomocí simulátoru pacienta nebo referenčního etalonu
- Kontrola alarmů – všechny alarmy musí fungovat (spustit se při překročení limitu)
- Kontrola nastavitelných parametrů

### 4. Kontrola příslušenství
- Elektrody, sondy, kabeláž, spotřební materiál
- Datum exspirace jednorázových součástí

---

## Frekvence BTK

| Faktor | Vliv na frekvenci |
|---|---|
| **Doporučení výrobce** | Minimální interval definuje výrobce v IFU |
| **Riziková třída ZP** | Vyšší třída → kratší interval (Třída III: půlroční) |
| **Intenzita využívání** | Přístroje v kontinuálním provozu → kratší interval |
| **Historická spolehlivost** | Přístroj s opakovanými závadami → kratší interval |

Typické intervaly: **6 měsíců (Třída IIb, III)** nebo **12 měsíců (Třída I, IIa)**.

---

## Dokumentace BTK

### Protokol BTK musí obsahovat
- Identifikace přístroje (typ, výrobce, SN, inventární č.)
- Datum provedení BTK
- Jméno a kvalifikace techniky
- Výsledky jednotlivých měření (naměřené hodnoty + limity)
- Celkový výsledek: **VYHOVUJE / NEVYHOVUJE**
- Termín příští BTK
- Podpis technika

### Archivace
- Protokoly BTK musí být archivovány po dobu **provozu přístroje + zákonná archivační lhůta**
- Fyzicky (karty přístrojů) nebo v CMMS systému

---

## Přístroj nevyhovující BTK

Pokud přístroj **nevyhoví** BTK:
1. **Okamžité vyřazení z provozu** – viditelné označení „MIMO PROVOZ"
2. **Hlášení vedoucímu oddělení**
3. **Oprava nebo rozhodnutí o vyřazení**
4. **Po opravě opakovaná BTK** před vrácením do provozu

---

# Otázka 63: Systém vigilance pro zdravotnické prostředky

## Co je vigilance?

Vigilance (dohled) je **systém hlášení, shromažďování, hodnocení a šíření informací** o nežádoucích příhodách spojených se zdravotnickými prostředky s cílem předcházet opakování.

---

## Legislativní základ vigilance

- **MDR 2017/745** – Článek 87–92, Příloha IX část B – povinnosti výrobce
- **Zákon č. 375/2022 Sb.** – povinnosti provozovatelů a zdravotnických pracovníků v ČR
- Dohled v ČR vykonává **SÚKL (Státní ústav pro kontrolu léčiv)**

---

## Definice nežádoucí příhody (Serious Incident)

Dle MDR čl. 2(64) – **závažná nežádoucí příhoda** je jakákoli porucha nebo zhoršení vlastností ZP nebo jeho označení nebo IFU, které přímo nebo nepřímo vedly nebo mohly vést k:
- **Úmrtí** pacienta, uživatele nebo jiné osoby
- **Závažnému zhoršení zdravotního stavu** (trvalé zranění, život ohrožující situace)
- **Závažné hrozbě veřejného zdraví**

---

## Povinné osoby a jejich odpovědnosti

| Subjekt | Povinnosti |
|---|---|
| **Výrobce** | Zřídit systém PMS, hlásit závažné příhody NCA do 15/30 dní, provádět FSCA |
| **Zdravotnické zařízení (provozovatel)** | Hlásit nežádoucí příhody výrobci a SÚKL |
| **Zdravotnický pracovník** | Zaznamenat a hlásit nežádoucí příhodu vedení + BMT |
| **SÚKL (NCA – National Competent Authority)** | Přijímat hlášení, koordinovat šetření, informovat EUDAMED |

---

## Lhůty hlášení výrobce NCA

| Typ příhody | Lhůta hlášení |
|---|---|
| Vážná hrozba veřejného zdraví | **2 dny** |
| Smrt nebo neočekávané závažné zhoršení | **10 dní** |
| Ostatní závažné příhody | **15 dní** |
| Trendy (opakující se ne-závažné příhody) | **Dle plánu PMS** |

---

## Postup hlášení nežádoucí příhody v nemocnici

```
Zjištění nežádoucí příhody (zdravotník, BMT)
        ↓
Okamžité zajištění přístroje (zachovat stav pro šetření)
        ↓
Hlášení biomedicínskému technikovi
        ↓
Hlášení výrobci (nebo autorizovanému zástupci)
        ↓
Hlášení SÚKL (při závažné příhodě)
        ↓
Šetření příčiny (výrobce / servis / BMT)
        ↓
Nápravná opatření (FSCA)
        ↓
Záverečná zpráva → archivace
```

---

## Souvislost vigilance s klasifikací ZP

- Vyšší třída ZP (III > IIb > IIa > I) → přísnější požadavky na vigilanci a PMS
- Implantáty třídy III → **PMCF (Post-Market Clinical Follow-up)** – aktivní sledování klinických dat po uvedení na trh

---

# Otázka 64: Bezpečnostní nápravná opatření

## Co je bezpečnostní nápravné opatření (FSCA)?

**FSCA (Field Safety Corrective Action)** = opatření přijaté výrobcem k nápravě rizika spojeného se ZP, který byl uveden na trh.

---

## Druhy FSCA a jejich hierarchie

Od nejzávažnějšího po nejméně závažné:

| Typ | Popis | Příklad |
|---|---|---|
| **Recall – stažení z trhu** | Fyzické stažení ZP od uživatelů a distribuce | Kardiostimulátory s vadnou baterií – stažení a výměna |
| **Recall – stažení z používání** | Příkaz přestat používat ZP | Defibrilátory s chybou SW – zastavit použití do aktualizace |
| **Modifikace ZP** | Výrobce dodá opravu nebo upgrade | SW patch pro chybu v algoritmu |
| **Varování (Advisory)** | Výrobce informuje o riziku a vydá pokyny k použití | Omezení v určitých podmínkách, doplnění varování v IFU |
| **Stažení z prodeje** | Zastavení distribuce (ale již nasazené přístroje mohou fungovat) | Nové šarže výrobku pozastaveny |

---

## FSN – Field Safety Notice

**FSN (Field Safety Notice)** = písemná komunikace výrobce zasílaná zákazníkům (nemocnicím) při FSCA.

### Obsah FSN
- Identifikace ZP (výrobce, typ, dotčené SN nebo šarže)
- Popis rizika a zjištěného problému
- Doporučená opatření (co má nemocnice udělat)
- Kontaktní informace výrobce
- Termín pro zpětné hlášení

---

## Povinnosti zdravotnického zařízení při FSCA

1. **Přijmout FSN** – registrace u výrobce nebo SÚKL pro zasílání FSN
2. **Identifikovat dotčené ZP** – prohledat inventář dle SN nebo šarže
3. **Provést opatření** dle instrukce FSN (stáhnout, aktualizovat, informovat)
4. **Informovat klinický personál** – bezpečnostní briefing
5. **Potvrdit provedení opatření výrobci** (zpětné hlášení – compliance report)
6. **Archivovat dokumentaci** o provedení FSCA

---

## Časová posloupnost FSCA

```
Identifikace problému (výrobce nebo zpráva z terénu)
        ↓
Interní šetření výrobce
        ↓
Rozhodnutí o FSCA a typu opatření
        ↓
Hlášení NCA (SÚKL) – souběžně s nebo před rozesláním FSN
        ↓
Rozeslání FSN zákazníkům (nemocnicím)
        ↓
Provedení opatření zákazníky
        ↓
Zpětné hlášení zákazníků výrobci
        ↓
Uzavření FSCA – závěrečná zpráva NCA
```

---

# Otázka 65: Postmarketingové sledování kvality ZP výrobcem

## Co je postmarketingové sledování (PMS)?

**PMS (Post-Market Surveillance)** je systém kontinuálního sledování bezpečnosti, výkonu a kvality ZP po jeho uvedení na trh, po celou dobu jeho životnosti.

---

## Legislativní základ PMS

- **MDR 2017/745** – Článek 83–86, Příloha III – povinný PMS plán a zprávy
- Výrobce musí mít **PMS plán** jako součást technické dokumentace

---

## Zdroje PMS dat

| Zdroj | Data |
|---|---|
| **Vigilance hlášení** | Nežádoucí příhody od provozovatelů a uživatelů |
| **Literatura** | Vědecké publikace o ZP nebo ekvivalentních ZP |
| **Klinické registry** | Registrační data o výkonu ZP v reálné praxi (RWD) |
| **Stížnosti zákazníků** | Complaint handling systém výrobce |
| **Servisní data** | Záznamy o poruchách a opravách |
| **Sociální média a databáze** | Zprávy uživatelů a pacientů |
| **PMCF studie** | Post-Market Clinical Follow-up – aktivní klinický sběr dat |

---

## PMS výstupy – zprávy

| Zpráva | Zkratka | Frekvence | Pro koho |
|---|---|---|---|
| **Periodic Safety Update Report** | PSUR | Třída IIa: každé 2 roky; IIb, III: ročně | NCA (SÚKL), NB |
| **Summary of Safety and Clinical Performance** | SSCP | Třída IIb, III – veřejně přístupná | EUDAMED – veřejnost |
| **Post-Market Surveillance Report** | PMS Report | Třída I – dle potřeby | Interně, na vyžádání |

---

## PMCF – Post-Market Clinical Follow-up

Aktivní sbírání klinických dat po uvedení ZP na trh pro ověření dlouhodobé bezpečnosti a výkonu.

### Metody PMCF
- **PMCF studie** – prospektivní studie v reálné klinické praxi
- **Registry** – zápis výsledků do registru (např. registr endoprotéz, kochleárních implantátů)
- **Dotazníky pro lékaře a pacienty**
- **Analýza dostupné literatury**

---

# Otázka 66: Klinická zkouška a klinické hodnocení ZP

## Klinická zkouška vs. Klinické hodnocení

| Pojem | Definice |
|---|---|
| **Klinické hodnocení (Clinical Evaluation)** | Kontinuální proces hodnocení klinických dat – zahrnuje literaturu, PMS data a výsledky klinického zkoušení. Výsledkem je CER. |
| **Klinická zkouška (Clinical Investigation)** | Prospektivní systematická klinická studie s účastí lidských subjektů pro generování nových klinických dat o ZP. |

> Klinická zkouška je jedním z nástrojů klinického hodnocení – ne vždy nutná (lze vycházet z literatury o ekvivalentních ZP).

---

## Kdy je klinická zkouška ZP povinná?

- ZP **třídy III** – vždy (pokud nelze prokázat ekvivalenci s existujícím ZP)
- ZP **třídy IIb implantovatelné** – vždy
- Inovativní ZP bez ekvivalentního srovnatelného ZP
- Pokud NB nebo NCA vyžaduje doplnění klinických dat

---

## Fáze klinické zkoušky ZP

Analogie s klinickými zkouškami léčiv, ale s odlišnostmi:

| Fáze | Popis |
|---|---|
| **Studie proveditelnosti (Feasibility)** | Malá pilotní studie – ověření principu na prvních pacientech |
| **Pivotní studie** | Klíčová studie pro registraci – definuje bezpečnost a výkon |
| **PMCF studie** | Po registraci – dlouhodobé sledování v reálné praxi |

---

## Etické a regulatorní požadavky klinické zkoušky

### Zapojené subjekty

| Subjekt | Role |
|---|---|
| **Sponzor** | Iniciuje, organizuje a financuje klinickou zkoušku |
| **Zkoušející (Principal Investigator)** | Zodpovědný lékař v centru |
| **Etická komise (EK)** | Hodnotí etičnost studie – souhlas nutný |
| **SÚKL** | Schvaluje klinická zkoušení ZP v ČR |
| **EUDAMED** | Registrace klinické zkoušky |

### Základní dokumenty
- **Protokol studie** – design, cíle, metodologie, statistika
- **Informovaný souhlas** – pacient musí být informován a podepsat souhlas
- **Investigator Brochure (IB)** – shrnutí dostupných dat o ZP pro zkoušejícího
- **Clinical Investigation Plan (CIP)** – plán klinické zkoušky dle MDR

### Právní základ
- **MDR 2017/745** – Kapitola VI, Příloha XV – požadavky na klinická zkoušení
- **ISO 14155** – Správná klinická praxe pro klinická zkoušení ZP (GCP pro ZP)
- **Helsinská deklarace** – etické principy klinického výzkumu

---

## Souvislost klinické zkoušky s klasifikací ZP

| Třída | Klinická zkouška | Klinické hodnocení |
|---|---|---|
| **Třída I** | Obvykle ne | Literatura + PMS data |
| **Třída IIa** | Výjimečně | Literatura + PMS data nebo vlastní data |
| **Třída IIb** | Často | Vlastní klinická data nebo přísná ekvivalence |
| **Třída III / implantáty** | **Povinná** (bez prokázané ekvivalence) | Povinné CER + PMCF |

---

## Klinické hodnocení – CER (Clinical Evaluation Report)

### Obsah CER
1. **Rozsah** – zamýšlený účel ZP, cílová populace, indikace
2. **Identifikace klinických dat** – literatura, vlastní data, vigilance
3. **Hodnocení relevance a kvality dat** – MEDLINE, EMBASE rešerše
4. **Analýza dat** – souhrn důkazů bezpečnosti a výkonu
5. **Závěry** – ZP splňuje / nesplňuje GSPR požadavky
6. **Plán PMCF** – co bude dále sledováno
7. **Datum a podpis** – CER musí být aktualizován průběžně

### Ekvivalence ZP
Pokud výrobce nemá vlastní klinická data, může argumentovat **ekvivalencí** s jiným ZP (pro nějž data existují), ale musí prokázat:
- **Technickou ekvivalenci** – stejný design, materiály, specifikace
- **Biologickou ekvivalenci** – stejné materiály v kontaktu s tkání
- **Klinickou ekvivalenci** – stejné indikace, zamýšlený účel, populace

> Pro ZP třídy III: ekvivalence vyžaduje **přístup k technické dokumentaci ekvivalentního ZP** – prakticky nutná dohoda mezi výrobci.

---

*Konec bloku – Bezpečnost zdravotnických technologií | Otázky 59–66*
