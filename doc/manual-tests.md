## Manuális tesztek

Első körben a program bemeneteit és kimeneteit vizsgáljuk.
A konverziókat a lefordított állomány futtatásával, CLI-on keresztül végezhetjük.
A lehetséges opciókat az alábbi paranccsal lehet kiistázni:

`java -jar dist/lib/csv2rdf.jar help convert`

A help kimenete:

![](help-output.PNG)

Ezeknek a funkciókank a működését teszteljük. A manuális teszthez szükségünk van több bemeneti csv-re és a belőlük generált elvárt rdf fájl template-jére.
A tesztekhez előállított csv file-ok és a nekik megfelelő template-ek a manual-tests mappában találhatóak.

Eltérő escape karakter használata:

Header nélküli csv konverziója

Eltérő quote karakter használata:

Eltérő elválasztó karakter használata:

Hibajelzés:
Nem megfelelő kiterjesztésű file-ok konverziója
Túl sok vagy túl kevés argumentum megadása
...
