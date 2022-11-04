# Rendszerterv
## 1. A rendszer célja

A Top G's nevű csapat feladata egy olyan felület fejlesztése, ami széleskörben elérhető, egyszerű megoldást nyújt különböző felmérések elvégzésére. Az alkalmazás feladatai közé tartozik kérdőívek létrehozása, kitölthetősége, kezelése, esetleg ezek törlése. Szükség van még a kérdőívek kiértékelésére, az ehhez tartozó felület létrehozására is. A Kérdőív létrehozásakor kötetlen számú kérdés hozzáadásához kell lehetőséget biztosítani, illetve vázat kell adni, hogy a felhasználó könnyen, előképzettség nélkül tudjon önállóan kérdőívet létrehozni. Mindenképpen szükséges még egy bejelentkező felület is, amiben a be nem lépett felhaználók korlátozott jogokat kapnak (nem hozhatnak létre, vagy törölhetnek kérést/kérdőívet, csak kitölteni tudják ezeket. Az felület fontosságához hozzájáruk az is, hogy ezzel megszabadulhatnak a felesleges papír pazarlástól (papír alapú kérdőívek), senkinek sem kell egy fix helyen lenni a kitöltéshez és még a hatékonyság is nőni fog

## 2. Projektterv

### 2.1 Projektszerepkörök, felelőségek:
   * Scrum masters: Szabó Gergő
   * Product owner: Szabó Gergő
   * Üzleti szereplő: Tajti Tibor
     
### 2.2 Projektmunkások és felelőségek:
   * Frontend: Mihály Balázs, Kaponya Martin, Szabó Zsolt, Négyesi Imre
   * Backend: Mihály Balázs, Kaponya Martin, Szabó Zsolt, Négyesi Imre
   * Tesztelés: Mihály Balázs, Kaponya Martin, Szabó Zsolt, Négyesi Imre
     
### 2.3 Ütemterv:

|Funkció                  | Feladat                                | Prioritás | Becslés (nap) | Aktuális becslés (nap) | Eltelt idő (nap) | Becsült idő (nap) |
|-------------------------|----------------------------------------|-----------|---------------|------------------------|------------------|---------------------|
|Követelmény specifikáció |Megírás                                 |         1 |             2 |                      2 |                2 |                   2 |             
|Funkcionális specifikáció|Megírás                                 |         1 |             2 |                      2 |                2 |                   2 |
|Rendszerterv             |Megírás                                 |         1 |             2 |                      2 |                2 |                   2 |
|Program                  |Képernyőtervek elkészítése              |         2 |             2 |                      2 |                2 |                   2 |
|Program                  |Prototípus elkészítése                  |         3 |             17 |                      17 |                17 |                   17 |
|Program                  |Alapfunkciók elkészítése                |         3 |             17 |                      17 |                17 |                   17 |
|Program                  |Tesztelés                               |         4 |             5 |                      5 |                5 |                   5 |

### 2.4 Mérföldkövek:

 - 09.26 Rendszerterv
 - 09.29 Funkcionális specifikáció
 - 09.29 Követelmény specifikáció           ******* ezt még átírni aktuálisra ******
 - 10.03 Adatbázis kialakítása
 - 10.09 Frontend design megtervezése
 - 10.09 Backend funkciók elkészítése

## 3. Üzleti folyamatok modellje



## 4. Követelmények

### funkcionális követelmények

| Id | Modul | Név | Leírás |
| :---: | --- | --- | --- |
| K1 | Felület | Remember me | Tick-box a belépési adatok tárolásának eldöntésére |
| K2 | Felület | Login | A megadott felhasunálónév és jelszó kombináció beléptetése a felületre |
| K3 | Felület | Add new question | Új kérdés hozzáadása a kérdőívhez  |
| K4 | Felület | Register | Új felhasználó hozzáadása a felület adatbázisához |
| K5 | Felület | Create Questionnaire | Új kérdőív hozzáadása a felület adatbázisához |
| K6 | Felület | Add question | Új kérdés hozzáadása a kérdőívhez |
| K7 | Felület | Add new question | Elnavigál a K6 funkció felületéhez |
| K8 | Felület | Delete question | Törli a kiválasztott/akkor szerkesztett kérdést |
| K9 | Felület | Megoszthatóság | Link, amellyel bárki a kérdőívhez navigálhatx  |
| K10 | Felület | Complete Survey | A kérdőív kitöltésének véglegesítése, válaszok leadása |

### Támogatott eszközök

Mivel egy webes felületet készítünk, ezért elegendő egy számítógép vagy bármilyen okos eszköz amin van internetkapcsolat.

## 5. Funkcionális terv

### 5.1 Rendszerszereplők

- belépett felhasználó (aki készíti a kérdőívet)
- felhasználó (aki közvetve, a linken keresztül, belépés nélkül éri el a kérdőívet)

### 5.2 Menühierarchiák

  - Belépett felhasználó
    - Kérdőívet hozhat létre
    - Kérdőívet tölthet ki
    - Kérdéseket adhat a kérdőívéhez
    - Kérdéseket törölhet a kérdőívéből
    - Láthatja a kérdőív statisztikáit
    - Ki- és bejelentkezhet a felületre
    - Megoszthat kérdőíveket
  - Felhasználó
    - Kérdőívet tölthet ki
    - Továbbadhatja a már megkapott linket a kérdőívhez


## 6. Fizikai környezet

- **Az alkalmazás csak web platformra készül, MySQL adatbázissal lesz futtatva.**
  - **Nincsenek megvásárolt komponensek.**
  - **Fejlesztői eszközök:**
    - **Visual Studio Code**
    - **XAMPP**
    - **Laravel**


## 7. Architekturális terv

A rendszer tökéletes működéséhez szükség van egy adatbázis szerverre, ebben az esetben MySql-t használunk. A bootstrap felel a reszponzív webdesign-ért. A backend php alapon nyugszik, laravel keretrendszerrel.

## 8. Adatbázis terv

### *Tábla*
- *students:* Az adatbázisba felvitt tanulók
  - *id:* Azonosító szám, a tanuló egyedi azonosítója
  - *name:* A tanuló neve
  - *email:* A tanuló email címe
  - *phone:* A tanuló telefonszáma
  - *course:* Szak megnevezése


*Szerkezet*
![Képernyőterv](../Project/Pictures/adatbazis_szerkezet.png)

*DSL*


CREATE TABLE `students` (
  `id` int(11) NOT NULL,
  `name` varchar(191) NOT NULL,
  `email` varchar(191) NOT NULL,
  `phone` varchar(191) NOT NULL,
  `course` varchar(191) NOT NULL
)

INSERT INTO `students` (`id`, `name`, `email`, `phone`, `course`) VALUES
(1, 'Balazs Mihaly', 'm.bazsi@gmail.com', '+36302561440', 'PTI bsc.');

ALTER TABLE `students`
  ADD PRIMARY KEY (`id`);

ALTER TABLE `students`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=2;
COMMIT;

## 9. Implementációs terv

A webes felület HTML, CSS és PHP nyelven fog elkészülni, Laravel keretrendszerrel. A nem egymáshoz kapcsolódó funkciókat amennyire csak lehet, elkülönítjük, úgy csatoljuk egymáshoz ezzel is egy átláthatóbb, könnyebben változtatható lesz a source code-unk. Az adatokat MYSQL adatbázisban fogjuk tárolni.

## 10. Tesztterv

A tesztelések célja, hogy meggyőződjünk a felület gombjainak, beviteli mezőinek, illetve minden komponensének működéséről. A teszteléseket minden tag megadott számban elvégzi, különfile-ba dokumentálni fogja.


## 11. Telepítési terv

Mivel egy webes felületről van szó, ezért nem szükséges semmit a számítógépre telepíteni, elegendő egy tetszőleges böngésző és internetkapcsolat.
Az URL-t ismerve bárki begépelheti a böngésző keresőjébe és elérheti az oldalt.

## 12. Karbantartási terv

Figyelembe kell venni a felhasználó által jött visszajelzést is a programmal kapcsolatban.
Ha hibát talált, mielőbb orvosolni kell, lehet az:
*	Működéssel kapcsolatos
*	Kinézet, dizájnnal kapcsolatos
