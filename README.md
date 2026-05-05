# AgentOntology
Defines an ontology centered arount agens, and draws consequences from it, effectively resulting in a description of required state and functions for a viable agent.

# Alapfogalmak

## Információáramlással kapcsolatos fogalmak

**állapottrajektória** - időhöz állapotot rendelő függvény; diszkrét esetben állapotok időbeli sorozata; az állapot időbeli változását reprezentálja, tehát egy kezdőállapot és változások sorozataként/függvényeként is értelmezhető

**információ ráta** - egy függvény, ami egy állapottrajektória adott pontjára (egy időpontra) meghatározza, hogy adott időpontban milyen gyorsan termelődik új információ, azaz mennyire tér el az állapotváltozás a korábbiakban megszokott mintázattól; nem más, mint az adott időpontig bezárólag értelmezett trajektória-csonk Shannon entrópiájának a differenciálja

**lokális regularitás** – az információ ráta differenciálhatósági rendje (azaz annak meghatározása, hogy a függvény hányadik differenciálja szinguláris, azaz szakad) egy adott (idő)pontban; ha az információ ráta egy adott időpontban szinguláris, akkor annak lokális regularitása 0; ha sima – tehát semelyik rendű differenciálja sem szakad -, akkor végtelen

**esemény** – az az időpont (és a hozzá tartozó állapotváltozás), amikor a lokális regularitás nem végtelen

**esemény regularitása** – a lokális regularitás az esemény bekövetkezésének pillanatában; definíciószerűen nem végtelen

**kaotikus esemény** – olyan esemény, aminek regularitása 0

**eseménytrajektória/folyamat** - időhöz eseményeket rendelő diszkrét függvény, azaz események időbeli sorozata; egy kezdőállapotból kiindulva rekonstruálható segítségével egy állapottrajektória

**globális regularitás** – a lokális regularitás reciprokának integráljának reciproka; azt határozza meg, hogy a teljes trajektória átlagosan milyen regularitással rendelkezett; ha a trajektóriában volt kaotikus esemény, akkor a trajektória regularitása is 0, tehát kaotikus. Mivel egy trajektória veszteségmentesen reprezentálható a különböző rendű differenciálok megváltozásának szuperpozíciójaként is, a globális regularitás tekinthető a trajektória reprezentációjának tömöríthetőségeként is; mivél magasabb szintű differenciálokkal reprezentálható a trajektória, annál kevesebb helyre van szükség a reprezentálásához.

**információáramlás** - olyan folyamat, ami kauzálisan rendezett, azaz minden eseményre igaz, hogy annak bekövetkezésének szükséges, de nem feltétlenül elégséges előfeltétele az előző esemény bekövetkezése

**csatorna** - az információáramlás tere/útja; az a fizikai vagy logikai közeg (a tér egy része), melynek állapotváltozásai alkotják egy információáramlás eseményeit; egy csatorna maga is csatornákra dekomponálható a terének particionálásával

**interfész** – csatornát particionáló sík; maga is értelmezhető állapotmentes csatornaként, az állapotváltozása a két oldalán zajló állapotváltozások differenciája; a két oldalának „limesze”

**információáramlási sebesség** – egy interfész állapotváltozásai által definiált trajektória információ rátája

**sávszélesség** – egy interfész által elhatárolt térrészek külső (pl. fizikai kényszerek) szülte maximális információáramlási sebessége; időben változhat, de nem az interfész állapotának része (hiszen az állapotmentes), hanem származtatott tulajdonság

**szűk keresztmetszet** – az az interfész, ami adott csatorna vonatkozásában a legkisebb sávszélességgel bír; egyben a csatorna sávszélessége

**csatorna topológia** - a különböző, térben potenciálisan átfedő csatornák rendszere

**csomópont** – a csatornák térbeli átfedésének helye; egy csomópontban egy eseménynek nem csak egy szükséges, hanem minden elégséges feltételeként bekövetkező esemény bekövetkezik.

**visszacsatolási hurok -** olyan önmagába záródó csatorna, melynek minden pontja csomópontként funkcionál (azaz az információáramlás önmagát fenntartó kauzális láncot alkot), és amelynek tetszőleges ponton vett vágása egy kétirányú interfészt eredményez.kimenet – az a csomóponti felület, ahol az állapotváltozásnak

**csomóponti kimenet maradék bizonytalansága -** egy adott csomópontra jellemző információs entrópia-többlet, amely a csomópontból kiinduló (kimeneti) eseménytrajektória azon információtartalmát reprezentálja, amely a csomópontba érkező (bemeneti) eseménytrajektóriából kauzális úton nem származtatható; a kimenet trajektória bemenő trajektória függvényében számolt Shannon-entrópiája

**kimenet meglepősége** – a csomóponti maradék bizonytalanság differenciálja, információ ráta

## Ágenciával kapcsolatos fogalmak

**ágens** - a tér egy összefüggő, véges része, melynek határolófelülete pontosan egy visszacsatolási hurok (az ágens-hurok) szűk keresztmetszetei közül a legkisebb felületű. A visszacsatolási hurok ágensen kívüli részét az ágens környezetének hívjuk; az ágens és környezete a hurok két kitüntetett csomópontja, a határolófelület pedig interfész.

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
·        az ágensnek rendszeresen szerencséje van, azaz véletlenszerűen képes mindig előállítani a megfelelő kimenet úgy, hogy az eredményül kapott kimeneti trajektória végül ne következzen a bemeneti trajektóriából
·        az ágens állapota minden pillanatban korrelál (valamilyen mértékben) a bemeneti és kimeneti trajektóriákkal, vagyis a a világ (benne a környezet és saját maga) dinamikus modelljével; másszóval az **ágens** **rendelkezik világmodellel**; ez alapján pedig „tudhatja”, hogy mi az a kimenet, ami nem okoz meglepetést a környezetnek

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

#### A világmodell, mint implicit döntési funkció

Fentiek miatt a döntés dekomponálható a szóba jövő (a sávszélesség által korlátozott) kimenetek enumerálására, az egyes kimenetekhez a haszon kiszámítására és a legnagyobb hasznú kimenet kiválasztására.

Ugyanakkor a világmodell önmagában tartalmaz minden ehhez szükséges információt: az aktuális trajektóriát követő lehetséges kimeneteket, illetve az azokat követő kimeneteket - azaz implicit módon azt, hogy akkor az ágens még "él"-e - így a döntés nem más, mint a világmodell inferenciája.

## A nagy mentális amortizációs ráta mellett túlélő ágensekre vonatkozó kényszerek

Rögzített, magas mentális amortizációs ráta mellett a várható élettartam az alábbi alfejezetkben leírt képességek mértékével pozitívan korrelál.

### Tanulás kényszere

Az ágens világmodellje semelyik pillanatban nem lehet teljesen lehorgonyzott, tekintve, hogy az ágens állapottere véges, a modell által (többek között) leírt környezeté viszont végtelen.

A világmodell (értéke) természetes módon amortizálódik, ha a környezet vagy az ágens működése olyan fázisba vált (és onnan már nem vált vissza), amiben a modell nem kalibrált; az amortizálódás sebessége értelemszerűen a mentális terheléssel arányos.

A kalibráció fenntartása/javítása a tanulás, mely a világmodell - vagyis a bemeneti és kimeneti trajektóriák - bővítését jelenti.

#### Naplózás, mint tanulás
A bemenetek - mint események - érzékelése és a kimenetek - mint események - kiváltása az ágens állapotának legalább ideiglenes megváltozásával jár, azonban ahhoz, hogy a világmodell változzon, a változásnak értelemszerűen permanensnek-, és a kauzalitás (leginkább idő-) sorrendjében rendezettnek-, azaz "naplószerűnek" kell lennie.

Amennyiben ez teljesül, tetszőleges bemenet érzékelése és tetszőleges kimenet kiváltása automatikusan tanulásnak is minősül, hiszen ezekkel a világmodell alapját képző trajektóriák bővülnek.

###  A pillanatnyi kognitív terhelés reciproka, mint nembináris célfüggvény

A bináris célfüggvénnyel az a probléma, hogy a döntési funkció pontatlansága esetén - pont, ahol a tanulás releváns - az ágens csak a saját halálából "tanulna", ami egyéni túlélés szempontjából kontraproduktív.

Ehelyett az ágensnek olyan célfüggvényt kell alkalmaznia, ami arányos a várható hátralévő élettartamával, méghozzá értelemszerűen nem temporális, hanem kognitív áldozat tartományban mérve; ez pedig nem más, mint a pillanatnyi kognitív terhelés reciproka.

####  1 lépéses világmodell inferencia, mind döntés

A világmodell inferenciája a bináris célfüggvényhez hasonló, azzal a különbséggel, hogy nem kell két lépést inferálni (a most választandó kimenetet, és az azt követő kimenetet), elég a közvetlenül következő kimeneteket-, és azok kognitív terhelésének reciprokát vizsgálni, melyhez a modell minden információt biztosít.

### Rekurzív szimuláció alapú prediktivitás

A célfüggvény fent leírt természetes rekurziójának szabadjára engedésével a számolás során egy szimulációt kapunk: meghatározzuk, hogy adott cselekvésláncolatot - valamint a self és a környezet várható reagálása esetén - követően mennyi lesz a vitalitása az ágensnek.

A folyamat nem más, mit a self-modell tanításához használt belső visszacsatolási hurok gerjesztettségi állapotaként.

A rekurzió egy, az ágensen belüli belső visszacsatolási hurkot feltételez; ennek gerjesztésének csillapítása - és a szimuláció konvergenciája - időbeli diszkontálással biztosítható; a rekurziók engedélyezett száma tekinthető a tervezési horizontnak; a vitalitásfüggvény a célfüggvény nem rekurzív komponense.

A predikcióhoz szintén szükséges a munkamemória, a szimulált állapotváltozások tárolásához.

#### A proaktivitás és a szimuláció alapú prediktivitás ekvivalenciája

A reaktív ágensek tekinthetők úgy, mint egy 0 rekurziós szintű célfüggvénnyel, tehát 0 tervezési horizonttal rendelkező, tisztán vitalitás alapú döntést preferáló ágensek; ezesetben azonban a vitalitásfüggvény binárisan is modellezhető, így kijelenthető, hogy proaktivitás feltétele a rekurzív szimuláció alapú prediktivitás, aminek előfeltétele a self-modell taníthatósága.

Fentiek miatt a proaktivitás és a rekurzív szimuláció alapú prediktivitás ekvivalensek, ezért nevezzük az erre képes ágenseket egyszerűen csak proaktív ágenseknek.




