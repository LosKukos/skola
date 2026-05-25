# Zobrazovací technika v lékařství
### Státnicová příprava – Biomedicínská technika 2026

---

# Otázka 40: Ultrazvukové zobrazovací systémy

## Fyzikální základ ultrazvuku

Ultrazvuk (UZ) je mechanické vlnění s frekvencí **> 20 kHz**. V diagnostické sonografii se používají frekvence **1–20 MHz**.

### Klíčové fyzikální vlastnosti

| Veličina | Vztah | Typické hodnoty v tkáni |
|---|---|---|
| **Rychlost zvuku (c)** | c = f × λ | ~1 540 m/s v měkkých tkáních |
| **Akustická impedance (Z)** | Z = ρ × c | Liší se pro každou tkáň |
| **Odraz** | Na rozhraní tkání s různým Z → echo | Základ B-mode zobrazení |
| **Útlum** | Exponenciální pokles s hloubkou | ~0,5 dB/cm/MHz |

### Piezoelektrický transducer
Krystal (PZT keramika, PVDF) mění elektrický signál na mechanickou vibraci (vysílání) a naopak (příjem). Funguje jako vysílač i přijímač.

---

## Zobrazovací módy

| Mód | Název | Popis | Použití |
|---|---|---|---|
| **A-mode** | Amplitude | 1D – amplituda echa vs. hloubka | Oftalmologie (délka oka) |
| **B-mode** | Brightness | 2D šedotónový obraz | Standard – břicho, srdce, plod |
| **M-mode** | Motion | 1D pohyb v čase – rychlé pohyby | Pohyb chlopní a stěn srdce |
| **Doppler CW** | Continuous Wave | Kontinuální měření rychlosti toku | Vysoké rychlosti (stenózy) |
| **Doppler PW** | Pulsed Wave | Měření rychlosti v konkrétní hloubce | Srdeční chlopně |
| **Color Doppler** | – | Barevné mapování toku v 2D obraze | Cévy, srdce |
| **Power Doppler** | – | Citlivější, nezobrazuje směr | Malé cévy, parenchym |
| **3D/4D UZ** | – | Prostorový obraz (3D = statický, 4D = real-time 3D) | Prenatální diagnostika |

---

## Typy transducerů (sond)

| Typ sondy | Tvar svazku | Frekvence | Použití |
|---|---|---|---|
| **Lineární** | Obdélníkový obraz | 5–18 MHz | Povrchové struktury, cévy, MSK |
| **Konvexní (curved)** | Trapézový obraz | 2–6 MHz | Břicho, pánev, plod |
| **Sektorová (phased array)** | Sektorový obraz | 1–4 MHz | Srdce (echokardiografie) – malé akustické okno |
| **Endokavitální** | – | 5–10 MHz | Transvaginální, transrektální UZ |
| **Jícnová (TEE)** | – | 3–8 MHz | Transezofageální echokardiografie |

---

## Echokardiografie

Ultrazvukové vyšetření srdce. Základní zobrazovací modalita kardiologie.

### Standardní pohledy (okna)
- **Parasternální** – dlouhá osa (PLAX), krátká osa (PSAX)
- **Apikální** – 4-dutinový, 5-dutinový, 2-dutinový pohled
- **Subkostální**, **suprasternální**

### Hodnocené parametry
- Rozměry a objemy komor (EDD, ESD, EDV, ESV)
- **EF (Ejekční frakce)** – systolická funkce LK – norma > 55 %
- Funkce chlopní – regurgitace, stenóza (gradientem z Doppleru)
- Diastolická funkce – E/A poměr, E/e' poměr
- Perikardní výpotek

---

## Dopplerovský princip

Frekvenční posun odraženého signálu závisí na rychlosti pohybu reflektoru (erytrocyty, stěny srdce):

**Δf = 2 × f₀ × v × cos(θ) / c**

kde θ = úhel mezi svazkem a směrem toku. Pro přesné měření je nutné, aby θ < 20°.

---

## Artefakty v UZ

| Artefakt | Příčina | Projev |
|---|---|---|
| **Akustický stín** | Totální odraz nebo absorpce (kost, vzduch, kalcifikace) | Tmavý stín za strukturou |
| **Zesílení za echo-volnou strukturou** | Nízký útlum tekutiny | Světlejší oblast za cystou |
| **Reverberační artefakt** | Vícenásobné odrazy mezi dvěma rozhraními | Opakující se linie – vzduch v střevě, jehla |
| **Akustické zrcadlení** | Silně reflexní povrch (bránice) | Zrcadlový obraz jater nad bránicí |

---

# Otázka 41: Rentgenové záření a rentgenová zobrazovací technika

## Vznik rentgenového záření

Rentgenové záření vzniká v **rentgence (RTG trubici)**:
1. Katoda (žhavené wolframové vlákno) emituje elektrony termoemisí
2. Elektrony jsou urychleny vysokým napětím (20–150 kV) na anodu
3. Na anodě (wolfram nebo molybden) vzniká RTG záření dvěma způsoby:
   - **Brzdné záření (Bremsstrahlung)** – elektrony jsou zpomaleny jádrem → spojité spektrum
   - **Charakteristické záření** – elektrony vytlačí elektron z vnitřní slupky atomu → diskrétní čáry

### Parametry RTG záření
- **kVp (kilovolt peak)** – napětí na trubici → ovlivňuje energii (tvrdost) záření a kontrast
- **mA (miliampéry)** – proud → ovlivňuje intenzitu (počet fotonů) → dávka
- **mAs** = mA × s – celková dávka → jas snímku

---

## Interakce záření s tkání

| Interakce | Podmínky | Efekt |
|---|---|---|
| **Fotoelektrický jev** | Nízké energie (< 100 keV), těžké prvky (kost, jod) | Absorpce → vysoký kontrast kostí a KL |
| **Comptonův rozptyl** | Střední energie, měkké tkáně | Rozptýlené záření → snižuje kontrast |
| **Párová produkce** | > 1,02 MeV (jen radioterapie) | Málo relevantní pro diagnostiku |

---

## Detektory RTG záření

| Typ | Princip | Poznámka |
|---|---|---|
| **Filmová kazeta** | Citlivý film + zesilovací fólie | Historický – analogová radiografie |
| **CR (Computed Radiography)** | Fosforová plotna (IP) – stimulovaná luminiscence → skenování laserem | Digitální, plotna znovupoužitelná |
| **DR (Direct Radiography)** | Flat-panel detektor – přímá nebo nepřímá konverze na elektrický signál | Nejmodernější – okamžitý obraz, nejnižší dávka |

### Flat-panel detektory (FPD)
- **Přímá konverze**: RTG → elektrický náboj (selen amorfní – a-Se)
- **Nepřímá konverze**: RTG → světlo (scintilátory CsI, Gd₂O₂S) → fotodiody → elektrický signál

---

## RTG zobrazovací systémy

| Systém | Popis | Použití |
|---|---|---|
| **Rentgenový přístroj (konvenční RTG)** | Statický snímek – skiagrafie | Hrudník, kosti, břicho |
| **Skiaskopie (fluoroskopie)** | Kontinuální RTG obraz v reálném čase | Kontrastní vyšetření, katetrizace, C-rameno |
| **Mamograf** | Nízké kVp (25–32 kVp), Mo nebo W anoda, komprese prsu | Screening a diagnostika karcinomu prsu |
| **Stomatologický OPG** | Rotační panoramatický snímek | Chrup, čelisti |
| **CBCT** | Kuželový svazek, 3D rekonstrukce | Stomatologie, ORL, ortopedie |
| **DSA** | Digitální subtrakční angiografie – odečtení masky → cévy | Intervenční radiologie, katetrizace |

---

## Kontrastní látky (KL)

| Typ | Příklady | Použití |
|---|---|---|
| **Jodové (pozitivní)** | Iohexol, Iopamidol (iontové a neiontové) | CT angiografie, urografie, DSA |
| **Barnaté (pozitivní)** | Síran barnatý (BaSO₄) | Kontrastní pasáž GIT |
| **Vzduch/CO₂ (negativní)** | – | Dvojkontrastní vyšetření střev |

### Nefropatie z kontrastní látky (CIN)
Riziko u pacientů s renální insuficiencí. Prevence: hydratace, minimalizace dávky KL, alternativa (CO₂ DSA).

---

## Ochrana před zářením

- **Princip ALARA** – As Low As Reasonably Achievable
- **Kolimace** – omezení svazku jen na oblast zájmu
- **Stínění** – olověné zástěry, sklo s olovem, přepážky
- **Vzdálenost** – intenzita záření klesá s kvadrátem vzdálenosti (zákon inverzního čtverce)
- **Monitorování** – osobní dozimetry pro personál

---

# Otázka 42: Výpočetní tomografie (CT)

## Princip CT

CT (Computed Tomography) rekonstruuje průřezové obrazy těla z mnoha RTG projekcí pořízených pod různými úhly. Výsledkem jsou **tomografické řezy (axiální slices)** a 3D rekonstrukce.

### Základní princip rekonstrukce
- RTG trubice a detektor rotují kolem pacienta
- Každý detektor měří oslabení svazku v dané projekci
- **Filtrovaná zpětná projekce (FBP)** nebo **iterativní rekonstrukce (IR)** → obraz

---

## Generace CT přístrojů

| Generace | Popis |
|---|---|
| **1. generace** | Tužkový svazek, translace + rotace – pomalé |
| **2. generace** | Malý vějíř, méně pohybů |
| **3. generace** | Vějíř + rotace trubice + detektoru – dnes standard |
| **4. generace** | Pevný kruhový detektor, rotuje jen trubice |
| **Spirální (helical) CT** | Kontinuální rotace + posuv stolu → spirální skenování |
| **Víceřadový CT (MDCT)** | Více řad detektorů (4, 16, 64, 128, 256, 320) → rychlost, rozlišení |

---

## Parametry CT

| Parametr | Popis |
|---|---|
| **Hounsfield Units (HU)** | Jednotka denzity tkáně – vzduch: −1000 HU, voda: 0 HU, kost: +400 až +1000 HU, tuk: −50 až −100 HU |
| **Slice thickness** | Tloušťka řezu – 0,5–10 mm |
| **FOV (Field of View)** | Zobrazované pole |
| **Pitch** | Poměr posuvu stolu za otáčku ku kolimaci – ovlivňuje rychlost a dávku |
| **Window Width/Level** | Nastavení okna pro zobrazení (okno kosti, měkkých tkání, plic, mozku) |

---

## Speciální CT techniky

| Technika | Princip | Použití |
|---|---|---|
| **CT angiografie (CTA)** | I.v. KL + rychlé skenování | Aorta, koronární tepny, plicní embolie |
| **Koronární CT (CCTA)** | EKG-gatované skenování | Koronární tepny, kalciový skóre |
| **CT perfuze** | Dynamické sledování průtoku KL | Mozková ischemie, onkologie |
| **DECT (Dual Energy CT)** | Dva různé kVp → dekompozice materiálů | Dna (urát), jod, virtuální nativní |
| **Subtrakční CT** | Odečtení pre- a post-kontrastního obrazu | Intrakraniální aneurysma |

---

## Dávka při CT

CT je nejvýznamnější zdroj lékařského ozáření – průměrná efektivní dávka:
- Hrudní CT: **5–7 mSv**
- CT břicha a pánve: **8–14 mSv**
- Koronární CCTA: **2–5 mSv** (moderní protokoly)

Redukce dávky: automatická modulace proudu (AEC), iterativní rekonstrukce, low-dose protokoly.

---

# Otázka 43: Magnetická rezonance (MRI)

## Fyzikální princip

MRI využívá **jadernou magnetickou rezonanci (NMR)** atomových jader s nenulovým spinem (nejčastěji ¹H – protony vody a tuku).

### Základní princip

1. **Statické magnetické pole B₀** – silný magnet (1,5 T, 3 T) zarovná magnetické momenty protonů podél pole
2. **RF puls** – radiofrekvenční pulz překlopí magnetizaci o 90° (nebo 180°) z rovnovážné polohy
3. **Relaxace** – protony se vrací do rovnovážné polohy a emitují RF signál:
   - **T1 (longitudinální relaxace)** – obnova podél B₀ – charakteristická pro tkáň
   - **T2 (transversální relaxace)** – zánik příčné magnetizace – charakteristická pro tkáň
4. **Gradientní cívky** – prostorové zakódování signálu (frekvenční a fázové kódování)
5. **Rekonstrukce** – 2D Fourierova transformace → obraz

---

## Kontrasty MRI (tkáňové charakteristiky)

| Tkáň | T1 | T2 |
|---|---|---|
| Tuk | Světlý (krátké T1) | Světlý |
| Voda (CSF, edém) | Tmavý (dlouhé T1) | Světlý (dlouhé T2) |
| Kost (kortikalis) | Tmavá | Tmavá |
| Svaly | Střední | Střední |
| Vzduch | Tmavý | Tmavý |

---

## MRI sekvence

| Sekvence | Zkratka | Zobrazuje |
|---|---|---|
| **T1-vážená** | T1W | Anatomie, tuk světlý, tekutina tmavá |
| **T2-vážená** | T2W | Edém, tekutina světlá – patologie |
| **FLAIR** | Fluid Attenuated IR | T2 s potlačením CSF – léze periventrik. bílé hmoty (RS) |
| **DWI** | Diffusion Weighted | Difuze molekul vody – akutní ischemie, abscesy |
| **ADC mapa** | Apparent Diffusion Coefficient | Kvantifikace difuze |
| **MR Angiografie** | MRA | Cévy – TOF nebo kontrastní |
| **BOLD fMRI** | Blood Oxygenation Level Dependent | Funkční aktivita mozku |
| **MR Spektroskopie** | MRS | Metabolity (NAA, cholin, laktát) – nádory, metabolická onemocnění |
| **DCE-MRI** | Dynamic Contrast Enhanced | Perfuze, permeabilita – onkologie |

---

## Komponenty MRI systému

| Komponenta | Funkce |
|---|---|
| **Supravodivý magnet** | Generuje B₀ (1,5 T nebo 3 T) – chlazen kapalným heliem (4,2 K) |
| **Gradientní cívky** | Prostorové kódování – Gx, Gy, Gz (příčina hluku!) |
| **RF cívky** | Vysílání RF pulzů a příjem signálu (povrchové, tělní, hlavová) |
| **Počítač a rekonstrukce** | Fourierova transformace, rekonstrukce obrazu |

---

## MRI bezpečnost

| Riziko | Popis |
|---|---|
| **Magnetický projektil** | Feromagnetické předměty jsou přitahovány – smrtelné nebezpečí |
| **Implantáty** | Kardiostimulátor (kontraindikace/podmíněná), kovové implantáty |
| **Teplo** | RF záření zahřívá tkáně – SAR (Specific Absorption Rate) limitován |
| **Hluk** | Gradientní cívky – 80–130 dB – sluchová ochrana nutná |
| **Klaustrofobie** | Uzavřený bore tunelu |

**Zóny MRI pracoviště:**
- Zóna I – veřejná
- Zóna II – přechodová (screening dotazník)
- Zóna III – omezený přístup (přítomnost personálu)
- Zóna IV – bore magnetu – pouze prověřené osoby a předměty

---

## Kontrastní látky MRI

- **Gadolinium (Gd)** – paramagnetická KL, zkracuje T1 → světlé zesílení (enhancement)
- Indikace: mozkové léze, nádory, zánět, perfuze
- **Nefrosystemická fibróza (NSF)** – komplikace u renálního selhání (starší nespecifické chelátory)
- Moderní makrocyklické chelátory (Gadovist, Dotarem) – vyšší stabilita

---

# Otázka 44: Metody filtrace a segmentace medicínských obrazů

## Digitální medicínský obraz

Medicínský obraz = 2D nebo 3D pole pixelů (nebo voxelů) s hodnotami intenzity (šedotónová hodnota, HU, signálová intenzita).

**Předzpracování obrazu** – filtrace šumu, zlepšení kontrastu → předstupeň pro segmentaci a analýzu.

---

## Filtrace obrazu

### Prostorová filtrace (konvoluce s jádrem)

| Filtr | Jádro / Princip | Efekt |
|---|---|---|
| **Průměrovací (Mean)** | Průměr okolí pixelu | Vyhlazení, redukce šumu – rozmazání hran |
| **Gaussovský** | Gaussovské váhy okolí | Plynulé vyhlazení, zachování hran lépe než Mean |
| **Mediánový** | Medián hodnot okolí | Redukce impulsního šumu (salt & pepper) – zachovává hrany |
| **Sobelův / Prewittův** | Gradient – derivace obrazu | Detekce hran |
| **Laplacián** | 2. derivace | Detekce hran, zostření |
| **Unsharp masking** | Originál − vyhlazený × koef. | Zostření hran |

### Frekvenční filtrace (FFT)

- Obraz transformován do frekvenční domény (Fourierova transformace)
- **Dolní propust** – vyhlazení, redukce šumu (odstraní vysoké frekvence)
- **Horní propust** – detekce hran (ponechá vysoké frekvence)
- **Pásmová propust / zádrž** – odstranění specifického rušení (pruhy, artefakty)

### Speciální filtry

- **Anizotropní difuze (Perona-Malik)** – vyhlazení homogenních oblastí, zachování hran
- **BM3D** – moderní denoising, využívá nelokalitu obrazu
- **Waveletové metody** – prahování koeficientů ve waveletové doméně

---

## Zlepšení kontrastu

| Metoda | Princip |
|---|---|
| **Window/Level** | Přemapování histogramu na zobrazovací rozsah (CT okna) |
| **Histogram equalization** | Rovnoměrné rozložení intenzit → zvýšení globálního kontrastu |
| **CLAHE** (Contrast Limited AHE) | Lokální ekvalizace s omezením (prevence přeexponování) – RTG, UZ |
| **Gamma korekce** | Nelineární úprava intenzit |

---

## Segmentace medicínských obrazů

Segmentace = rozdělení obrazu na smysluplné oblasti (tkáně, orgány, léze).

### Prahování (Thresholding)

- Nejjednodušší metoda – pixely nad prahem = popředí, pod prahem = pozadí
- **Globální práh** – jeden práh pro celý obraz (Otsuova metoda – minimalizace rozptylu)
- **Lokální práh** – adaptivní práh podle lokálního okolí – pro nehomogenní osvětlení
- Použití: segmentace kostí v CT (HU > 200), extrakce vzduchových dutin

### Detekce hran a oblasti

- **Watershed** – zalití obrazu vodou z lokálních minim → oddělení regionů
- **Region growing** – semínko + přidávání sousedních pixelů dle kritéria homogenity
- **Level-set metody** – implicitní kontura se deformuje minimalizací energie

### Active Contours (Snakes / Balloon)

- Kontura se deformuje pod vlivem interní energie (hladkost) a externí energie (hrany obrazu)
- Klasická metoda pro segmentaci orgánů s jasně definovanými hranami

### Atlas-based segmentace

- Předregistrovaný anatomický atlas (template + segmentace) se registruje na nový obraz
- Přenesení labelů z atlasu → segmentace nového obrazu
- Multi-atlas = průměrování více atlasů → robustnější výsledek

### Deep learning segmentace

- **U-Net** – nejrozšířenější architektura pro medicínskou segmentaci (encoder-decoder + skip connections)
- **nnU-Net** – self-configuring framework, automatická konfigurace parametrů
- **Transformer-based modely** – SwinUNETR, TransUNet – dlouhé závislosti v obraze

---

## Registrace obrazů

Registrace = zarovnání dvou nebo více obrazů (různé časy, modality, pacienti).

| Typ | Příklad |
|---|---|
| **Rigidní** | Translace + rotace – mozek (kost) |
| **Afinní** | + škálování, zkosení |
| **Nerigidní (deformovatelná)** | Volná deformace (B-spline, difuzní) – měkké tkáně |
| **Multimodální** | CT-MRI, PET-CT – mutual information jako metrika |

---

# Otázka 45: Strojové učení – supervizorní a nesupervizorní přístupy

## Základní pojmy

| Pojem | Definice |
|---|---|
| **Strojové učení (ML)** | Počítač se učí ze dat bez explicitního programování pravidel |
| **Hluboké učení (DL)** | ML s vícevrstvými neuronovými sítěmi (deep neural networks) |
| **Trénovací data** | Data s anotacemi (labely) pro učení modelu |
| **Validační data** | Data pro sledování výkonu během trénování a ladění hyperparametrů |
| **Testovací data** | Data pro finální vyhodnocení modelu – nikdy nevidí model při trénování |
| **Overfitting** | Model se přeučil – dobře funguje na tréninkových datech, špatně na nových |
| **Underfitting** | Model je příliš jednoduchý – nenaučil se ani trénovací data |

---

## Supervizorní učení (Supervised Learning)

Model se učí ze dvojic **(vstup, správná odpověď)**. Cílem je naučit funkci f: X → Y.

### Klasifikace

Výstup je třída (diskrétní label).

| Algoritmus | Popis | Použití v medicíně |
|---|---|---|
| **Logistická regrese** | Lineární model + sigmoid funkce | Binární diagnostika |
| **SVM** (Support Vector Machine) | Maximalizace margin mezi třídami | Klasifikace nádorů |
| **Rozhodovací strom** | Stromová struktura podmínek | Interpretovatelná pravidla |
| **Random Forest** | Ensemble rozhodovacích stromů | Robustní, méně overfitting |
| **Gradient Boosting** (XGBoost, LightGBM) | Sekvenční ensemble | Klinická predikce, EHR data |
| **CNN** (Convolutional Neural Network) | Konvoluční vrstvy pro extrakci příznaků | Klasifikace RTG, dermatoskopie, patologie |

### Regrese

Výstup je spojitá hodnota.

- Předpověď dávky léku, délky hospitalizace, věku z obrazu

### Evaluační metriky – klasifikace

| Metrika | Vzorec | Popis |
|---|---|---|
| **Sensitivity (Recall/TPR)** | TP / (TP + FN) | Záchyt nemocných – klíčové pro screening |
| **Specificity (TNR)** | TN / (TN + FP) | Správné vyloučení zdravých |
| **Precision (PPV)** | TP / (TP + FP) | Přesnost pozitivních predikcí |
| **F1-score** | 2 × Prec × Rec / (Prec + Rec) | Harmonický průměr precision a recall |
| **AUC-ROC** | Plocha pod ROC křivkou | Celková diskriminační schopnost modelu |
| **Accuracy** | (TP + TN) / celkem | Celková správnost – nevhodná pro nevyvážené třídy |

---

## Nesupervizorní učení (Unsupervised Learning)

Model hledá strukturu v datech **bez labelů**.

### Shlukování (Clustering)

| Algoritmus | Princip | Použití |
|---|---|---|
| **K-means** | Iterativní přiřazení k nejbližšímu centroidu – k shluků | Subtypy nádorů, genomická data |
| **Hierarchické shlukování** | Dendrogram – postupné slučování nebo dělení | Vizualizace podobnosti vzorků |
| **DBSCAN** | Shlukování dle hustoty – robustní na šum | Detekce anomálií |
| **Gaussian Mixture Models** | Pravděpodobnostní shlukování | |

### Redukce dimenzionality

| Metoda | Princip | Použití |
|---|---|---|
| **PCA** (Principal Component Analysis) | Lineární transformace – maximální rozptyl | Vizualizace, preprocessing |
| **t-SNE** | Nelineární – zachování lokální struktury | Vizualizace vysokodimenzionálních dat (genomika, histologie) |
| **UMAP** | Rychlejší než t-SNE, zachovává globální i lokální strukturu | Moderní vizualizace |
| **Autoenkodér** | Neuronová síť – enkodér (komprese) + dekodér (rekonstrukce) | Feature learning, anomalie |

---

## Semisupervizorní a self-supervised učení

- **Semisupervizorní** – malé množství labelovaných + velké množství nelabelovaných dat (typické v medicíně – anotace jsou drahé)
- **Self-supervised** – model si vytváří labely sám ze struktury dat (kontrastivní učení, masked image modeling)
- **Transfer learning** – předtrénovaný model (ImageNet, MedicalNet) + doladění na malém medicínském datasetu

---

## Aplikace ML v medicínském zobrazování

| Aplikace | Metoda |
|---|---|
| Detekce pneumonie na RTG | CNN klasifikátor (CheXNet – Stanford) |
| Segmentace nádoru na MRI | U-Net, nnU-Net |
| Detekce diabetické retinopatie | CNN – FDA schválena (IDx-DR) |
| Klasifikace kolorektálních polypů z endoskopie | CNN real-time (GI Genius) |
| Analýza EKG – detekce FiS | 1D CNN nebo RNN (Apple Watch, AliveCor) |
| Předpověď mortality na ICU | LSTM, XGBoost (MIMIC dataset) |

---

# Otázka 46: Kvalitativní analýza obrazových výstupů, digitální pacientská dokumentace

## Kvalita medicínského obrazu

### Parametry kvality obrazu

| Parametr | Definice | Ovlivňuje |
|---|---|---|
| **Prostorové rozlišení** | Nejmenší rozlišitelný detail (lp/mm nebo MTF) | Ostrost, viditelnost detailů |
| **Kontrastní rozlišení** | Nejmenší viditelný kontrast mezi strukturami | Rozlišení měkkých tkání |
| **Poměr signál/šum (SNR)** | Signál / standardní odchylka šumu | Čistota obrazu |
| **CNR (Contrast-to-Noise Ratio)** | Kontrast mezi dvěma oblastmi / šum | Detekovatelnost lézí |
| **MTF (Modulation Transfer Function)** | Přenos kontrastu v závislosti na frekvenci | Objektivní hodnocení prostorového rozlišení |
| **DQE (Detective Quantum Efficiency)** | Účinnost detektoru → SNR výstupu²/SNR vstupu² | Kvalita detektoru RTG/CT |

---

## Hodnocení kvality obrazu

### Subjektivní hodnocení
- **Vizuální skóre** – radiolog hodnotí na stupnici (1–5) diagnostickou použitelnost
- **ROC analýza (Receiver Operating Characteristic)** – jak dobře je pozorovatel schopen detekovat lézi
- **JAFROC / FROC** – hodnocení lokalizace a detekce lézí (free-response ROC)

### Objektivní hodnocení
- Fyzikální měření MTF, NPS (Noise Power Spectrum), DQE – fantomové měření
- **ACR fantoM** – standardizované fantomy pro MRI, CT, mammografii, UZ
- **Dávkové audity** – sledování dávky při dodržení diagnostické kvality (DRL – Diagnostic Reference Levels)

---

## PACS – Picture Archiving and Communication System

PACS je systém pro ukládání, přenos a zobrazení medicínských obrazů.

### Komponenty PACS

| Komponenta | Funkce |
|---|---|
| **Modalita** (CT, MRI, RTG) | Pořizuje obraz a odesílá do PACS |
| **DICOM server** | Archivuje obrazy (krátkodobě + dlouhodobě) |
| **Pracovní stanice (workstation)** | Zobrazení, analýza, reporting |
| **Web viewer** | Prohlížení z libovolného počítače |
| **RIS (Radiology Information System)** | Správa žádanek, reportů, workflow |

---

## DICOM standard

**DICOM (Digital Imaging and Communications in Medicine)** – mezinárodní standard pro ukládání, přenos a zobrazení medicínských obrazů.

### Klíčové vlastnosti DICOM
- Každý obraz je **DICOM soubor** = obrazová data + **header (metadata)**
- Metadata: jméno pacienta, rodné číslo, modalita, datum, parametry akvizice, UID...
- **DICOM UID** – unikátní identifikátor každého obrazu/série/studie
- **DICOM SR (Structured Reporting)** – strukturovaný radiologický report
- **DICOM RT** – radioterapeutické plánování (RT Dose, RT Plan, RT Structure Set)

### DICOM síťové služby
- **C-STORE** – odeslání obrazu do PACS
- **C-FIND** – vyhledání studie
- **C-MOVE** – stažení obrazu
- **DICOM Modality Worklist (MWL)** – přenesení demografických dat pacienta z RIS do modality

---

## Digitální pacientská dokumentace

### EHR vs. EMR

| Zkratka | Název | Rozsah |
|---|---|---|
| **EMR** (Electronic Medical Record) | Elektronická zdravotní dokumentace | Jeden poskytovatel |
| **EHR** (Electronic Health Record) | Elektronický zdravotní záznam | Sdílený napříč poskytovateli |
| **PHR** (Personal Health Record) | Osobní zdravotní záznam | Spravuje pacient sám |

### Komponenty digitální dokumentace
- Anamnéza, fyzikální nález, diagnózy (MKN-10/11)
- Laboratorní výsledky, zobrazovací výsledky (PACS link)
- Medikace, alergie, operační protokoly
- Ošetřovatelská dokumentace
- **Propouštěcí zpráva** – strukturovaný dokument při propuštění

### Standardy pro výměnu dat

| Standard | Oblast | Popis |
|---|---|---|
| **HL7 v2.x** | Nemocniční integrace | Zprávy mezi NIS, LIS, RIS, PACS |
| **HL7 FHIR** | Moderní REST API | Interoperabilita, mobilní aplikace, AI |
| **IHE profily** | Integrace systémů | XDS, PIX, PDQ – sdílení dokumentů a identit |
| **SNOMED CT** | Klinická terminologie | Standardizace diagnóz a procedur |
| **LOINC** | Laboratorní kódy | Standardizace laboratorních testů |

### Bezpečnost a ochrana dat
- **GDPR** – ochrana osobních údajů v EU
- **Pseudonymizace / anonymizace** – pro výzkum a AI trénování
- **Přístupová práva** – role-based access control (RBAC)
- **Audit trail** – záznam každého přístupu k pacientské dokumentaci

---

*Konec bloku – Zobrazovací technika v lékařství | Otázky 40–46*
