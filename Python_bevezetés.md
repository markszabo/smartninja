# Python bevezetés #

Ennek a feladatnak során a Python alapok átismétlésére lesz lehetőség. A feladat alap felállása: egy kocsma pénztárgép rendszerének megírására kértek fel titeket. A feladat részekre van bontva, minden rész tartalmazza az aktuális részfeladat előírásait, egy példa működést, segítséget (ha elakadtok), illetve a megoldást is. Ha sikerül megoldanotok akkor is érdemes lehet megnézni a megoldást, mert valószínűleg én máshogy oldottam meg és sokszor abból is lehet tanulni. Ettől természetesen minden megoldás, ami az elvárt működéshez vezet jó megoldás.

A program amit írnotok kell fog futni a kocsmában a pénztárgépen. A program fogja bekérni, hogy a vendégek miből mennyit rendelnek, majd a végén kinyomtatni a blokkot. Kezdetben egyszerűbb lesz a program, majd fokozatosan kerül be több ital, a borravaló lehetősége, törzsvásárlói kedvezmény, asztalok kezelése stb.

A program működése két részre bontható: első részben a pincértől/csapostól kér információt a fogyasztásról, majd a második részben, amikor a vendég fizetni szeretne, akkor kiírja a blokkot. A két rész elválasztására egy `================` kiírását használjátok (lásd az adott részfeladatok példafutásánál is).

## 1. Fejléc 

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

## 2. Egy sör 

Kinyitott a kocsma! Itt az idő az első terméket hozzáadni: sör. Egyelőre nagyon egyszerű a program dolga: ha valaki kér egy sört, a csapos lefuttatja a programot, ami nyomtat egy blokkot az egy sörről. Figyelj az üres sorra a fejléc és a termékek, valamint a termékek és a végösszeg között!

Példa kimenet:
```
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00 
P-Sz: 16:00-24:00

Sör     1 db 500.-

Végösszeg:   500.-
```
<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Üres sor kiírásához használd a `print ""` parancsot.
   
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
print ""
print "Sör     1 db 500.-"
print ""
print "Végösszeg:   500.-"
   ```
</details>

## 3. Öt sör

Elterjed a kocsma híre és ötösével jönnek az emberek, mindig 5 sört kérve. Módosítsd a programot, hogy 5 sörről nyomtassa a blokkot. Az 5-öt tárold változóban.

Példa kimenet:
```
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Sör    5 db 2500.-

Végösszeg:  2500.-
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Folytasd az előző feladat során megkezdett programot. Először is a `print`-ek elé írj egy sort, amiben létrehozod a változót, ami a sörök számát tárolja, például: `sorok_szama = 5` (azért csak példa, mert lehet más is a változó neve).
   
   Utána a blokk `print`-elésekor tudod ezt a változót használni. Először módosítsd a `print "Sör     1 db 500.-"` sort a sör mennyiségével: `print "Sör     " + str(sorok_szama) + " db 500.-"`. Az `str()` függvényre azért van szükség, mert különben hibát dob: szöveget (string-et) és számot (int-et) nem tud összeadni.
   
   Ezután frissítsd az árakat is hasonlóan. Egy sör ára továbbra is `500.-`, úgyhogy az új árat úgy kapjuk, hogy `500*sorok_szama`. Ezt ismét szöveggé kell alakítani az `str()` függvénnyel, hogy ki tudjuk írni.
   
   Végül a végösszeg sort is frissítsük hasonlóan.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```
# -*- coding: utf-8 -*-

sorok_szama = 5

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
print "Sör    " + str(sorok_szama) + " db " + str(500*sorok_szama) + ".-"
print ""
print "Végösszeg:  " + str(500*sorok_szama) + ".-"
   ```
</details>

## 4. Akármennyi sör

Igenám, de vannak vendégek, akik nem 5 sört kérnek. Bővítsd a programot, hogy először megkérdezze a csapost, hogy hány sört kérnek, majd annak alapján készítse el a blokkot.

Példa kimenet:
```
Hány sört kérnek? 8
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Sör    8 db 4000.-

Végösszeg:  4000.-
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   A felhasználótól (csapostól) bemenetet kérni a `raw_input("Kérdés?")` függvénnyel lehet, ami visszaadja a beadott értéket. Ha ezt változóban akarjuk tárolni, azt így tehetjük meg: `valasz = raw_input("Kérdés?")`. Ugyanakkor a `raw_input()` szöveggel, string-gel tér vissza. Ahhoz, hogy ezt számként tudjuk használni az `int()` függvénnyel számmá kell konvertálni. Összerakva így fog kinézni a parancs: `valasz = int(raw_input("Kérdés?"))`
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```
# -*- coding: utf-8 -*-

sorok_szama = int(raw_input("Hány sört kérnek? "))

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
print "Sör    " + str(sorok_szama) + " db " + str(500*sorok_szama) + ".-"
print ""
print "Végösszeg:  " + str(500*sorok_szama) + ".-"
   ```
</details>

## 5. Barna sör


<details> 
  <summary>Segítség (kattints ide) </summary>
   
   
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```

   ```
</details>

## 6. Összevissza sorrend

## 7. Búzasör

## 8. Borravaló egyösszegben

## 9. Borravaló százalékosan

## 10. Borravaló kerekítve

## 11. Asztalok kezelése

## 12. Törzsvendég program

## 13. Törzsvendég program fájlba írással

## 14. Percenkénti akciók

