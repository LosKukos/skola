# Měření na elektronických přístrojích – vypracované otázky

---

## 1. Měření změn odporu v biomedicíně můstkovými metodami, Wheatstoneův můstek, měření U/I/R multimetrem, zvětšení rozsahu voltmetru a ampérmetru

### Wheatstoneův můstek
- Slouží k přesnému měření odporu **nepřímo**, porovnáním se známými odpory.
- Zapojení: čtyři odpory R1, Rx, R2 (proměnný), R3 do kosočtverce, do jedné úhlopříčky zdroj, do druhé indikátor (galvanometr/voltmetr).
- Vyvážení můstku (U mezi C a D = 0) nastane při: **R1·R3 = R2·Rx** (podle značení ve slajdu: poměr ramen).
- V biomedicíně se používá pro **měření malých změn odporu** (např. tenzometry, snímače tlaku, teploty) – jedno rameno tvoří snímač Rx, ostatní jsou pevné/nastavitelné odpory.
- Pro zesílení malého rozdílového signálu z můstku se používá:
  - **Rozdílový (diferenční) zesilovač** – zesiluje rozdíl napětí mezi dvěma uzly můstku vůči zemi.
  - **Přístrojový zesilovač (instrumentation amplifier)** – kombinace dvou vstupních zesilovačů + rozdílového zesilovače na výstupu, vyšší vstupní impedance a lepší potlačení souhlasného signálu (CMRR) než prostý rozdílový zesilovač.

### Ohmmetr obecně
- Obsahuje zdroj napětí/proudu, který připojí k měřenému odporu, odpor se určí nepřímo R = U/I.
- Používá se pro měření malých odporů a pro můstková měření.
- Pro velmi velké odpory (izolační stavy, GΩ) se používá **gigaohmmetr** (zdroj cca 1 kV), pro velmi malé odpory (mΩ) **miliohmmetr** (proudový zdroj cca 10 A, U = R·I).
- **Pikoampérmetr** lze podle Ohmova zákona využít jako gigaohmmetr – proud v řádu pA přes rezistor 1 GΩ dá napětí v řádu mV; je nutné řešit šumové napětí rezistoru (u_š = √(4kTRf)) a paralelní kompenzační kapacitu k omezení šířky pásma šumu.

### Měření vnitřního odporu zdroje
- Vyžaduje dvě měření (na prázdno a se zátěží, nebo se dvěma různými zátěžemi):
  - Ri = Ui/I2 = (U0 − U2)/I2 (měření naprázdno + zatížené)
  - Ri = ΔU/ΔI = |U1 − U2| / |I1 − I2| (dvě různé zátěže)
- Čím menší Ri, tím „tvrdší" zdroj (menší pokles svorkového napětí při zátěži).

### Voltmetr
- Měří rozdíl potenciálů – **připojuje se paralelně** k měřenému místu.
- Ideální vnitřní odpor je nekonečný; nedostatečný vnitřní odpor způsobuje chybu metody a zatěžuje měřené místo.
- Měření velkých napětí → **předřadník** (sériový odpor Rp).
- Měření malých napětí → zesilovač.
- Střídavá napětí (efektivní hodnoty): magnetoelektrické měřidlo s usměrňovačem, elektromagnetické měřidlo, operační usměrňovač + voltmetr, VF sonda (do GHz).

### Ampérmetr
- Měří procházející proud – zařazuje se **sériově** do obvodu.
- Ideální vnitřní odpor je nulový; nenulový odpor způsobuje chybu metody a úbytek napětí.
- Měření velkých proudů → **bočník** (paralelní odpor Rb).
- Měření malých proudů → zesilovač.

### Zvětšení měřicího rozsahu – výpočet (příklad ze slajdů)
- **Předřadník** (V-metr 200 mV / 500 Ω → rozsah 20 V): Up = 19,8 V při Iv = 400 µA, Rp = 49,5 kΩ.
- **Bočník** (A-metr 10 mA / 5 Ω → rozsah 10 A): Ib = 9,99 A při Ua = 50 mV, Rb = 5,005 mΩ.
- Předřadník bývá "obyčejný" rezistor – nutno hlídat jeho max. provozní napětí.

### Chyba metody u nepřímého měření výkonu (analogie pro U/I měření)
- Zapojení s ampérmetrem blíž ke zdroji (proudová chyba) vs. zapojení s voltmetrem blíž ke zdroji (napěťová chyba) – u obou vzniká systematická chyba metody danou vnitřní spotřebou přístroje, kterou lze korigovat, pokud známe Rv (odpor voltmetru) resp. RA (odpor ampérmetru).

### Multimetry
- **Ručkové** i **číslicové**; měří ss/stř. U, I, odpor, případně kapacitu a další veličiny.
- Svorky pro měření U a I bývají **oddělené** – svorka pro velké proudy nemá pojistku (trvale připojený bočník ke svorce COM), svorka pro malé proudy pojistkou chráněna bývá.
- Ručkové: magnetoelektrická soustava s usměrňovačem, cejchovány v efektivních hodnotách (platí jen pro sinusový průběh); při neznámé velikosti se volí nejprve největší rozsah a postupně snižuje, aby výchylka byla v horních 2/3 stupnice.
- Číslicové: elektronická měřicí soustava, výsledek na LCD, ruční/automatické přepínání rozsahu, A/D převodník, převod měřené veličiny na napětí, velký vstupní odpor, perioda měření obvykle 0,5 s, bargraf.
- Blokové schéma: přepínač rozsahů (dělič) → vstupní zesilovač → A/D převodník → paměť/displej.

### Chyby měření (obecný rámec, relevantní i zde)
- Absolutní chyba: ΔX = XM − XP; relativní chyba δ = ΔX/XP (v %, nebo ppm).
- **Systematické chyby** – stále stejné znaménko a velikost, lze je určit a korigovat (chyba metody, chyba nuly, chyba zesílení).
- **Náhodné chyby** – nelze odstranit korekcí, minimalizují se statisticky (aritmetický průměr, směrodatná odchylka).
- **Třída přesnosti** analogového přístroje: δTP = |ΔP|/XR · 100 [%], řada 0,05–0,1–0,2–0,5–1–1,5–2,5–5. Pro minimální chybu má být měřená hodnota co nejblíže hornímu konci rozsahu.
- U **digitálního** přístroje: F = k·M/100 + z·l (k = třída přesnosti v %, M = zobrazená hodnota, z = odchylka poslední číslice, l = rozlišitelnost displeje).
- Typy chyb měřicích přístrojů: multiplikativní, aditivní, chyba linearity, chyba reverzibility (hystereze).

---

## 2. Použití analogového a číslicového osciloskopu v biomedicíně, časová základna, nastavení spouštění, ruční nastavení pro defibrilační impuls, sonda

### Princip analogového osciloskopu
- Vytváří na stínítku CRT čárový graf časového průběhu napětí.
- Elektronový paprsek vychylují na sebe kolmé systémy: X (časová základna – pilovitý signál) a Y (měřený signál).
- Části CRT: elektronové dělo (žhavená katoda), svazek elektronů, zaostřovací cívky, vychylovací elektrody, luminoforová vrstva stínítka.
- Zpětný chod paprsku je zatemněn.
- Dvoukanálové zobrazení: DUAL (přepínání kanálů) nebo ADD (součet), případně dvoupaprskový osciloskop.

### Časová základna v biomedicíně (bioosciloskop)
| Signál | Rychlost |
|---|---|
| Trend | 25 mm/hod |
| Gastrogram, tokogram | 25 mm/min |
| Kardiogram, EEG | 25 mm/s |
| Myogram | 250 mm/s |
| Kardiostimulace | 2,5 mm/ms |

- Režim XY (Orthoskop): tokokorelogram (časové značky po 3 s), vektorkardiogram (jasová modulace po 1 ms).

### Spouštění časové základny (triggering)
- Bez vstupního signálu běží časová základna volně dle nastavení TIME/DIV, na obrazovce vodorovná čára.
- **Triggering** = spouštění časové základny synchronizované vstupním signálem – zajišťuje stabilní (nepohyblivý) obraz.
- Může být **vnitřní** (odvozený ze zobrazovaného signálu v osciloskopu) nebo **vnější** (taktovací signál na konektor TRIG.INP.).
- Klíčové ovládací prvky:
  - **LEVEL** – úroveň (napětí) signálu, při které dojde ke spuštění.
  - **SLOPE (+/−)** – volba náběžné, nebo sestupné hrany signálu pro spuštění.
  - Volba vazby spouštění: AC/DC/HF/LF/LINE (LINE = synchronizace se síťovým kmitočtem 50 Hz).
- Pro **ruční nastavení spouštění na jednorázový defibrilační impuls** (jde o neperiodický, vysokoenergetický, krátký děj):
  - Použije se **jednorázový (single/normal) režim spouštění** místo automatického, aby osciloskop nečekal na periodický signál.
  - Nastaví se **LEVEL** na úroveň odpovídající náběhu impulsu (nad úroveň klidového šumu, pod očekávanou amplitudu impulsu).
  - Zvolí se vhodná **SLOPE** (+ pro nástupnou hranu impulsu).
  - Pro zachycení jednorázového děje je nutný **paměťový (digitální) osciloskop**, který uloží průběh i po jediném spuštění (analogový paměťový osciloskop uměl totéž speciální technologií stínítka).
  - Časová základna (TIME/DIV) se nastaví podle očekávané délky impulsu, aby byl celý průběh vidět na obrazovce.

### Obsluha osciloskopu – klíčové prvky
- FOCUS – zaostření paprsku, INTENSITY – jas.
- AC/DC/GND přepínač vstupu – potlačení stejnosměrné složky / úplný signál / zemnění vstupu.
- X-POS, Y-POS – posun obrazu.
- VOLT/DIV – citlivost vertikálního zesilovače.
- Při měření musí být všechny knoflíky jemného nastavení (VAR) v poloze **CAL** (kalibrováno), jinak neplatí stupnice VOLT/DIV a TIME/DIV.

### Osciloskopické sondy
- **Aktivní vs. pasivní** sondy.
- Klíčové parametry: **vstupní impedance**, **vstupní kapacita** → společně určují **frekvenční rozsah** sondy.
- Typická pasivní sonda 10:1 – dělič tvořený odporem sondy (např. 9 MΩ) a vstupním odporem osciloskopu (1 MΩ), kompenzační kapacita (C_comp) se ladí proti vstupní kapacitě osciloskopu.
- **Kalibrace sondy** – přivedením obdélníkového kalibračního signálu se seřídí kompenzační kapacita tak, aby hrany byly ostré (bez zaoblení = podkompenzováno, bez překmitu = překompenzováno).

### Digitální osciloskop – shrnutí
- Výhody: zobrazuje parametry signálu (Umax/min, mezivrcholová hodnota, efektivní hodnota…), vyšší přesnost, přenos dat do PC.
- Nevýhody: složitost, riziko aliasingu (podvzorkování).
- Hlavní parametry: počet kanálů, šířka pásma, hloubka záznamové paměti, max. vzorkovací frekvence, typ displeje, doplňkové funkce, cena.

---

## 3. Měření časových charakteristik signálu osciloskopem – amplituda, frekvence, fáze, doba náběžné/sestupné hrany, režim XY, Lissajousovy křivky

### Základní měření osciloskopem
- **Napětí (amplituda)**: odečet z Y osy × VOLT/DIV (počet dílků svisle mezi zvolenými body – špička-špička, nebo amplituda vůči nule).
- **Kmitočet**: odečet periody T z X osy (počet dílků × TIME/DIV), f = 1/T.
- **Fáze**: u dvou signálů na společné časové základně se určí časový posun Δt mezi odpovídajícími průchody nulou/hranami a přepočte na úhel φ = 360°·Δt/T; nebo pomocí Lissajousových obrazců (viz níže).
- **Doba náběžné/sestupné hrany**: měří se čas mezi úrovněmi 10 % a 90 % (případně 0–100 %) amplitudy přechodu signálu, odečtený z X osy pomocí jemného TIME/DIV rozsahu (často se zvětší časová základna, aby hrana vyplnila obrazovku).
- Měření nelineárního zkreslení – porovnání tvaru výstupního obdélníkového signálu s ideálem (rezonanční zákmity, útlum na vysokých/nízkých kmitočtech – viz obrázek zkreslených obdélníkových kmitů ve slajdech).
- Diagnostika el. zařízení porovnáním signálů v testovacích bodech, zobrazení převodních charakteristik, zobrazení frekvenčních charakteristik pomocí rozmítacího generátoru (wobbleru) – rozmítání kmitočtu = jeho periodická změna, velikost změny = **kmitočtový zdvih**; po usměrnění a filtraci obálky signálu získáme přímo tvar frekvenční charakteristiky na obrazovce.

### Režim X-Y
- Místo časové základny na vstup X přivedeme druhý signál – na obrazovce se zobrazí závislost Y na X.
- Použití: **Lissajousovy obrazce**, měření převodních charakteristik, vektorkardiogram, tokokorelogram (viz bod 2).

### Lissajousovy obrazce
- Vznikají skládáním dvou navzájem kolmých harmonických kmitů (na X a Y vstupu).
- Tvar křivky určuje **poměr kmitočtů** obou signálů a jejich **fázový posun** φ.
- Je-li poměr kmitočtů racionální číslo, jde o uzavřenou křivku.
- Použití: přesné určení poměru dvou kmitočtů (kalibrace generátoru vůči normálu) a měření fázového posunu mezi dvěma stejně kmitočtovými signály.
- Tabulka typických obrazců (U = Un, f = fn, měněn jen fázový úhel φ):

| Tvar | Vztahy |
|---|---|
| Úsečka (/) | f = fn, φ = 0° |
| Elipsa | f = fn, φ = 30° |
| Kružnice | f = fn, φ = 90° nebo 270° |
| Úsečka (\\) | f = fn, φ = 180° |
| Osmička (∞) | f = 2fn |
| Dvojitá smyčka | f = ½·fn |

kde U je měřené napětí, f měřený kmitočet, Un normálové srovnávací napětí, fn normálový kmitočet, φ úhel fázového posunu.

---

## 4. Logický analyzátor – konstrukce, parametry, metody měření, časová a stavová analýza, glitch detekce

### Definice a provedení
- **Logický analyzátor** je měřicí přístroj, který **zaznamenává a zobrazuje logické signály** v číslicových obvodech (na rozdíl od osciloskopu neukazuje analogový průběh, ale logické úrovně 0/1 na mnoha kanálech současně).
- Provedení: přenosný, modulární, nebo modul pro PC.

### Základní parametry
- **Počet měřicích kanálů** – dnes desítky až stovky (výjimečně tisíce).
- **Max. rychlost vzorkování** – desítky Mvz/s až jednotky Gvz/s (kSPS/MSPS/GSPS).
- **Hloubka záznamové paměti** – až desítky MB.
- Velikost a typ displeje.
- Rozhraní/ovládání – Ethernet, USB, Flash Disk, VGA…

### Měřicí kanál
- Soubor prostředků pro vzorkování, záznam a zobrazení jednoho signálu.
- Blokové schéma kanálu: vstupní signál → **vstupní sonda** (impedanční přizpůsobení) → **napěťový komparátor** (převod na logickou úroveň dle prahu) → **vzorkovací obvod** → **záznamová paměť** → zobrazení. Vzorkovací obvod je řízen buď externím hodinovým signálem (State), nebo interní **časovou základnou** (Time).

### Komparátor vs. Schmittův klopný obvod
- Prostý komparátor s jedním prahem (single threshold) reaguje na každý průchod prahem – u zašuměného signálu blízko prahu vznikají **zákmity** (mnohonásobné překlápění).
- **Schmittův klopný obvod** má **hysterezi** (dvě prahové úrovně – horní a dolní) – šum uvnitř pásma hystereze nezpůsobí falešné překlopení → čistší detekce hran (viz příklad zákmitů komparátoru bez hystereze na optické závoře).

### Časová vs. stavová analýza
- **Časová analýza (Time Analysis) – asynchronní**: pro systémy bez (nebo s neurčitelnými) vlastními hodinovými signály; vzorkování řízeno vnitřním generátorem logického analyzátoru s nastavitelnou periodou.
- **Stavová analýza (State Analysis) – synchronní**: vzorkovací signál je odvozen z hodinového signálu analyzovaného systému – zaznamenávají se stavy sběrnice synchronně s taktem systému (typicky zobrazeno jako tabulka ADR/DATA/STAT v hex).

### Základní pojmy
- **Sledování (Tracing)** – řízený proces vzorkování signálů na vstupech.
- **Spouštěcí událost / spouštěcí slovo (Trigger word)** – vektor stavů sledovaných signálů v daném okamžiku; nedůležité signály se označují stavem **X** (nezáleží na hodnotě).
- **Spouštěcí podmínka** – podmínění operace analyzátoru výskytem spouštěcí události.
- **Skupina (POD/LABEL)** – seskupení více kanálů podle logického významu (např. adresová/datová sběrnice).
- **Sekvenční spouštění** – spuštění vyžaduje výskyt několika spouštěcích událostí v daném pořadí.
- **Selektivní sledování** – ukládají se jen vybrané vzorky podle kritéria.
- **Ukládací kvalifikátory** – speciální podmínka, při jejímž splnění se data vůbec ukládají do paměti.

### Glitch (zákmit)
- **Glitch** = vícenásobná změna logické úrovně signálu **mezi dvěma okamžiky vzorkování** – tedy krátký impulz, který by při nedostatečné vzorkovací rychlosti (a jen bodovém vzorkování) unikl detekci.
- Logické analyzátory mívají speciální glitch-detekční obvody, které zachytí, že mezi vzorky došlo k dodatečné změně, i když samotné vzorky ukazují stejnou hodnotu.

### Logický hazard (v návaznosti na měření logickým analyzátorem)
- V sekvenčních/kombinačních obvodech dva druhy:
  - **1. druhu (statický)** – výstup se nemá změnit (0 změn požadováno), ale kvůli různým zpožděním se dočasně překlopí a vrátí zpět → reálně 2 změny.
  - **2. druhu (dynamický)** – výstup se má změnit jednou, ale kvůli hazardu se signál dočasně vrátí na původní hodnotu, než se ustálí → reálně 3 změny.
- Logický analyzátor s glitch detekcí dokáže tyto krátké přechodné jevy odhalit, i když jsou kratší než vzorkovací perioda.

---

## 5. Měření el. výkonu a energie, spektrální analyzátor – princip měření, parametry

### Měření výkonu stejnosměrného proudu
- P = U · I [W, V, A]
- **Nepřímá metoda** – měření U a I odděleně ampérmetrem a voltmetrem, dvě možná zapojení:
  - a) Ampérmetr blíž zdroji (voltmetr měří i úbytek na ampérmetru) → korekce: P = UZ(IA − IV), IV = UZ/RV.
  - b) Voltmetr blíž zdroji (ampérmetr měří i proud voltmetrem) → korekce: P = IA(UV − UA), UA = IA·RA.
- V obou případech vzniká **systematická chyba metody** danou vnitřním odporem přístrojů, kterou lze korigovat, pokud známe RV resp. RA.

### Měření výkonu střídavého proudu
- Rozlišujeme:
  - **činný výkon P [W]**
  - **jalový výkon Q [Var]**
  - **zdánlivý výkon S [VA]**, S = P + jQ, φ = úhel mezi P a S (účiník cos φ).
- Činný výkon se měří **wattmetry** – ručkovými (elektrodynamické ústrojí) nebo elektronickými.
- Z údaje wattmetru nelze poznat napětí a proud v obvodu → nutno vždy paralelně připojit i voltmetr a ampérmetr.

### Elektrodynamická měřicí soustava (ručkový wattmetr)
- Skládá se z pevné **proudové cívky** (proudová větev, do obvodu sériově) a otočné **napěťové cívky** (napěťová větev, paralelně, přes předřadný odpor RV) na společné ose s ručkou.
- Výchylka je úměrná součinu proudu a napětí (a jejich fázovému posunu) → přímo ukazuje činný výkon.
- Vlastnosti: lze měřit ss i stř. proud/napětí i výkon (wattmetr); lineární stupnice; tlumení vířivými proudy.
- Nutno dávat pozor na přetížení proudové nebo napěťové větve i při nepřekročení rozsahu ve wattech (např. při nízkém účiníku).

### Elektronický (číslicový) wattmetr
- Pro činný výkon P dodávaný do libovolné zátěže za čas T platí: P = (1/T)·∫₀ᵀ u(t)·i(t) dt (střední hodnota okamžitého výkonu).
- Blokové schéma: napětí u a proud i se každé zvlášť převedou (převodník napětí / převodník proudu) → dolní propust → vzorkovač → A/D převodník → mikropočítač (vynásobí a zprůměruje vzorky) → zobrazovač.

### Měření elektrické energie
- E = P · T [Ws, W, s]; 1 J = 1 Ws.
- E = ∫₀ᵀ u(t)·i(t) dt (integrace okamžitého výkonu v čase).
- Realizace: klasický indukční elektroměr (otáčející se kotouček), nebo moderní elektronický elektroměr (na DIN lištu) počítající digitálně dle vzorce výše.

### Spektrální analyzátor (doplněno – v podkladech není samostatně rozebrán)
- Měří **rozložení výkonu/amplitudy signálu ve frekvenční oblasti** (na rozdíl od osciloskopu, který ukazuje časový průběh).
- Princip: obvykle **heterodynní** (superheterodynní přijímač) – vstupní signál se směšuje s laditelným místním oscilátorem (mixer), výsledný mezifrekvenční signál prochází úzkopásmovým filtrem (RBW filtr) a detektorem, výsledek se zobrazí jako závislost amplitudy na kmitočtu (postupné "sweepnutí" pásma) – analogie k rozmítacímu měření frekvenční charakteristiky osciloskopem zmíněnému výše. Modernější přístroje pracují na principu FFT (digitální, rychlé, širokopásmové zobrazení najednou).
- Hlavní parametry: frekvenční rozsah, rozlišovací šířka pásma (RBW – Resolution Bandwidth), šířka video filtru (VBW), dynamický rozsah, citlivost (zobrazený šumový práh, DANL), rychlost rozmítání/FFT, fázový šum lokálního oscilátoru.
- Využití v biomedicíně/elektronice: analýza harmonického zkreslení signálu, EMC měření (rušení), spektrální analýza biosignálů (např. výkonové spektrum EEG).

*(Poznámka: k tomuto bodu spektrálního analyzátoru nebyly v dodaných podkladech žádné slajdy – doplněno z obecných znalostí, ostatní body vycházejí přímo z materiálů.)*
