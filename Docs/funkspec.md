# FalatPont -  Funkcionális specifikáció

## 1. Bevezetés
A dokumentum célja, hogy részletesen bemutassa a FalatPont rendszer funkcionális specifikációját.
A FalatPont egy online receptmegosztó platform, amely a közösségi élményt és az egyszerű használhatóságot helyezi előtérbe.
A rendszer elsődleges feladata, hogy lehetőséget biztosítson a felhasználóknak receptek feltöltésére, keresésére, megosztására és értékelésére.
A specifikáció tartalmazza a jelenlegi helyzet elemzését, a megvalósítandó rendszer működésének leírását, a felhasználói műveleteket, valamint a rendszer reakcióit.
Kiemelt cél, hogy egy modern, biztonságos és átlátható weboldal jöjjön létre, amely hosszú távon is fenntartható.
A fejlesztés során a felhasználóbarát működés, a reszponzív kialakítás és a közösségi funkciók egyaránt kiemelt szerepet kapnak.
Fontos szempont továbbá, hogy a rendszer képes legyen a jövőben új funkciókkal bővülni, például mobilalkalmazás vagy közösségi médiás integráció formájában.
## 2. Rendszer áttekintés
A FalatPont egy központi receptmegosztó weboldal, amely strukturált és felhasználóbarát módon kezeli a recepteket.
A rendszer fő funkciói közé tartozik a receptek létrehozása, kategorizálása és megosztása, a keresési és szűrési lehetőségek biztosítása, valamint az értékelési és hozzászólási funkciók.
A felhasználók saját profillal rendelkeznek, ahol nyomon követhetik kedvenc receptjeiket és aktivitásaikat.
A moderátorok szerepe kiemelt, mivel ők biztosítják a tartalom minőségét, valamint kiszűrik a nem megfelelő bejegyzéseket.
A rendszer támogatja a közösségi interakciókat, elősegítve a tudásmegosztást és a közös élményeket.
A biztonságos működés érdekében az adatkezelés megfelel a vonatkozó adatvédelmi előírásoknak és GDPR szabályozásnak.
A weboldal reszponzív kialakításának köszönhetően minden eszközön teljes funkcionalitással elérhető.
A rendszer hosszú távon skálázható, így képes kezelni a növekvő felhasználói és tartalmi igényeket.
A fejlesztés során modern technológiák kerülnek alkalmazásra, amelyek gyors működést és stabilitást biztosítanak.
## 3. Felhasználói műveletek
A rendszer a felhasználóknak többféle művelet végrehajtását teszi lehetővé.
- Regisztráció és belépés: a felhasználók új fiókot hozhatnak létre, vagy használhatják meglévő belépési adataikat.
- Receptfeltöltés: strukturált űrlap segítségével, képekkel és kategóriákkal ellátva.
- Receptek böngészése és keresése: kulcsszavak, kategóriák, illetve hozzávalók alapján.
- Értékelés és hozzászólás: a közösség véleményének megosztása, amely segíti a receptek rangsorolását.
- Kedvencek kezelése: receptek elmentése és személyes listák kialakítása.
- Kapcsolatfelvétel: az üzemeltetőkkel való kommunikáció a weboldalon megadott csatornákon.
- Profil testreszabása: a felhasználó beállíthatja személyes adatait, profilképét és értesítési beállításait.
A felhasználói műveletek célja, hogy mindenki számára gyors, egyszerű és intuitív interakciót biztosítsanak.

A felhasználói műveletek célja, hogy mindenki számára gyors, egyszerű és intuitív interakciót biztosítsanak.
## 4. Rendszer reakciók
A rendszer minden felhasználói műveletre egyértelmű és következetes választ ad.
- Regisztráció vagy belépés után a felhasználó automatikusan a kezdőoldalra kerül.
- Új recept feltöltésekor a rendszer validálja az adatokat, és hibás mezők esetén részletes hibaüzenetet jelenít meg.
- A keresőfunkció valós időben kínál találatokat a megadott kulcsszavak alapján.
- Hozzászólás vagy értékelés elküldése után a bejegyzés azonnal megjelenik a nyilvános felületen.
- Kedvencnek jelölés esetén a recept azonnal elmentésre kerül a felhasználói profilban.
- Ha a moderátor tartalmat töröl vagy szerkeszt, a rendszer figyelmeztetést jelenít meg a változtatásról.
- Hibás működés esetén a felhasználóbarát hibaüzenetek segítenek a probléma elhárításában.
- A rendszer minden sikeres művelet után vizuális visszajelzést ad (pl. zöld jelzés vagy megerősítő üzenet).
- A hibák naplózásra kerülnek, hogy az üzemeltetők könnyebben azonosíthassák és javíthassák azokat.
  
Ez biztosítja, hogy a felhasználók mindig tisztában legyenek a műveleteik eredményével.
## 5. Adatbevitel és -kimenet
A rendszer egyszerű és intuitív adatbeviteli lehetőségeket kínál a felhasználók számára.
### Adatbevitel
- A receptfeltöltés egy strukturált, szöveges űrlapon keresztül történik.
- Az űrlap kötelező mezőket tartalmaz, például:
  - Recept neve
  - Hozzávalók listája
  - Elkészítési lépések
  - Kategória kiválasztása (pl. leves, főétel, desszert)
- Minden adatbeviteli mező validálva van a kliens- és szerveroldalon is (pl. nem lehet üres, nem tartalmazhat HTML kódot stb.).
- A rendszer nem enged fájlfeltöltést, csak tisztán szöveges adatbevitelt tesz lehetővé.
### Adatkimenet
- A receptek listája könnyen böngészhető formában jelenik meg a kezdőképernyőn.
- A kereső funkció azonnali szűrt találatokat jelenít meg a megadott kulcsszavak és kategóriák alapján.
- A kiválasztott receptoldal részletesen mutatja:
  - A recept nevét
  - A hozzávalókat
  - Az elkészítési lépéseket
  - A beküldés dátumát
- A kimeneti adatokat reszponzív dizájnban jeleníti meg, minden képernyőméreten olvashatóan.
## 6. Teljesítmény
A rendszer kialakítása során kiemelt figyelmet kapott a gyors működés és kis erőforrásigény biztosítása.
- A weboldal gyors betöltési sebességet biztosít minden eszközön és böngészőben.
- A felhasználói felület minimalista kialakítása hozzájárul a kis sávszélesség-használathoz és a gyors válaszidőhöz.
- A keresési funkció optimalizált, amely nagy mennyiségű recept esetén is gyorsan ad vissza találatokat.
- A szerver folyamatos karbantartása biztosítja, hogy a rendszer mindig naprakész legyen teljesítmény és biztonság szempontjából is.
- A mobilos és asztali felhasználói élmény egyaránt gyors és zökkenőmentes.
## 7. Biztonság
A felhasználók jelszavait biztonságosan táruljuk a rendszerben.
Minden felhasználói adatátvitelt HTTPS protokoll biztosít.
A rendszer nem kér és tárol személyes adatokat a felhasználókról.
A feltöltött recepteket az adminisztrátorok folyamatosan felülvizsgálják, hogy ne történhessen visszaélés.
A moderátorok gyorsan eltávolíthatják a nem megfelelő tartalmakat.
A rendszer figyeli a spam jellegű tartalmakat a posztolás előtt.
A weboldalon nincs olyan felület, amely lehetővé tenné a külső és személyes támadásokat.
A felhasználók nem tölthetnek fel fájlokat, így nincs fertőzés veszély.
Csak szöveges tartalmat enged a felhasználóknak közzétenni.
A weboldal szervere frissítve van a biztonsági hibák minimalizálásának érdekében.
## 8. Kompatibilitás
A weboldal minden modern böngészőben elérhető, például Chrome, Firefox, Safari, Opera és Edge.
Az oldal szükség esetén reszponzív, így mobilon, tableten és asztali gépen is jól jelenik meg.
A rendszer ellenőrzi a képernyőméretet, és ennek megfelelően rendezi az oldalelemeket.
A receptlista és a receptkereső minden eszközön olvasható formában jelennek meg.
A keresési találatok listája mobilon is könnyen görgethető.
A receptkereső funkció minden eszközön gyorsan működik, nem okoz kellemetlenséget a felhasználónak a túl sok várakozás.
A receptfeltöltés egyszerű szöveges űrlap segítségével történik, ezért minden eszközzel kompatibilis.
A weboldal nem igényel speciális bővítményeket vagy plugineket a felhasználóktól.
A rendszer böngésző független működést biztosít, hogy minden felhasználó hozzáférhessen a tartalmakhoz.
Az oldal menüje egyszerű, így minden platformon egyszerűen és könnyedén használható.
A linkek és gombok minden eszközön kattinthatóak és megfelelően reagálnak a felhasználói interakcióra.
A receptfeltöltő űrlap minden eszközön egyformán működik, nincs szükség külön programra.
A weboldal gyors betöltődése minden platformon biztosított.
## 9. UI Képernyőtervek - interakciók
A kezdőképernyő áttekinthetően mutatja a recepteket.
A felhasználó könnyen böngészhet kategóriák szerint.
A keresőmező egyszerű és gyors, azonnali találatokat ad.
A recept feltöltése űrlapon keresztül történik, egyszerű mezőkkel, könnyű kezelhetőséget biztosítva.
A receptlistán minden recept egészében jelenik meg.
A mobilos menü egyszerű, könnyen kezelhető.
A gombok és linkek elég nagyok a könnyű kattintáshoz mobilon is.
A weboldal vizuális visszajelzést ad a kattintásokra és műveletekre, példaul, színezéssel vagy méretezéssel.
A keresési találatokat szűrni lehet kategória alapján.
A receptoldalon minden fontos információ, például hozzávalók és elkészítési lépések jól láthatóan van elrendezve.
Az oldal görgethető, de a fontos elemek mindig könnyen megtalálhatóak.
A receptoldal nem zsúfolt, egyszerű elrendezése megkönnyíti az olvasást és a böngészést.
A karbantartó csoport és a weboldal üzemeltetőinek elérhetősegeik megjelennek a fő oldal lábjegyzékében.
Email, telefonszám, egyéb elérhetőség is elérhető a jegyzékből.
A kapcsolódó jogi szabályok és törvények is linken keresztül elérhetőek a jegyzékből kattintva.
A feltöltésre vonatkozó szabályzat könnyedén elérhető és feltűnően van jelezve a fő oldalon.

**Formázás nélküli Képernyő tervezetek:**

Főoldal elrendezés:

<img src="\Images\UIterv.png" width="525" height="380" alt="UI terv" />

Poszt szekció - Receptek szekció:

<img src="\Images\PostSection.png" width="220" height="250" alt="Post Section" /> <img src="\Images\RecipesSection.png" width="300" height="250" alt="Recipes Section" />

Recept elrendezés:

<img src="\Images\SingleRecipe.png" width="220" height="340" alt="Single Recipe" /> 

## 10. Fogalomtár
| Fogalom       | Meghatározás |
|---------------|--------------|
| **HTTPS**     | Biztonságos, titkosított adatátviteli protokoll a felhasználó és a szerver között. |
| **Reszponzív dizájn** | Olyan weboldal-kialakítás, amely a képernyőmérethez igazodik, így minden eszközön megfelelően jelenik meg. |
| **Spam**         | Nem kívánt vagy kéretlen tartalom, amelyet automatizáltan vagy rosszindulatúan küldenek be a rendszerbe. |
| **Szerver**      | Az a távoli számítógép, amely tárolja a weboldalt és kiszolgálja a felhasználói kéréseket. |
| **Kliens**       | A felhasználó eszköze vagy böngészője, amelyről a weboldal elérése történik. |
