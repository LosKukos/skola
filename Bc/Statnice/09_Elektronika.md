# Elektronika
### Státnicová příprava – Biomedicínská technika 2026

---

# Otázka 67: Pasivní elektronické prvky – rezistory, kondenzátory, cívky

## Rezistory

Rezistor je pasivní prvek, který **klade odpor průchodu elektrického proudu**. Řídí se Ohmovým zákonem:

**U = R × I** → **R = U / I** [Ω]

### Typy rezistorů

| Typ | Popis | Použití |
|---|---|---|
| **Uhlíkový (carbon film)** | Vrstva uhlíku na keramickém substrátu | Obecné obvody, levné |
| **Metalický (metal film)** | Vrstva kovové slitiny – přesnější, méně šumu | Přesné obvody, audio |
| **Drátový (wirewound)** | Odporový drát navinutý na tělísko | Výkonové aplikace |
| **SMD (Surface Mount)** | Pro povrchovou montáž na DPS | Moderní elektronika |
| **Potenciometr** | Proměnný odpor – jezdec | Nastavování, senzory polohy |
| **Termistor NTC/PTC** | Odpor závislý na teplotě | Teplotní senzory, kompenzace |
| **Varistor (MOV)** | Odpor závislý na napětí | Přepěťová ochrana |
| **LDR (fotoresistor)** | Odpor závislý na osvětlení | Světelné senzory |

### Základní vlastnosti rezistorů
- **Jmenovitý odpor** – hodnota v Ω (kódována barevnými pruhy nebo číslem)
- **Výkonová ztráta** – P = I² × R = U²/R [W] – nesmí být překročena
- **Teplotní koeficient (TCR)** – změna odporu s teplotou [ppm/°C]
- **Tolerance** – přesnost hodnoty (±1 %, ±5 %, ±10 %)
- **Šum** – tepelný (Johnsonův) šum – U²_noise = 4kTRΔf

### Zapojení rezistorů
- **Sériové**: R_celk = R₁ + R₂ + ... + Rₙ
- **Paralelní**: 1/R_celk = 1/R₁ + 1/R₂ + ... + 1/Rₙ

---

## Kondenzátory

Kondenzátor je pasivní prvek, který **ukládá elektrický náboj** (elektrickou energii v elektrickém poli).

**Q = C × U** → **C = Q / U** [F]

Impedance kondenzátoru: **Z_C = 1 / (jωC)** → s rostoucí frekvencí impedance klesá.

### Typy kondenzátorů

| Typ | Dielektrikum | Vlastnosti | Použití |
|---|---|---|---|
| **Keramický (MLCC)** | Keramika | Malý, levný, nepolární, stabilní | Blokovací, vazební, filtrační |
| **Fóliový** | Polyester, polypropylén | Nepolární, malý únik | Audio, filtry |
| **Elektrolytický (Al)** | Oxidová vrstva Al | Velká kapacita, **polarizovaný** | Zdroje, filtrační (velké C) |
| **Tantalový** | Oxidová vrstva Ta | Malý, polarizovaný, SMD | Přenosné přístroje |
| **Superkondenzátor** | Dvojvrstva | Obrovská kapacita (F), nízké napětí | Záloha energie |

### Základní vlastnosti kondenzátorů
- **Kapacita** [F] – schopnost uchovat náboj
- **Jmenovité napětí** – max. provozní napětí
- **ESR (Equivalent Series Resistance)** – parazitní odpor – ztrátový faktor
- **Teplotní koeficient** – stabilita kapacity s teplotou
- **Polarita** – elektrolytické a tantalové jsou polarizované!

### Zapojení kondenzátorů
- **Sériové**: 1/C_celk = 1/C₁ + 1/C₂ (kapacita klesá)
- **Paralelní**: C_celk = C₁ + C₂ + ... (kapacita roste)

---

## Cívky (induktory)

Cívka je pasivní prvek, který **ukládá energii v magnetickém poli** při průchodu elektrického proudu.

**U_L = L × dI/dt** → impedance: **Z_L = jωL** → s rostoucí frekvencí impedance roste.

### Typy cívek

| Typ | Jádro | Vlastnosti | Použití |
|---|---|---|---|
| **Vzduchová** | Vzduch | Lineární, bez hystereze, malá L | VF obvody, oscilátory |
| **Feritová** | Ferit | Velká L, nízké ztráty do stovek kHz | Filtry, EMI tlumivky |
| **Práškové železo** | Práškové Fe | Střední frekvence | Napájecí zdroje (buck/boost) |
| **Toroidní** | Toroid | Malé elektromagnetické vyzařování | Napájecí zdroje |

### Základní vlastnosti cívek
- **Indukčnost L** [H] – schopnost akumulovat magnetickou energii
- **Jakost Q** – poměr reaktance k odporu Q = ωL/R (vyšší = lepší)
- **Vlastní rezonanční frekvence (SRF)** – nad SRF se cívka chová jako kondenzátor
- **Saturační proud** – proud, při kterém jádro saturuje a L prudce klesá

### Zapojení cívek
- **Sériové**: L_celk = L₁ + L₂ (bez vzájemné indukce)
- **Paralelní**: 1/L_celk = 1/L₁ + 1/L₂

---

## RC, RL, RLC obvody

### RC článek (dolní propust 1. řádu)
- Mezní frekvence: **f_c = 1 / (2πRC)**
- Pod f_c: signál prochází; nad f_c: signál je tlumen

### RLC obvod – rezonance
- **Rezonanční frekvence**: **f₀ = 1 / (2π√(LC))**
- Při rezonanci: X_L = X_C → impedance je minimální (sériový) nebo maximální (paralelní)
- Jakost: **Q = f₀ / Δf** (Δf = šířka pásma)

---

# Otázka 68: Aktivní elektronické prvky

## Polovodičové diody

Dioda je jednosměrný prvek – propouští proud pouze v propustném směru.

### Princip P-N přechodu
- P-typ: akceptory (díry), N-typ: donory (elektrony)
- Na P-N přechodu vzniká **vyprázdněná oblast** (depletion layer) s elektrickým polem
- **Propustný směr**: U_A > U_K → bariéra snížena → proud teče (práhové napětí Si ≈ 0,6–0,7 V)
- **Závěrný směr**: U_A < U_K → bariéra zvýšena → proud neteče (jen malý závěrný proud)

### Typy diod

| Typ | Vlastnosti | Použití |
|---|---|---|
| **Usměrňovací** | Standardní Si dioda (1N4001–4007) | Usměrňovače, ochrana |
| **Zenerova** | Stabilní průraz v závěrném směru (Z-napětí) | Stabilizace napětí |
| **Schottkyho** | Nízké práhové napětí (0,2–0,4 V), rychlá | Spínané zdroje, RF |
| **LED** | Světelná emise při propustném proudu | Indikátory, osvětlení, optoelektronika |
| **Fotodioda** | Proud generovaný světlem | Detektory světla, pulsní oxymetrie |
| **Varikap (varactor)** | Kapacita závislá na napětí | VCO, nalaďovací obvody |
| **PIN dioda** | Spínání RF signálu | RF přepínače, atenuátory |
| **Tunelová dioda** | Záporný diferenciální odpor | Oscilátory, přepínače (rychlé) |

---

## Bipolární tranzistory (BJT)

BJT je proudem řízený prvek se třemi vrstvami polovodiče: **Emitor (E) – Báze (B) – Kolektor (C)**.

### Typy: NPN a PNP
- **NPN**: I_C = β × I_B (β = proudové zesílení, typicky 50–500)
- **PNP**: opačná polarita napětí a proudů

### Pracovní oblasti BJT

| Oblast | Podmínky | Použití |
|---|---|---|
| **Aktivní** | B-E propustně, B-C závěrně | Lineární zesilovač |
| **Saturace** | Obě přechody propustně | Spínač – sepnut |
| **Uzávěr (Cutoff)** | Obě přechody závěrně | Spínač – rozepnut |

### Základní zapojení BJT

| Zapojení | Vstup | Výstup | Vlastnosti |
|---|---|---|---|
| **SE (Common Emitter)** | Báze | Kolektor | Velké napěťové i proudové zesílení, inverze fáze |
| **SB (Common Base)** | Emitor | Kolektor | Proudové zesílení < 1, velké napěťové, VF použití |
| **SK (Common Collector / Emitter Follower)** | Báze | Emitor | Napěťové zesílení ≈ 1, velký vstupní / malý výstupní odpor – impedanční přizpůsobení |

---

## Unipolární tranzistory (FET)

FET je napětím řízený prvek. Proud kanálem řídí napětí na hradle (Gate).

### JFET (Junction FET)
- N-kanál nebo P-kanál
- Depletion mode (normálně otevřen, hradlo uzavírá)

### MOSFET (Metal-Oxide-Semiconductor FET)

| Typ | Popis | Použití |
|---|---|---|
| **Enhancement NMOS** | Normálně zavřen – U_GS > U_th otevírá | Digitální logika, spínání |
| **Enhancement PMOS** | Normálně zavřen – U_GS < -U_th otevírá | Spínání, CMOS |
| **Depletion MOSFET** | Normálně otevřen – hradlo zavírá | Speciální aplikace |

### Výhody FET oproti BJT
- Vysoká vstupní impedance (prakticky ∞ – hradlo izolováno oxidem)
- Nižší šum (vhodný pro vstupní stupně zesilovačů)
- Řízení napětím (ne proudem) – jednodušší buzení
- **CMOS** – komplementární NMOS+PMOS – základ digitální logiky (minimální statická spotřeba)

---

## Tyristory a triaky

### Tyristor (SCR – Silicon Controlled Rectifier)
- Čtyřvrstvá struktura P-N-P-N (PNPN)
- Řídicí elektroda: **Gate (G)**
- Spouštěcí pulz na Gate → tyristor se zapne a zůstane zapnut i po odstranění pulzu (latch)
- Vypíná se přerušením anodového proudu nebo jeho poklesem pod holding current
- Jednosměrný spínač – pouze v propustném směru

### Triak (TRIAC)
- Ekvivalent dvou antiparalelních tyristorů
- **Obousměrný spínač** – řídí AC proud v obou poloperiodách
- Použití: dimery, regulátory výkonu, teplotní regulátory

### Diak (DIAC)
- Symetrická spínací dioda – spíná v obou směrech při překročení prahového napětí
- Používán pro spouštění triaku (fázová regulace)

---

# Otázka 69: Síťové napájecí zdroje

## Základní blokové schéma síťového zdroje

```
Síťové napájení (230V AC 50Hz)
        ↓
Transformátor (snížení napětí)
        ↓
Usměrňovač (AC → pulzující DC)
        ↓
Filtr (vyhlazení pulzujícího DC)
        ↓
Stabilizátor (stabilní DC výstup)
        ↓
Výstupní napětí (např. +5V, +12V, ±15V)
```

---

## Transformátor

- Převádí střídavé napětí na jiné napětí při zachování frekvence
- **Převodní poměr**: U₂/U₁ = N₂/N₁ (poměr počtu závitů)
- Galvanické oddělení primárního a sekundárního obvodu
- **Síťový transformátor**: 50 Hz → velký, těžký, ale spolehlivý
- **Spínaný zdroj**: transformátor pracuje na vysoké frekvenci (20 kHz–MHz) → malý a lehký

---

## Usměrňovače

### Jednocestný usměrňovač
- 1 dioda – propouští pouze jednu poloperiodu
- Výstup: pulzující DC s frekvencí sítě (50 Hz)
- Nízká využitelnost transformátoru, velké zvlnění

### Dvoucestný usměrňovač (Graetzův můstek)
- 4 diody v můstkovém zapojení
- Propouští obě poloperiody
- Frekvence zvlnění: 100 Hz
- **Střední hodnota výstupu**: U_DC ≈ 0,9 × U_AC (RMS)

### Trojfázový usměrňovač
- 6 diod (nebo tyristorů) – trojfázové napájení
- Velmi malé zvlnění, vysoký výkon

---

## Filtrace usměrněného napětí

### Kondenzátorový filtr
- Kondenzátor C nabíjen při kladné poloperiodě, vybíjen do zátěže
- Zvlnění: **ΔU ≈ I_load / (f × C)**
- Čím větší C nebo f → menší zvlnění

### LC filtr (tlumivka + kondenzátor)
- Lepší filtrace pro velké výkony
- Tlumivka brání rychlým změnám proudu

---

## Stabilizátory napětí

### Parametrický stabilizátor (Zenerova dioda)
- Zenerova dioda v závěrném zapojení – udržuje stabilní napětí na výstupu
- Jednoduchý, levný, malý výkon
- Nevhodný pro velké výstupní proudy

### Lineární stabilizátor (zpětnovazební)
- Tranzistor v sérii (sériový pass element) řízený zpětnovazební smyčkou
- Udržuje stabilní výstupní napětí i při změnách zatížení nebo vstupního napětí
- Integrované obvody: **LM78xx** (kladná napětí), **LM79xx** (záporná), **LM317** (nastavitelné)
- **Nevýhoda**: velká ztrátová energie → P_ztráta = (U_in – U_out) × I_load
- **Výhoda**: nízký šum, jednoduché

### Spínaný stabilizátor (SMPS – Switched-Mode Power Supply)
Pracuje na principu rychlého spínání tranzistoru (PWM) a akumulace energie v tlumivce nebo kondenzátoru.

| Topologie | Popis | Použití |
|---|---|---|
| **Buck (snižující)** | U_out < U_in | Nejčastější – CPU napájení, bateriové nabíječky |
| **Boost (zvyšující)** | U_out > U_in | LED drivery, UPS |
| **Buck-Boost** | U_out < nebo > U_in (invertující) | Univerzální |
| **Flyback** | Galvanicky oddělený – transformátor | Síťové zdroje, nabíječky |

**Výhody SMPS**: vysoká účinnost (85–95 %), malé rozměry
**Nevýhody**: EMI rušení, složitější obvod

---

## Násobič napětí

- Soustava diod a kondenzátorů generující násobky vstupního AC napětí
- **Villardův obvod** – zdvojovač napětí
- **Cockcroft-Waltonův generátor** – několikanásobné napětí
- Použití: vysokonapěťové zdroje (RTG trubice, katodové trubice, elektrostatické přístroje, ionizátory)
- V bioelektronice: napájení piezoelektrických senzorů, HV obvody

---

# Otázka 70: Širokopásmové zesilovače malého signálu, zpětná vazba

## Pracovní bod tranzistoru

### Nastavení klidového pracovního bodu (Q-point)
Tranzistor musí být nastaven do **aktivní oblasti** tak, aby mohl zesilovat bez oříznutí signálu.

### Metody nastavení pracovního bodu BJT

| Metoda | Schéma | Vlastnosti |
|---|---|---|
| **Pevné předpětí** | Jeden rezistor z U_cc na bázi | Jednoduché, nestabilní (závislé na β) |
| **Dělič napětí** | Dva rezistory z U_cc na bázi | Stabilnější, nejčastější metoda |
| **Zpětná vazba emitorem** | R_E v sérii s emitorem | Termická stabilizace Q-bodu |

### Stabilizace Q-bodu emitorovým rezistorem
- R_E zavede zápornou zpětnou vazbu na stejnosměrný provozní bod
- Pokud teplota roste → β roste → I_C roste → U_E roste → U_BE klesá → I_B klesá → I_C se vrátí

---

## Přenosové parametry (h-parametry) BJT

| Parametr | Symbol | Definice | Typická hodnota |
|---|---|---|---|
| Vstupní impedance | h_ie | U_be / I_b při U_ce = konst. | 1–5 kΩ |
| Proudové zesílení | h_fe (β) | I_c / I_b při U_ce = konst. | 50–500 |
| Zpětný napěťový přenos | h_re | U_be / U_ce při I_b = 0 | ≈ 0 (malé) |
| Výstupní admitance | h_oe | I_c / U_ce při I_b = 0 | malé |

---

## Rozklad na kmitočtová pásma

Zesilovač zesiluje signály v určitém kmitočtovém pásmu:

### Nízkofrekvenční útlum (dolní mezní frekvence f_L)
- Způsoben vaznými a blokovacími kondenzátory (C_in, C_out, C_E)
- Pod f_L: kondenzátory mají velkou impedanci → zesílení klesá

### Vysokofrekvenční útlum (horní mezní frekvence f_H)
- Způsoben parazitními kapacitami tranzistoru (C_be, C_bc) a rozložením vedení
- Nad f_H: parazitní kapacity zkratují signál → zesílení klesá

### Šířka pásma (Bandwidth)
**BW = f_H – f_L** [Hz]

---

## Vícestupňové zesilovače

- Kaskádní zapojení – celkové napěťové zesílení: **A_v = A_v1 × A_v2 × ... × A_vn**
- V decibelech: **A_v[dB] = A_v1[dB] + A_v2[dB] + ... + A_vn[dB]**
- Problém: šum prvního stupně je zesílen všemi dalšími → NF (Noise Figure) prvního stupně je klíčová

---

## Zpětná vazba v elektronických obvodech

### Typy zpětné vazby

| Typ | Efekt na zesílení | Efekt na vstupní/výstupní impedanci |
|---|---|---|
| **Záporná (negativní) ZV** | Snižuje zesílení | Stabilizuje, linearizuje, rozšiřuje BW |
| **Kladná (pozitivní) ZV** | Zvyšuje zesílení | Nestabilní → oscilace |

### Parametry záporné zpětné vazby

**A_ZV = A / (1 + A × β_ZV)**

kde A = zesílení bez ZV, β_ZV = faktor ZV (pozor: β_ZV ≠ β tranzistoru!)

### Efekty záporné zpětné vazby
- **Stabilizace zesílení** – méně závislé na parametrech tranzistoru
- **Linearizace** – snížení zkreslení (THD)
- **Rozšíření šířky pásma** – BW × (1 + Aβ)
- **Změna impedancí** – dle topologie ZV (sériová/paralelní na vstupu/výstupu)

---

# Otázka 71: Diferenční zesilovač, výkonové zesilovače

## Diferenční zesilovač

### Princip
Diferenční zesilovač zesiluje **rozdíl** dvou vstupních signálů a potlačuje jejich **souhlasnou složku** (Common Mode – CM).

**U_out = A_diff × (U+ – U–)**

### Klíčový parametr: CMRR

**CMRR = 20 × log(A_diff / A_CM)** [dB]

- Ideální: CMRR → ∞ (nulové zesílení souhlasné složky)
- Reálné diskrétní: 60–80 dB
- Integrované OZ: 80–120 dB
- Přístrojové zesilovače (InAmp): 80–130 dB

### Proč je CMRR důležitý v biomedicíně?
- Biologické signály (EKG, EEG, EMG) jsou slabé (μV–mV)
- Síťové rušení 50 Hz se indukuje na obou elektrodách → souhlasná složka → musí být potlačena
- Vysoký CMRR = odolnost vůči síťovému rušení

---

## Výkonové zesilovače

Výkonové zesilovače dodávají **velký výkon do zátěže** (reproduktory, motory, výkonové prvky).

### Třídy výkonových zesilovačů

| Třída | Klidový proud | Účinnost | Zkreslení | Použití |
|---|---|---|---|---|
| **Třída A** | Velký (tranzistor vede celou dobu) | ≤ 25 % | Nízké | Hi-Fi audio, nízkošumové stupně |
| **Třída B** | Nulový (komplementární pár, každý vede poloperiodu) | ≤ 78,5 % | Přechodové zkreslení (crossover distortion) | Výkonová audio |
| **Třída AB** | Malý klidový proud (eliminuje crossover zkreslení) | 50–70 % | Nízké | Standard výkonových zesilovačů |
| **Třída C** | Vede méně než poloperiodu | > 78,5 % | Velké | RF zesilovače (rezonančně filtrováno) |
| **Třída D** | Spínaný (PWM) | 85–95 % | Nízké (po filtraci) | Digitální audio, napájecí aplikace |

### Třída A – princip
- Tranzistor vede celou dobu (360°) → lineární
- Velká ztrátová energie i v klidu
- Použití: předzesilovače, referenční zesilovače

### Třída B – princip
- Komplementární pár NPN + PNP – každý vede 180°
- Přechodové zkreslení (crossover distortion) v okolí nuly

### Třída AB – princip
- Malý klidový proud nastavuje oba tranzistory těsně do propustného stavu
- Eliminuje crossover zkreslení → kompromis účinnosti a kvality

### Třída D – princip
- Vstupní signál moduluje šířku pulzů (PWM)
- Výstupní tranzistory spínají s vysokou frekvencí (200 kHz–1 MHz)
- Dolní propust filtruje PWM → rekonstruuje analogový signál
- Velmi vysoká účinnost → malé tepelné ztráty

---

# Otázka 72: Teorie operačního zesilovače, základní zapojení

## Ideální operační zesilovač

Operační zesilovač (OZ, Op-Amp) je diferenční zesilovač s velmi vysokým zesílením a symetrickými vstupy.

### Parametry ideálního OZ

| Parametr | Ideální hodnota |
|---|---|
| Napěťové zesílení A_OL (open-loop) | → ∞ |
| Vstupní impedance Z_in | → ∞ |
| Výstupní impedance Z_out | → 0 |
| CMRR | → ∞ |
| Šířka pásma BW | → ∞ |
| Offset napětí | 0 |

### Zlatá pravidla ideálního OZ (se zápornou ZV)
1. **U+ = U–** (napětí na obou vstupech je stejné – virtuální zkrat)
2. **I+ = I– = 0** (do vstupů neteče žádný proud)

---

## Operační síť a operační rovnice

Výstupní napětí OZ závisí na **operační síti** (zpětnovazební a vstupní rezistory):

**U_out = – (Z_f / Z_in) × U_in** (invertující zapojení)

---

## Základní zapojení OZ

### 1. Invertující zesilovač

```
        R_f
   ┌────┤├────┐
   │          │
U_in──R_in──(–)──── U_out
              (+)──GND
```

**A_v = – R_f / R_in**

- Inverze fáze (znaménko minus)
- Vstupní impedance = R_in

### 2. Neinvertující zesilovač

```
U_in──(+)──── U_out
        (–)──R_1──GND
         └───R_f──┘
```

**A_v = 1 + R_f / R_1**

- Bez inverze fáze
- Vstupní impedance velmi vysoká (Z_in OZ)

### 3. Sledovač napětí (Voltage Follower / Buffer)

**A_v = 1** (R_f = 0, R_1 = ∞)

- Výstup sleduje vstup
- Impedanční přizpůsobení – vysoký Z_in, nízký Z_out

### 4. Diferenční zesilovač

**U_out = (R_f / R_1) × (U₂ – U₁)**

- Zesiluje rozdíl vstupů

### 5. Sumační zesilovač

**U_out = – R_f × (U₁/R₁ + U₂/R₂ + U₃/R₃)**

- Součet vážených vstupů

---

# Otázka 73: Lineární a nelineární aplikace OZ

## Lineární aplikace

### Integrátor

```
        C
   ┌────||────┐
   │           │
U_in──R──(–)──── U_out
          (+)──GND
```

**U_out = – (1/RC) × ∫U_in dt**

- Výstupní napětí je integrál vstupního signálu
- Použití: přechodové obvody, delta-sigma ADC, filtry
- **Problém**: drift (DC offset se integruje → výstup se saturuje) → nutný reset nebo omezovací rezistor

### Derivátor

```
        R
   ┌────┤├────┐
   │           │
U_in──C──(–)──── U_out
         (+)──GND
```

**U_out = – RC × dU_in/dt**

- Výstup je derivace vstupního signálu
- **Problém**: zesiluje vysokofrekvenční šum (derivace šumu) → nestabilní → nutný sériový rezistor s C

### Zdroj konstantního proudu (Howland current pump, Transimpedanční zesilovač)
- Výstupní proud nezávislý na zatížení
- Použití: buzení elektrod (bipolární stimulátory), měřicí aplikace

---

## Nelineární aplikace

### Komparátor

OZ bez zpětné vazby (nebo s kladnou ZV):
- U+ > U– → U_out = +U_sat (rail)
- U+ < U– → U_out = –U_sat (rail)

**Schmittův klopný obvod** (komparátor s hysterezí):
- Kladná zpětná vazba přidává **hysterezi** → odolnost vůči šumu

```
Hystereze: U_H = 2 × U_sat × R₁ / (R₁ + R₂)
```

Použití: detekce prahů, tvarovač signálu, generátory

### Operační usměrňovač (precizní usměrňovač)

OZ kompenzuje prahové napětí diody:
- Standardní dioda: práhové napětí ≈ 0,6 V → nepřesné pro malé signály
- S OZ: chyba usměrnění ≈ 0,6 V / A_OL → prakticky nulová
- Použití: usměrnění přesných malých signálů (detektory obálky, RMS obvody)

### Logaritmický a exponenciální zesilovač
- Logaritmický: ve ZV dioda nebo tranzistor → U_out = k × ln(U_in)
- Exponenciální (antilog): dioda nebo tranzistor na vstupu
- Použití: výpočty, zpracování signálů s velkým dynamickým rozsahem

---

# Otázka 74: Generátory periodických signálů

## Harmonické oscilátory

Oscilátory generují periodický signál bez vnějšího vstupu. Vyžadují **kladnou zpětnou vazbu** splňující **Barkhausenovo kritérium**:

**|A × β_ZV| = 1 a φ(A × β_ZV) = 0° (nebo 360°)**

### Wienův oscilátor (RC)
- RC článek ve zpětné vazbě (dolní + horní propust)
- Rezonanční frekvence: **f₀ = 1 / (2πRC)**
- OZ s automatickým řízením amplitudy (AGC)
- Výstup: sinusový signál, nízké zkreslení
- Frekvenční rozsah: 1 Hz – 1 MHz
- Použití: audio, měřicí přístroje

### LC oscilátor (Colpittsův, Hartleyův)
- Rezonančný LC obvod ve zpětné vazbě
- **f₀ = 1 / (2π√(LC))**
- Colpittsův: kapacitní dělič ve zpětné vazbě
- Hartleyův: induktivní dělič ve zpětné vazbě
- Frekvenční rozsah: stovky kHz – stovky MHz
- Použití: RF zdroje, rádiové vysílače/přijímače

### Krystalový oscilátor
- Krystal křemene – piezoelektrický rezonátor s velmi vysokým Q
- Extrémně přesná a stabilní frekvence (< 50 ppm)
- Použití: hodiny, mikroprocesory, komunikace, GPS

---

## Generátory nesinusových signálů

### Astabilní klopný obvod (obdélníkový signál)

**Pomocí OZ (Schmittův oscilátor):**
- OZ s kladnou ZV + RC článek ve zpětné vazbě
- Kondenzátor se nabíjí/vybíjí přes R → výstup přepíná mezi ±U_sat
- **f = 1 / (2RC × ln((1 + β)/(1 – β)))** kde β = R₁/(R₁+R₂)

**Pomocí 555 (Timer):**
- 555 ve astabilním režimu → obdélníkový signál
- Frekvence a střída nastavitelné rezistory a kondenzátorem
- f ≈ 1,44 / ((R_A + 2R_B) × C)

### Generátor trojúhelníkového signálu
- Integrátor + komparátor v uzavřené smyčce
- Komparátor generuje obdélník → integrátor ho integruje na trojúhelník
- Frekvence: **f = R₁ / (4R₂ × R × C)**

### Generátor pilového signálu
- Rychlé nabíjení + pomalé vybíjení (nebo obráceně) kondenzátoru
- Varianta: integrátor + rychlý reset (spínač nebo tranzistor)
- Použití: deflekce v osciloskopech, PWM modulátory, ADC (rampa)

---

## Přehled generátorů

| Typ | Signál | Princip | Použití |
|---|---|---|---|
| Wienův oscilátor | Sinus | RC ZV, OZ | Zvuková technika, měření |
| LC oscilátor | Sinus | Rezonance LC | RF technika |
| Krystalový oscilátor | Sinus | Piezo rezonance | Hodiny, referenční zdroje |
| Schmittův oscilátor | Obdélník | OZ + RC | Časovače, taktovací signály |
| 555 Timer | Obdélník | Nabíjení/vybíjení C | Jednoduché časovače, PWM |
| Integrátor + komparátor | Trojúhelník | Integrace obdélníku | VCO, funkční generátory |
| Rampový generátor | Pila | Reset kondenzátoru | Časové základny, ADC |

---

*Konec bloku – Elektronika | Otázky 67–74*
