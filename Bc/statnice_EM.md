# Elektrická měření – vypracované státnicové okruhy

*Zpracováno na základě skript "Metody a měření v elektrotechnice 2.0"*

---

## 1. Chyby měření a nejistota

### 1.1 Chyba (odchylka) měření – základní pojmy

Přesnost měření se vyjadřuje chybou (odchylkou) měření.

- **Absolutní chyba**: Δ = X_M − X_S (X_M – naměřená hodnota, X_S – skutečná/konvenčně pravá hodnota). Má stejný rozměr jako měřená veličina.
- **Relativní (poměrná) chyba**: δ = Δ/X_M, vyjadřuje se v (–), v %, nebo v p.p.m. (parts per million, 10⁻⁶).

Ke skutečné hodnotě se lze přiblížit přesnějším přístrojem, přesnější metodou, nebo teoretickým výpočtem chyby.

Výsledek měření se zapisuje ve tvaru:

X_M = (X'_M − Δ_m) ± |Δ_U|

kde Δ_m je absolutní chyba metody a Δ_U absolutní chyba údaje přístroje.

### 1.2 Chyba nahodilá a systematická

V technické praxi se uvažují především dvě **soustavné (systematické)** chyby:
- **chyba metody** – vzniká už samotným zapojením měřicího přístroje do obvodu,
- **chyba měřicího přístroje** – daná nedokonalostí měřidla.

Vedle toho existují **chyby náhodné** (nahodilé), např. způsobené rušivými vlivy – jejich velikost a znaménko nelze predikovat, lze je jen statisticky omezit/popsat (viz nejistota typu A).

### 1.3 Chyba metody, její vznik a korekce

Chyba metody vzniká zejména:
- vnitřním odporem přístrojů (chybu lze přesně vypočítat včetně znaménka),
- zjednodušeným zapojením (chybu lze pouze odhadnout),
- zjednodušeným výpočtem (chybu lze pouze odhadnout).

**Měření napětí** – voltmetr s vnitřním odporem R_V zatěžuje zdroj s vnitřním odporem R₀:

U_V = U₀ · R_V/(R₀+R_V) ⟹ U₀ = U_V·(1 + R₀/R_V)

Absolutní chyba: Δ_M = U_V − U₀ = −U_V·R₀/R_V
Relativní chyba: δ_M = −(R₀/R_V)·100 (%)

Čím větší vnitřní odpor voltmetru, tím menší chyba metody (ideální voltmetr má R_V → ∞).

Obdobně u děliče napětí, kde voltmetr zatěžuje jeden z odporů děliče paralelní kombinací R_c = R₂·R_V/(R₂+R_V).

**Měření proudu** – ampérmetr s vnitřním odporem R_A zapojený do série sníží proud z I = U/R na I' = U/(R+R_A). Ideální ampérmetr má R_A → 0. Chyba metody může být i v řádu desítek procent, pokud je R_A srovnatelný s R.

**Korekce**: je-li chyba metody vypočitatelná (viz výše), naměřenou hodnotu o ni opravíme (odečteme Δ_m). Je-li jen odhadnutelná, volí se vhodnější zapojení (např. u měření odporu zapojení s ampérmetrem v sérii vs. voltmetrem paralelně k zátěži – volba dle poměru R vůči R_A, R_V).

### 1.4 Chyba (odchylka) měřicího přístroje

Chyba přístroje se zjišťuje **kalibrací** – porovnáním údaje kalibrovaného přístroje s přesnějším referenčním přístrojem. Z rozdílu se určí absolutní chyba a **korekce** K = −Δ_M (v jednotkách měřené veličiny), kterou lze vynést jako **korekční křivku** (závislost korekce na hodnotě na stupnici).

**Analogové přístroje** – chyba je dána **třídou přesnosti** (řada dle normy: 0,05; 0,1; 0,2; 0,3; 0,5; 1; 1,5; 2; 2,5; 3; 5 – vyjádřeno v %). Třída přesnosti udává maximální dovolenou chybu **vztaženou k rozsahu** přístroje (X_R), platí za definovaných **vztažných podmínek** (teplota, poloha, kmitočet, tvar křivky…).

Absolutní chyba: Δ_u = ±(δ_TP·X_R)/100
Relativní chyba vůči naměřené hodnotě: δ_u = ±δ_TP·(X_R/X_M)

→ z toho plyne, že relativní chyba analogového přístroje roste, čím dál je odečítaná hodnota od konce rozsahu (proto se doporučuje měřit v horní třetině stupnice).

#### 1.4.1 Vztažné podmínky

Třída přesnosti platí jen za vztažných podmínek (vztažná teplota ±2 °C, vztažná poloha, vztažný kmitočet, cos φ = 1 u wattmetru apod.). Mimo tento rozsah, v tzv. rozsahu použití, dochází k dovolené změně údaje (typicky o 100 % třídy přesnosti na definovaný interval, např. ±10 °C u teploty). Při nedodržení více podmínek současně se jednotlivé vlivy sčítají.

Speciální případ: u wattmetru, měřiče účiníku a ohmmetru se vztažné podmínky liší i typem povolené veličiny (u wattmetru lze měnit jen proud, měří přesně jen při cos φ = 1 nebo jmenovitém cos φ; při obecné zátěži se chyba zdvojnásobuje).

### 1.5 Chyby číslicových měřicích přístrojů

Chyba digitálního přístroje má **dvě složky** různého charakteru:

δ = ±(|δ₁| + |δ₂|)

- **δ₁ (MH, rdg – "of reading")** – relativní chyba vztažená k naměřené hodnotě X_M, nezávisí na rozsahu (dána nestabilitou vstupního děliče, referenčního zdroje, kmitočtu generátoru). Absolutní chyba Δ₁ roste lineárně s X_M.
- **δ₂ (MHMR, FS, ± digit/count/LSB)** – chyba vztažená k maximální hodnotě rozsahu X_R (dána chybou nuly zesilovačů, komparátoru, kvantizační chybou A/D převodníku). Absolutní chyba Δ₂ je v celém rozsahu konstantní – chová se jako chyba analogového přístroje z rozsahu.

Zápis: ±(0,05 % rdg + 1 digit) apod. Digit (jednotka na posledním místě displeje) se převádí na % takto: δ₂ = ±(dig/displej)·100.

Tyto základní chyby platí za vztažných podmínek a v určité době po kalibraci; mimo ně přistupují přídavné chyby (teplotní koeficient, časová stabilita).

### 1.6 Nepřímé měření

Je-li hledaná veličina Y = f(X₁,…,X_n) funkcí několika přímo měřených veličin, je maximální chyba dána **zákonem hromadění chyb**:

|Δ_T(Y)| = |∂Y/∂X₁|·|ΔX₁| + |∂Y/∂X₂|·|ΔX₂| + … + |∂Y/∂X_n|·|ΔX_n|

Relativní chyba: |δ_T(Y)| = |Δ_T(Y)|/Y

Praktická pravidla (odvozená z výše uvedeného zákona):

| Operace | Chyba |
|---|---|
| součet/rozdíl Y = X₁ ± X₂ | sčítají se **absolutní** chyby |
| součin/podíl Y = X₁·X₂ nebo X₁/X₂ | sčítají se **relativní** chyby |
| mocnina Y = Xⁿ | δ_Y = n·δ_X |
| násobek konstantou Y = n·X | Δ_Y = n·Δ_X, δ_Y = δ_X |

Příklad – výkon P = U·I: |δ_T(P)| = |δ_T(U)| + |δ_T(I)| (chyby se sčítají, protože jde o součin).

Složitější výraz se rozloží na dílčí jednoduché operace a chyba se počítá postupně (v každém kroku se volí výhodnější forma – absolutní/relativní).

### 1.7 Chyby rušivými vlivy

Vznikají působením rušivých činitelů v měřicím obvodu: rušivá napětí indukovaná cizím polem, parazitní kapacitní/indukční vazby, odpory spojovacích vodičů a přechodové odpory na svorkách, termoelektrická napětí, svodové odpory nedokonalé izolace apod. Mají soustavnou i nahodilou složku a jejich odhalení a korekce je obtížné, zvláště u složitých metod. (Nepatří sem rušivé vlivy působící přímo na přístroj – ty se počítají jako chyba údaje přístroje.)

### 1.8 Nejistota měření

Moderní přístup k vyjádření přesnosti (ISO/ČSN EN 60359) namísto "chyby a správné hodnoty" pracuje s pojmem **nejistota měření** – rozsah hodnot, v němž se s určitou pravděpodobností nachází měřená hodnota. Základní charakteristikou je **standardní nejistota u** (směrodatná odchylka).

#### 1.8.1 Standardní nejistota typu A (u_A)

Určuje se **statistickým zpracováním opakovaných měření** (analogie náhodné chyby). Nutno provést alespoň 10 opakování za stejných podmínek (jinak korekce koeficientem k_s).

Aritmetický průměr: x̄ = (1/n)·Σxᵢ

Výběrová směrodatná odchylka průměru:

u_A = √[ 1/(n·(n−1)) · Σ(xᵢ − x̄)² ]

Předpokládá se **normální rozdělení** – u_A odpovídá polovině šířky intervalu kolem x̄, v němž s pravděpodobností cca 68 % leží skutečná hodnota.

#### 1.8.2 Standardní nejistota typu B (u_B)

Vyhodnocuje se z mezní chyby měřicího přístroje (dle specifikace výrobce, tj. třídy přesnosti / digitální chyby) a volby typu rozdělení. Nejčastěji se volí **rovnoměrné rozdělení**:

u_B = Δx/√3

kde Δx je interval, v němž leží všechny hodnoty měřené veličiny (vypočtený stejně jako klasická chyba přístroje z třídy přesnosti apod.). Pro rovnoměrné rozdělení odpovídá u_B pravděpodobnosti pokrytí cca 58 %.

#### 1.8.3 Kombinovaná a rozšířená nejistota

Kombinovaná standardní nejistota (geometrický součet):

u_C = √(u_A² + u_B²)

Rozšířená nejistota:

U = k·u_C

Koeficient rozšíření k se volí podle požadované pravděpodobnosti pokrytí a typu rozdělení:
- normální rozdělení, 95 % → k = 2
- normální rozdělení, 99,7 % → k = 3
- rovnoměrné rozdělení, 95 % → k = 0,95·√3 ≈ 1,65

Pokud je přítomna jak u_A, tak u_B, volí se zpravidla k = 2 (výsledné rozdělení se blíží normálnímu). Pokud se u_A neuvažuje a převažuje rovnoměrné rozdělení u_B, volí se k = 1,65.

Výsledek měření se zapisuje jako x̄ ± U, s poznámkou, že uvedená rozšířená nejistota je součinem standardní nejistoty a koeficientu rozšíření k, což odpovídá dané pravděpodobnosti pokrytí (typicky 95 %).

#### 1.8.4 Nejistota nepřímých měření

Pro Y = f(X₁,…,X_N) platí **zákon šíření nejistot** (na rozdíl od teorie chyb se nejistoty skládají **geometricky**, nikoli aritmeticky):

u_y² = Σᵢ (∂f/∂xᵢ)² · u_xᵢ²

U součinu/podílu se tedy relativní nejistoty sčítají geometricky: u_R = √(u₁² + u₂²) (namísto aritmetického součtu jako u chyb).

**Shrnutí rozdílu teorie chyb vs. teorie nejistot:** teorie chyb pracuje s nejhorším možným (aritmetickým) součtem chyb → dává "bezpečnější" (širší) interval; teorie nejistot pracuje s pravděpodobnostním (geometrickým) skládáním → dává užší, realističtější interval s danou pravděpodobností pokrytí.

---

## 2. Měření výkonu

### 2.1 Výkon obecně a jeho typy

Ve stejnosměrném obvodu: **P = U·I** (W).

Ve střídavém obvodu se rozlišují tři výkony:
- **okamžitý výkon**: p(t) = u(t)·i(t)
- **činný výkon** P – střední hodnota okamžitého výkonu za periodu: P = (1/T)∫p(t)dt; pro harmonický průběh: **P = U·I·cos φ** (W)
- **jalový výkon**: **Q = U·I·sin φ** (var)
- **zdánlivý výkon**: **S = U·I** (VA), je maximální hodnotou střídavé složky p(t)

Vztah mezi výkony: S² = P² + Q² ⟹ S = √(P² + Q²)

Zdánlivý výkon je roven činnému pouze u čistě odporové zátěže (bez reaktanční složky).

### 2.2 Výkon ve stejnosměrném obvodu

Analogie měření odporu – zapojení buď s ampérmetrem v sérii, nebo s voltmetrem paralelně k zátěži; vnitřní odpory přístrojů (resp. cívek wattmetru) způsobují chybu metody vypočitatelnou stejným způsobem jako u měření odporu.

Přímé měření: **wattmetr** – jediné analogové ústrojí schopné násobení je **elektrodynamické ústrojí** (pevná + otočná cívka), jehož výchylka je úměrná M_p ~ I₁·I₂ ~ U·I (u DC), resp. střední hodnotě u(t)·i(t) = U_ef·I_ef·cos φ = P (u AC).

Elektronické wattmetry provádějí násobení jinak, např.:
- **modulační (TDM) násobička** – amplitudově-šířková modulace obdélníkového signálu, integrační článek získá střední hodnotu úměrnou součinu okamžitých hodnot; chyba v desetinách % do cca 10 kHz,
- **Hallova násobička** – Hallovo napětí u_H ~ k·i·B, po integraci úměrné činnému výkonu.

### 2.3 Měření jednofázového výkonu

**Činný výkon** (5.3.1.1): přímé měření wattmetrem, zapojení analogické měření odporu – buď proudová cívka v sérii se zátěží, nebo napěťová cívka paralelně se zátěží. Volba zapojení ovlivňuje chybu metody:

- zapojení a): P_a = P'_W − ΔP_pW = P'_W − R_pW·I_Z² (chyba od proudové cívky)
- zapojení b): P_b = P'_W − ΔP_nW = P'_W − U_Z²/R_nW (chyba od napěťové cívky)

**Jalový výkon** v jednofázové síti: princip – natočit napětí na napěťové cívce wattmetru o 90° vůči napětí na zátěži (proud pootočit nelze, prochází zátěží). Realizace: RC fázovací člen (posuv 90° jen pro dané napětí, obvod nemusí být výkonový), nebo u souměrného 3f zdroje využití toho, že sdružené napětí mezi zbylými dvěma fázemi je vůči fázovému napětí měřené fáze posunuto přesně o 90° – naměřený výkon je pak √3× větší a je nutno přepočítat (varmetry mají dělení již zabudováno).

### 2.4 Měření výkonu v třífázové síti

Činný výkon: P = U₁I₁cos φ₁ + U₂I₂cos φ₂ + U₃I₃cos φ₃

**Blondelův teorém**: v n-vodičové soustavě lze činný výkon obecné zátěže při obecné soustavě napětí (i nesinusového průběhu) správně změřit nejméně (n−1) wattmetry.

Konfigurace:
- **4vodičová síť (dostupný N), obecná zátěž** – 3 wattmetry, napěťové cívky na fázová napětí, součet údajů = celkový výkon.
- **4vodičová síť, souměrná zátěž** – stačí 1 wattmetr × 3.
- **3vodičová síť (bez N), obecná zátěž** – **Aronovo zapojení**, 2 wattmetry (n−1 = 2): proudové cívky ve dvou fázích, napěťové cívky vztaženy ke třetí fázi; P = P_A1 + P_A2 (funguje i při nesouměrné soustavě/zátěži).

**Jalový výkon** ve 3f síti: měří se buď přímo varmetry, nebo wattmetry v zapojení s posunutým napětím o 90°:
- souměrný zdroj, obecná zátěž – 3 wattmetry se sdruženým napětím ze zbylých fází, součet údajů se dělí √3,
- obecný zdroj, obecná zátěž – nutný blok fázového posuvu 90° pro všechny wattmetry,
- souměrný zdroj, souměrná zátěž – modifikované Aronovo zapojení s uměle vytvořenou nulou (odpor R_nW), Q_Ac = √3·(Q_AW1 − Q_AW2).

Celková chyba přístrojů se u jalového výkonu dělí √3, u Aronova zapojení násobí √3 (vícesystémové varmetry mají korekci již v sobě zahrnutou).

### 2.5 Účiník a fázový posun

Účiník cos φ vyjadřuje poměr činného a zdánlivého výkonu (cos φ = P/S). Měří se buď **měřičem účiníku** (elektrodynamické poměrové ústrojí), nebo výpočtem z naměřených P, Q, S, případně přímo odečtem fázového posunu φ mezi napětím a proudem (např. z osciloskopu – měřítko časové základny umožní přepočet časového posunu na úhlový, nebo z fázorového diagramu vypočteného z arkustangens Q/P).

### 2.6 Chyba metody při měření výkonu

Vzniká vnitřní spotřebou (odporem) proudové a/nebo napěťové cívky wattmetru, obdobně jako u měření odporu – viz vztahy P_a, P_b výše. Volba zapojení (proudová cívka v sérii vs. napěťová cívka paralelně) se řídí poměrem odporu zátěže vůči vnitřním odporům cívek (analogie malých/velkých odporů). Při nepřímém měření (U, I → P = U·I) je celková chyba přístrojů dána součtem relativních chyb voltmetru a ampérmetru (pravidlo pro součin u nepřímých měření).

### 2.7 Měření výkonu vzorkováním

Číslicové (elektronické) wattmetry a měřicí karty využívají principu **digitalizace** okamžitých hodnot napětí a proudu. Napěťový a proudový signál (proud převeden na napětí bočníkem/proudovým transformátorem) jsou současně (synchronně) vzorkovány dvěma kanály A/D převodníku s dostatečnou vzorkovací frekvencí (dle vzorkovacího teorému, s rezervou pro harmonické složky nesinusového průběhu). Z diskrétních vzorků u[k], i[k] se číslicově počítá:

- okamžitý výkon v jednotlivých vzorcích: p[k] = u[k]·i[k]
- činný výkon jako aritmetický průměr přes celou periodu (resp. celočíselný počet period): P ≈ (1/N)·Σp[k]
- efektivní hodnoty U, I ze vzorků (TRMS výpočet), zdánlivý výkon S = U·I, jalový a účiník dopočtem.

Výhodou je přesné měření i při nesinusových (zkreslených) průbězích, možnost současného výpočtu více veličin (harmonická analýza, THD) a uložení průběhu pro další zpracování. Přesnost je dána bitovou hloubkou a linearitou A/D převodníku, synchronizací obou kanálů (fázová chyba mezi kanály se projeví jako chyba cos φ) a dodržením vzorkovacího teorému (jinak aliasing zkresluje výsledek).

---

## 3. Konverze měřicího signálu

### 3.1 Proces vzorkování, kvantování a kódování

Převod spojitého analogového signálu na číslicový tvar probíhá ve třech krocích:

1. **Vzorkování (sampling)** – spojitý signál je v pravidelných časových okamžicích (perioda T_vz = 1/f_vz) nahrazen diskrétními hodnotami (vzorky). Signál je diskrétní v čase, ale stále spojitý v amplitudě.
2. **Kvantování (quantization)** – spojitý rozsah amplitud se rozdělí na konečný počet **kvantizačních úrovní** (kroků) a každému vzorku se přiřadí nejbližší úroveň. Vzniká tak **kvantizační chyba**, rovná polovině kvantizačního kroku.
3. **Kódování (coding)** – přiřazené kvantizační úrovni se přiřadí binární číslo (kód), obvykle b-bitové.

Velikost kvantizačního kroku: X_K = X_R/(2^b − 1), kde X_R je rozsah vstupního napětí a b počet bitů A/D převodníku.
Kvantizační chyba: Δ_K = ±½·X_K, relativně δ_K = ±Δ_K/X_R·100.

Čím více bitů, tím menší kvantizační krok a přesnější převod (např. 8bitový převodník na rozsahu 10 V: X_K ≈ 39,2 mV; 12bitový: X_K ≈ 2,44 mV).

### 3.2 Vzorkovací teorém

Aby bylo možné ze vzorků beze ztráty informace zrekonstruovat původní spojitý signál, musí být vzorkovací frekvence f_vz alespoň dvojnásobkem nejvyšší kmitočtové složky obsažené v signálu (Shannon–Nyquistův vzorkovací teorém):

f_vz ≥ 2·f_max

Není-li teorém dodržen (podvzorkování), dochází k jevu **aliasing** – ve vzorcích se objeví falešný (nesprávný, nižší) kmitočet, protože vysokofrekvenční signál je nesprávně interpretován jako signál s nižší frekvencí. U digitálních osciloskopů se poměr vzorkovací frekvence a horní mezní frekvence přístroje používá jako kritérium vhodnosti pro zobrazení jednorázových dějů (poměr ≥ 4 – lze zobrazovat i neopakující se děje) nebo jen periodických dějů (poměr < 1 – nutné použít režim opakovaného vzorkování, sběr vzorků postupně během několika period).

Prakticky se před vzorkováním používá **antialiasingový (dolnopropustní) filtr**, který omezí šířku pásma signálu pod f_vz/2.

### 3.3 Princip činnosti základních typů A/D převodníků

| Typ | Princip | Doba převodu | Bitová hloubka | Vlastnosti |
|---|---|---|---|---|
| **Kompenzační se schodovitým napětím** | Komparátor srovnává U_x s postupně (schodovitě) rostoucím referenčním napětím z generátoru schodovitého napětí (GSN); čítač počítá impulsy, dokud je U_ref < U_x | závisí na velikosti U_x (roste s ní) | – | jednoduchý, pomalejší |
| **Kompenzační s postupnou aproximací (SAR)** | Postupné nastavování bitů registru od MSB k LSB, D/A převodník generuje referenční napětí, komparátor rozhoduje o ponechání/zrušení bitu | konstantní, nezávislá na U_x, řádově desítky ms | 8–16 bitů | nejsou odolné proti sériovému rušení |
| **Komparační (paralelní, "flash")** | Současné srovnání U_x se všemi úrovněmi najednou pomocí 2^b−1 komparátorů | velmi krátká, 0,5 ns až stovky ns | 6–10 bitů | nejrychlejší, ale drahé (exponenciální nárůst počtu komparátorů s bity) |
| **Integrační s dvojí integrací** | Integrace U_x po pevnou dobu T₁, poté integrace opačně polárního U_ref do nuly (doba T₂ úměrná U_x) | pomalá, 100–200 ms | až 18 bitů | vysoká přesnost, odolnost proti síťovému rušení 50 Hz (T₁ = 20 ms nebo násobek) |

Srovnání rychlost vs. přesnost: integrační (nejpomalejší, nejpřesnější) → kompenzační s aproximací (střední) → paralelní (nejrychlejší, nejméně bitů).

### 3.4 Zpětná rekonstrukce signálu

Číslicové vzorky se pomocí **D/A převodníku** převedou zpět na analogové (schodovité) napětí; následným **rekonstrukčním (vyhlazovacím, dolnopropustním) filtrem** se odstraní vysokofrekvenční schodovité složky (vzorkovací kmitočet a jeho násobky) a získá se opět spojitý průběh. Podmínkou věrné rekonstrukce je opět dodržení vzorkovacího teorému při snímání signálu.

### 3.5 Přivedení digitalizovaného signálu do počítače

- **Měřicí karta** – zasunuta do PC (nebo externí), obsahuje vstupní multiplexer (postupné připojování kanálů), programově řízený zesilovač, vzorkovač s pamětí a A/D převodník; může obsahovat i D/A převodníky, digitální (TTL) vstupy/výstupy a čítače/časovače. Typické parametry: vstupní rozsah (0–5 V, 0–10 V, ±5 V…), počet kanálů, zesílení, šířka výstupního slova (8–24 bitů), vzorkovací rychlost (desítky kHz až jednotky MHz).
- **Komunikační rozhraní k externímu přístroji** – paralelní sběrnice **GPIB** (General Purpose Interface Bus, IEEE-488, zavedeno 1965, standard rozvíjený firmou National Instruments), dále sériová rozhraní RS232, USB, Ethernet.
- **VXI sběrnice** (od 1987) – modulární systém (VXI mainframe, max. 13 pozic), na pozici 0 buď vestavěný PC, nebo konvertor GPIB–VXI pro připojení externího PC; ostatní pozice obsazeny měřicími moduly (A/D, D/A, digitální I/O, osciloskop, čítač…) bez vlastního čelního panelu. Výhody: rychlá 32bitová VME sběrnice (vysoká propustnost, přesné časování), vysoká integrace (delší MTBF), otevřený průmyslový standard, podpora softwarové vrstvy.
- Software pro tvorbu **virtuálních měřicích přístrojů** (např. LabVIEW) – funkce přístroje určuje uživatel programem, hardware (karta) slouží jen ke sběru dat.

---

## 4. Měření pasivních elektrických prvků

### 4.1 Volba metody s ohledem na velikost prvku, pracovní bod a kmitočet

Volba metody závisí na tom, zda je hodnota prvku závislá na pracovním bodě (velikost proudu, kmitočet). Není-li závislost významná → jednoduché měření ohmmetrem / RLC měřičem. Je-li závislost významná (typicky tlumivky se železným jádrem) → nutno měřit **Ohmovou metodou** (ampérmetr + voltmetr, u impedancí doplněné wattmetrem pro činnou složku) přímo v provozním pracovním bodě (správný proud, kmitočet), protože měření malým proudem/stejnosměrně nepostihne např. ztráty v železe.

Podle velikosti odporu se rozlišuje:
- **malé odpory** – srovnatelné s odporem přívodů a přechodovými odpory svorek,
- **velké odpory** – srovnatelné s izolačním (svodovým) odporem,
- **střední odpory** – mezi těmito extrémy.

### 4.2 Měření rezistorů (odporu)

**Ohmmetr** – přímá metoda:
- **2vodičové (2W)** zapojení – běžné multimetry, odpor přívodů a přechodové odpory zanedbatelné jen u větších hodnot R; některé multimetry umožňují relativní měření (vynulování odporu přívodů).
- **4vodičové (4W)** zapojení – oddělený budicí (proudový) a měřicí (napěťový) okruh; napájecí proud je přesný a nezávislý na R_x, úbytky na přívodech měřicího okruhu jsou zanedbatelné (I_V ≪ I) → umožňuje přesně měřit i velmi malé odpory.

**Nepřímá Ohmova metoda** (U, I): dvě možná zapojení stejná jako u obecného měření napětí/proudu:
- ampérmetr v sérii se zátěží: R' = U_V/I_A, chyba metody Δ_ma = R_A (odpor ampérmetru), korekce R = R' − R_A,
- voltmetr paralelně se zátěží: R' = U_V/I_A, chyba metody Δ_mb = (R')²/(R' − R_V), obvykle výrazně menší než u prvního zapojení pro malé R.

Volba zapojení: pokud se neprovádí korekce, volí se zapojení s menší chybou metody (poměr R vůči R_A resp. R_V).

Celková chyba přístrojů (nepřímé měření – podíl) = součet relativních chyb voltmetru a ampérmetru (viz kap. 1).

### 4.3 Měření impedance

Analogické zapojení jako u odporu, ale zdroj střídavý. Komplikace: napětí a proud na impedanci nejsou ve fázi, takže úbytky na vnitřních odporech přístrojů nejsou ve fázi s měřenou veličinou → nutno uvažovat vektorový (fázorový) součet; velikost chyby metody lze proto většinou jen odhadnout (známe-li fázový úhel zátěže).

Impedance je popsána dvěma parametry (Z a φ, nebo R a X, nebo L/C a Q/D) → další chyba metody vzniká měřením činné složky (odporu vinutí) stejnosměrně, zatímco prvek bude provozován střídavě (u cívky se železným jádrem se tak nepostihnou ztráty v železe) – tuto chybu nelze vypočítat, lze ji jen odstranit volbou vhodné metody/kmitočtu/proudu odpovídajícího provozu.

Výpočet: Z = U/I; Z² = R_x² + X_Lx² ⟹ X_Lx = √(Z² − R_x²); L = X_Lx/(2πf)

### 4.4 Měření parametrů cívek a tlumivek

U tlumivek (cívky s feromagnetickým jádrem) závisí parametry na proudu i kmitočtu → nelze měřit LCR měřičem ani stejnosměrně (tím se změří jen odpor vinutí). Ekvivalentní odpor R_x (vinutí + ztráty v jádře) se určuje ze zapojení A-V-W (ampérmetr, voltmetr, wattmetr):

R_x = P/I² (bez korekce), nebo s korekcí na chybu metody: R_x = (P' − U²/R_nW)/I² (napěťová cívka wattmetru) resp. odečtením ΔP = R_pW·I² (proudová cívka).

### 4.5 Rezonanční metoda měření indukčnosti a kapacity

Používá se pro cívky pracující od stovek kHz výše. Měřená cívka L_x je zapojena paralelně s kapacitní dekádou C_N; při rezonanci (X_L = X_C) je impedance paralelního obvodu maximální a proud do obvodu minimální (indikace ampérmetrem/voltmetrem). Z Thomsonova vztahu:

f_r = 1/(2π√(L·C)) ⟹ L_x = 1/(ω²·C_N)

Na tomto principu pracují také **Q-metry**, které navíc měří činitel jakosti cívky Q a ztrátový úhel/činitel rozptylu D kondenzátorů.

### 4.6 Číslicové LCR měřiče, RLC můstky

Moderní číslicové LCR měřiče (a klasické střídavé můstky, např. Wheatstoneův pro R, Wienův/Maxwellův pro L, C) měří přímo hodnotu prvku při zvolené měřicí frekvenci a napájecím napětí/proudu; umožňují volbu náhradního schématu (sériové/paralelní R-C, R-L) a zobrazují i doplňkové parametry (Q, D, ESR). Je nutné volit měřicí frekvenci a úroveň signálu odpovídající skutečnému pracovnímu bodu prvku, jinak vzniká systematická chyba metody.

### 4.7 Měření malých odporů

Řeší se **čtyřvodičovým (4W)** zapojením – budicí (proudový) okruh odděleně od měřicího (napěťového) okruhu. Napájecí proud je dodáván přesným proudovým zdrojem, není ovlivněn velikostí R_x; úbytky napětí na přívodních a přechodových odporech měřicího okruhu jsou zanedbatelné, protože jím protéká zanedbatelný proud (I_V ≪ I). Umožňuje měřit i odpory menší, než je odpor přívodních vodičů.

### 4.8 Měření velkých odporů

Jde o nepřímé měření Ohmovou metodou (U, I), obvykle se zapojením voltmetru přímo na zdroj (kvůli velmi malému proudu, řádově pA, se měří piko-ampérmetrem). Kvůli srovnatelnosti měřeného odporu s izolačním odporem vodičů je nutné celé zapojení **stínit a zemnit**, aby se neuplatnil svodový proud. Volba zapojení (a chyba metody) vychází ze stejných principů jako v kap. 1.1 a 4.2.

### 4.9 Náhradní schéma prvku a měření jeho částí

Reálný prvek lze nahradit náhradním elektrickým schématem zahrnujícím parazitní vlastnosti (u cívky – sériový odpor vinutí R_s a při vyšších kmitočtech paralelní parazitní kapacita mezi závity; u kondenzátoru – sériový ztrátový odpor ESR a svodový odpor izolace paralelně ke kapacitě). Jednotlivé prvky náhradního schématu lze měřit odděleně vhodnou kombinací metod (např. R_s stejnosměrně/ohmmetrem, X při provozním kmitočtu wattmetrovou nebo rezonanční metodou, svodový/izolační odpor metodou pro velké odpory) – volba vždy závisí na kmitočtovém pásmu a pracovním bodě, ve kterém bude prvek reálně provozován.
