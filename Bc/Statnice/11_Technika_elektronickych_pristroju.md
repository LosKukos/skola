# Technika elektronických přístrojů
### Státnicová příprava – Biomedicínská technika 2026

---

# Otázka 79: Konstrukce zdroje ss napětí pro bioelektroniku

## Požadavky na napájecí zdroj v bioelektronice

Napájecí zdroje pro biomedicínské přístroje mají specifické požadavky oproti průmyslové elektronice:

| Požadavek | Důvod |
|---|---|
| **Galvanické oddělení od sítě** | Bezpečnost pacienta – eliminace rizika mikrošoku |
| **Nízký šum a zvlnění** | Biologické signály jsou μV–mV – šum zdroje nesmí maskovat signál |
| **Stabilita výstupního napětí** | Přesná měření vyžadují stabilní referenční napájení |
| **Nízký unikající proud** | Dle IEC 60601-1 – max. 10 μA pro CF typ |
| **Odolnost vůči EMI** | Přístroj pracuje v prostředí s MRI, ESU, defibrilátory |
| **Symetrické napájení** | OZ a přístrojové zesilovače vyžadují ±napájení (např. ±15 V) |

---

## Síťový transformátor

Základní prvek lineárního zdroje – galvanické oddělení od sítě 230 V AC.

### Typy transformátorů

| Typ | Vlastnosti | Použití |
|---|---|---|
| **EI (laminovaný)** | Velký, těžký, 50 Hz, levný | Laboratorní zdroje, starší přístroje |
| **Toroidní** | Menší, nižší elektromagnetické vyzařování, vyšší účinnost | Kvalitní audio, biomedicína |
| **Bezpečnostní izolační** | Splňuje IEC 61558, zvýšená izolace | ZP třídy II, medicínské IT systémy |

### Bezpečnostní parametry transformátoru pro ZP
- **Základní izolace** – jedna vrstva izolace mezi primárem a sekundárem
- **Zesílená izolace** – ekvivalent dvojité izolace v jedné vrstvě
- **Průrazné napětí** – min. 1 500–4 000 V AC dle třídy izolace
- **Kapacita mezi vinutími** – parazitní kapacita přenáší síťové rušení → min. kapacita nebo stínění

### Výpočet transformátoru
- Převodní poměr: n = U₂/U₁ = N₂/N₁
- Výstupní napětí po usměrnění: U_DC ≈ 1,41 × U₂(RMS) – U_dioda

---

## Spínaný zdroj (SMPS) v bioelektronice

Moderní biomedicínské přístroje stále více používají SMPS pro jeho kompaktnost a účinnost.

### Výhody SMPS pro biomedicínu
- Malé rozměry a hmotnost → přenosné přístroje
- Vysoká účinnost (85–95 %) → méně tepla
- Galvanická izolace pomocí VF transformátoru

### Nevýhody a řešení pro biomedicínu
- **EMI rušení** – spínání na 20–500 kHz generuje harmonické → nutné EMI filtry, stínění
- **Šum na výstupu** – spínací frekvence proniká na výstup → lineární post-regulátor (LDO) za SMPS
- **Parazitní kapacita** transformátoru → přenos HF rušení → Y kondenzátory na vstupu/výstupu

### Typická topologie pro ZP: **Flyback konvertor**
- Galvanicky oddělený
- Výkon 5–150 W
- Primár + feritový transformátor + sekundár + usměrnění + filtrace
- Řídící IC: TOPSwitch, NCP1200, UCx84x

---

## Násobič napětí

Pro aplikace vyžadující vysoké napětí z nízkého napájení (baterie → HV pro piezo senzory, elektrostimulátory).

### Villardův zdvojovač napětí
```
Vstup AC → C₁ → D₁ → C₂ → Výstup DC ≈ 2 × U_peak
                  D₂ ↓
                     GND
```
- Výstup: přibližně 2× vstupní amplituda
- Malý výkon, jednoduché

### Cockcroft-Waltonův generátor
- Kaskáda diod a kondenzátorů
- Výstup: N × 2 × U_peak (pro N stupňů)
- Použití: RTG trubice HV napájení, ionizátory, piezoelektrické buzení

---

## Lineární regulátor (LDO) pro bioelektroniku

**LDO (Low Dropout Regulator)** – lineární regulátor s velmi malým minimálním diferenčním napětím (< 0,3 V).

### Výhody LDO v bioelektronice
- **Velmi nízký šum** – žádné spínání → vhodný jako finální regulátor za SMPS
- **Rychlá odezva na změny zátěže**
- Jednoduchý obvod, malé rozměry (SOT-23)

### Typické obvody
- **LM1117, AMS1117** – 3,3 V nebo 5 V, 800 mA
- **MAX8881, TPS7A47** – ultra-nízký šum pro přesné ADC a OZ

---

# Otázka 80: Zesilovače pro bioelektroniku

## Specifické požadavky zesilovačů v biomedicíně

| Požadavek | Hodnota / Popis |
|---|---|
| **Vysoký vstupní odpor** | > 10 MΩ (nesmí zatěžovat elektrody) |
| **Vysoký CMRR** | > 80 dB (potlačení síťového rušení 50 Hz) |
| **Nízký šum** | < 1 μVrms (pro EEG) |
| **Nízký offset** | Stabilní DC pracovní bod |
| **Galvanická izolace** | U přístrojů s přímým kontaktem se srdcem (CF) |
| **Frekvenční rozsah** | Přizpůsoben signálu (EKG: 0,05–150 Hz, EMG: 10–5 000 Hz) |

---

## Zapojení zesilovačů s OZ

### Invertující zesilovač
**A_v = – R_f / R_in**

- Vstupní impedance = R_in → pro bioelektroniku příliš nízká (přetěžuje elektrody)
- Inverze fáze

### Neinvertující zesilovač
**A_v = 1 + R_f / R₁**

- Vstupní impedance ≈ Z_in(OZ) = velmi vysoká (GΩ)
- Bez inverze fáze
- Vhodný pro první stupeň předzesilovače

### Problém vstupní impedance

Impedance elektrody–kůže: typicky **1–100 kΩ** (závisí na frekvenci, přípravě kůže, gelu). Vstupní impedance zesilovače musí být >> impedance elektrody, aby nedocházelo k:
- Napěťovému dělení (oslabení signálu)
- Nesymetrii impedancí → zhoršení CMRR

---

## Přístrojový zesilovač (Instrumentation Amplifier – InAmp)

Přístrojový zesilovač je **specializovaný diferenční zesilovač** s vynikajícími vlastnostmi pro biomedicínské aplikace.

### Tříčipová architektura (klasická)

```
           R_gain
    ┌──────┤├──────┐
    │               │
U+ ─(OZ₁)──────────────────────┐
                                (OZ₃)── U_out
U– ─(OZ₂)──────────────────────┘
    │               │
    └───────────────┘
         R₁  R₂  R₃  R₄ (diferenční stupeň)
```

**Zesílení**: **A_v = (1 + 2R/R_gain)**

### Klíčové vlastnosti InAmp
- **Velmi vysoký vstupní odpor** (GΩ – oba vstupy jsou vstupy OZ)
- **Vysoký CMRR** (100–130 dB)
- **Nastavitelné zesílení** jedním externím rezistorem R_gain
- **Nízký offset a drift**

### Příklady integrovaných InAmp
- **INA128, INA333** (Texas Instruments) – obecné použití, EKG, EMG
- **AD8221, AD8220** (Analog Devices) – nízký šum
- **INA116** – extrémně vysoký vstupní odpor (FET vstup)

---

## Vliv vstupní impedance na CMRR

CMRR celého systému (elektroda + zesilovač) závisí na **symetrii impedancí elektrod**:

**CMRR_syst ≈ CMRR_amp / (1 + Z_elekt / Z_in)**

Pokud Z_elekt << Z_in → CMRR_syst ≈ CMRR_amp (dobré)
Pokud Z_elekt ~ Z_in → CMRR_syst << CMRR_amp (problém!)

→ Proto je nutná **příprava kůže** (broušení, odmašťování gel) pro snížení impedance elektrod a **DRL obvod (Driven Right Leg)** pro aktivní potlačení CM napětí.

### DRL (Driven Right Leg) obvod
- Invertovaná souhlasná složka je přivedena zpět na tělo pacienta přes DRL elektrodu
- Aktivně snižuje souhlasné napětí → zvyšuje efektivní CMRR systému
- Standard v 12svodovém EKG

---

# Otázka 81: Galvanické oddělení biosignálu

## Proč galvanické oddělení?

Galvanické oddělení = **přerušení přímé elektrické cesty** mezi pacientem a zemí přístroje / sítí.

### Důvody galvanického oddělení v biomedicíně
1. **Bezpečnost pacienta** – eliminace rizika mikrošoku (< 10 μA pro CF typ)
2. **Ochrana před defibrilačním výbojem** – přístroj musí přežít výboj a obnovit funkci
3. **Potlačení souhlasného rušení** – přerušení zemní smyčky
4. **Oddělení různých napájecích domén** – primár (230 V) vs. sekundár (pacientská část)

---

## Galvanicky izolované zesilovače

### Izolační zesilovač s transformátorem (modulační přenos)

```
Biosignál → Modulátor → Transformátor → Demodulátor → Výstup
              (AM/FM)      (izolace)      (demodulace)
```

**Princip:**
1. Biosignál moduluje nosnou frekvenci (100 kHz–1 MHz)
2. Modulovaný signál se přenese přes izolační transformátor (galvanická bariéra)
3. Na výstupní straně se demoduluje zpět na původní signál

**Typy modulace:**
- **AM (Amplitudová modulace)** – jednodušší, náchylná na rušení
- **FM (Frekvenční modulace)** – odolnější vůči amplitudovému rušení

### Příklady integrovaných izolačních zesilovačů
- **ISO124, ISO122** (Texas Instruments) – kapacitní izolace, ±10 V, BW 50 kHz
- **AD202, AD204** (Analog Devices) – transformátorová izolace, přesné

---

## Optron (Optokopléř)

Optron přenáší signál světlem → galvanická izolace.

### Princip optronu
```
Vstupní signál → LED → [vzduch/pryskyřice] → Fototransistor/fotodioda → Výstupní signál
     (elektrický)   (světlo)                   (světlo → elektrický)
```

### Vlastnosti optronu
- **CTR (Current Transfer Ratio)** – poměr výstupního proudu k vstupnímu (I_C / I_F)
- **Nelinearita** – LED má nelineární V-I charakteristiku → nutná linearizace nebo zpětná vazba
- **Rychlost** – závisí na typu (standardní: stovky kHz; rychlé: desítky MHz)
- **Izolační napětí** – typicky 2 500–5 000 V

### Lineární optron
Pro přesný přenos analogových biosignálů – nutná zpětná vazba pro linearizaci (viz IL300, HCNR200):
```
Vstup → LED₁ → Fotodioda₁ (zpětnovazební) → OZ → LED₁ (regulace proudu)
                Fotodioda₂ → výstupní signál
```

### Používané modulace při optickém přenosu
- **PWM (Pulse Width Modulation)** – signál → PWM → optron → demodulace
- **Delta-sigma modulace** – 1-bitový přenos s oversampling
- **FM** – frekvenční modulace → méně citlivá na nelinearitu LED

---

## Kapacitní izolace

Přenos signálu přes izolační kondenzátor (malá C, vysoké dielektrikum):
- **Digitální izolátory** (ISO7241, Si8421) – přenos digitálních signálů přes SiO₂
- Šířka pásma: desítky Mbit/s
- Použití: SPI, I²C, UART izolace pro komunikaci s pacientskou částí

---

# Otázka 82: Aktivní a pasivní frekvenční filtry, filtr notch

## Základní charakteristiky frekvenčních filtrů

### Typy filtrů podle frekvenční propustnosti

| Typ | Propouští | Tlumí | Použití v biomedicíně |
|---|---|---|---|
| **Dolní propust (LP)** | f < f_c | f > f_c | Anti-aliasing, vyhlazení signálu |
| **Horní propust (HP)** | f > f_c | f < f_c | Odstranění DC offsetu, pohybových artefaktů |
| **Pásmová propust (BP)** | f₁ < f < f₂ | ostatní | Selekce EKG, EEG pásem |
| **Pásmová zádrž (BS/Notch)** | ostatní | f₁ < f < f₂ | Potlačení síťového rušení 50 Hz |

### Základní parametry

| Parametr | Definice |
|---|---|
| **Mezní frekvence f_c** | Frekvence poklesu o 3 dB (–3 dB bod) |
| **Sklon útlumu** | dB/dekáda nebo dB/oktáva (1. řád: 20 dB/dek, 2. řád: 40 dB/dek) |
| **Řád filtru** | Počet reaktančních prvků → určuje sklon a složitost |
| **Zvlnění propustného pásma** | Nerovnoměrnost přenosu v propustném pásmu |
| **Skupinové zpoždění** | Zpoždění různých frekvencí → deformace tvaru signálu |

---

## Pasivní filtry (RC, LC)

Pasivní filtry obsahují pouze R, L, C – bez aktivních prvků.

### RC dolní propust 1. řádu
```
U_in──R──┬──U_out
         C
         ┴ GND
```
**f_c = 1 / (2πRC)**
**|H(jω)| = 1 / √(1 + (f/f_c)²)**

### LC filtry
- Strmější útlum bez ztrátového výkonu
- Induktory jsou drahé a velké → v biomedicíně méně časté
- Vhodné pro výkonové aplikace (SMPS výstupní filtry)

**Nevýhody pasivních filtrů:**
- Útlum signálu i v propustném pásmu (dělič napětí se zátěží)
- Nemohou zesilovat signál
- Induktory jsou citlivé na rušení

---

## Aktivní filtry (s OZ)

Aktivní filtry kombinují R, C a OZ – **mohou zesilovat** a mají **nízký výstupní odpor**.

### Aproximace frekvenční charakteristiky

| Aproximace | Vlastnosti | Použití |
|---|---|---|
| **Butterworth** | Maximálně plochá v propustném pásmu, bez zvlnění | Univerzální, anti-aliasing |
| **Chebyshev** | Strmější útlum, zvlnění v propustném pásmu | Kde je důležitý sklon útlumu |
| **Bessel** | Lineární fázová charakteristika (konstantní skupinové zpoždění) | EKG, EEG – zachování tvaru signálu |
| **Elliptic (Cauer)** | Nejstrmější útlum, zvlnění v obou pásmech | Antialiasing s min. řádem |

> **V biomedicíně je Besselova aproximace preferovaná** – zachovává tvar signálu (konstantní skupinové zpoždění), nezkresluje tvar vln EKG nebo EEG.

### Sallen-Key (VCVS) topologie – 2. řád LP

```
U_in──R₁──R₂──┬──(+OZ)──U_out
              C₂      │
              ┴      C₁──┘
             GND
```

**f_c = 1 / (2π√(R₁R₂C₁C₂))**

Jednoduchá, stabilní topologie pro 2. řád.

### Multiple Feedback (MFB) – 2. řád LP/BP

Alternativní topologie s inverting OZ – kompaktnější, lepší výkonový šum.

---

## Filtr notch (pásmová zádrž 50/60 Hz)

### Proč notch filtr v bioelektronice?

Síťové rušení **50 Hz** (Evropa) nebo **60 Hz** (USA/Kanada) se indukuje do biosignálů. Notch filtr ho odstraní s minimálním ovlivněním okolních frekvencí.

### Twin-T notch filtr

Klasická RC topologie pro notch filtr:

```
                R       R
U_in ──┬───R───┬───C───┬─── U_out
       C       C       R/2
       ┴       ┴       ┴ GND
```

**f_notch = 1 / (2πRC)**

- Pasivní verze: hluboká zádrž, ale nízká selectivita (širší zádrž)
- Aktivní verze (s OZ): nastavitelná hloubka a šířka zádrže

### Aktivní notch (state-variable)
Přesný notch filtr s nastavitelným Q a hloubkou zádrže.

### Číslicový notch filtr (IIR)
V moderních digitálních přístrojích (EKG, EEG monitory) se notch filtr implementuje digitálně:
- **IIR Notch**: přesná frekvence, ostrý notch
- **Adaptivní notch**: sleduje kolísající frekvenci sítě (49–51 Hz)

### Nevýhody notch filtru pro EKG
- Filtr 50 Hz může deformovat **vlnu T** (obsahuje složky kolem 50 Hz)
- Proto se notch v diagnostickém EKG **nedoporučuje** – preferuje se CMRR > 100 dB a stínění

---

# Otázka 83: Převod biosignálu do číslicové podoby

## Přehled A/D a D/A převodníků pro biosignály

> Viz také **Otázka 77** (Konverze měřicího signálu) – základní teorie vzorkování a ADC typů. Zde rozšíření o specifika bioelektroniky.

---

## Požadavky ADC pro biosignály

| Parametr | EKG | EEG | EMG | Poznámka |
|---|---|---|---|---|
| Rozlišení | 12–16 bit | 16–24 bit | 12–16 bit | Vyšší → menší kvantizační šum |
| Vzorkovací frekvence | 500–1 000 Hz | 256–2 048 Hz | 10–50 kHz | Dle Nyquistova teorému |
| Vstupní rozsah | ±5 mV | ±500 μV | ±5 mV | Malé signály → nutný předzesilovač |
| Šum ADC | < 1 μVrms | < 0,1 μVrms | < 5 μVrms | Šum ADC musí být << šum signálu |
| Počet kanálů | 1–12 | 8–256 | 1–64 | Multiplexované nebo paralelní |

---

## Hlavní parametry ADC

### Statické parametry

| Parametr | Zkratka | Definice |
|---|---|---|
| **Rozlišení** | N | Počet bitů → počet kvantizačních úrovní 2^N |
| **LSB** | LSB | Nejmenší bit = U_FSR / 2^N |
| **Integrální nelinearita** | INL | Max. odchylka skutečné převodní charakteristiky od ideální přímky |
| **Diferenciální nelinearita** | DNL | Odchylka šířky kvantizačního stupně od ideálního LSB |
| **Offset error** | – | Posun nulového bodu převodníku |
| **Gain error** | – | Chyba sklonu převodní charakteristiky |

### Dynamické parametry

| Parametr | Zkratka | Definice |
|---|---|---|
| **Efektivní počet bitů** | ENOB | Skutečné rozlišení s uvažováním šumu ENOB = (SINAD – 1,76) / 6,02 |
| **SINAD** | – | Signal-to-Noise and Distortion Ratio |
| **SFDR** | – | Spurious Free Dynamic Range – vzdálenost signálu od největšího parazitního tónu |
| **THD** | – | Total Harmonic Distortion |

---

## ADC pro biomedicínské systémy

### Sigma-Delta ADC – dominantní pro biosignály

**Proč Sigma-Delta pro biosignály?**
- Biosignály jsou **nízkofrekvenční** (DC – 5 kHz) → Sigma-Delta je ideální
- Vysoké rozlišení (16–24 bit)
- Integrovaný **digitální filtr** (decimační FIR) – anti-aliasing bez externích komponent
- Nízký šum

**Princip Sigma-Delta:**
```
Vstup → Σ (sčítač) → Δ (integrátor) → Komparátor (1-bit ADC) → Výstup 1-bit
           ↑                                      |
           └──────────── 1-bit DAC ←──────────────┘
                    (záporná zpětná vazba)

Decimační filtr (FIR) → N-bitový výstup s f_s/M (M = decimační faktor)
```

### Integrované AFE (Analog Front-End) pro biosignály

Moderní řešení integruje předzesilovač + filtr + ADC do jednoho čipu:

| Obvod | Výrobce | Aplikace |
|---|---|---|
| **ADS1298** | Texas Instruments | 8-kanálový 24-bit ADC pro EKG |
| **ADS1299** | Texas Instruments | 8-kanálový 24-bit ADC pro EEG |
| **MAX30003** | Maxim/Analog Devices | 1-kanálový ECG AFE |
| **AD8232** | Analog Devices | Jednoduchý ECG frontend |
| **ADAS1000** | Analog Devices | 5-kanálový EKG AFE |

---

## D/A převodník (DAC)

DAC převádí digitální číslo na analogové napětí nebo proud.

### Princip R-2R sítě

```
MSB ──2R──┬──2R──┬──2R──┬── LSB
          R      R      R
          ┴      ┴      ┴ GND
              → U_out (součet vážených proudů)
```

- Každý bit přispívá half napětí předchozího bitu
- Přesnost závisí na přesnosti poměru R a 2R

### Parametry DAC

| Parametr | Definice |
|---|---|
| **Rozlišení** | Počet bitů → nejmenší krok = U_FSR / 2^N |
| **Settling time** | Čas ustálení na novou hodnotu |
| **Glitch** | Napěťový špičat při přechodu hodnot (MSB přechod) |
| **DNL, INL** | Stejné jako ADC |

### Použití DAC v bioelektronice
- Terapeutická stimulace (kardiostimulátor, FES, TENS)
- Kalibrační signály pro testování zesilovačů
- Referenční napěťové zdroje
- Zpětnovazební systémy (servo, PID)

---

# Otázka 84: Logické obvody v bioelektronice

## Digitální logika – základy

### Logické úrovně
- **TTL** (Transistor-Transistor Logic): LOG 0 = 0–0,8 V, LOG 1 = 2–5 V, napájení 5 V
- **CMOS**: LOG 0 = 0 – 0,3×U_DD, LOG 1 = 0,7×U_DD – U_DD, napájení 1,8–5 V
- **LVTTL/LVCMOS**: 3,3 V nebo 1,8 V – moderní FPGA, mikrokontroléry

---

## Kombinační logické obvody

Výstup závisí pouze na **aktuálním stavu vstupů** – bez paměti.

### Základní logické brány

| Brána | Symbol | Funkce | Pravdivostní tabulka |
|---|---|---|---|
| **AND** | & | Y = A·B | 0·0=0, 0·1=0, 1·0=0, 1·1=1 |
| **OR** | ≥1 | Y = A+B | 0+0=0, 0+1=1, 1+0=1, 1+1=1 |
| **NOT** | 1 | Y = Ā | 0→1, 1→0 |
| **NAND** | &̄ | Y = NOT(A·B) | Inverze AND |
| **NOR** | ≥1̄ | Y = NOT(A+B) | Inverze OR |
| **XOR** | =1 | Y = A⊕B | 0⊕0=0, 0⊕1=1, 1⊕0=1, 1⊕1=0 |
| **XNOR** | – | Y = NOT(A⊕B) | Inverze XOR |

### Realizace kombinačních funkcí

- **Pravdivostní tabulka** → Karnaughova mapa → minimalizovaný logický výraz
- **SOP (Sum of Products)**: Y = AB + ĀB̄ + ...
- **POS (Product of Sums)**: Y = (A+B)(Ā+B̄)...

### Příklady kombinačních obvodů
- **Multiplexer (MUX)** – výběr jednoho z N vstupů
- **Demultiplexer (DEMUX)** – rozdělení jednoho vstupu na N výstupů
- **Dekodér** – binární kód → aktivace jednoho z 2^N výstupů
- **Enkodér** – aktivní vstup → binární kód
- **Komparátor** – porovnání dvou N-bitových čísel
- **Sčítačka (Adder)** – binární sčítání

---

## Sekvenční logické obvody

Výstup závisí na **aktuálních vstupech i předchozím stavu** – mají paměť.

### Klopné obvody (Flip-Flops)

| Typ | Vstupy | Funkce | Použití |
|---|---|---|---|
| **SR FF** | S, R | Set/Reset – nastavení a nulování | Základní paměťový prvek |
| **D FF** | D, CLK | Data FF – na náběžnou hranu CLK: Q = D | Registry, posuvné registry |
| **JK FF** | J, K, CLK | Universální – J=K=1 → toggle | Čítače |
| **T FF** | T, CLK | Toggle – Q přepíná při T=1 | Čítače |

### Registry
- **Posuvný registr** – sériový vstup, paralelní výstup (SIPO) nebo obráceně (PISO)
- **Paralelní registr** – uložení N-bitového slova

### Čítače
- **Binární čítač** – čítá binárně (0 → 1 → 2 → ... → 2^N–1 → 0)
- **BCD čítač** – čítá 0–9 (dekadický)
- **Synchronní vs. asynchronní** – synchronní: všechny FF spínají současně

---

## Způsoby popisu logického obvodu

### 1. Pravdivostní tabulka (Truth Table)
Výčet všech kombinací vstupů a odpovídající výstupy.

### 2. Logický výraz (Boolean algebra)
- **SOP / POS** – minimalizovaný algebraický výraz
- Karnaughova mapa pro minimalizaci

### 3. Schematický diagram
- Grafické zapojení logických hradel

### 4. Stavový diagram (State Diagram)
- Pro sekvenční obvody – uzly = stavy, hrany = přechody při vstupních podmínkách

### 5. Stavová tabulka (State Table)
- Tabulkový popis stavového diagramu: aktuální stav + vstup → nový stav + výstup

### 6. HDL (Hardware Description Language)
- **VHDL** nebo **Verilog** – textový popis digitálního obvodu
- Syntéza do FPGA nebo ASIC

---

## Použití logických obvodů v bioelektronice

| Aplikace | Logický obvod | Funkce |
|---|---|---|
| **Řídící jednotka přístroje** | Mikrokontrolér (AVR, STM32, ESP32) | CPU + periferie (ADC, UART, SPI, I²C) |
| **FPGA v biomedicíně** | Xilinx, Intel Altera | Vysokorychlostní zpracování signálů, real-time DSP |
| **Multiplexování kanálů** | Analog MUX (CD4051, ADG506) | Přepínání mezi elektrodami pro vícekanálové EEG/EMG |
| **Digitální filtry** | DSP / FPGA | FIR, IIR filtry pro EKG, EEG |
| **Komunikační rozhraní** | UART, SPI, I²C, USB, BLE | Přenos dat do počítače nebo cloudu |
| **Časování a synchronizace** | Čítač + hodinový signál | Synchronizace vzorkování ADC s QRS komplexem (R-trigger) |
| **Detekce prahů a alarmů** | Komparátor + logika | Alarmové systémy monitorů |
| **Bezpečnostní logika** | Watchdog timer | Detekce zamrznutí SW → reset přístroje |

---

## Mikrokontrolér vs. FPGA v biomedicíně

| Vlastnost | Mikrokontrolér (MCU) | FPGA |
|---|---|---|
| Architektura | Sekvenční (von Neumann) | Paralelní (konfigurabilní logika) |
| Rychlost zpracování | MHz, sekvenční instrukce | GHz, paralelní operace |
| Flexibilita | SW programování | HW konfigurace (HDL) |
| Spotřeba | Nízká (μW–mW) | Střední (mW–W) |
| Cena | Nízká | Vyšší |
| Použití v biomedicíně | EKG monitory, glukometry, wearables | Ultrazvuk, MRI gradientní řízení, real-time DSP |

---

*Konec bloku – Technika elektronických přístrojů | Otázky 79–84*
