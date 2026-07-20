# Technika elektronických přístrojů (Kašík) – vypracované otázky

---

## 1. Konstrukce zdroje ss napětí pro bioelektroniku

### Klasický lineární zdroj
Skládá se z bloků: **síť → TR (transformátor) → U (usměrňovač) → F (filtr) → S (stabilizátor) → Uvýst**

- **Transformátor** – transformuje síťové napětí na požadovanou úroveň, zajišťuje galvanické oddělení od sítě (energie se přenáší elektromagnetickou indukcí mezi vinutími), působí i jako filtr proti vf rušení. Rozměry/hmotnost rostou s výkonem (cca s 2. a 3. odmocninou). Může mít víc vinutí pro víc nezávislých výstupů.
- **Usměrňovač** – mění střídavé napětí na stejnosměrné (zvlněné/tepavé):
  - **jednocestný** (1 dioda) – využívá jen jednu půlvlnu
  - **dvoucestný** (2 diody, dělené sekundární vinutí)
  - **Graetzův můstek** (4 diody) – nejběžnější, plné využití obou půlvln
- **Filtr** – vyhlazuje zbytkovou střídavou složku (zvlnění), nejčastěji kondenzátor, případně tlumivka nebo kombinace LC/RC. Velikost součástek určuje požadované zvlnění.
- **Stabilizátor** – udržuje výstupní napětí konstantní bez ohledu na kolísání vstupu i zátěže. Kvalita je dána:
  - **činitelem stabilizace** K = (ΔU₁/U₁)/(ΔU₂/U₂) (co největší)
  - **vnitřním diferenciálním odporem** R_Tst = ΔU₂/ΔI₂ (co nejmenší)
  
  Typy:
  - **parametrické** (Zenerova dioda, doutnavka, dioda v propustném směru) – pro malé zatěžovací proudy (desítky mA)
  - **se zpětnou vazbou (degenerativní)** – regulační prvek řízený odchylkou výstupu od referenčního napětí (dnes většinou integrované, např. 7805/LM317)

### Symetrické napájení
Dvojice zdrojů (+U, 0, −U), lze vytvořit i "uměle" pomocí odporového děliče. Typicky dvojice stabilizátorů 78xx/79xx.

### Zdvojovač a násobič napětí
Zapojení diod a kondenzátorů, které z jednoho zdroje AC vytváří vyšší DC napětí (2U₀, 5U₀ atd.) – využití tam, kde je potřeba vyšší napětí při malém proudovém odběru.

### Spínané zdroje s transformátorem
Blok: vstup → AC/DC → filtr → **spínač** → **trafo** (vf, menší a lehčí než síťové) → AC/DC → filtr → výstup, se zpětnovazební smyčkou (COMP–PWM), která řídí střídu spínače.
- Výhody oproti lineárním: menší, lehčí, účinnější (menší ztrátový výkon)
- Nevýhody: složitější, generují elektromagnetické rušení (nutnost odrušení)

### Bezpečnostní hlediska (relevantní pro bioelektroniku)
- Bezpečné malé napětí: 25 V~ / 60 V= (normální i nebezpečné prostory)
- IEC 601-1 pro zdravotnickou techniku: příložná část max. 10 µA, přístupná část max. 100 µA
- Práh vnímání proudu: 0,5 mA~ / 2 mA=; práh bolesti: 3,5 mA~ / 10 mA=
- Pro bioelektroniku (přímý kontakt s pacientem) se preferuje **galvanické oddělení** (transformátor, optron) a přísné dodržení unikajících proudů dle IEC 60601.

---

## 2. Zesilovače pro bioelektroniku

### Operační zesilovač (OZ) – základ
Ideální OZ: nekonečné napěťové/proudové zesílení, nekonečný vstupní odpor, nulový výstupní odpor, frekvenční nezávislost, nekonečné potlačení souhlasného signálu (CMRR).

Rozdělení OZ: univerzální, **přístrojové** (malé napětí, velké zesílení, malý drift – vhodné pro biosignály), širokopásmové/rychlé, pro velká výstupní napětí, speciální (mikropříkonové).

### Základní zapojení s OZ
| Zapojení | Vztah | Poznámka |
|---|---|---|
| Neinvertující | U₂ = (1 + R₂/R₁)·U₁ | vysoký vstupní odpor, zesílení ≥ 1, ve fázi |
| Invertující | U₂ = −(R₂/R₁)·U₁ | nízký vstupní odpor (daný R₁), fáze otočena o 180° |
| Sumátor | U₀ = −Σ(R₀/Rₙ)·Uₙ | váhový součet vstupů |
| Diferenční (rozdílový) | U₀ = (R₂/R₁)·(U₂−U₁) | zesiluje jen rozdíl napětí, nutné přesné páry R |
| Komparátor | bez zpětné vazby, plné zesílení | výstup je +Umax/−Umax podle znaménka rozdílu |
| Integrátor | výstup ~ integrál vstupu (RC člen) | tvoří trojúhelníkový průběh z obdélníkového |
| Derivátor | výstup ~ derivace vstupu | používá se zřídka – zesiluje šum a vf rušení |

### Problematika vstupní impedance zesilovače
- U invertujícího zapojení je vstupní odpor prakticky roven R₁ (relativně malý) – nevýhoda pro biosignály, protože zatěžuje zdroj signálu (elektrodu/tkáň).
- U neinvertujícího zapojení je vstupní odpor velmi vysoký (daný vstupním odporem OZ) – vhodné pro snímání biopotenciálů s vysokou zdrojovou impedancí (kožní elektrody mají odpor v řádu desítek kΩ až MΩ).
- Vysoká a symetrická vstupní impedance je klíčový požadavek na zesilovače biosignálů (EKG, EEG, EMG) – minimalizuje zkreslení signálu a citlivost na souhlasné rušení (např. síťový brum).

### Přístrojový zesilovač (Instrumentation Amplifier)
Skládá se ze **tří OZ**: dva neinvertující vstupní stupně (vysoká vstupní impedance, symetrie) + výstupní diferenční zesilovač.

Zesílení: U₃/(U₂−U₁) = (1 + 2R₂/R₁)·(R₄/R₃)

Vlastnosti klíčové pro bioelektroniku:
- velmi malá vstupní napěťová nesymetrie (offset)
- vysoký činitel potlačení souhlasného signálu (CMRR) – potlačuje síťový brum a jiné souhlasné rušení na obou elektrodách
- velký a symetrický vstupní odpor na obou vstupech
- zesílení nastavitelné jedním externím odporem (R₁)

### Šum zesilovače
Šum snižuje informační obsah signálu, nesmí překročit minimální sledovanou amplitudu (u biosignálů řádově µV–mV). Zdroje: vnější (rušení z okolí) a vnitřní (tepelný šum odporů, šum tranzistorů OZ). Tepelný (Johnsonův) šum na odporu je bílý šum se spektrální hustotou S = 4kϑR (k = Boltzmannova konstanta).

---

## 3. Galvanické oddělení biosignálu

### Proč galvanické oddělení
Při měření biosignálů je pacient v přímém kontaktu s elektronikou – z bezpečnostních důvodů (ochrana před úrazem el. proudem, IEC 60601) je nutné oddělit obvod na straně pacienta od obvodu napájeného ze sítě/napájecího zdroje.

### Galvanicky izolované zesilovače
- Umožňují pracovat s **plovoucím vstupem** na straně snímače (samy si generují vstupní klidový proud)
- Umožňují pracovat s vysokým rozdílem potenciálů (souhlasným napětím) mezi vstupem od snímače a zemněným výstupem
- Malé souhlasné napětí (jednotky V) lze potlačit běžným přístrojovým zesilovačem; větší potenciály se řeší **izolačním mechanismem**:
  - **transformátorová vazba** (modulace signálu na vf nosnou, přenos přes transformátor, demodulace)
  - **optická vazba** (LED–fototranzistor)
  - **kapacitní spoj**

### Optočlen (optron)
- Optoelektronický vazební člen pro galvanické oddělení obvodů
- Vysílač (IR LED) i přijímač (fotodioda, fototranzistor, fototyristor) v jednom pouzdře, vazba světlem
- Parametry: izolační odpor > 10¹¹ Ω, izolační napětí 2,5–5 kV
- Existují v různých konfiguracích (s tranzistorovým, tyristorovým výstupem, s Darlingtonem, s Zero-Cross detekcí atd.), v pouzdrech s 1, 2 nebo 4 kanály (DIL)

### Používané modulace při přenosu izolovaného signálu
Aby bylo možné analogový biosignál přenést přes izolační bariéru (transformátor, optron), moduluje se na vhodný nosný signál:

- **Spojité analogové**: AM (amplitudová), FM (frekvenční), PM (fázová)
- **Spojité digitální**: ASK, FSK, PSK (BPSK, QPSK)
- **Diskrétní nekvantované**: PAM (pulzně amplitudová), **PWM** (pulzně šířková – velmi časté u izolačních zesilovačů, protože se snadno přenáší přes transformátor/optron a demoduluje filtrem DP), PPM (pulzně polohová)
- **Diskrétní kvantované**: **PCM** (pulzně kódová modulace – vzorkování, kvantování, kódování), DM, ADM, DPCM, ADPCM
- **Složené**: QAM, APSK

U izolovaných zesilovačů (např. Burr-Brown ISO122) se často používá kombinace napěťem řízeného oscilátoru + duty-cycle (PWM) modulace přenášené kapacitní/transformátorovou vazbou a synchronní demodulace (sample&hold) na druhé straně bariéry.

---

## 4. Aktivní a pasivní frekvenční filtr

### Definice a základní typy
Filtr = elektrický obvod, který definovaným způsobem omezuje frekvenční spektrum signálu.

| Typ | Zkratka | Použití |
|---|---|---|
| Dolní propust | DP (LP) | antialiasing, omezení šumu |
| Horní propust | HP | potlačení rušení (síť, nf), frekvenční výhybky |
| Pásmová propust | PP (BP) | vstupní/mf filtry přijímačů, kanálové filtry |
| Pásmová zádrž | PZ (BS, notch) | potlačení úzkopásmového rušivého signálu |

### Rozdělení podle provedení
- **Pasivní** – pouze z pasivních součástek (R, L, C, piezoelektrické prvky), bez zesílení, jednoduché, ale citlivé na zatížení zátěží
- **Aktivní** – navíc obsahují aktivní prvky (tranzistory, OZ, speciální IO) – umožňují realizovat strmé charakteristiky bez cívek (nevýhodných pro nízké kmitočty – velké, těžké), mají definovaný výstupní odpor, mohou signál i zesilovat

### Filtr typu notch (pásmová zádrž) v bioelektronice
- Nejčastější aplikace: **potlačení síťového rušení 50 Hz** (příp. 60 Hz) v biosignálech (EKG, EEG, EMG), kde je síťový brum indukován do měřicích kabelů a přes vysokou vstupní impedanci pacientských elektrod snadno naruší velmi malý biosignál
- Realizuje se typicky jako aktivní filtr s OZ (např. dvojité T-článek s OZ ve zpětné vazbě) – úzké pásmo potlačení kolem 50 Hz, minimální ovlivnění zbytku spektra
- Nevýhoda: notch filtr zkresluje i užitečné složky signálu blízko 50 Hz (harmonické EKG mohou zasahovat do této oblasti) – v moderních přístrojích se často nahrazuje digitálním zpracováním (adaptivní filtrace)

### Shrnutí požadavků pro bioelektroniku
- filtry musí mít lineární fázovou charakteristiku (aby nedeformovaly tvar biosignálu – např. QRS komplex)
- kombinace HP (odstranění stejnosměrné složky a driftu elektrod, ~0,05 Hz) + DP (odstranění vf šumu, antialiasing před A/D převodem) + notch (50 Hz)

---

## 5. Převod biosignálu do číslicové podoby

### Signál – základní dělení
- **Analogový** – spojitý v čase i amplitudě
- **Číslicový (digitální)** – diskrétní v čase i amplitudě
- Výhody digitálního zpracování: odolnost proti rušení, snadná rekonstrukce, zpracování mikroprocesorem/PC, uchování a komprese dat, téměř bezztrátová reprodukce
- Nevýhody: nutnost převodu (zpoždění, konečné rozlišení), u neelektrických veličin nutný mezipřevod na elektrickou veličinu (snímačem)

### A/D převodník (ADC)
Převádí spojitý (analogový) signál na diskrétní (digitální) signál vzhledem k referenční veličině. Dvě fáze:
1. **Vzorkování** – periodické odebírání vzorků v čase (vzorkovací frekvence f_vz)
2. **Kvantování** – přiřazení diskrétní hodnoty amplitudě (počet úrovní = 2^N, N = počet bitů)

**Aliasing** – nevratné zkreslení signálu vlivem podvzorkování (vzorkovací frekvence nesplňuje Shannon–Nyquistův teorém, f_vz < 2×f_max signálu). Řeší se **antialiasing filtrem** (dolní propust) zařazeným před ADC.

#### Typy A/D převodníků podle principu
| Typ | Rozlišení [bit] | Princip |
|---|---|---|
| Paralelní (komparační, flash) | 6–10 | nejrychlejší, 2^N−1 komparátorů pracujících současně, výsledek zapsán do DKO a dekodérem převeden na binární kód |
| Kompenzační s postupnou aproximací (SAR) | 8–16 | postupně nastavuje srovnávací (referenční) napětí přes D/A převodník a aproximační registr; nejběžnější typ v průmyslové elektronice |
| Integrační (s dvojitou integrací) | 10–27 | integruje nejprve vstupní napětí po konstantní čas t₁, pak referenční napětí po dobu t₂ úměrnou vstupnímu napětí; velmi přesný, pomalý; typicky v multimetrech |
| Sigma-delta | 16–24 | vysoké rozlišení, převzorkování a tvarování šumu; vhodný pro pomalé, přesné měření (např. váhy, přesná měření biosignálů) |

Podle připojení: s paralelním výstupem / se sériovým výstupem.

Hlavní parametry ADC: rozlišovací schopnost N [bit], maximální vzorkovací frekvence f_vz [vz/s].

Pro biosignály (EKG, EEG) je typické použití **sigma-delta nebo SAR převodníků** s vysokým rozlišením (12–24 bit) a vzorkovací frekvencí řádově stovky Hz až jednotky kHz, s předřazeným antialiasing filtrem.

### D/A převodník (DAC)
Zajišťuje opačný převod – z číslicové informace (datového slova) generuje analogový signál (napětí, méně často proud). Typické zapojení: vážené odpory (2^n R) spínané datovými bity, sečtené operačním zesilovačem (převodník proud→napětí).
- Hlavní parametry stejné jako u ADC (rozlišení, rychlost)
- Výstupní signál má schodovitý průběh (nutno vyhladit filtrem DP)
- Levnou náhradou DAC může být PWM modulátor + filtr DP

---

## 6. Použití logických obvodů v bioelektronice

### Základy číslicové techniky
Dvoustavové signály – logická '0' a '1'. **Pozitivní logika**: nižší napětí L = '0', vyšší H = '1' (opačně negativní logika). U TTL: H ≥ 2,4 V (výstup) / 2,0 V (vstup min.), L ≤ 0,4 V (výstup) / 0,8 V (vstup max.), mezi tím zakázané pásmo.

### Booleova algebra – základní zákony
Komutativní, asociativní, distributivní zákon; zákony o agresivnosti/neutrálnosti prvků 0 a 1; zákon vyloučení třetího; zákon dvojité negace; zákony absorpce; **De Morganovy zákony**: A+B = A·B a A·B = A+B (negace součtu/součinu).

### Kombinační logické obvody
Výstup závisí pouze na okamžité kombinaci vstupů (bez paměti).

- **Elementární hradla**: AND, NAND, OR, NOR, XOR, XNOR, invertor (NOT), opakovač – se svými pravdivostními tabulkami a standardizovanými značkami (americký MIL/ANSI, britský BS3939, IEC)
- **Dekodér** – převádí binární kód šířky k na kód 1 z N (N=2^k), signál E (Enable) povoluje výstup (např. 74LS138 3/8)
- **Multiplexor** – číslicový přepínač, na výstup propojí ten vstupní kanál, jehož adresu určují adresové vstupy (S0, S1…)
- **Číslicový komparátor** – porovnává dvě binární čísla A, B, výstupy A>B, A=B, A<B
- **Sčítačka/odčítačka** – aritmetický součet/rozdíl dvou čísel, se vstupem přenosu CI a výstupem přenosu CO

### Sekvenční logické obvody
Výstup závisí i na předchozím stavu (obvod obsahuje paměť) – dělí se na astabilní, monostabilní a bistabilní (klopné obvody).

- **RS klopný obvod** – nejjednodušší, ze 2 hradel NAND/NOR; S=Set, R=Reset; kombinace R=S=1 je zakázaný stav
- **JK klopný obvod** – bez zakázaného stavu, kombinace J=K=1 překlápí výstup (toggle)
- **T klopný obvod** – překlápí výstup při T=1 (dělička kmitočtu 2)
- **D klopný obvod** – realizuje jednobitovou paměť, aktivní hranou CLK zapamatuje hodnotu D na výstup Q; CE povoluje hodiny, CLR nuluje výstup (nejvyšší priorita)
- **Datový registr** – paralelní spojení DKO se společným CLK, uloží N-bitové slovo najednou
- **Posuvný registr** – sériové spojení DKO, při každé hraně CLK se obsah posune o krok, vstup SLI, výstup SRO (příp. i paralelní)
- **Binární čítač** – každou aktivní hranou CLK se zvýší (nebo sníží – DIR) binární hodnota na výstupu o 1; CE povoluje čítání, CLR nuluje

### Způsoby popisu logického obvodu
- **Pravdivostní tabulka** – výčet všech kombinací vstupů a odpovídajících výstupů
- **Logická (Booleova) funkce/rovnice** – algebraický zápis pomocí AND/OR/NOT
- **Logické (obvodové) schéma** – grafické znázornění pomocí normovaných značek hradel
- **Časový diagram (průběh)** – závislost logických úrovní na čase (typicky pro sekvenční obvody – CLK, D, Q…)
- **Karnaughova mapa** – grafická metoda minimalizace logické funkce (nezmíněno explicitně v podkladech, ale běžná doplňková metoda)
- **Stavový diagram/graf** – u čítačů a automatů znázorňuje přechody mezi jednotlivými stavy (viz binární čítač 0→1→2→…→F→0)

### Aplikace v bioelektronice
Logické obvody se v bioelektronických přístrojích využívají pro: řízení vzorkování a časování A/D převodníků, generování hodinových a synchronizačních signálů, realizaci čítačů (např. čítání tepové frekvence, časové základny), multiplexování více kanálů biosignálu na jeden A/D převodník, dekódování adres pro výběr kanálů/pamětí a řízení stavových automatů (sekvenční logika) v mikroprocesorových a vestavěných systémech přístroje.
