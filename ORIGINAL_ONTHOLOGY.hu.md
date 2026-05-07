# Bevezetés
Jelen dokumentum egy ágens ontológiát, és az abból következő, a túlélésben hatékony ágensekre vonatkozó követelményeket vázol fel.

Az ontológia és dedukció legnagyobb újítása (egyebek mellett), hogy míg Karl Friston Szabadenergia Elve (FEP) azt posztulálja, hogy az ágensek a környezetből érkező meglepetést (variációs szabadenergiát) minimalizálják [Friston, 2010], addig a jelen ontológia ezt megfordítja. Az én tézisem szerint az ágensek elsődleges hajtóereje a környezetre gyakorolt hatás (okozott meglepetés) maximalizálása, aminek a belső meglepetés csökkenése csupán szükségszerű mellékterméke; ezzel effektíve feloldva a "Dark Room" paradoxont.

Az eredeti cél egy célorientált IT projekt-menedzsment módszertan létrehozása volt, melynek követése - a kétkedők számára bebizonyítható módon - szükséges és elégséges egy információs cél megvalósulásához. Ennek létjogosultságát az indokolja, hogy a fellelhető módszertanok általában funkcionális leírások, melyek nem mutatják be a kényszereket, amik a funkciók mögött állnak, tehát nehezen bizonyítható az indokoltságuk.
A módszertan kidolgozása során hamar világossá vált, hogy valójában tetszőleges célorientált irányítási módszertan alkalmas a feladat ellátására, és innen könnyen elvezetett az út egy (elosztott) ágens architektúra szükségességéhez.
A jelenleg (általam) ismert ágens architektúrák szintén funkcionális leírások, melyek jól modellezik az ágensek működését, de nem adnak maradéktalan válaszokat a kényszerekre, melyek miatt adott funkciók szükségesek; ezért született ez az ontológia, mely a kényszerek felől közelíti meg az ideális architektúrát.

Az eredeti cél nem teljesült, semmilyen architektúra nem született (még), de a kényszerek jelentős részben feltárásra kerültek, és számot tarthatnak az érdeklődésre.

# Fogalmak

## Információáramlással kapcsolatos fogalmak

**állapottrajektória** - időhöz állapotot rendelő függvény; diszkrét esetben állapotok időbeli sorozata; az állapot időbeli változását reprezentálja, tehát egy kezdőállapot és változások sorozataként/függvényeként is értelmezhető

**információ ráta** - egy függvény, ami egy állapottrajektória adott pontjára (egy időpontra) meghatározza, hogy adott időpontban milyen gyorsan termelődik új információ, azaz mennyire tér el az állapotváltozás a korábbiakban megszokott mintázattól; nem más, mint az adott időpontig bezárólag értelmezett trajektória-csonk Shannon entrópiájának a differenciálja

**lokális regularitás** – az információ ráta differenciálhatósági rendje (azaz annak meghatározása, hogy a függvény hányadik differenciálja szinguláris, azaz szakad) egy adott (idő)pontban; ha az információ ráta egy adott időpontban szinguláris, akkor annak lokális regularitása 0; ha sima – tehát semelyik rendű differenciálja sem szakad -, akkor végtelen

**esemény** – az az időpont (és a hozzá tartozó állapotváltozás), amikor a lokális regularitás nem végtelen

**esemény regularitása** – a lokális regularitás az esemény bekövetkezésének pillanatában; definíciószerűen nem végtelen

**kaotikus esemény** – olyan esemény, aminek regularitása 0

**eseménytrajektória/folyamat** - időhöz eseményeket rendelő diszkrét függvény, azaz események időbeli sorozata; egy kezdőállapotból kiindulva rekonstruálható segítségével egy állapottrajektória

**globális regularitás** – a lokális regularitás reciprokának integráljának reciproka; azt határozza meg, hogy a teljes trajektória átlagosan milyen regularitással rendelkezett; ha a trajektóriában volt kaotikus esemény, akkor a trajektória regularitása is 0, tehát kaotikus. Mivel egy trajektória veszteségmentesen reprezentálható a különböző rendű differenciálok megváltozásának szuperpozíciójaként is, a globális regularitás tekinthető a trajektória reprezentációjának tömöríthetőségeként is; mivél magasabb szintű differenciálokkal reprezentálható a trajektória, annál kevesebb helyre van szükség a reprezentálásához.

**információáramlás** - olyan folyamat, ami kauzálisan rendezett, azaz minden eseményre igaz, hogy annak bekövetkezésének szükséges, de nem feltétlenül elégséges előfeltétele az előző esemény bekövetkezése

**csatorna** - az információáramlás tere/útja; az a fizikai vagy logikai közeg (a tér egy része), melynek állapotváltozásai alkotják egy információáramlás eseményeit; egy csatorna maga is csatornákra dekomponálható a terének particionálásával

**interfész** – csatornát particionáló sík; maga is értelmezhető állapotmentes csatornaként, az állapotváltozása a két oldalán zajló állapotváltozások differenciája; a két oldalának „limesze”

**információáramlási sebesség** – egy interfész állapotváltozásai által definiált trajektória információ rátája

**sávszélesség** – egy interfész által elhatárolt térrészek külső (pl. fizikai kényszerek) szülte maximális információáramlási sebessége; időben változhat, de nem az interfész állapotának része (hiszen az állapotmentes), hanem származtatott tulajdonság

**szűk keresztmetszet** – az az interfész, ami adott csatorna vonatkozásában a legkisebb sávszélességgel bír; egyben a csatorna sávszélessége

**csatorna topológia** - a különböző, térben potenciálisan átfedő csatornák rendszere

**csomópont** – a csatornák térbeli átfedésének helye; egy csomópontban egy eseménynek nem csak egy szükséges, hanem minden elégséges feltételeként bekövetkező esemény bekövetkezik.

**visszacsatolási hurok -** olyan önmagába záródó csatorna, melynek minden pontja csomópontként funkcionál (azaz az információáramlás önmagát fenntartó kauzális láncot alkot), és amelynek tetszőleges ponton vett vágása egy kétirányú interfészt eredményez.kimenet – az a csomóponti felület, ahol az állapotváltozásnak

**csomóponti kimenet maradék bizonytalansága -** egy adott csomópontra jellemző információs entrópia-többlet, amely a csomópontból kiinduló (kimeneti) eseménytrajektória azon információtartalmát reprezentálja, amely a csomópontba érkező (bemeneti) eseménytrajektóriából kauzális úton nem származtatható; a kimenet trajektória bemenő trajektória függvényében számolt Shannon-entrópiája

**kimenet meglepősége** – a csomóponti maradék bizonytalanság differenciálja, információ ráta

## Ágens

**ágens** - a tér egy összefüggő, véges része, melynek határolófelülete pontosan egy visszacsatolási hurok (az ágens-hurok) szűk keresztmetszetei közül a legkisebb felületű. A visszacsatolási hurok ágensen kívüli részét az ágens környezetének hívjuk; az ágens és környezete a hurok két kitüntetett csomópontja, a határolófelület pedig interfész.

## Ágenssel kapcsolatos fogalmak

**környezet pillanatnyi meglepettsége** – az ágens kimenetének meglepősége

**ágens pillanatnyi meglepettsége** – a környezet kimenetének, vagyis az ágens bemenetének meglepősége

**élettapasztalat** –a bemenet információ rátájának integrálja az ágens teljes élettartamára; azt határozza meg, hogy az ágens mennyi új információval találkozott élete során

**tapasztalati intenzitás** – az élettapasztalat élettartamra vetített átlaga

**pillanatnyi kognitív terhelés** – a bemenet információ rátájának és lokális regularitásának hányadosa; minél nagyobb, az ágens annál inkább olyan eseménnyel szembesül éppen, amihez még csak „hasonlót” sem látott

**kognitív áldozat** – a pillanatnyi kognitív terhelés integrálja; az ágens élettapasztalatának és annak globális regularitásának hányadosa

**mentális amortizációs ráta** – a kognitív áldozat élettartamra vetített átlaga

**ágencia** – az ágens azon tendenciája, hogy meglepi a környezetét

**lehorgonyzottság** – dinamikus modell (pl. világmodell) és a funkció (pl. a világ működése) közti korreláció

# Feltételezések

Az információáramlás energiaáramlással jár, még ha nem is feltétlenül egyező az irányban.

Energiaáramlás nem következhet be sem végtelenül rövid idő alatt, sem végtelen teljesítménnyel (sem ezek együtt).

Az ágens és környezete által particionált tér (praktikusan) végtelen.

Tetszőleges véges térrész információsűrűsége véges, de végtelen térrész – így az ágens környezete - állapottere (és így információtartalma) lehet végtelen, ugyanakkor lokálisan véges.

Az információfeldolgozás sebessége véges, így az ágens kimenetének előállítása >0 idő alatt megy végbe a bemenet rendelkezésre állását követően.

# Következtetések

## Fizikai kényszerek és korlátok

### A sávszélesség korlátossága

A sávszélesség tetszőleges fizikai csatornán és tetszőleges vágásán, így egy ágens interfészén is véges, tekintve, hogy ennek ellentéte végtelen teljesítményű energiaáramlást feltételezne; következésképpen fizikai rendszer állapotában tökéletesen kaotikus esemény nem következhet be; ugyanakkor létezhet olyan kvázi-kaotikus esemény, ami az ágens fizikai korlátain (lásd lentebb) túlmutat, ezért az ágens szempontjából kaotikusnak tekinthető.

### A sávszélesség determinizmusa

Az interfész (az elhatárolt térrészek fizikai tulajdonságaiból származtatott) sávszélessége kizárólag az ágens kimenete és a környezet bemenetének egymás állapotára gyakorolt hatására, determinisztikusan változik.

### Az ágens és környezete korlátai

Fentiek miatt sem az ágens, sem környezete nem lehet omnipotens, illetve az ágens nem lehet omnikogens, tekintve, hogy térfogata és információsűrűsége véges; ugyanakkor a környezet definíciószerűen potenciálisan omnikogens (hiszen térfogata végtelen).

### A megszűnés kényszere

Egy létező ágens nem tudja végtelen ideig fenntartani a környezet meglepését, tekintve, hogy – mivel állapottere véges – a környezet előbb-utóbb “kiismeri”, ezáltal a visszacsatolási hurok megszűnik.

Azért lehetséges egyáltalán az ágens fennmaradása – fentiek miatt statisztikailag véges ideig -, mert a környezetnek az ágens megismerést biztosító képességei lokálisan végesek (hiszen a “lokális” környezet egy véges térrész), és a globális környezet bevonódása a folyamatba időt igényel, tekintve, hogy az információáramlás sebessége korlátos.

## A túlélő ágensre vonatkozó abszolút kényszerek

Az ágensek létezése nem feltétlenül kényszer, de a létező ágensekre (fentiek miatt kényszerű) megszűnésükkor visszatekintve az alábbiakban leírt kényszereknek igaznak kell találtatniuk.

### Az ágencia kényszere

Az ágens határolófelületének- és a visszacsatolási hurok létezése fentiek miatt ekvivalensek: nem létező visszacsatolási huroknak nincs vágása, létezőnek viszont mindig van az ágens definíciónak megfelelő vágása.

Információnak a környezet felől nézve definíció szerint a környezet pillanatnyi meglepettsége, vagyis az ágens által szolgáltatott meglepetés; míg az ágens felől nézve az ágens pillanatnyi meglepettsége, vagyis a környezet által szolgáltatott meglepetés minősül; emiatt a visszacsatolási hurok fennmaradása – vagyis az ágens fennmaradása - egymás folyamatos meglepetését jelenti.

Mivel a környezet statisztikailag – hacsak a sávszélesség nem 0 – mindenképpen okoz meglepetést az ágensnek (a tekintve, hogy az ágens állapota által hordozott információ véges, a környezeté pedig praktikusan végtelen), az ágens fennmaradásának feltétele elsősorban a saját ágenciája, tehát a sávszélesség >0 fennmaradása és a környezet meglepetésének képessége.

### Lehorgonyzott világmodell meglétének kényszere

Egy ágens akkor tudja rendszerszerűen meglepni a környezetét, ha:
- az ágensnek rendszeresen szerencséje van, azaz véletlenszerűen képes mindig előállítani a megfelelő kimenet úgy, hogy az eredményül kapott kimeneti trajektória végül ne következzen a bemeneti trajektóriából
- az ágens állapota minden pillanatban korrelál (valamilyen mértékben) a bemeneti és kimeneti trajektóriákkal, vagyis a a világ (benne a környezet és saját maga) dinamikus modelljével; másszóval az **ágens** **rendelkezik világmodellel**; ez alapján pedig „tudhatja”, hogy mi az a kimenet, ami nem okoz meglepetést a környezetnek

A szerencsés ágens túléléséhez szükséges szerencse az élettapasztalattal exponenciálisan nő; rögzített tapasztalati intenzitás mellett ezért az ágens várható élettartama pozitívan korrelál a világmodellje lehorgonyzottságával.

Extrém esetben a lehorgonyzottság 0, vagyis az ágensnek nincs világmodellje, ebből az is következik, hogy **egy minimális lehorgonyzottság az ágens létrejöttének szükséges feltétele**.

#### Bemenet meglepőségének csökkenése, mint mellékhatás

A bemenet meglepősége a világmodell lehorgonyzottságával értelemszerűen automatikusan csökken, de ez csak mellékhatás; nem azért él túl az ágens, mert csökkenti a saját meglepettségét, hanem azért, mert növeli a kimenet meglepőségét; az utóbbi pedig az előbbit is magával hozza, a környezet ugyanis elkezd egyre inkább az ágens által rákényszerített pályán mozogni.

### Döntéskényszer

Az ágensnek, amennyiben több – a sávszélesség és az ágenciakényszer által nem korlátozott – kimenete is lehetséges, döntenie kell, hogy melyik kimenetet választja.

#### Célorientáltság kényszere

A döntés valójában az ágens világmodelljének és a bemenetek függvényében determinisztikus, tekintve, hogy nincs egyéb információ, ami azt befolyásolja.

Fentiek miatt utólag megfigyelve az egyes, aktuálisan lehetséges kimenetekhez az ágens aktuális állapota és az aktuális bemenetek függvényében egy – a túlélés szempontjából értelmezett – determinisztikus hasznosság rendelhető úgy, hogy a modell mindig a legnagyobb hasznú kimenet mellett dönt; szélsőséges (ellenben mindig megvalósítható) esetben úgy, hogy a ténylegesen választott kimenethez 1, más minden más kimenethez pedig egységesen 0 hasznosság kerül hozzárendelésre.

Tekintve, hogy fentiek miatt az ágens állapota a bemeneti és kimeneti trajektóriákkal korrelál, felírható egy olyan háromváltozós célfüggvény, ami egy adott bemeneti és kimeneti állapottrajektória-csonkhoz, valamint egy kimenethez hasznot rendel.

##### Leképzés „tradicionális” célfüggvényre

Ha a választott kimenetet beemeljük a kimeneti trajektóriába, valamint a bemeneti és kimeneti trajektóriákat összefésüljük, eredményként egy „hagyományos”, egyváltozós célfüggvényt kapunk, ami trajektóriacsonkhoz rendel hasznot; erre tekinthetünk úgy is, hogy az ágens trajektóriák között dönt, melyeknek az aktuális kimenetet leszámítva a múltja az ágens számára ismert (lehet).

### A világmodell inferenciája, mint döntési funkció

Fentiek miatt a döntés elméletben dekomponálható a szóba jövő (a sávszélesség által nem korlátozott) kimenetek enumerálására, az egyes kimenetekhez a haszon kiszámítására, és a legnagyobb hasznú kimenet kiválasztására.

Ugyanakkor a trajektóriákból álló világmodell önmagában tartalmaz minden ehhez szükséges információt, és annak inferenciájával kinyerhető a döntés; az inferencia több féle képpen megvalósítható, de alapja egy korábbi trajektória-rész autokorrelációja az aktuális trajektória-csonk végével. Ezt követően lehetséges a korreláló rész megfelelő (pl. leghosszabb, vagy legalább adott hosszúságú - tehát valahány lépésben nem halállal végződő) folytatásának, és ezáltal a közvetlenül következő kimenet kiválasztása.

### A fizikai struktúra fenntartásának és fejlesztésének kényszere

Az ágensnek megfelelő sávszélességgel - azaz fizikai struktúrával - kell rendelkeznie, ami lehetővé teszi a megfigyelést és az ágenciát, ugyanakkor megfelelően véd a fizikai behatások ellen. Ez valójában ellentmondás, mert a bemenetek és kimenetek könnyű állapotváltozást, azaz magas sávszélességet feltételeznek, míg a fizikai védekezés alacsonyat. Ez a gyakorlatban többféle alternatív stratégiával kezelhető (pl. interfész differenciálása, kimeneti és bemeneti sávszélesség differenciálása), de ezen stratégiák jelen dokumentum célja szempontjából nem relevánsak.

## A nagy mentális amortizációs ráta mellett túlélő ágensekre vonatkozó kényszerek

Rögzített, magas mentális amortizációs ráta mellett a várható élettartam az alábbi alfejezetkben leírt képességek mértékével pozitívan korrelál.

### Tanulás kényszere

Az ágens világmodellje semelyik pillanatban nem lehet teljesen lehorgonyzott, tekintve, hogy az ágens állapottere véges, a modell által (többek között) leírt környezeté viszont végtelen.

A világmodell (értéke) természetes módon amortizálódik, ha a környezet vagy az ágens működése olyan fázisba vált (és onnan már nem vált vissza), amiben a modell nem kalibrált; az amortizálódás sebessége értelemszerűen a mentális terheléssel arányos.

A kalibráció fenntartása/javítása a tanulás, mely a világmodell - vagyis a bemeneti és kimeneti trajektóriák - bővítését jelenti.

#### Naplózás, mint tanulás
A bemenetek - mint események - érzékelése és a kimenetek - mint események - kiváltása az ágens állapotának legalább ideiglenes megváltozásával jár, azonban ahhoz, hogy a világmodell változzon, a változásnak értelemszerűen permanensnek-, és a kauzalitás (leginkább idő-) sorrendjében rendezettnek-, azaz "naplószerűnek" kell lennie.

Amennyiben ez teljesül, tetszőleges bemenet érzékelése és tetszőleges kimenet kiváltása automatikusan tanulásnak is minősül, hiszen ezekkel a világmodell alapját képző trajektóriák bővülnek.

#### A pillanatnyi kognitív terhelés reciproka, mint a tanulást lehetővé tevő nembináris célfüggvény

A bináris célfüggvénnyel az a probléma, hogy a döntési funkció pontatlansága esetén - pont, ahol a tanulás releváns - az ágens csak a saját halálából "tanulna", ami egyéni túlélés szempontjából kontraproduktív.

Ehelyett az ágensnek olyan folytonos célfüggvényt kell alkalmaznia, ami ugyanúgy arányos a várható hátralévő élettartamával, méghozzá értelemszerűen nem temporális, hanem a kognitív áldozat tartományában mérve; ez pedig nem más, mint a pillanatnyi kognitív terhelés reciproka.

###  Proaktivitás

Bár a modell alapú inferencia natívan alkalmas predikciókra (az autokorrelált múltbéli részlet kiterjesztésével), tanulás hiányában ez kívülről mindig egy huzalozott döntésnek, reaktív viselkedésnek tűnik.

Folytonos célfüggvénnyel, és tanulással azonban ez valódi proaktivitássá minősül, ráadásul ha a célfüggvény a kognitív terhelés reciproka, a hosszú távú haszon rendkívül egyszerűen - az aktuális trajektória-csonk és a kiterjesztett trajektória-rész összeillesztésével kapott trajektória-csonk végének kognitív terhelésével - számolható.

##### Szimuláció

Az autokorreláció miatt eleve rekurzív, tehát belső visszacsatolási kör alapú interferencia kiegészíthető a meghosszabbított, projektált trajektória csonk további - rekurzív - inferenciájával, tehát hosszú távú szimulációval, ahol a belső visszacsatolási kör gerjesztésének csillapítását - tehát a szimuláció konvergenciáját - temporális (standard, vagy élettapasztalat alapú) diszkontálás biztosíthatja; mindez azonban fentiek miatt nem szükséges feltétele a proaktivitásnak.

##### Exploráció

A fentiek miatt a múlt kisebb "darabkáiból" összerakott jövőre alapozó szimuláció - a pontatlansága miatt - explorációnak is tűnhet, és nem teljesen kalibrált világmodell bővítésének - jobb híján - alapvető eszköze.

### A mentális- és fizikai állapot szétválasztásának kényszere

Magas mentális amortizációs ráta mellett a fennmaradás alapvető feltétele a gyors tanulás, ami többek között gyors állapotváltozást és nagy információsűrűséget igényel, míg a fizikai behatásoknak ellenálló fizikai struktúra pont az ellenkezőjét.

Ebből következik, hogy magas mentális amortizációs ráta mellett a túlélés feltétele a mentális és a fizikai állapot szétválasztása; ennek pedig következménye a visszacsatolási hurok (legalább) 8-assá formálódása: egy külső visszacsatolási hurok (az interakciós kör) a környezet és a fizikai állapot-, valamint egy belső - a fizikai állapoton keresztül az előzővel összekötött - visszacsatolási hurok (a kognitív kör) a fizikai állapot és a mentális állapot között.

## Optimalizáció és heurisztikák

Az ágens korlátos állapottere (azaz információtároló kapacitás) és számítási kapacitása a nagyobb hatékonyság érdekében különböző "trükköket" követel meg az ágens működésére vonatkozóan.

Ezen optimalizációs technikák alapvetően az alábbi három jelenségre alapoznak:
- dekompozíció
- priorizálás
- elimináció
- materializálás

Ezekből már levezethetők bonyolultabb optimalizációs technikák, pl.:
- absztrakció/veszteséges tömörítés (dekompozíció és priorizálás relevancia szerint, majd a kevésbé releváns komponensek eliminációja), ezzel számítási kapacitás és tárolókapacitás egyaránt megspórolható, értelemszerűen a kalibráltság csökkenése mellett
- veszteségmentes tömörítés (dekompozíció redundancia szerint, majd redundáns részletek eliminációja), ezzel tárolókapacitás nyerhető számítási kapacitás kárára)

Ezekre alapozva pedig képezhetők az ágensekre specifikusan jellemző optimalizációs technikák, pl.:
- szemantizálás (a "napló" absztrakciója és materializálása, lehetőve téve a gyorsabb - de kevésbé pontos - inferenciát; egyben szükségessé téve a szemantikus- és epizodikus memória szétválasztását)
- felejtés (a szemantikus- és epizodikus memória kevéssé releváns részeinek törlése, helyet nyitva az új emlékeknek)
- a predikció materializálása (azaz a hasznosság tárolása a trajektóriákhoz és az új tapasztalatokból származó, megváltozott hasznosság visszapropagálását az oda vezető múltbeli trajektóriákra; ezáltal lehetővé téve az inferencia során az 1 mélységű, mégis prediktív előretekintést)
- hierarchikus absztrakció ("Level Of Detail"; lehetővé teszi a modell több szintű absztrahálását, ezáltal az iteratív, de idő hiányában bármikor - egy adott pontosság mellett - leállítható számításokat)
- modularitás és párhuzamosítás (beleértve a cél dekompozíciót, arbitrálást, szinkronizációt/kommunikációt/állatmegosztást)
- dinamikus mintavételezés

A technikák felsorolása nem teljes körű.

# Érdekes következmények

A fentiek következményei az alábbi, a jelenleg (legalább részlegesen) elterjedt konszenzussal szembenő állítások validitása:
- nincsenek "tanult" reflexek, csak a gyakorlás (és a fenti technikák) miatt gyorsabb/nagyobb hosszú/jobb autokorreláció
- nincs mintakövetés, mint optimalizációs technika; ehelyett minden mintakövetés
- nincs megerősítéses tanulás, csak tanulás (bár előbbihez közell áll a haszon materializálása és visszapropagálása, ez azonban inkább optimalizációs technika, mint önálló funkció)
- nincs külön self-modell és környezet-modell, csak világmodell
- az ágens nem a saját meglepetését minimalizálja, hanem a környezetét maximalizálja; előbbi csak melléktermék; ez feloldja a Dark Room paradoxont is

# Továbfejlesztési  irányok

Fenti ontológia és dedukció - annak érdekében, hogy teljes legyen - kiterjesztendő további optimalizációs technikákkal, az azokra kényszerekkel és alkalmazásuk feltételeivel; valamint az elosztott/hiearchikus ágensek viselkedésére, együttműködésére és kommunikációjára (mentális állapotuk megosztására) vonatkozó kényszerekkel.

Ezt követően levezethető egy ágens (és ágens-hierarchia) "referencia architektúrája", mely már használható tetszőleges ágens (pl. MI, egy vállalat, biológiai, stb.) konstruktív vizsgálatára; ennek az az alapja, hogy az egyszerű túlélésre (vagy a faj túlélésére) optimalizált célfüggvény transzformálható, egy túlélésben jó ágens-architektúra másban is hatékony lesz (az instrumentális konvegencia elismerése mellett természetesen, ez azonban egy kellően hosszú - pl. egy állapotcél eléréséig tartó - trajektóriákhoz hasznot rendelő célfüggvény formájában eleve előáll).

## Referenciák

Friston, K. (2010). The free-energy principle: a unified brain theory? Nature Reviews Neuroscience, 11(2), 127-138. doi.org
Friston, K., Thornton, C., & Clark, A. (2012). Free-energy minimization and the dark-room problem. Frontiers in Psychology, 3, 130. doi.org



