# Snímače a senzory v biomedicíně
### Státnicové otázky – Biomedicínská technika 2026

---

## Otázka 1: Snímače a jejich rozdělení

### Co je snímač?
Snímač (senzor) je zařízení, které **převádí fyzikální, chemickou nebo biologickou veličinu** na signál vhodný ke zpracování — nejčastěji elektrický.

> Měřená veličina → **Snímač** → Elektrický signál (napětí, proud, odpor, kapacita...)

---

### Základní rozdělení snímačů

#### 1. Podle výstupního signálu
| Typ | Popis | Příklady |
|-----|-------|---------|
| **Aktivní** | Generují elektrický signál samy, nepotřebují napájení | Termoelektrické články, piezoelektrické senzory, fotovoltaické články |
| **Pasivní** | Mění elektrický parametr (R, C, L), potřebují napájení | Termistory, tenzometry, kapacitní snímače |

#### 2. Podle měřené veličiny
- Tlaku, průtoku, teploty, chemické, akustické, mechanické, optické, magnetické...

#### 3. Podle principu činnosti
| Princip | Popis | Příklad |
|---------|-------|---------|
| **Odporový** | Mění odpor vlivem měřené veličiny | Termistor, tenzometr, odporový teploměr |
| **Kapacitní** | Mění kapacitu | Kapacitní snímač tlaku, vlhkosti |
| **Indukční** | Mění indukčnost | LVDT, snímač polohy |
| **Piezoelektrický** | Deformace → napětí (přímý piezoefekt) | Snímač tlaku, akcelerometr, ultrazvuková sonda |
| **Termoelektrický** | Teplotní rozdíl → napětí (Seebeckův jev) | Termočlánek |
| **Optický** | Využívá světlo | Fotodioda, optovláknový senzor, pulsní oxymetr |
| **Elektrochemický** | Chemická reakce → el. signál | pH elektroda, glukózový senzor |
| **Magnetický** | Reaguje na magnetické pole | Hallova sonda, SQUID |

#### 4. Podle kontaktu s pacientem
- **Invazivní** – zavedeny do těla (katétry, implantabilní senzory, jehlové elektrody)
- **Neinvazivní** – na povrchu těla nebo bezkontaktní (EKG elektrody, manžeta TK, termovize)
- **Miniinvazivní** – minimální průnik do těla (kapilární glukometr)

#### 5. Podle výstupního signálu
- **Analogové** – spojitý výstup (napětí, proud)
- **Digitální** – diskrétní výstup (pulzy, binární signál)

---

### Základní pojmy
- **Primární snímač** – přímo reaguje na měřenou veličinu
- **Sekundární snímač** – převádí primárně snímanou veličinu na jinou (např. tlak → výchylka → elektrický signál)
- **Transducer (převodník)** – obecnější pojem zahrnující snímač i případnou úpravu signálu
- **Senzor** – část snímače citlivá na měřenou veličinu

---

## Otázka 2: Vlastnosti a charakteristiky senzorů

### Statické vlastnosti (měřeny při ustáleném stavu)

| Vlastnost | Definice |
|-----------|----------|
| **Citlivost** | Změna výstupního signálu na jednotkovou změnu vstupní veličiny (S = ΔV_out / ΔV_in) |
| **Rozsah (range)** | Interval hodnot vstupní veličiny, pro který je senzor specifikován |
| **Linearita** | Míra shody skutečné charakteristiky s ideální přímkou; udává se jako % z plného rozsahu |
| **Rozlišení** | Nejmenší rozlišitelná změna měřené veličiny |
| **Přesnost** | Shoda výstupní hodnoty se skutečnou hodnotou měřené veličiny |
| **Hystereze** | Rozdíl výstupní hodnoty pro stejný vstup při rostoucím a klesajícím průběhu |
| **Opakovatelnost** | Schopnost senzoru podávat stejné výsledky za stejných podmínek |
| **Drift (posun nuly)** | Pomalá změna výstupního signálu bez změny měřené veličiny (vliv teploty, stárnutí) |
| **Offset** | Nenulový výstup při nulovém vstupu |

### Dynamické vlastnosti (chování při změnách v čase)

| Vlastnost | Definice |
|-----------|----------|
| **Přenosová funkce** | Matematický popis závislosti výstupu na vstupu v Laplaceově oblasti |
| **Frekvenční odezva** | Závislost citlivosti na frekvenci měřené veličiny |
| **Doba odezvy** | Čas potřebný k dosažení definovaného procenta výsledné hodnoty po skokové změně vstupu |
| **Časová konstanta (τ)** | Čas, za který výstup dosáhne 63,2 % konečné hodnoty (pro systém 1. řádu) |

### Ostatní důležité vlastnosti
- **Selektivita** – schopnost reagovat pouze na sledovanou veličinu a ignorovat rušivé vlivy
- **Stabilita** – zachování parametrů v čase
- **Impedance** – vstupní a výstupní impedance senzoru (důležitá pro připojení k měřicímu řetězci)
- **Šum** – vlastní elektrický šum senzoru
- **Životnost a biokompatibilita** – zejména pro implantabilní senzory

---

## Otázka 3: Senzory tlaku

### Fyzikální principy měření tlaku

#### Odporové senzory (tenzometrické)
- Využívají **tenzometry** – vodiče nebo polovodiče, jejichž odpor se mění při mechanické deformaci
- **Kovové tenzometry**: malá citlivost (gauge factor ≈ 2), odolné
- **Polovodičové tenzometry**: velká citlivost (gauge factor až 150), teplotně závislé
- Zapojení do Wheatstoneova můstku pro kompenzaci teploty a zvýšení citlivosti
- Aplikace: měření invazivního krevního tlaku (katétrové snímače), nitrolebeční tlak

#### Kapacitní senzory tlaku
- Membrána tvoří pohyblivou elektrodu kondenzátoru
- Tlak → průhyb membrány → změna vzdálenosti elektrod → změna kapacity
- Výhody: vysoká citlivost, malý drift, nízká spotřeba
- Aplikace: neinvazivní měření TK, barometrické senzory

#### Piezoelektrické senzory tlaku
- Piezoelektrický materiál (křemen, PVDF) generuje náboj při mechanickém napětí
- **Vhodné pouze pro dynamické měření** (nezachytí statický tlak – náboj uniká)
- Aplikace: fonokardiografie, ultrazvukové sondy, snímání rázové vlny

#### Piezoresistivní senzory (MEMS)
- Využívají změnu odporu polovodiče při mechanickém namáhání
- Miniaturizované pomocí technologie MEMS (mikro-elektro-mechanické systémy)
- Aplikace: miniaturní katétrové senzory, implantabilní senzory

### Klinické aplikace
| Typ měření | Metoda | Princip |
|------------|--------|---------|
| Invazivní TK | Katétr + tenzometrický snímač | Přenos tlaku přes sloupec kapaliny |
| Neinvazivní TK | Oscilometrická, Korotkovovy ozvy | Manžeta, detekce oscilací |
| Nitrolebeční tlak | Epidurální/intraventrikulární čidlo | Přímé měření |
| Oční tlak | Tonometr | Applanační nebo bezkontaktní metoda |

---

## Otázka 4: Senzory průtoku

### Princip měření průtoku

Průtok Q [m³/s nebo l/min] = průřez S × střední rychlost v

#### Elektromagnetický průtokoměr
- Faradayův zákon elektromagnetické indukce: tekutina (vodivá) pohybující se v magnetickém poli generuje napětí
- **U = B · d · v** (B = mag. indukce, d = průměr trubice, v = rychlost)
- Podmínka: měřené médium musí být elektricky vodivé (krev ano)
- Aplikace: perivazální průtokoměr (operační sál), měření průtoku krve

#### Ultrazvukový průtokoměr (Dopplerův)
- Využívá **Dopplerův jev**: frekvence odraženého ultrazvuku se mění v závislosti na rychlosti pohybujících se částic (erytrocytů)
- **Δf = 2 · f₀ · v · cos(θ) / c** (f₀ = vysílaná frekvence, v = rychlost krve, θ = úhel, c = rychlost zvuku)
- Neinvazivní nebo invazivní (jícnová sonda)
- Aplikace: cévní Doppler, echokardiografie, fetální Doppler

#### Tranzitní ultrazvukový průtokoměr
- Měří rozdíl doby průchodu ultrazvuku po proudu a proti proudu tekutiny
- Výhody: neinvazivní (lze přiložit na cévu zvenku)

#### Tepelný průtokoměr (Termální diluce)
- Vstříkne se bolus studené tekutiny → termodiluční křivka → výpočet průtoku
- **Fickův princip**: průtok = množství indikátoru / plocha pod diluční křivkou
- Aplikace: měření srdečního výdeje (Swan-Ganzův katétr)

#### Rotametr a Fleischův pneumotachograf
- **Rotametr**: kuličkový průtokoměr pro plyny (kyslík, CO₂)
- **Pneumotachograf**: měří průtok vzduchu jako pokles tlaku přes laminární odpor (Δp = R · Q)
- Aplikace: respirátory, ventilační diagnostika

---

## Otázka 5: Senzory tepelných veličin

### Teploměry odporové (RTD – Resistance Temperature Detector)
- Odpor kovů roste s teplotou (platina, nikl, měď)
- **Platinový odporový teploměr Pt100**: R = 100 Ω při 0°C, lineární charakteristika, přesný, stabilní
- Rozsah: −200 °C až +850 °C
- Aplikace: klinické teploměry, inkubátory, operační sál

### Termistory (NTC/PTC)
- **NTC (Negative Temperature Coefficient)**: odpor s teplotou klesá, exponenciální závislost, vysoká citlivost
- **PTC (Positive Temperature Coefficient)**: odpor s teplotou roste, ochranné obvody
- Výhody NTC: malé rozměry, velká citlivost, rychlá odezva
- Nevýhody: nelinearita (nutná linearizace), nutná kalibrace
- Aplikace: katétrové teploměry, měření teploty jádra těla, termodiluční průtokoměry

### Termočlánky (termoelektrické senzory)
- **Seebeckův jev**: na spoji dvou různých kovů vzniká termoelektrické napětí závislé na teplotě
- Nutný referenční spoj (studený konec) nebo elektronická kompenzace
- Typy: K (chromel-alumel), J (železo-konstantan), T (měď-konstantan)
- Výhody: robustní, velký rozsah, bod. měření
- Nevýhody: malé napětí, nutná kompenzace studeného konce
- Aplikace: měření teploty tkáně při chirurgii, kryochirurgie

### Pyrometry a termovize (bezkontaktní)
- Měří infračervené záření vyzařované tělesem (**Stefan-Boltzmannův zákon**)
- **Ušní pyrometr**: měří infračervené záření ušního bubínku (≈ teplota mozku)
- **Termovizní kamera**: zobrazuje rozložení teploty na povrchu těla
  - Detekce zánětu, nádorů, cévních poruch, diabetické nohy
- Výhody: bezkontaktní, rychlé
- Nevýhody: citlivost na prostředí, povrchová teplota ≠ tělesné jádro

### Kapalné krystalické teploměry
- Barva krystalů závisí na teplotě → zobrazení teplotního rozložení
- Levné, jednoduché – např. čelní teploměrné pásky

---

## Otázka 6: Senzory chemických veličin

### Elektrochemické senzory

#### Potenciometrické senzory (měří napětí)
- **pH elektroda**: skleněná elektroda citlivá na aktivitu H⁺ iontů
  - Nernstova rovnice: E = E₀ + (RT/nF) · ln[a_H⁺]
  - Nutná referenční elektroda (kalomelová nebo Ag/AgCl)
  - Aplikace: krevní plyny (ABR), močová analýza
- **ISE (Ion-Selective Electrode)**: selektivní membrána pro konkrétní ion (Na⁺, K⁺, Ca²⁺, Cl⁻)
  - Aplikace: elektrolytové analyzátory

#### Ampérometrické senzory (měří proud)
- **Clarkova elektroda (O₂ elektroda)**:
  - Platinová katoda + Ag/AgCl anoda + KCl elektrolyt + kyslíkopropustná membrána
  - O₂ difunduje přes membránu a redukuje se na katodě → proud ∝ [O₂]
  - Aplikace: pO₂ v krvi, inkubátory, ventilátory
- **Glukózový senzor**:
  - Glukóza + O₂ → glukuronolakton + H₂O₂ (glukóza-oxidáza)
  - Měří se vzniklý H₂O₂ ampérometricky nebo spotřeba O₂
  - Aplikace: glukometry, kontinuální CGM senzory

#### Konduktometrické senzory
- Měří elektrickou vodivost roztoku
- Aplikace: hemodialýza (kontrola dialyzátu), měření hematokritu

### Optochemické senzory
- **Optody**: optovláknové senzory využívající fluorescenci nebo absorbanci
- Aplikace: pulzní oxymetrie (SpO₂), kapnografie (CO₂)

### Biosenzory
→ Viz otázka 8 (Biosenzory)

---

## Otázka 7: Biopotenciálové elektrody

### Vznik biopotenciálů
- Na buněčné membráně existuje klidový membránový potenciál (≈ −70 mV)
- Při vzrušení (depolarizaci) dochází k akčnímu potenciálu → šíří se tkání → měřitelné na povrchu těla

### Rozhraní elektroda-elektrolyt
- Elektrody jsou kovové, tkáň je iontový vodič → na rozhraní probíhají elektrochemické reakce
- **Oxidačně-redukční reakce**: kov ↔ ionty v roztoku → vzniká **polovodičový potenciál** (elektrodový potenciál)
- **Polarizovatelné elektrody**: na rozhraní nevzniká stejnosměrný proud (kapacitní chování) – platina, zlato
- **Nepolarizovatelné elektrody**: umožňují průchod ss proudu – ideální pro biopotenciály → **Ag/AgCl elektrody**

### Ag/AgCl elektroda
- Nejpoužívanější pro biopotenciálová měření
- Ag pokryt vrstvou AgCl + chloridový elektrolyt (KCl gel)
- Stabilní polovodičový potenciál, malý šum, nízká impedance
- Výroba: elektrolytické pokovení stříbra chloridem

### Druhy biopotenciálových elektrod

| Typ | Popis | Použití |
|-----|-------|---------|
| **Povrchové (EKG)** | Ag/AgCl disk s gelem, lepicí | EKG, EEG (skalp), EMG (povrchový) |
| **Jehlové** | Kovová jehla zavedená do tkáně | EMG (jehlové), EEG (kortikální) |
| **Sací (přísavné)** | Přísavka + elektroda | Hrudní svody EKG |
| **Plovoucí** | Elektroda s distancí od kůže + gel | Pohybové artefakty menší |
| **Katétrové** | Elektroda na konci katétru | Intrakardiální měření (EPS) |
| **Mikro-elektrody** | Skleněné nebo kovové, průměr μm | Intracelulární měření, neurologie |

### Artefakty a jejich potlačení
- **Pohybové artefakty**: relativní pohyb elektrody vůči kůži → plovoucí elektrody, dobrý kontakt
- **Síťové rušení 50 Hz**: stínění, notch filtr, zapojení pravé nohy (DRL obvod)
- **Elektrodový potenciál**: Ag/AgCl minimalizuje nestabilitu
- **Svalové artefakty (EMG)**: dolnopropustná filtrace při EEG/EKG

### Vodivý gel
- Snižuje impedanci rozhraní kůže-elektroda
- Chloridový elektrolyt (NaCl, KCl) – zajišťuje iontový kontakt

---

## Otázka 8: Biosenzory

### Definice
Biosenzor je analytické zařízení kombinující **biologický rozpoznávací prvek** (biorecepror) s **fyzikálně-chemickým převodníkem** (transducer) pro detekci biologických nebo chemických látek.

> Analyt → Bioreceptor → Biochemická reakce → Převodník → Elektrický signál

### Složky biosenzoru
1. **Bioreceptor (biologická složka)**:
   - Enzymy (glukóza-oxidáza, urináza)
   - Protilátky (imunochemické senzory)
   - DNA/RNA (hybridizační senzory, aptamery)
   - Buňky, mikroorganismy
   - Buněčné receptory
2. **Převodník (transducer)**:
   - Elektrochemický (ampérometrický, potenciometrický, konduktometrický)
   - Optický (fluorescence, SPR – surface plasmon resonance)
   - Piezoelektrický (QCM – quartz crystal microbalance)
   - Kalorimetrický (měření tepla reakce)

### Příklady biosenzorů

| Biosenzor | Bioreceptor | Převodník | Aplikace |
|-----------|-------------|-----------|----------|
| Glukózový | Glukóza-oxidáza | Ampérometrický | Glukometr, CGM |
| Ureový | Uráza | Potenciometrický (pH) | Funkce ledvin |
| Imunologický (ELISA) | Protilátka | Optický, elektrochemický | Diagnostika, troponin |
| DNA hybridizační | DNA sonda | Elektrochemický, optický | Genetická diagnostika |
| SPR | Protilátka | Optický (plazmonový) | Proteiny, léky |

### Výhody biosenzorů
- Vysoká selektivita (bioreceptor reaguje na konkrétní analyt)
- Možnost miniaturizace (MEMS, lab-on-chip)
- Rychlá odezva
- Point-of-care diagnostika

### Výzvy
- Stabilita biologické složky (denaturace, stárnutí)
- Fouling (nespecifická adsorpce)
- Kalibrace a životnost

---

## Otázka 9: Senzory biomagnetických polí

### Zdroje biomagnetických polí
Elektricky aktivní tkáně generují nejen elektrická, ale i magnetická pole:
- **Magnetokardiogram (MCG)**: magnetické pole srdce (~100 pT)
- **Magnetoencefalogram (MEG)**: magnetické pole mozku (~100 fT)
- **Magnetomyogram (MMG)**: magnetické pole svalů

Tato pole jsou **extrémně slabá** → nutné vysoce citlivé senzory a stínění.

### SQUID (Superconducting Quantum Interference Device)
- Nejcitlivější senzor magnetického pole
- Funguje na principu **Josephsonových spojů** v supravodivé smyčce
- Nutné chlazení tekutým heliem (4 K) nebo dusíkem (77 K pro HTS SQUID)
- Citlivost: až 10⁻¹⁵ T (femtotesla)
- Vyžaduje **magneticky stíněnou místnost** (MSR – Magnetically Shielded Room)
- Aplikace: MEG (mapování mozkové aktivity), MCG (prenatální kardiologie)

### Fluxgate magnetometry
- Princip: nasycení feromagnetického jádra střídavým polem → citlivé na vnější pole
- Citlivost: ~pT–nT
- Aplikace: orientace (kompas), detekce feromagnetických těles v těle

### Hall sondy
- Princip: Hallův jev – v magnetickém poli teče proud příčně (Hallovo napětí)
- Jednodušší, levnější, méně citlivé (~μT)
- Aplikace: NMR/MRI (měření homogenity magnetu), průtokoměry

### Opticky pumpované magnetometry (OPM)
- Novější alternativa k SQUID, pracují při pokojové teplotě
- Citlivost srovnatelná se SQUID
- Aplikace: MEG bez chlazení, wearable MEG

### Stínění
- Biomagnetická pole jsou rušena zemským magnetickým polem (50 μT) a elektrickými sítěmi
- Nutná stíněná místnost: vrstvy μ-kovu (Permalloy) + aktivní kompenzace

---

## Otázka 10: Detektory ionizujícího záření

### Typy ionizujícího záření
| Záření | Zdroj | Pronikavost | Ionizace |
|--------|-------|-------------|----------|
| **α (alfa)** | Jádra He⁴ | Malá (stopky v papíru) | Silná |
| **β (beta)** | Elektrony/pozitrony | Střední (Al mm) | Střední |
| **γ (gama)** | Elektromagnetické záření | Velká (olovo cm) | Slabá přímá |
| **X záření** | Brzdné záření elektronů | Velká | Slabá přímá |
| **Neutrony** | Jaderné reakce | Velká | Nepřímá |

### Ionizační detektory

#### Ionizační komora
- Plyn mezi elektrodami je ionizován zářením → ionty sbírány elektrodami → proud
- Aplikace: dozimetrie, měření radioaktivity

#### Geiger-Müllerův počítač (GM trubice)
- Vysoké napětí → lavina ionizace → pulz pro každou částici
- Výhody: jednoduché, levné
- Nevýhody: neslouží k energetické analýze, mrtvá doba
- Aplikace: radiační ochrana, osobní dozimetry

#### Proporcionální počítač
- Mezi ionizační komorou a GM trubicí – zachovává proporci náboje → lze rozlišit energii záření

### Scintilační detektory
- Záření excituje scintilační materiál → emise světelných fotonů → fotonásobič (PMT) → elektrický pulz
- **Anorganické scintilátory**: NaI(Tl) – pro γ záření, vysoká účinnost
- **Organické scintilátory**: plastové, kapalné – pro β záření
- Aplikace: gama kamera, PET, SPECT, nukleární medicína

### Polovodičové detektory
- Záření vytváří páry elektron-díra v polovodiči (Si, Ge, CdTe)
- Velmi dobré energetické rozlišení
- Ge detektory nutno chladit kapalným dusíkem
- Aplikace: energetická spektrometrie, CT detektory (CdTe, GaAs)

### Termoluminiscenční dozimetry (TLD)
- Záření vytváří zachycené elektrony v krystalové mřížce → zahříváním se uvolní jako světlo
- Aplikace: osobní dozimetry pro zdravotnický personál

### Flat-panel detektory (pro digitální RTG)
- **Přímá konverze**: záření → elektrický náboj přímo (Se, CdTe)
- **Nepřímá konverze**: záření → scintilátorem na světlo → fotodiodou na náboj (CsI + a-Si)
- Aplikace: digitální rentgen, CT

---

## Otázka 11: Senzory akustických veličin

### Základy akustiky
- Zvuk = mechanická vlna v elastickém prostředí
- **Frekvence slyšitelného zvuku**: 20 Hz – 20 kHz
- **Ultrazvuk**: > 20 kHz (v medicíně 1–20 MHz)
- **Infrasound**: < 20 Hz

### Mikrofony (zvukové senzory)

#### Kondenzátorový mikrofon
- Membrána = pohyblivá elektroda kondenzátoru, pevná zadní deska = druhá elektroda
- Zvuk → vibrace membrány → změna kapacity → napěťový signál
- Velmi dobrá frekvenční charakteristika, malý šum
- Aplikace: fonokardiografie, stetoskopy (elektronické), audiometrie

#### Elektretový mikrofon
- Kondenzátorový mikrofon s permanentně nabitou membránou (elektret) → nepotřebuje polarizační napětí
- Miniaturní, levný
- Aplikace: fonendoskopy, naslouchadla

#### Piezoelektrický senzor zvuku
- Piezoelektrický materiál vibruje → generuje napětí
- Aplikace: ultrazvukové snímače, kontaktní mikrofony (fonokardiografie – snímání srdečních ozev přes hrudník)

#### MEMS mikrofon
- Miniaturizovaný kondenzátorový mikrofon na křemíkovém chipu
- Aplikace: wearable zařízení, naslouchadla, mobilní telefony

### Ultrazvukové senzory (sondy)

#### Piezoelektrické ultrazvukové měniče
- Piezoelektrický krystal (PZT – olovo-zirkonát-titanát) vysílá i přijímá UZ
- **Přímý piezoefekt**: mechanická deformace → napětí (příjem)
- **Nepřímý piezoefekt**: napětí → deformace → UZ vlna (vysílání)
- Rezonanční frekvence závisí na tloušťce krystalu: f = c / 2d
- Aplikace: UZ diagnostika, echokardiografie, Doppler

### Fonendoskop a elektronické stetoskopy
- Klasický fonendoskop: akustický přenos zvuku
- Elektronický stetoskop: mikrofon + zesílení + digitální zpracování, potlačení šumu
- Aplikace: srdeční ozvy, dýchací zvuky

### Audiometrie
- Měření sluchového prahu pomocí kalibrovnaných tónů
- **Vzdušné vedení**: sluchátky
- **Kostní vedení**: vibrátor přiložený na mastoid
- Výstup: **audiogram** (prahy slyšení v dB HL pro různé frekvence)

---

## Otázka 12: Senzory mechanických veličin

### Měřené mechanické veličiny
- Síla, tlak, posunutí, rychlost, zrychlení, vibrace, poloha, deformace (napětí)

### Tenzometry (strain gauges)
- Měří deformaci (strain) materiálu
- **Kovové tenzometry**: fóliové, drátové – gauge factor ≈ 2
  - R = ρ·l/A → při deformaci se mění l i A → mění se R
- **Polovodičové tenzometry**: gauge factor 50–150, velmi citlivé, nelineární
- Zapojení: Wheatstoneův můstek pro teplotní kompenzaci a zvýšení citlivosti
- Aplikace: váhy, dynamometry, snímače síly, měření tlaku krve

### LVDT (Linear Variable Differential Transformer)
- Indukční snímač lineárního posunutí
- Pohyblivé jádro mění vzájemnou indukčnost primárního a dvou sekundárních vinutí
- Výstupní napětí lineárně závislé na posunutí jádra
- Bezkontaktní, vysoká přesnost, dlouhá životnost
- Aplikace: spirometrie, měření rozsahu pohybu kloubů, snímač polohy pístu

### Akcelerometry
- Měří zrychlení = sílu působící na seismickou hmotu
- **Piezoelektrické akcelerometry**: seismická hmota + piezoelektrický krystal → náboj ∝ zrychlení
- **Kapacitní MEMS akcelerometry**: pohyblivá hmota mění kapacitu kondenzátoru
- Aplikace: gyroskopy, krokometry, detekce pádu (LifeAlert), analýza chůze, ballistokardiografie

### Snímače polohy a pohybu
- **Potenciometrické**: kluzný kontakt na odporovém drátu
- **Optické enkodéry**: přerušování světelného paprsku = impulzy
- **Kapacitní snímače vzdálenosti**
- Aplikace: robotická rehabilitace, protetika, ergometrie

### Silové senzory
- Kombinace tenzometrů v Wheatstoneově můstku
- **Vícesložkové silové senzory**: současné měření sil a momentů ve více osách
- Aplikace: ortopedické (měření tlaku na chodidlo), rehabilitace, biomechanika

### Vibrační senzory
- Akcelerometry, piezoelektrické senzory
- Aplikace: analýza chůze, tremor (Parkinsonova choroba), ballistokardiograf

---

*Soubor zpracován pro státní zkoušky – Biomedicínská technika 2026*
*Předmět: Snímače a senzory v biomedicíně (Augustynek)*
