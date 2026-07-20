# Elektrická měření
### Státnicová příprava – Biomedicínská technika 2026

---

# Otázka 75: Chyby měření a nejistota

## Základní pojmy

| Pojem | Definice |
|---|---|
| **Měřená veličina (measurand)** | Fyzikální veličina, která je předmětem měření |
| **Naměřená hodnota** | Hodnota přiřazená měřené veličině na základě měření |
| **Skutečná hodnota** | Pravá hodnota měřené veličiny – nikdy přesně neznámá |
| **Odchylka (chyba)** | Rozdíl mezi naměřenou a skutečnou hodnotou |
| **Nejistota měření** | Parametr charakterizující rozsah hodnot přiřaditelných měřené veličině |

---

## Chyby měření

### Podle příčiny

#### Náhodná (statistická) chyba
- Způsobena **nepředvídatelnými fluktuacemi** – šum, vibrace, kolísání sítě
- **Nelze eliminovat** jedním měřením – snižuje se průměrováním více měření
- Projevuje se jako **rozptyl naměřených hodnot** kolem střední hodnoty
- Charakterizována **směrodatnou odchylkou (σ)**

#### Systematická chyba
- Způsobena **stálými vlivy** – nepřesnost kalibrací, nelinearita přístroje, chyba metody, parazitní efekty
- Způsobuje **posun** naměřených hodnot od skutečné hodnoty
- **Nelze eliminovat** opakováním měření – vyžaduje identifikaci a korekci

#### Hrubá chyba (omyl)
- Způsobena **chybou obsluhy** nebo selháním přístroje
- Identifikuje se statistickými testy (Grubbs, Dixon) a vyřadí se

---

### Chyba metody

Chyba metody vzniká z **principu samotné měřicí metody** – ne z nepřesnosti přístroje.

**Příklady chyb metody:**

#### Chyba voltmetru při měření napětí
Voltmetr s konečnou vstupní impedancí R_V zatěžuje měřený obvod:

```
Skutečné napětí: U
Po připojení voltmetru: U_m = U × R_V / (R + R_V)
Chyba: δU = –R / (R + R_V)
```
→ Chyba klesá s rostoucím R_V (proto chceme vysokou vstupní impedanci voltmetru)

#### Chyba ampérmetru při měření proudu
Ampérmetr s konečnou impedancí R_A způsobuje pokles napětí na obvodu.

#### Korekce chyby metody
- Matematická korekce na základě znalosti parametrů přístroje
- Použití přístroje s nižší chybou (vyšší R_V, nižší R_A)
- **Extrapolace na nulové zatížení**

---

## Výpočet chyb

### Absolutní chyba
**Δx = x_naměřené – x_skutečné**

### Relativní chyba
**δx = Δx / x_skutečné × 100 %**

### Chyba analogových přístrojů
- Vyjádřena jako **třída přesnosti** = max. absolutní chyba / rozsah × 100 %
- Příklad: třída 1,5 na rozsahu 100 V → max. chyba = ±1,5 V
- **Chyba je konstantní v celém rozsahu** → na malých hodnotách škály je relativní chyba větší!

### Chyba digitálních přístrojů
- Vyjádřena jako **% z odečtu + počet nejméně významných číslic (LSB)**
- Příklad: ±(0,5 % + 2 digits) → závisí na naměřené hodnotě

---

## Ověření a kalibrace – korekční křivka

### Ověření (verifikace)
Porovnání přístroje s etalonem → výsledek: **vyhovuje / nevyhovuje** (binární).

### Kalibrace
Porovnání přístroje s etalonem ve více bodech → výsledkem je **korekční křivka** nebo tabulka korekcí.

**Korekce = hodnota etalonu – naměřená hodnota přístroje**

Přístroj se kalibruje v N bodech → proloží se korekční křivkou → při měření se přičte korekce.

---

## Nejistota měření (dle GUM – Guide to the Expression of Uncertainty in Measurement)

Nejistota měření nahrazuje pojem „chyba" – vyjadřuje **interval hodnot, v němž se s danou pravděpodobností nachází skutečná hodnota**.

### Složky nejistoty

#### Nejistota typu A (u_A)
Stanovena **statistickými metodami** z opakovaných měření:

**u_A = s / √n**

kde s = výběrová směrodatná odchylka, n = počet měření.

#### Nejistota typu B (u_B)
Stanovena **jinými metodami** (kalibrační list, specifikace výrobce, literatura, fyzikální úvaha):

**u_B = a / √3** (pro rovnoměrné rozdělení, a = polorozpětí)
**u_B = a / 2** (pro normální rozdělení – 95% interval)

#### Kombinovaná nejistota (u_c)
**u_c = √(u_A² + u_B²)** (pro nezávislé příspěvky)

#### Rozšířená nejistota (U)
**U = k × u_c**

kde k = koeficient rozšíření (typicky k = 2 pro 95% pravděpodobnost).

**Výsledek měření se uvádí jako: x ± U (jednotka)**

---

### Zápis výsledku měření

```
Příklad:
Naměřená hodnota: 5,234 V
Kombinovaná nejistota: u_c = 0,008 V
Rozšířená nejistota (k=2): U = 0,016 V

Výsledek: U = (5,234 ± 0,016) V  (k = 2, P ≈ 95 %)
```

---

# Otázka 76: Měření výkonu

## Výkon ve stejnosměrném obvodu

**P = U × I = I² × R = U² / R** [W]

- Přímá metoda: wattmetr
- Nepřímá metoda: voltmetr + ampérmetr → P = U × I
  - Chyba metody: proud ampérmetrem nebo napětí voltmetrem zvyšuje odečtenou hodnotu

---

## Výkon v jednofázovém střídavém obvodu

### Druhy výkonů

| Výkon | Symbol | Jednotka | Definice |
|---|---|---|---|
| **Činný výkon** | P | W (watt) | Střední hodnota okamžitého výkonu – skutečná spotřeba |
| **Jalový výkon** | Q | VAr | Výkon akumulovaný a vracený reaktancemi (L, C) |
| **Zdánlivý výkon** | S | VA | S = U × I (bez ohledu na fázový posun) |
| **Komplexní výkon** | S̃ | VA | S̃ = P + jQ |

### Vztahy

**P = U × I × cos(φ)** [W]
**Q = U × I × sin(φ)** [VAr]
**S = U × I** [VA]
**S² = P² + Q²**

### Účiník (Power Factor)

**PF = cos(φ) = P / S**

- Ideální: cos(φ) = 1 (čistě odporová zátěž, P = S)
- Induktivní zátěž: φ > 0, cos(φ) < 1, Q > 0
- Kapacitní zátěž: φ < 0, cos(φ) < 1, Q < 0

---

## Výkon v trojfázovém obvodu

### Symetrická trojfázová soustava
**P = 3 × U_f × I_f × cos(φ) = √3 × U_L × I_L × cos(φ)**

kde U_f = fázové napětí, U_L = sdružené (linkové) napětí, I_f = I_L pro zapojení do hvězdy.

### Metody měření trojfázového výkonu

| Metoda | Počet wattmetrů | Podmínky |
|---|---|---|
| **Aronova metoda** | 2 wattmetry | Trojvodičová soustava (3 vodiče, bez neutrály) |
| **3 wattmetry** | 3 wattmetry | Čtyřvodičová soustava (3 fáze + nulový vodič) |
| **1 wattmetr** | 1 wattmetr | Pouze symetrická zátěž: P_celk = 3 × P_1 |

---

## Měření účiníku a fázového posunu

### Fázoměr
- Měří fázový úhel φ mezi napětím a proudem
- Princip: nulový detektor, analogový fázoměr nebo digitální (zero-crossing detekce)

### Účiníkový článek
- Výpočet z P a S: **cos(φ) = P / S**

### Cosφ – meter (analogový)
- Logometrický přístroj – poměr dvou proudů

---

## Přímý a nepřímý způsob měření výkonu

### Přímý způsob – wattmetr
- **Elektrodynamický wattmetr** – proudová cívka × napěťová cívka → točivý moment ~ P
- **Digitální wattmetr** – vzorkuje u(t) a i(t), vypočítá P = (1/T)∫u(t)×i(t)dt

### Nepřímý způsob
- Voltmetr + ampérmetr → P = U × I × cos(φ) (nutné znát nebo změřit φ)
- **Chyba metody**: viz výše (ampérmetr nebo voltmetr v různých polohách)

---

## Měření výkonu vzorkováním

Moderní digitální wattmetry vzorkují okamžité hodnoty napětí a proudu:

**P = (1/N) × Σ u(k) × i(k)**

kde N = počet vzorků za periodu.

### Požadavky na vzorkování výkonu
- Vzorkovací frekvence musí splňovat **Nyquistův teorém** pro nejvyšší harmonickou složku
- Synchronizace s periodou signálu pro přesný výpočet
- Dostatečný dynamický rozsah ADC (zejména při měření se zkreslením)

---

## Měření fázového posunu

### Metoda nulového detektoru
- Porovnání fází pomocí OZ komparátoru → detekce průchodu nulou
- Fázový posun = časový interval mezi průchody nulou × 360°/T

### Lissajousovy křivky (osciloskop)
- X vstup: napětí, Y vstup: proud (přes bočník)
- Eliptický tvar → φ = arcsin(b/a) kde b = průsečík s Y-osou, a = amplituda Y
- Viz také **Otázka 87** (Měření na elektronických přístrojích)

---

# Otázka 77: Konverze měřicího signálu – vzorkování, kvantování, A/D převodníky

## Digitalizace analogového signálu

Proces převodu spojitého analogového signálu na diskrétní číslicový:

```
Analogový signál
        ↓
Vzorkování (sampling) – diskrétní v čase
        ↓
Kvantování (quantization) – diskrétní v amplitudě
        ↓
Kódování (coding) – binární číslo
        ↓
Digitální signál
```

---

## Vzorkování (Sampling)

### Vzorkovací teorém (Nyquist-Shannon)
> Aby byl signál rekonstruovatelný bez aliasingu, musí být vzorkovací frekvence **alespoň dvojnásobkem nejvyšší frekvence** obsažené ve vzorkovaném signálu.

**f_s ≥ 2 × f_max** (Nyquistův limit)

**f_s / 2 = f_Nyquist** – Nyquistova frekvence (maximální rekonstruovatelná frekvence)

### Aliasing
Pokud f_s < 2 × f_max → **aliasing** = zdánlivé frekvence v digitálním signálu, které v původním signálu nebyly.

**Prevence aliasingu:**
- Anti-aliasing filtr (dolní propust) **před** vzorkováním → omezí signál na f < f_s/2
- Zvýšení vzorkovací frekvence (oversampling)

### Vzorkovací frekvence v medicíně

| Signál | f_max | Doporučená f_s |
|---|---|---|
| EKG (monitorování) | 40 Hz | ≥ 250 Hz |
| EKG (diagnostické) | 150 Hz | ≥ 500 Hz |
| EEG | 100 Hz | ≥ 256 Hz |
| EMG | 5 000 Hz | ≥ 10 000 Hz |
| Audio | 20 000 Hz | 44 100 Hz (CD) |

---

## Kvantování (Quantization)

Přiřazení spojité amplitudy diskrétní hodnotě z konečného počtu úrovní.

### Kvantizační krok

**Δ = U_FSR / (2^N – 1) ≈ U_FSR / 2^N**

kde U_FSR = Full Scale Range (rozsah ADC), N = počet bitů.

### Kvantizační chyba
- Maximální chyba: **±Δ/2** (zaokrouhlení)
- **Kvantizační šum**: SNR ≈ 6,02 × N + 1,76 dB (pro sinusový signál)
- Každý přidaný bit zvyšuje SNR o ~6 dB

### Příklady rozlišení ADC

| Počet bitů | Počet úrovní | SNR (teoretické) | Použití |
|---|---|---|---|
| 8 bit | 256 | 50 dB | Audio nízká kvalita, jednoduché senzory |
| 12 bit | 4 096 | 74 dB | Průmyslové senzory, ECG monitorování |
| 16 bit | 65 536 | 98 dB | Audio (CD), přesné biomedicínské měření |
| 24 bit | 16 777 216 | 146 dB | Laboratorní přístroje, EEG |

---

## Principy A/D převodníků

### 1. Flash ADC (paralelní)
- **2^N – 1 komparátorů** porovnává vstup s referenčními napětími současně
- **Nejrychlejší** – konverze za jeden takt
- Nevýhody: exponenciální nárůst komparátorů s N → jen do ~8 bit
- Použití: osciloskopy, radar, vysokorychlostní sběr dat

### 2. Successive Approximation ADC (SAR)
- **Binární vyhledávání** – postupné přibližování od MSB k LSB
- N kroků pro N-bitový převod
- **Kompromis rychlosti a přesnosti** – nejběžnější typ
- Použití: mikrořadiče, EKG, průmyslové senzory (12–16 bit, stovky kSPS)

### 3. Sigma-Delta (ΔΣ) ADC
- **Oversampling** (mnohem vyšší f_s než Nyquist) + **noise shaping** + **decimační filtr**
- Velmi vysoké rozlišení (16–32 bit)
- **Pomalý** – vhodný pro DC a nízkofrekvenční signály
- Použití: audio, laboratorní přístroje, EEG, váhy, senzory teploty

### 4. Rampový ADC (single-slope, dual-slope)
- **Single-slope**: kondenzátor se nabíjí konstantním proudem, čítač měří čas do dosažení U_in
- **Dual-slope**: přesnější – kompenzace teplotního driftu
- Pomalý, ale přesný
- Použití: digitální multimetry

### 5. Pipeline ADC
- Série rychlých hrubých ADC + DAC + korekce
- Vysoká rychlost i rozlišení (12–16 bit, stovky MSPS)
- Použití: osciloskopy, komunikace

---

## Zpětná rekonstrukce signálu (D/A převod)

Po digitálním zpracování → D/A převodník rekonstruuje analogový signál.

### Princip DAC
- N-bitové binární číslo → vážená suma napětí nebo proudů
- **R-2R sítě** – nejčastější implementace
- **Oversampling + interpolační filtr** – pro audio kvalitu

### Artefakty rekonstrukce
- **Vzorkování a udržování (sample & hold)** → obdélníkový charakter → sinc funkce ve spektru
- **Rekonstrukční filtr (dolní propust)** po DAC → odstranění obrazů spektra

---

## Přivedení digitalizovaného signálu do počítače

### Rozhraní

| Rozhraní | Rychlost | Použití |
|---|---|---|
| **USB** | 12 Mbit/s – 10 Gbit/s | Měřicí přístroje, EKG, EEG |
| **Ethernet / LAN** | 100 Mbit/s – 10 Gbit/s | Nemocniční přístroje, monitoring |
| **PCIe / PCI** | Gbit/s | Interní DAQ karty |
| **SPI / I²C** | Mbit/s | Senzory k mikrokontroléru |
| **Bluetooth / Wi-Fi** | Desítky Mbit/s | Wearables, mobilní monitoring |

### DAQ (Data Acquisition) systémy
- Hardwarové karty nebo moduly (National Instruments, Measurement Computing)
- Software: **LabVIEW, MATLAB DAQ Toolbox**

---

# Otázka 78: Měření pasivních elektrických prvků

## Obecné principy

Měření R, L, C závisí na:
- **Velikosti hodnoty** → volba metody a přístroje
- **Požadované přesnosti**
- **Měřicí frekvenci** – pasivní prvky mají frekvenčně závislé vlastnosti (parazitní L, C, R)
- **Pracovním bodu** – některé prvky jsou nelineární (ferity saturují, kondenzátory mají napěťovou závislost)

---

## Měření odporu (R)

### Ohmova metoda (voltmetr-ampérmetr)

**R = U / I**

Dvě varianty zapojení:

**Ampérmetr vně (pro velká R):**
```
I = I_R + I_V (malá chyba pro R >> R_V)
```

**Ampérmetr uvnitř (pro malá R):**
```
U = U_R + U_A (malá chyba pro R << R_A)
```

### Wheatstoneův můstek (pro střední R – 1 Ω až 1 MΩ)
Viz **Otázka 85** – podrobně.

### Kelvinův (čtyřsvodový) můstek (pro malá R < 1 Ω)
- Eliminuje vliv odporů přívodních vodičů
- Čtyři svorky: dvě pro proud (I+, I–), dvě pro napětí (U+, U–)
- Použití: měření odporů vodičů, kontaktů, zemnicích svorek, PE vodičů ZP (BTK!)

### RLC meter / LCR meter (impediancemetr)
- Měří R, L, C, Z, Q, D na nastavitelné frekvenci
- Vhodný pro automatické měření v širokém rozsahu hodnot
- Princip: generátor + měření napětí a proudu + výpočet

---

## Měření kapacity (C)

### LCR metr
- Nejběžnější metoda – automatické měření
- Měří sériový nebo paralelní model (C_s + R_s nebo C_p ‖ R_p)

### Můstkové metody (pro přesné měření)
- **Sohestův (Schering) můstek** – pro měření kapacity a dielektrických ztrát
- Vyvažuje se pro nulový signál → přesné odečtení C a D (ztrátového činitele)

### Frekvenční závislost kondenzátorů
- Keramické (X7R, Y5V): kapacita se mění s napětím a teplotou → měřit na pracovním napětí
- Elektrolytické: velká ESR → měřit na nízké frekvenci (100–1000 Hz)
- Fóliové: nejstabilnější

---

## Měření indukčnosti (L)

### LCR metr
- Automatické měření na zvolené frekvenci
- Sériový model: L_s + R_s (pro malé L s odporem vinutí)

### Rezonanční metoda
- Připojit kondenzátor C o známé hodnotě → nalézt rezonanční frekvenci f₀
- **L = 1 / (4π² × f₀² × C)**

### Frekvenční závislost cívek
- Feritová jádra: permeabilita klesá s frekvencí → L se mění
- Saturace jádra: při velkém proudu L prudce klesá → měřit na pracovním proudu

---

## Náhradní elektrické schéma

### Reálný kondenzátor
```
C_p (paralelní model): C_ideal ‖ R_leak (izolační odpor)
C_s (sériový model): C_ideal + R_ESR + L_ESL
```

- **ESR** (Equivalent Series Resistance) – ztrátový odpor
- **ESL** (Equivalent Series Inductance) – parazitní indukčnost (vodivé cesty, nožičky)
- Nad SRF (Self-Resonant Frequency) se chová jako induktor

### Reálná cívka
```
L_s (sériový model): L_ideal + R_DC (odpor vinutí)
L_p (paralelní model): L_ideal ‖ C_winding (mezizávitová kapacita)
```

- **Q = ωL / R_DC** – jakost cívky
- Nad SRF se chová jako kondenzátor

---

## Přehled metod měření pasivních prvků

| Veličina | Rozsah | Doporučená metoda |
|---|---|---|
| R malé (< 1 Ω) | Kelvinův 4-svodový | Přesné, eliminace vlivu přívodů |
| R střední (1 Ω – 1 MΩ) | Wheatstoneův můstek, LCR metr | Standardní, přesné |
| R velké (> 1 MΩ) | Voltmetr-ampérmetr, megaohmmetr | Izolační odpory |
| C (pF – mF) | LCR metr, Scheringův můstek | Automatické nebo přesné |
| L (nH – H) | LCR metr, rezonanční metoda | Automatické nebo přesné |
| Z (impedance) | Impedanční analyzátor | Frekvenční charakteristika |

---

*Konec bloku – Elektrická měření | Otázky 75–78*
