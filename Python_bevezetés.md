# Python bevezetés #

Ennek a feladatnak során a Python alapok átismétlésére lesz lehetőség. A feladat alap felállása: egy kocsma pénztárgép rendszerének megírására kértek fel titeket. A feladat részekre van bontva, minden rész tartalmazza az aktuális részfeladat előírásait, egy példa működést, segítséget (ha elakadtok), illetve a megoldást is. Ha sikerül megoldanotok akkor is érdemes lehet megnézni a megoldást, mert valószínűleg én máshogy oldottam meg és sokszor abból is lehet tanulni. Ettől természetesen minden megoldás, ami az elvárt működéshez vezet jó megoldás.

A program amit írnotok kell fog futni a kocsmában a pénztárgépen. A program fogja bekérni, hogy a vendégek miből mennyit rendelnek, majd a végén kinyomtatni a blokkot. Kezdetben egyszerűbb lesz a program, majd fokozatosan kerül be több ital, étel, a borravaló lehetősége, törzsvásárlói kedvezmény, asztalok kezelése stb.

A program működése két részre bontható: első részben a pincértől/csapostól kér információt a fogyasztásról, majd a második részben, amikor a vendég fizetni szeretne, akkor kiírja a blokkot. A két rész elválasztására egy `================` kiírását használjátok (lásd az adott részfeladatok példafutásánál is).

## 1. Fejléc ##

Első feladatként a blokk fejlécét kell kiírnotok, benne a kocsma nevével, címével és nyitvatartásával:
```
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00 
P-Sz: 16:00-24:00
```
Példa kimenet:
```
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00 
P-Sz: 16:00-24:00
```
<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Pythonban szöveg kiírására a `print "Valami"` parancsot használjuk
   
   Ékezetes betűk használatához aduk hozzá a következő sort a programunk legelejéhez: `# -*- coding: utf-8 -*-`
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```
# -*- coding: utf-8 -*-

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
   ```
</details>

2. Egy sör

3. Öt sör

4. Akármennyi sör

5. Barna sör

6. Összevissza sorrend

7. Búzasör

8. Borravaló egyösszegben

9. Borravaló százalékosan

10. Borravaló kerekítve

11. Asztalok kezelése

12. Törzsvendég program

13. Törzsvendég program fájlba írással

14. Percenkénti akciók

8. 
