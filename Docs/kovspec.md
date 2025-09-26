# FalatPont - Követelmény specifikáció

## 1. Bevezetés
Ez a dokumentum a tervezett weboldal követelményeit részletezi.
Segíti a fejlesztőcsoport munkáját a rendszer pontos megvalósításában, illetve a követelmények felmérésében.
A dokumentáció összefoglalja egy recepteket összegyűjtő weboldal követelményeinek részletezését pontokba foglalva.
A cél egy felhasználóbarát egyszerű, áttekinthető platform biztosítása.
Ezen weboldal lehetővé kell tegye saját, régi, illetve új receptek létrehozását, közzétételét, keresését.
További cél, hogy az oldalon könnyedén tudjon eligazodni minden korosztály és felhasználó.
## 2. Jelenlegi helyzet
Jelenleg nincs összpontosított webes platform az egyedi felhasználói receptek számára.
A receptek csak különböző oldalakon, fórumokon, blogokon találhatóak meg.
Nincs egységes keresés, kategorizálás és a tervekhez hasonló egyszerű, letisztult, kezelhető weboldal.
Ezért kifejezetten nehéz a kedvenc receptek megtalálása.
Emellett magas kockázat rejlik az ismeretlen oldalokon való keresésben.
Fizetésre, nem kívánatos reklámokra, illetve szigorú feltételek elfogadására vannak kényszerítve a felhasználók.
## 3. Vágyálom rendszer
Regisztrálás után posztolhatnak recepteket a felhasználók.
Minden recept tartalmaz címet, leírást, hozzávalók listába rendezett felsorolását, illetve tálalási javaslatot.
A receptek kategorizálhatóak, például: desszert, főétel, vacsora, reggeli.
Keresési és szűrési funkció biztosítja a könnyű recept keresést.
A felhasználási szabályzat megtalálható kell legyen a főoldalon.
A platform biztosítja a felhasználóknak a weboldalt üzemeltető csoport elérését.
Email, telefonszám illetve, egyéb jogi törvényekhez vezető linkek feltüntetése a főoldalon.
Az oldal színes könnyen értelmezhető megfelelő méretű ikonokkal és megjelenéssel kell dolgozzon.
Jól összpontosuló látványt és könnyű követhetőséget biztosítson minden felhasználónak.
## 4. Jelenlegi üzleti folyamatok
Jelenleg a felhasználók különböző blogokon, közösségi média oldalakon osztják meg a receptjeiket. 
Ezek a platformok azonban nem nyújtanak egységes és struktúrált lehetőséget a receptek rendezésére vagy keresésére.
Az üzleti folyamat nem autómatizált, az adatvédelem, a szerkeszthetőség és a hosszú távú hozzáférés szintén nem garantált ezekben a környezetekben. 
Nem mellesleg a felhasználók egy része a saját jegyzeteit, papíralapú receptgyűjteményét használja.
## 5. Igényelt üzleti folyamatok
A weboldal létrehozásával az alábbi üzleti folyamatok autómaziálása és támogatása válik elérhetővé:
- Felhasználók kezelése (Regisztráció, Belépés).
- Receptfeltöltés: A felhasználók új recepteket hozhatnak létre a felületen keresztül.
- Kategorizálás és címkézés: A receptek kategóriákba sorolhatók és címkékkel is elláthatóak.
- Keresés és szűrés: A felhasználók kulcsszavak, kategóriák és egyéb szempontok alapján.kereshetnek a receptek között.
- Kapcsolattartás és visszajelzés: A felhasználók könnyen kapcsolatba léphetnek az oldal üzemeltetőivel.
## 6. A rendszerre vonatkozó szabályok
A rendszer működését az alábbi alapelvek és szabályok biztosítják:
- Csak regisztrált felhasználók tölthetnek fel recepteket.
- Tilos olyan tartalmat feltölteni, mely obszcén, jogsértő vagy sérti az oldal szabályzatát.
- A feltöltött receptekért a felhasználó a felelős, az oldal nem vállal felelősséget a harmadik fél tulajdonában álló tartalmakért.
- A moderátorok jogosultak a nem megfelelő tartalom törlésére/szerkesztésére.
- A rendszer reszponzív designnel készül, különböző eszközökön is könnyen használható. A biztonságos kapcsolatot a HTTPS protokoll biztosítja.

## 7. Követelménylista
A rendszerrel szemben az alábbi főbb követelmények kerülnek meghatározásra:
- A felhasználók számára biztosított legyen az egyszerű receptfeltöltés, -megosztás és -böngészés.
- A receptek kategorizálása és kulcsszavas keresése megvalósuljon.
- A receptekhez hozzászólási és értékelési lehetőség álljon rendelkezésre.
-	A rendszer biztosítson regisztrációs és belépési funkciót.
-	Minden felhasználó rendelkezzen saját profillal, ahol elmentheti és kezelheti kedvenc receptjeit.
-	A rendszer legyen megbízható, könnyen kezelhető és későbbi fejlesztésekhez bővíthető.
-	Biztosítani kell irányított és szabad szöveges riportok készítését:
 	        Irányított riport: kimutatások a kategóriák népszerűségéről, illetve a legtöbbször elmentett receptekről.
 	        Szabad szöveges riport: a felhasználói visszajelzések és vélemények összegyűjtése, melyek a rendszer fejlesztését segítik.
-	A riportok legyenek letölthetők és áttekinthető formátumban elérhetők.

## 8. Üzelti folyamat modell
1. **Regisztráció / Bejelentkezés**:
 A felhasználó létrehoz egy fiókot vagy belép meglévő adataival.
2. **Profilkezelés**:
A felhasználó szerkesztheti személyes adatait és elérheti kedvenc receptjeit.
3. **Receptfeltöltés**:
A felhasználó új receptet adhat hozzá címmel, leírással, hozzávalókkal és kategóriával.
4. **Recept közzététele**:
A rendszer eltárolja a receptet, amely megjelenik a többi felhasználónak is.
5. **Keresés és szűrés**:
A felhasználó kategóriák, címkék vagy kulcsszavak alapján kereshet recepteket.
6. **Interakció mások receptjeivel**:
A felhasználó megtekintheti, elmentheti.
7. **Moderálás**:
A moderátor szükség esetén eltávolítja vagy szerkeszti a szabályellenes tartalmakat.
8. **Riportkészítés**:
A rendszer automatikus statisztikákat és riportokat állít elő.

**Folyamatábra:**

<img src="\Images\abra01.jpg" width="525" height="410" alt="Üzleti folyamat modell ábra" /> 

## 9. Fogalomszótár
A dokumentációban szereplő alapfogalmak tisztázása érdekében az alábbi definíciók kerülnek rögzítésre:
- Recept: Egy adott étel elkészítésének leírása, amely tartalmazza a hozzávalók listáját, az elkészítés lépéseit és opcionálisan tálalási javaslatokat.
- Felhasználó: A weboldalon regisztrált személy, aki recepteket tölthet fel, kereshet, értékelhet, hozzászólhat, valamint mentheti kedvenc receptjeit.
- Profil: A felhasználó személyes oldala, ahol megtekintheti saját adatait, feltöltött receptjeit, valamint az általa elmentett kedvenc recepteket.
- Kategória: A receptek tematikus csoportosítása az étel típusa vagy jellege szerint (pl. levesek, főételek, desszertek, reggeli).
- Címke (tag): Kulcsszó, amellyel a felhasználó kiegészítheti a receptet, megkönnyítve a keresést és a szűrést.
- Hozzászólás: A felhasználók által a receptekhez fűzött szöveges visszajelzés.
- Értékelés: A felhasználók által adott pontszám vagy értékelési forma, amely a recept minőségét jelzi.
- Riport: A rendszer által előállított kimutatás vagy összesítés, amely a receptek használatáról és a felhasználói aktivitásokról ad információt (pl. népszerűségi statisztikák, visszajelzések).
- Moderátor: A rendszer üzemeltetője által kijelölt személy, aki jogosult a nem megfelelő tartalmak kezelésére (pl. törlésére vagy szerkesztésére).
- Adminisztrátor: A weboldalt üzemeltető személy(ek), akik teljes körű hozzáféréssel rendelkeznek a rendszerhez, és felelősek annak működéséért, karbantartásáért.

Ez a szótár biztosítja, hogy a fejlesztők, a megrendelő és a felhasználók egységesen értelmezzék a dokumentumban használt fogalmakat.
