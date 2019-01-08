# Python bevezetés #

Ennek a feladatnak során a Python alapok átismétlésére lesz lehetőség. A feladat alap felállása: egy kocsma pénztárgép rendszerének megírására kértek fel titeket. A feladat részekre van bontva, minden rész tartalmazza az aktuális részfeladat előírásait, egy példa működést, segítséget (ha elakadtok), illetve a megoldást is. Ha sikerül megoldanotok akkor is érdemes lehet megnézni a megoldást, mert valószínűleg én máshogy oldottam meg és sokszor abból is lehet tanulni. Ettől természetesen minden megoldás, ami az elvárt működéshez vezet, jó megoldás.

A program amit írnotok kell fog futni a kocsmában a pénztárgépen. A program fogja bekérni, hogy a vendégek miből mennyit rendelnek, majd a végén kinyomtatni a blokkot. Kezdetben egyszerűbb lesz a program, majd fokozatosan kerül be több ital, a borravaló lehetősége, törzsvásárlói akciók, asztalok kezelése stb.

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
   
   ```python
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
   
   ```python
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
   
   ```python
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
   
   ```python
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

Nagyon jól megy a kocsmának, és ezért úgy döntenek, hogy a sima (világos) sör mellé elkezdenek barna sört is kínálni 600 Ft-os áron. Bővítsd ki az előző kódot, hogy bekérje, hogy hány világos sört kérnek, majd hogy hány barna sört kérnek és végül kiírja a blokkot.

Példa kimenet:

```
Hány világos sört kérnek? 3
Hány barna sört kérnek? 4
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 3 db 1500.-
Barna   4 db 2400.-

Végösszeg:  3900.-
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Először is kérj be még egy információt a csapostól, hogy hány darab barna sört kérnek. Ehhez használd ugyanazt a parancsot mint korábban (a `raw_input()`-osat), csak figyelj, hogy jót kérdezzen a program és hogy új változóba tárold le (ha ugyanabba tárolod le, akkor felülírod az első kérdés válaszát).
   Utána adj hozzá egy új sort a blokkhoz, ahol ezt a változót használva kiírod a barna sörök számát és kiírod a végösszeget. (Figyelj, hogy a barna sör korsója 600 Ft!)
   Ezután frissítsd a végösszeget is, hogy figyelembe vegye a barna sört is.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = int(raw_input("Hány világos sört kérnek? "))

barna_sorok_szama = int(raw_input("Hány barna sört kérnek? "))

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
print ""
print "Végösszeg:  " + str(500*vilagos_sorok_szama + 600*barna_sorok_szama) + ".-"
   ```
</details>

## 6 Egyoldalú rendelések

Igenám, de mi van ha egy társaság csak egyféle sört kér? Jelenleg olyankor is ráírjuk a másik sört a blokkra 0 Ft-tal. Írd át a programot, hogy ha 0 sört kérnek valamelyik fajtából, akkor ne írjuk ki azt a fajtát a blokkra.

Példa kimenet:

```
Hány világos sört kérnek? 0
Hány barna sört kérnek? 3
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Barna   3 db 1800.-

Végösszeg:  1800.-
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Ahhoz, hogy valamit csak bizonyos feltételek esetén csináljunk az `If` szerkezetet használhatjuk, például:
   ```python
eletkor = 15
if eletkor < 18:
   print "Kiskorúakat nem szolgálunk ki"
   ```
   Vagyis az `if` utasítás után jön egy igaz vagy hamis feltétel, például, hogy egy változó kisebb-e egy számnál. Ezt követi egy `:`, majd a következő sor(ok)-at beljebb kezdjük valamennyi szóközzel (általában 4-gyel). Amíg a sorok beljebb kezdődnek, addig tart az `if` hatásköre: ezeket az utasításokat fogja csak akkor végrehajtani, ha a feltétel teljesül.
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = int(raw_input("Hány világos sört kérnek? "))

barna_sorok_szama = int(raw_input("Hány barna sört kérnek? "))

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
print ""
print "Végösszeg:  " + str(500*vilagos_sorok_szama + 600*barna_sorok_szama) + ".-"
   ```
</details>

## 7. Összevissza sorrend

Mostmár nagyon jól megy a kocsma, viszont a csapos elégedetlen, mert össze-vissza rendelnek a vendégek: 1 világost, 2 barnát, még 1 világost, 1 barnát, 2 világost, és most neki kell fejben tartania ezeket. Egészítsd ki a programot, hogy lehetőséget adjon arra, hogy a csaposnak csak azt kelljen beírnia, amit éppen kérnek: `v`-t ha világost, `b`-t ha barnát. Ha úgy nyom entert, hogy nem írt be semmit, akkor nyomtassuk ki a blokkot.

Példa kimenet:

```
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 3 db 1500.-
Barna   2 db 1200.-

Végösszeg:  2700.-
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Ez most jelentősen más, mint eddig. Van egy feladat (a `Mit kérnek` kiírása és a válasz feldolgozása), amit addig kell csinálni, amíg el nem fogynak a rendelések. Az ilyen "addig kell csinálni amíg egy feltétel teljesül" feladatokra használható a `while` ciklus. A `while` ciklusnak egy speciális formája a `while True:`, amikor a feltétel helyére azt írjuk, hogy `True`, ami mindig igaz. Ez sima esetben azt eredményezné, hogy a program örökké fut, próbáljuk csak ki:
```python
while True:
    print "Futok"
```
   (A piros négyzet - stop gombbal tudjuk megállítani a programot ilyenkor.) Ez nem túl hasznos, ezért általában a `while True:` cikluson belül írunk egy feltétel, és ha az teljesül, akkor kilépünk a `break` használatával, például:
```python
while True:
    print "Futok"
    valasz = raw_input("Menjunk meg? ")
    if valasz == "nem":
        break
```
   Itt is ugyanezt kell használni. Minden körben feltesszük a kérdést a csaposnak: `Mit kérnek? (v - világos, b - barna): `, majd ha `v`-t válaszolnak, akkor a világos sörök számát növeljük eggyel (`vilagos_sorok_szama = vilagos_sorok_szama + 1`), ha `b`-t, akkor a barna sörökét. Hogyha a válasz üres, vagyis `valasz == ""`, akkor kilépünk (`break`).
   
   Várjunk csak! Ha így futtatjuk, akkor első alkalommal, amikor próbálja megnövelni a világos sörök számát (`vilagos_sorok_szama = vilagos_sorok_szama + 1`) ezt a hibát fogjuk kapni: `NameError: name 'vilagos_sorok_szama' is not defined`, mivel még nincs értéke a változónak, ezért nem is tudja megnövelni. Ennek kijavítására a `while True:` ciklus előtt adjunk értéket a változónak: `vilagos_sorok_szama = 0`. Ugyanezt tegyük meg a barna sörök számát tartalmazó változóval is.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = 0
barna_sorok_szama = 0

while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    if kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    if kovetkezo_sor == "":
        break

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
print ""
print "Végösszeg:  " + str(500*vilagos_sorok_szama + 600*barna_sorok_szama) + ".-"
   ```
   
   Ezt a feladatot meg lehet oldani `if-elif-else` használatával is, ekkor a `while True:` ciklus a következőre módosul:
   ```python
while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    elif kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    else:
        break   
   ```
   Ebben az esetben ha bármi mást, mint `b`-t vagy `v`-t ír be a csapos, akkor nyomtatjuk is a számlát. Ez is teljesíti az eredeti feltételt, mert az csak a `v`, `b` és üres enter esetére definiálta a viselkedést.
</details>

## 8. Borravaló egyösszegben

A vendégek szeretnek borravalót adni, és mivel igyekszünk mindent szépen vezetni (és adózni utána), ezért szeretnénk, ha ez a blokkon is megjelenne. Miután a vendégek befejezték a rendelést, kérdezzük meg a csapost, hogy mennyi borravalót adtak (írjon 0-t, ha nem adtak), és adjuk hozzá azt is a számlához.

Példa kimenet:

```
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
Mennyi borravalót adtak? (írj 0-t, ha nem adtak): 400
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 2 db 1000.-
Barna   1 db 600.-
Borravaló    400.-

Végösszeg:  2000.-
```

Figyelj arra, hogy ha nem adtak borravalót, akkor ne jelenjen meg az a sor a számlán!

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Mikor akarjuk bekérni a borravaló összegét? A `while` vége után és a `print ========` előtt. Figyelj arra, hogy számmá konvertálva (`int()`) tudod hozzáadni a végösszeghez, viszont csak szövegként (`str()`) tudod kiírni.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = 0
barna_sorok_szama = 0

while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    elif kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    else:
        break

borravalo = int(raw_input("Mennyi borravalót adtak? (írj 0-t, ha nem adtak): "))

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
if borravalo > 0:
    print "Borravaló    " + str(borravalo) + ".-"
print ""
print "Végösszeg:  " + str(500*vilagos_sorok_szama + 600*barna_sorok_szama + borravalo) + ".-"
   ```
</details>

## 9. Borravaló alapján köszönés

Vannak vendégek, akik adnak borravalót és vannak, akik nem. A csapos szeretné, ha a borravalót adó vendégeknek a blokkjára ráírnánk, hogy visszavárjuk őket. Egészítsd ki a blokkot a végösszeg után még egy sorral: `Visszavárunk!` amennyiben adott borravalót a vendég.

Példa kimenet:

```
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): 
Mennyi borravalót adtak? (írj 0-t, ha nem adtak): 100
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 1 db 500.-
Borravaló    100.-

Végösszeg:  600.-
Visszavárunk!
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Hasonlóan az előző feladathoz, ahol a `Borravaló ` sor kiírása csak akkor történt, ha volt borravaló.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = 0
barna_sorok_szama = 0

while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    elif kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    else:
        break

borravalo = int(raw_input("Mennyi borravalót adtak? (írj 0-t, ha nem adtak): "))

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
if borravalo > 0:
    print "Borravaló    " + str(borravalo) + ".-"
print ""
print "Végösszeg:  " + str(500*vilagos_sorok_szama + 600*barna_sorok_szama + borravalo) + ".-"
if borravalo > 0:
    print "Visszavárunk!"
   ```
</details>

## 10. Borravaló felkerekítve

A vendégek általában úgy adnak borravalót, hogy felkerekítik az összeget: `2000-ből kérek vissza`. Módosítsuk a programunkat ehhez a körülményhez: ahelyett, hogy a borravaló összegét kérnénk be, írjuk ki a végösszeget, és kérjük be, hogy mennyiből kérnek vissza. Ha a csapos nem ír be semmit, akkor vegyük úgy, hogy nem adtak borravalót.

Példa kimenet:

```
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
A végösszeg: 600.-
Mennyiből kérnek vissza? 750
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Barna   1 db 600.-
Borravaló    150.-

Végösszeg:  750.-
Visszavárunk!
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Figyelj a konvertálásra (`str()` és `int()`).
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = 0
barna_sorok_szama = 0

while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    elif kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    else:
        break

vegosszeg = 500*vilagos_sorok_szama + 600*barna_sorok_szama

print "A végösszeg: " + str(vegosszeg) + ".-"
teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
if teljes_osszeg == "":
    teljes_osszeg = vegosszeg

borravalo = int(teljes_osszeg) - vegosszeg

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
if borravalo > 0:
    print "Borravaló    " + str(borravalo) + ".-"
print ""
print "Végösszeg:  " + str(teljes_osszeg) + ".-"
if borravalo > 0:
    print "Visszavárunk!"
   ```
</details>

## 11. Csalók kiszűrése

Igenám, de az eddigi programunk lehetőséget adott arra, hogy kevesebből kérjünk vissza, mint amennyi a végösszeg volt, például ha 1700 volt a vége, és mi 1500-ból kértünk vissza, akkor csak annyit kellett fizetnünk. Javítsuk ki ezt, és ha valaki kevesebből kér vissza, akkor is a helyes végösszeget kérjük el tőle.

Példa kimenet:

```
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
A végösszeg: 600.-
Mennyiből kérnek vissza? 500
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Barna   1 db 600.-

Végösszeg:  600.-
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Ellenőrizd, hogy a teljes összeg (amiből visszakérnek) kisebb-e, mint a végösszeg (az italok ára), és ha igen, akkor legyen a teljes összeg egyenlő a végösszeggel. Figyelj a konvertálásra (`int()` és `str()`)! 
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = 0
barna_sorok_szama = 0

while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    elif kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    else:
        break

vegosszeg = 500*vilagos_sorok_szama + 600*barna_sorok_szama

print "A végösszeg: " + str(vegosszeg) + ".-"
teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
if teljes_osszeg == "" or int(teljes_osszeg) < vegosszeg:
    teljes_osszeg = vegosszeg

borravalo = int(teljes_osszeg) - vegosszeg

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
if borravalo > 0:
    print "Borravaló    " + str(borravalo) + ".-"
print ""
print "Végösszeg:  " + str(teljes_osszeg) + ".-"
if borravalo > 0:
    print "Visszavárunk!"
   ```
</details>

## 12. Minden 5. sör ingyen akció

Nagyon jól megy a kocsmának, ezért akciót hirdetnek: minden 5. sör az azonos fajtából ingyen van. Ezt a blokkon külön szeretnék feltűntetni, mint pl. `Akció   -600.-`. Módosítsd a programot, hogy amennyiben valamelyik sörből több, mint 5-öt isznak, akkor az 5. ára levonásra kerüljön az akció részeként. Ha világos és barna sörből is több, mint 5-öt isznak, akkor vonja le mindkettőt a program. (Egyelőre elég csak az 5. sört kezelni, ha valaki pl. 12 sört kér, akkor is elég, ha egyet kapnak ingyen.)

Példa kimenet:

```
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): 
A végösszeg: 3100.-
Mennyiből kérnek vissza? 3300
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 6 db 3000.-
Barna   1 db 600.-
Akció       -500.-
Borravaló    200.-

Végösszeg:  3300.-
Visszavárunk!
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   A `Mit kérnek` után és a `A végösszeg` előtt kell kiszámolni az akciót és levonni a végösszegből.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

vilagos_sorok_szama = 0
barna_sorok_szama = 0

while True:
    kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
    if kovetkezo_sor == "v":
        vilagos_sorok_szama = vilagos_sorok_szama + 1
    elif kovetkezo_sor == "b":
        barna_sorok_szama = barna_sorok_szama + 1
    else:
        break

akcio = 0
if vilagos_sorok_szama >= 5:
    akcio = akcio + 500
if barna_sorok_szama >= 5:
    akcio = akcio + 600

vegosszeg = 500*vilagos_sorok_szama + 600*barna_sorok_szama - akcio

print "A végösszeg: " + str(vegosszeg) + ".-"
teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
if teljes_osszeg == "" or int(teljes_osszeg) < vegosszeg:
    teljes_osszeg = vegosszeg

borravalo = int(teljes_osszeg) - vegosszeg

print "================"
print "Kincstár Kocsma"
print "Budapest, Váci u. 47."
print "V-Cs: 16:00-22:00"
print "P-Sz: 16:00-24:00"
print ""
if vilagos_sorok_szama > 0:
    print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
if barna_sorok_szama > 0:
    print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
if akcio > 0:
    print "Akció       " + str(-akcio) + ".-"
if borravalo > 0:
    print "Borravaló    " + str(borravalo) + ".-"
print ""
print "Végösszeg:  " + str(teljes_osszeg) + ".-"
if borravalo > 0:
    print "Visszavárunk!"
   ```
</details>

Módosítsd a kódot, hogy ne csak az 5. sör legyen ingyen, hanem minden 5. (vagyis ha valaki 12-t vesz, akkor kapjon kettőt ingyen, ha 28-at, akkor 5-öt stb.).

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   A kérdés voltaképp az, hogy a sörök számában hányszor van meg az 5, vagyis `sorok_szama / 5`. Viszont ez lehet tört szám lesz (pl 7 esetén 1.4), úgyhogy kerekítsük le. Ehhez használhatjuk az `int()` függvényt, ami egyszerűen levágja a tizedes pont utáni részt, vagy a `floor()` függvényt a `math` könyvtárból így:
   ```python
from math import floor

print floor(7/5)
   ```
   
</details>

## 13. Kód darabolása

Egyre hosszabb a kód, ideje kicsit rendbe szedni. Szervezd ki a különböző funkcionalitás a következő függvényekbe:

```
def rendeles_felvetel():
   # visszatér a rendelt világos és barna sörök számával egy listában
   return [vilagos_sorok_szama, barna_sorok_szama]
   
def vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, van_akcio):
   # a van_akcio változó True vagy False és ettől függ, hogy van-e épp a minden 5. ingyenes akció
   # visszatér a végösszeggel borravaló nélkül
   return vegosszeg

def borravalo_kerese(vegosszeg):
   # megkérdezi, hogy mennyiből kértek vissza és visszatér a borravaló összegével
   return borravalo

def blokk_nyomtatasa(vilagos_sorok_szama, barna_sorok_szama, vegosszeg, borravalo):
   # kinyomtatja a blokkot és nem tér vissza semmivel
```
Utána a program maga már csak ezeknek a függvényeknek az egymás utáni meghívása lesz:
```
[vilagos_sorok_szama, barna_sorok_szama] = rendeles_felvetel()

vegosszeg = vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, True)

borravalo = borravalo_kerese(vegosszeg)

blokk_nyomtatasa(vilagos_sorok_szama, barna_sorok_szama, vegosszeg, borravalo)
```

<details> 
  <summary>Segítség (kattints ide) </summary>
   
   Ez egy bonyolultabb feladat, elég, ha elakadtál, nézd meg nyugodtan az én megoldásom és próbáld meg megérteni.
   
</details>

<details> 
  <summary>Az én megoldásom (kattints ide) </summary>
   
   ```python
# -*- coding: utf-8 -*-

def rendeles_felvetel():
    vilagos_sorok_szama = 0
    barna_sorok_szama = 0

    while True:
        kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
        if kovetkezo_sor == "v":
            vilagos_sorok_szama = vilagos_sorok_szama + 1
        elif kovetkezo_sor == "b":
            barna_sorok_szama = barna_sorok_szama + 1
        else:
            break
    return [vilagos_sorok_szama, barna_sorok_szama]

def vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, van_akcio):
    akcio = 0
    if van_akcio:
        if vilagos_sorok_szama >= 5:
            akcio = akcio + 500
        if barna_sorok_szama >= 5:
            akcio = akcio + 600

    return 500*vilagos_sorok_szama + 600*barna_sorok_szama - akcio

def borravalo_kerese(vegosszeg):
    print "A végösszeg: " + str(vegosszeg) + ".-"
    teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
    if teljes_osszeg == "" or int(teljes_osszeg) < vegosszeg:
        teljes_osszeg = vegosszeg

    borravalo = int(teljes_osszeg) - vegosszeg
    return borravalo

def blokk_nyomtatasa(vilagos_sorok_szama, barna_sorok_szama, vegosszeg, borravalo):
    akcio = vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, False) - vegosszeg
    print "================"
    print "Kincstár Kocsma"
    print "Budapest, Váci u. 47."
    print "V-Cs: 16:00-22:00"
    print "P-Sz: 16:00-24:00"
    print ""
    if vilagos_sorok_szama > 0:
        print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
    if barna_sorok_szama > 0:
        print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
    if akcio > 0:
        print "Akció       " + str(-akcio) + ".-"
    if borravalo > 0:
        print "Borravaló    " + str(borravalo) + ".-"
    print ""
    print "Végösszeg:  " + str(vegosszeg) + ".-"
    if borravalo > 0:
        print "Visszavárunk!"


[vilagos_sorok_szama, barna_sorok_szama] = rendeles_felvetel()

vegosszeg = vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, True)

borravalo = borravalo_kerese(vegosszeg)

blokk_nyomtatasa(vilagos_sorok_szama, barna_sorok_szama, vegosszeg, borravalo)

   ```
</details>

## 14. Asztalok kezelése

Bővült a kocsma, és most már nem a pultnál kérnek és fizetnek a vendégek, hanem felszolgáló megy ki a 4 asztalhoz és csak távozáskor fizetnek. Ennek alapján bővítsd ki a programot arra, hogy kezelje a 4 asztalhoz a fogyasztást, valamint kérésre tudjon blokkot nyomtatni nekik (és ekkor törölje az ahhoz az asztalhoz tárolt fogyasztást).

A megoldáshoz használhatsz osztályokat, vagy simán asztalonként 2 változót a barna és világos sörökre.

Példa kimenet, de lehet más is a logika:
```
Hanyas asztalt szeretnéd kezelni? 1
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
Fizetnének? nem
Hanyas asztalt szeretnéd kezelni? 2
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): 
Fizetnének? nem
Hanyas asztalt szeretnéd kezelni? 3
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
Fizetnének? nem
Hanyas asztalt szeretnéd kezelni? 1
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): 
Fizetnének? igen
A végösszeg: 2900.-
Mennyiből kérnek vissza? 3000
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 1 db 500.-
Barna   5 db 3000.-
Akció       -600.-
Borravaló    100.-

Végösszeg:  2900.-
Visszavárunk!
================
Hanyas asztalt szeretnéd kezelni? 2
Mit kérnek? (v - világos, b - barna): v
Mit kérnek? (v - világos, b - barna): 
Fizetnének? igen
A végösszeg: 1000.-
Mennyiből kérnek vissza? 1000
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Világos 2 db 1000.-

Végösszeg:  1000.-
================
Hanyas asztalt szeretnéd kezelni? 1
Mit kérnek? (v - világos, b - barna): b
Mit kérnek? (v - világos, b - barna): 
Fizetnének? igen
A végösszeg: 600.-
Mennyiből kérnek vissza? 700
================
Kincstár Kocsma
Budapest, Váci u. 47.
V-Cs: 16:00-22:00
P-Sz: 16:00-24:00

Barna   1 db 600.-
Borravaló    100.-

Végösszeg:  600.-
Visszavárunk!
================
Hanyas asztalt szeretnéd kezelni? 
```
<details> 
  <summary>Az én megoldásom 1 (kattints ide) - osztályok nélkül </summary>
   
   ```python
   # -*- coding: utf-8 -*-

def rendeles_felvetel():
    vilagos_sorok_szama = 0
    barna_sorok_szama = 0

    while True:
        kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
        if kovetkezo_sor == "v":
            vilagos_sorok_szama = vilagos_sorok_szama + 1
        elif kovetkezo_sor == "b":
            barna_sorok_szama = barna_sorok_szama + 1
        else:
            break
    return [vilagos_sorok_szama, barna_sorok_szama]

def vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, van_akcio):
    akcio = 0
    if van_akcio:
        if vilagos_sorok_szama >= 5:
            akcio = akcio + 500
        if barna_sorok_szama >= 5:
            akcio = akcio + 600

    return 500*vilagos_sorok_szama + 600*barna_sorok_szama - akcio

def borravalo_kerese(vegosszeg):
    print "A végösszeg: " + str(vegosszeg) + ".-"
    teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
    if teljes_osszeg == "" or int(teljes_osszeg) < vegosszeg:
        teljes_osszeg = vegosszeg

    borravalo = int(teljes_osszeg) - vegosszeg
    return borravalo

def blokk_nyomtatasa(vilagos_sorok_szama, barna_sorok_szama, vegosszeg, borravalo):
    akcio = vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, False) - vegosszeg
    print "================"
    print "Kincstár Kocsma"
    print "Budapest, Váci u. 47."
    print "V-Cs: 16:00-22:00"
    print "P-Sz: 16:00-24:00"
    print ""
    if vilagos_sorok_szama > 0:
        print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
    if barna_sorok_szama > 0:
        print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
    if akcio > 0:
        print "Akció       " + str(-akcio) + ".-"
    if borravalo > 0:
        print "Borravaló    " + str(borravalo) + ".-"
    print ""
    print "Végösszeg:  " + str(vegosszeg) + ".-"
    if borravalo > 0:
        print "Visszavárunk!"
    print "================"


class Asztal(object):
    def __init__(self, asztal_szama):
        self.asztal_szama = asztal_szama
        self.vilagos_sorok_szama = 0
        self.barna_sorok_szama = 0

asztal1_vilagos = 0
asztal1_barna = 0
asztal2_vilagos = 0
asztal2_barna = 0
asztal3_vilagos = 0
asztal3_barna = 0
asztal4_vilagos = 0
asztal4_barna = 0

while True:
    asztal_szama = int(raw_input("Hanyas asztalt szeretnéd kezelni? "))
    if asztal_szama == 1:
        valasztott_asztal_vilagos = asztal1_vilagos
        valasztott_asztal_barna = asztal1_barna
    elif asztal_szama == 2:
        valasztott_asztal_vilagos = asztal2_vilagos
        valasztott_asztal_barna = asztal2_barna
    elif asztal_szama == 3:
        valasztott_asztal_vilagos = asztal3_vilagos
        valasztott_asztal_barna = asztal3_barna
    elif asztal_szama == 4:
        valasztott_asztal_vilagos = asztal4_vilagos
        valasztott_asztal_barna = asztal4_barna
    [vilagos_sorok_szama, barna_sorok_szama] = rendeles_felvetel()
    valasztott_asztal_vilagos += vilagos_sorok_szama
    valasztott_asztal_barna += barna_sorok_szama
    fizetnenek = raw_input("Fizetnének? ")
    if fizetnenek == "igen":
        vegosszeg = vegosszeg_kiszamitasa(valasztott_asztal_vilagos, valasztott_asztal_barna, True)
        borravalo = borravalo_kerese(vegosszeg)
        blokk_nyomtatasa(valasztott_asztal_vilagos, valasztott_asztal_barna, vegosszeg, borravalo)
        valasztott_asztal_vilagos = 0
        valasztott_asztal_barna = 0
    if asztal_szama == 1:
         asztal1_vilagos = valasztott_asztal_vilagos
         asztal1_barna = valasztott_asztal_barna
    elif asztal_szama == 2:
         asztal2_vilagos = valasztott_asztal_vilagos
         asztal2_barna = valasztott_asztal_barna
    elif asztal_szama == 3:
         asztal3_vilagos = valasztott_asztal_vilagos
         asztal3_barna = valasztott_asztal_barna
    elif asztal_szama == 4:
         asztal4_vilagos = valasztott_asztal_vilagos
         asztal4_barna = valasztott_asztal_barna
   ```
</details>

<details> 
  <summary>Az én megoldásom 2 (kattints ide) - minimális osztály használattal </summary>
   
   ```python
   # -*- coding: utf-8 -*-

def rendeles_felvetel():
    vilagos_sorok_szama = 0
    barna_sorok_szama = 0

    while True:
        kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
        if kovetkezo_sor == "v":
            vilagos_sorok_szama = vilagos_sorok_szama + 1
        elif kovetkezo_sor == "b":
            barna_sorok_szama = barna_sorok_szama + 1
        else:
            break
    return [vilagos_sorok_szama, barna_sorok_szama]

def vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, van_akcio):
    akcio = 0
    if van_akcio:
        if vilagos_sorok_szama >= 5:
            akcio = akcio + 500
        if barna_sorok_szama >= 5:
            akcio = akcio + 600

    return 500*vilagos_sorok_szama + 600*barna_sorok_szama - akcio

def borravalo_kerese(vegosszeg):
    print "A végösszeg: " + str(vegosszeg) + ".-"
    teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
    if teljes_osszeg == "" or int(teljes_osszeg) < vegosszeg:
        teljes_osszeg = vegosszeg

    borravalo = int(teljes_osszeg) - vegosszeg
    return borravalo

def blokk_nyomtatasa(vilagos_sorok_szama, barna_sorok_szama, vegosszeg, borravalo):
    akcio = vegosszeg_kiszamitasa(vilagos_sorok_szama, barna_sorok_szama, False) - vegosszeg
    print "================"
    print "Kincstár Kocsma"
    print "Budapest, Váci u. 47."
    print "V-Cs: 16:00-22:00"
    print "P-Sz: 16:00-24:00"
    print ""
    if vilagos_sorok_szama > 0:
        print "Világos " + str(vilagos_sorok_szama) + " db " + str(500*vilagos_sorok_szama) + ".-"
    if barna_sorok_szama > 0:
        print "Barna   " + str(barna_sorok_szama) + " db " + str(600*barna_sorok_szama) + ".-"
    if akcio > 0:
        print "Akció       " + str(-akcio) + ".-"
    if borravalo > 0:
        print "Borravaló    " + str(borravalo) + ".-"
    print ""
    print "Végösszeg:  " + str(vegosszeg) + ".-"
    if borravalo > 0:
        print "Visszavárunk!"
    print "================"


class Asztal(object):
    def __init__(self, asztal_szama):
        self.asztal_szama = asztal_szama
        self.vilagos_sorok_szama = 0
        self.barna_sorok_szama = 0

asztalok = [Asztal(1), Asztal(2), Asztal(3), Asztal(4)]

while True:
    asztal_szama = int(raw_input("Hanyas asztalt szeretnéd kezelni? "))
    valasztott_asztal = asztalok[asztal_szama-1]
    [vilagos_sorok_szama, barna_sorok_szama] = rendeles_felvetel()
    valasztott_asztal.vilagos_sorok_szama += vilagos_sorok_szama
    valasztott_asztal.barna_sorok_szama += barna_sorok_szama
    fizetnenek = raw_input("Fizetnének? ")
    if fizetnenek == "igen":
        vegosszeg = vegosszeg_kiszamitasa(valasztott_asztal.vilagos_sorok_szama, valasztott_asztal.barna_sorok_szama, True)
        borravalo = borravalo_kerese(vegosszeg)
        blokk_nyomtatasa(valasztott_asztal.vilagos_sorok_szama, valasztott_asztal.barna_sorok_szama, vegosszeg, borravalo)
        asztalok[asztal_szama - 1].vilagos_sorok_szama = 0
        asztalok[asztal_szama - 1].barna_sorok_szama = 0
   ```
</details>

<details> 
  <summary>Az én megoldásom 3 (kattints ide) - nagy mennyiségű osztály használattal </summary>
  Figyeld, hogy mennyivel rövidebb lett a kód.
   
   ```python
   # -*- coding: utf-8 -*-


class Asztal(object):
    def __init__(self, asztal_szama):
        self.asztal_szama = asztal_szama
        self.vilagos_sorok_szama = 0
        self.barna_sorok_szama = 0

    def rendeles_felvetel(self):
        while True:
            kovetkezo_sor = raw_input("Mit kérnek? (v - világos, b - barna): ")
            if kovetkezo_sor == "v":
                self.vilagos_sorok_szama = self.vilagos_sorok_szama + 1
            elif kovetkezo_sor == "b":
                self.barna_sorok_szama = self.barna_sorok_szama + 1
            else:
                break
        return

    def vegosszeg_kiszamitasa(self, van_akcio):
        akcio = 0
        if van_akcio:
            if self.vilagos_sorok_szama >= 5:
                akcio = akcio + 500
            if self.barna_sorok_szama >= 5:
                akcio = akcio + 600

        return 500*self.vilagos_sorok_szama + 600*self.barna_sorok_szama - akcio

    def borravalo_kerese(this, vegosszeg):
        print "A végösszeg: " + str(vegosszeg) + ".-"
        teljes_osszeg = raw_input("Mennyiből kérnek vissza? ")
        if teljes_osszeg == "" or int(teljes_osszeg) < vegosszeg:
            teljes_osszeg = vegosszeg

        borravalo = int(teljes_osszeg) - vegosszeg
        return borravalo

    def blokk_nyomtatasa(self, vegosszeg, borravalo):
        akcio = self.vegosszeg_kiszamitasa(False) - vegosszeg
        print "================"
        print "Kincstár Kocsma"
        print "Budapest, Váci u. 47."
        print "V-Cs: 16:00-22:00"
        print "P-Sz: 16:00-24:00"
        print ""
        if self.vilagos_sorok_szama > 0:
            print "Világos " + str(self.vilagos_sorok_szama) + " db " + str(500*self.vilagos_sorok_szama) + ".-"
        if self.barna_sorok_szama > 0:
            print "Barna   " + str(self.barna_sorok_szama) + " db " + str(600*self.barna_sorok_szama) + ".-"
        if akcio > 0:
            print "Akció       " + str(-akcio) + ".-"
        if borravalo > 0:
            print "Borravaló    " + str(borravalo) + ".-"
        print ""
        print "Végösszeg:  " + str(vegosszeg) + ".-"
        if borravalo > 0:
            print "Visszavárunk!"
        print "================"
        self.barna_sorok_szama = 0
        self.vilagos_sorok_szama = 0


asztalok = [Asztal(1), Asztal(2), Asztal(3), Asztal(4)]

while True:
    asztal_szama = int(raw_input("Hanyas asztalt szeretnéd kezelni? "))
    valasztott_asztal = asztalok[asztal_szama-1]
    valasztott_asztal.rendeles_felvetel()
    fizetnenek = raw_input("Fizetnének? ")
    if fizetnenek == "igen":
        vegosszeg = valasztott_asztal.vegosszeg_kiszamitasa(True)
        borravalo = valasztott_asztal.borravalo_kerese(vegosszeg)
        valasztott_asztal.blokk_nyomtatasa(vegosszeg, borravalo)

   ```
</details>
