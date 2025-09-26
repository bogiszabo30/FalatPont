# FalatPont - Rendszerterv

## 1. Bevezetés
A **FalatPont** projekt célja egy olyan webes rendszer kialakítása, amely összegyűjti és rendszerezi a felhasználói recepteket.
A jelenlegi helyzetben a receptek szétszórtan, különböző fórumokon, blogokon és közösségi oldalakon találhatóak meg.
Ezért kifejezetten nehéz őket keresni, és a hozzáférés sem egységes ([Követelmény spec.](/Docs/kovspec.mdec.md), 2. Jelenlegi helyzet).

A rendszer megvalósításával a felhasználók egyszerűen, regisztráció után tölthetnek fel recepteket.
A feltöltött receptek strukturáltan tartalmazzák a címet, hozzávalókat. 
Ezek mellett tartalmazzák az elkészítési lépéseket, egy tálalási javaslatot és a kategóriát ([Funkcionális spec.](/Docs/funkspec.mdec.md), 5. Adatbevitel).
Ez lehetővé teszi a hatékony keresést és szűrést a receptek között.
Ennek következtében a receptek jól áttekinthetőek és ez minden korosztály számára könnyen kezelhető felületet biztosít ([Követelmény spec.](/Docs/kovspec.mdec.md), 3. Vágyálom rendszer).

A fejlesztés során a hangsúly a reszponzív kialakításon, a gyors működésen és a biztonságon van. 
A rendszer HTTPS protokollt alkalmaz az adatok védelmére, a jelszavak biztonságosan tárolódnak.
A felhasználók csak szöveges adatokat vihetnek fel, ami kizárja a kártékony fájlok feltöltésének veszélyét ([Funkcionális spec.](/Docs/funkspec.mdec.md), 7. Biztonság).

A rendszer architektúrája rugalmasan alakítható, így könnyen bővíthető új funkciókkal, miközben a teljesítmény és a stabilitás megőrződik.
A fejlesztés során alkalmazott modern technológiák biztosítják a skálázhatóságot és a megbízhatóságot, így a rendszer hosszú távon is stabilan működik ([Funkcionális spec.](/Docs/funkspec.mdec.md), 8. Kompatibilitás).

Ez a rendszerterv a [követelményspecifikáció](/Docs/kovspec.mdec.md) és a [funkcionális specifikáció](/Docs/funkspec.mdec.md) alapján mutatja be a rendszer architektúráját, az adatbázis felépítését és a fő működési folyamatokat.
A tervezet fokozott figyelmet helyez a követelmények teljesítésére, illetve a funkcionalitás helyes kivitelezésére és betartására.

## 2. Architektúra és rendszerkomponensek
### 2.1 Áttekintés
A **FalatPont** háromrétegű architektúrára épül:
- **Prezentációs réteg (frontend)**, a felhasználói böngészőben futó reszponzív webes felület.
- **Alkalmazási réteg (backend)**, a szerveroldali logika, amely kezeli a felhasználói kéréseket és érvényesíti az adatokat.
- **Adatréteg (adatbázis)**, a receptek, felhasználók és kategóriák tárolásáért felelős relációs adatbázis.

Ez a rétegezés biztosítja, hogy a rendszer bővíthető legyen, például új funkciók (értékelések, hozzászólások) hozzáadásával anélkül, hogy a stabilitás sérülne ([Követelmény spec.](/Docs/kovspec.mdec.md), 5. Igényelt üzleti folyamatok).

<img src="\Images\2_1_Abra.png" width="525" height="420" alt="Architektúra rétegek ábra" /> 

### 2.2 Frontend
A kliensoldali komponens biztosítja a felhasználók számára a receptek böngészését, keresését és feltöltését. 
A felület minden modern böngészőben működik (Chrome, Firefox, Safari, Edge).

A weboldal mobilon, tableten, valamint asztali eszközökön is jól használható ([Funkcionális spec.](/Docs/funkspec.mdec.md), 8. Kompatibilitás).
A dizájn minimalista, így gyors betöltést és könnyű navigációt tesz lehetővé. 

A vizuális visszajelzések, például színváltozás vagy gombkiemelés segítik a felhasználót az interakciók során ([Funkcionális spec.](/Docs/funkspec.mdec.md), 9. UI Képernyőtervek).
Ezek az interaktív elemek növelik a felhasználói élményt, mivel egyértelmű visszajelzést adnak a felhasználó műveleteire és csökkentik a hibázás lehetőségét.

### 2.3 Backend
A szerveroldali logika felel a felhasználói hitelesítésért, a receptfeltöltésért, a keresésért és az adatellenőrzésért. 
Az űrlapok validálása kliens és szerveroldalon egyaránt történik, hogy megakadályozza a hibás vagy rosszindulatú adatok bevitelét ([Funkcionális spec.](/Docs/funkspec.mdec.md), 5. Adatbevitel).

<img src="\Images\2_3_3_3_Abra.png" width="525" height="370" alt="Architektúra rétegek ábra" /> 

A backend moduláris felépítésű, így könnyen bővíthető.
Ez a moduláris felépítés lehetővé teszi új szolgáltatások és funkciók gyors integrálását a rendszerbe, anélkül, hogy a meglévő működést zavarná.
Emellett a karbantartás és a hibakeresés is egyszerűbbé válik, mivel az egyes modulok önállóan tesztelhetők és frissíthetők.

Az adminisztrátorok számára külön felület biztosítja a moderálást. 
A weboldal lehetővé teszi a nem megfelelő tartalmak gyors eltávolítását ([Követelmény spec.](/Docs/kovspec.mdec.md), 6. A rendszerre vonatkozó szabályok).

### 2.4 Kommunikáció és biztonság
A kliens és a szerver közötti kommunikáció HTTP protokollon keresztül történik.
A weboldal titkosított HTTPS kapcsolattal üzemel ([Funkcionális spec.](/Docs/funkspec.mdec.md), 7. Biztonság). 
Az adatok szöveg alapú formátumban kerülnek továbbításra, amely könnyen feldolgozható és integrálható más rendszerekkel.
A rendszer figyeli a spam jellegű tartalmakat, és a moderátorok jogosultak a szabálytalan bejegyzések törlésére. 
Ezzel biztosítható a tartalom minősége és a felhasználói élmény megőrzése ([Funkcionális spec.](/Docs/funkspec.mdec.md), 7. Biztonság).

## 3. Adatbázis terv
### 3.1 Entitások
Az adatbázis relációs modellre épül, amely biztosítja a konzisztens és jól strukturált adattárolást. 

**A fő entitások a következők:**
- **Felhasználó:** azonosító, név, e-mail, jelszó, regisztráció dátuma ([Követelmény spec.](/Docs/kovspec.mdec.md), 5. Igényelt üzleti folyamatok).
- **Recept:** receptazonosító, cím, leírás, hozzávalók, elkészítési lépések, tálalási javaslat, beküldés dátuma, kategória ([Funkcionális spec.](/Docs/funkspec.mdec.md), 5. Adatbevitel).
- **Kategória:** kategóriaazonosító, megnevezés (pl. leves, főétel, desszert, vacsora, reggeli).

<img src="\Images\3_1_Abra.png" width="525" height="410" alt="Architektúra rétegek ábra" /> 

### 3.2 Kapcsolatok
- Egy felhasználó több receptet tölthet fel ([Követelmény spec.](/Docs/kovspec.mdec.md), 5. Igényelt üzleti folyamatok).
- Egy recept több hozzávalót tartalmazhat ([Funkcionális spec.](/Docs/funkspec.mdec.md), 5. Adatbevitel).
- Egy recept pontosan egy kategóriába tartozik, de egy kategóriához több recept is kapcsolódhat.
- A receptek azonosítása a nevüktől független, azonos nevű receptek is feltöltésre kerülhetnek.
- Egy recept több elkészítési lépést tartalmazhat, amelyek sorrendje meghatározott.
- Egy recepthez több címke is tartozhat, ami segíti a szűrést és keresést.
- A rendszer naplózza a felhasználói tevékenységeket, így egy felhasználóhoz több művelet (feltöltés, módosítás) is kapcsolódhat.

### 3.3 Normalizálás és teljesítmény
Az adatbázis-tervezés során a redundancia minimalizálására és a normalizálásra törekedtünk, hogy az adatok karbantarthatósága biztosított legyen.
Ugyanakkor az indexek kialakítása fontos szerepet játszik a gyors keresési funkció megvalósításában ([Funkcionális spec.](/Docs/funkspec.mdec.md), 6. Teljesítmény).

A rendszer támogatja a kulcsszavas keresést és a kategória szerinti szűrést, ami felhasználóbarát módon jeleníti meg az eredményeket ([Funkcionális spec.](/Docs/funkspec.mdec.md), 5. Adatkimenet).
Ez lehetővé teszi a felhasználók számára, hogy gyorsan megtalálják a számukra releváns recepteket, akár konkrét hozzávalók, akár étel típus alapján keresnek.

### 3.4 Biztonság és adatvédelem
Minden felhasználói adat biztonságosan tárolódik, a jelszavak biztonságosan kerülnek az adatbázisba. 
A szerver folyamatosan frissítve van a biztonsági hibák minimalizálásának érdekében ([Funkcionális spec.](/Docs/funkspec.mdec.md), 7. Biztonság).
A rendszer nem tárol személyes adatokat a felhasználókról a szükséges minimumon túl, így az adatvédelmi szempontok is érvényesülnek ([Funkcionális spec.](/Docs/funkspec.mdec.md), 7. Biztonság).

## 4. Funkcionális tervek / folyamatok
### 4.1 Rendszer szereplők
A rendszer fő szereplői:
- Vendég felhasználó: regisztráció nélkül böngészhet, kereshet recepteket, de nem tud értékelni vagy feltölteni.
- Regisztrált felhasználó: új recepteket tölthet fel, értékelhet, hozzászólhat, recepteket elmenthet a kedvencei közé.
- Adminisztrátor / moderátor: jogosult a tartalmak felülvizsgálatára, törlésére, valamint a felhasználók kezelésére.
- 
<img src="\Images\Felhasznalo_hierarchia.png" width="925" height="820" alt="Architektúra rétegek ábra" />

### 4.2 Használati esetek és lefutásaik
- Recept feltöltése:
1. A felhasználó belép a rendszerbe.
2. A „Recept feltöltése” menüpontra kattint.
3. Kitölti a kötelező mezőket (cím, hozzávalók, elkészítési leírás, kategória).
4. Opcionálisan képet tölt fel.
5. A rendszer validálja az adatokat, majd eltárolja az adatbázisban.
6. A recept azonnal megjelenik a kategóriájában.
- Receptek keresése:
1. A felhasználó beír egy kulcsszót a keresőmezőbe.
2. A rendszer kilistázza a találatokat relevancia szerint.
3. A felhasználó szűrőfeltételeket alkalmazhat (pl. kategória, hozzávaló, időtartam).
4. A kiválasztott recept részletei egy külön oldalon jelennek meg.
- Értékelés és hozzászólás:
1. A felhasználó kiválaszt egy receptet.
2. Értékelést ad (1–5 csillag).
3. Írásos hozzászólást fűzhet a recepthez.
4. A rendszer menti az értékelést, és átlagot számít.
### 4.3 Határosztályok
- Belépési felület: felhasználónév/jelszó mezők, hibajelzések.
- Receptfeltöltő űrlap: szöveges mezők, kategóriaválasztó legördülő lista, kép feltöltés.
- Recept megjelenítő felület: hozzávalók listája, elkészítési lépések, értékelési lehetőség, hozzászólások.
- Keresőfelület: kulcsszómező, szűrőpanelek, találati lista.

### 4.4 Menü hierarchia

- Kezdőlap
  - Receptek böngészése
    - Kategóriák (Levesek, Főételek, Desszertek stb.)
  - Keresés
  - Saját profil
    - Kedvenc receptek
    - Saját feltöltések
  - Recept feltöltése
  - Admin felület (csak moderátoroknak)
 
  <img src="\Images\Kategoriak.png" width="925" height="820" alt="Architektúra rétegek ábra" />
  
## 5. Felhasználói felület tervei
### 5.1 Képernyőtervek
- Kezdőlap: kiemelt receptek, keresősáv a tetején.
- Receptoldal: bal oldalt kép és hozzávalók, jobb oldalt elkészítési lépések és értékelések.
- Receptfeltöltő oldal: űrlapmezők, kép feltöltési lehetőség, mentés gomb.
- Profil oldal: kedvencek, feltöltött receptek listája, beállítások.

### 5.2 Felhasználói élmény (UX)
- Reszponzív kialakítás: mobilon és asztali gépen is könnyen kezelhető.
- Interaktív gombok: vizuális visszajelzések (pl. zöld pipa sikeres mentéskor).
- Hibaüzenetek: piros színnel, pontos magyarázattal (pl. „A recept címe nem lehet üres”).
- Navigáció: mindig látható menüsor, gyors elérés a fő funkciókhoz.
  
## 6. Nem funkcionális tervek
A rendszer nem funkcionális követelményei a teljesítmény, megbízhatóság, hordozhatóság és skálázhatóság szempontjai szerint lettek meghatározva.

### 6.1 Teljesítmény
- A webalkalmazás célja a gyors válaszidő és gördülékeny felhasználói élmény biztosítása. Az oldal statikusan vagy szerver oldalon generált tartalmait a [Vercel](https://vercel.com/) szolgálja ki, amely automatikusan CDN-en keresztül osztja el azokat, így a válaszidő jelentősen csökken.
- A projekt [Next.js](https://nextjs.org/) keretrendszerre épül, amely a buildelés során statikus optimalizálást, valamint automatikus kód szeparálást végez. A Next buildfolyamata kizárja a használaton kívüli változókat, és szigorú lintinget alkalmaz, így a végeredmény egy karcsú, optimalizált alkalmazás, amely biztonságos és gyors.

<img src="https://vercel.com/vc-ap-vercel-marketing/_next/image?url=https%3A%2F%2Fassets.vercel.com%2Fimage%2Fupload%2Fcontentful%2Fimage%2Fe5382hct74si%2F4pRLTKDLGLcTMFb0NFwXZK%2F09dacaa656e6d55f6ac096360313c572%2FGroup_513639__2_.png&w=1920&q=75" alt="vercel-git-integration">

### 6.2 Megbízhatóság
- Az alkalmazás folyamatos üzemeltetését a Vercel infrastruktúra biztosítja, amely automatikusan skálázódik. A Vercel által biztosított load balancing, valamint az automatikus cachelés minimalizálja a kimaradást.
- Az alkalmazás backend adatbázisa a [MongoDB Atlas](https://www.mongodb.com/products/platform), amely egy felhőalapú NoSQL adatbázis. Az adatbázis egy németországi AWS szerveren fut, így az európai adatvédelmi szabályozásoknak (pl. GDPR) is megfelel, miközben magas rendelkezésre állást és automatikus backupot biztosít.

### 6.3 Skálázhatóság
- A Next.js architektúrája lehetővé teszi a projekt jövőbeli skálázását mind frontend, mind backend irányba. A Vercel automatikus skálázást biztosít, így a növekvő forgalom nem befolyásolja a teljesítményt.
- A MongoDB Atlas szintén képes automatikusan skálázódni, mind tárolókapacitás, mind lekérdezési teljesítmény tekintetében.

### 6.4 Hordozhatóság
- A teljes rendszer platformfüggetlen, és konténerizált környezetbe is könnyen átültethető, ha szükséges. A fejlesztési stack (Node.js, Next.js, MongoDB) széles körben támogatott, nyílt forráskódú és jól dokumentált, így a projekt könnyen átadható más fejlesztők vagy csapatok számára is.

## 7. Üzemeltetés és karbantartás
- A rendszer üzemeltetése teljes egészében a GitHub és Vercel integrációján keresztül történik, így minimalizálható a manuális beavatkozás szükségessége, miközben biztosítható a magas minőségű és gyors fejlesztési folyamat.

### 7.1 Automatikus Deploy (CI/CD)
- A projekt GitHub repository-jában minden commit vagy pull request automatikusan triggereli a build folyamatot. A `main` ágra történő push esetén a Vercel automatikusan újrabuildeli és publikálja az oldalt. Ez garantálja, hogy a produkciós verzió mindig a legfrissebb állapotot tükrözi.

- A Next.js build során automatikusan lefutnak a statikus és dinamikus ellenőrzések, beleértve:
  - Linter szabályok (ESLint)
  - Használaton kívüli változók, függvények kiszűrése
  - Tipushibák (ha TypeScript-et használunk)
  - Route optimalizáció és automatikus statikus generálás (ISR/SSG)

- Ennek köszönhetően a produkciós környezetbe csak tiszta, optimalizált és biztonságos kód kerülhet.

<img src="\Images\flowchart.png" alt="Github-Vercel CI/CD" /> 

### 7.2 Környezeti változók kezelése
- Az érzékeny információk (pl. MongoDB URI, titkos kulcsok) nincsenek a forráskódban. Ezeket a Vercel adminisztrációs felületén, projekt szintű Environment Variable-ként adjuk meg. A változók különböző környezetekhez külön is beállíthatók (pl. `development`, `preview`, `production`).
- Ez a megközelítés egyrészt biztonságos, másrészt rugalmas, mivel a környezeti konfiguráció módosítása nem igényli a forráskód újraverziózását.

### 7.3 Monitorozás és hibakezelés
- A Vercel adminfelülete részletes logokat biztosít minden egyes build és deploy folyamatra, valamint a runtime hibákra is. A hibák könnyen visszakereshetők a GitHub commit hash alapján, így gyors hibakeresés valósítható meg.

### 7.4 Mentések és adatbiztonság
- Az adatbázis automatikusan végzi az adatok biztonsági mentését és beállítható napi, heti vagy havi mentési ciklus is. Emellett a felhasználók adatainak védelmét titkosítás, jogosultságkezelés és audit logok biztosítják.

### 7.5 Dokumentáció és frissítések
- A rendszer dokumentációja a `README.md` fáljban van tárolva. Ezt folyamatosan frissítjük a változásokkal összhangban.
- Az automatikus CI/CD rendszernek köszönhetően minden új commit egységes módon kerül deployolásra, így a dokumentáció és az alkalmazás működése folyamatosan szinkronban tartható.


