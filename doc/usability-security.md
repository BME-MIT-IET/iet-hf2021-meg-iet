# Nem-funkcionális jellemzők vizsgálata 1/2

Alapvetően 4 különböző nem-funkcionális jellemző vizsgálatát végeztük el. Ebből ez a dokumentáció tartalmazza a biztonság és a használhatóság kérdését.

## Biztonsági teszt

*A teszt célja kimeríteni a szoftver esetleges biztonsági réseit és potenciális hibalehetőségeit*

A biztonsági teszt 7 fő lépésből áll, melyek az alábbiak:

* Sebezhetőségi vizsgálat
* Biztonsági vizsgálat
* Penetrációs vizsgálat
* Kockázatértékelés
* Biztonsági auditálás
* Etikus hackelés
* Állapotfelmérés

Ezek közül mi a **sebezhetőségi vizsgálat**ra koncentráluk legfőképp, továbbá a manuálisan is végezhető **biztonsági auditálás**ra. Elsőként a SonarQube eszköz által észlelt biztonsági hibákat detektáltuk, mely röviden arról írt, hogy ne a System.out-ot használjuk a hibák megjelenítésére, hanem használjunk loggert helyette.

A CSV fájlok olvasására használt külső könyvtár jól kezeli a biztonsági kockázatokat jelentő egyéb kiterjesztésű fájlok olvasását. 

A SonarCloud nem jelzett bizonsági hibákat, sem sebezhetőségeket. 

Külső fájlok beolvasása mindig is kockázatos folyamatnak minősült, de nem sikerült olyan adatot csempésznünk a bemeneti fájlba, ami miatt a könyvtár kockázatosan viselkedett volna.

Konklúzióként a könyvtárat biztonságosnak ítléjük meg.

## Használhatósági teszt

*Más néven UX testing, célja kideríteni, hogy mennyire felhasználóbarát az eszköz, továbbá mennyire egyszerű használni azt.*

A következő teszt esetek merülnek fel:

* A rendszer hatékonysága
* A rendszer pontossága
* A rendszer felhasználó barátsága

A teljesség igénye érdekében közösen megalkotott vélemények és tapasztalatok után jutottunk a következő eredményekre.

A CSV2RDF egy egyszerű, és könnyen kezelhető könyvtár. A neve önmagában sokatmondó, és lefedi a kevés funkciója által nyújtott szűk képességeinek halmazát. A rendszer hatékonysága egy külön dokumentációban kerül részletes kifejtésre.

Tapasztalataink alapján a tervezők a fejlesztés során - a könyvtár egyszerűsége révén - öszpontosítottak a pontosságra, és tesztjeink során kiderült, hogy jól alkalmazkodik nem várt felhasználói viselkedésekhez, azonban a hibák és a kivételek kezelése hagy némi kivánnivalót maga után. Ha valami hibaüzenet lép fel, az nem túl informatív, valamint nem a legpontosabb visszajelzéseket kapja a felhasználó.

Ezen tapasztalatok során arra jutottunk, hogy kezelni, valamint használni a könyvtárat nem okoz nehézségeket, és a rövid és tömör dokumentáció elégnek bizonyul. A jövőbeni használhatóság érdekében mindenképp javasoljuk az egyedi kivételek létrehozását, és alkalmazását, továbbá kiterjeszteni a hibák detektálásának spektrumát.
