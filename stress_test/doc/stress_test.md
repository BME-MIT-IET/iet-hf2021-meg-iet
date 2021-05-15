# Stresszteszt 

Az alkalmazás jellegéből adódóan nehezen találni szűk keresztmetszetet rajta, hiszen egyszálon futó, rövid életű programról beszélhetünk. Két input fájlt kell megnyitnia, egy konverziót végezni és az eredményt kiírni. 

## Program futásidejének mérése

Az egyedüli terhelési pontja a programnak az input fájl mérete, így az internetről letöltöttem egy példa .csv fájlt, mely kb. 100 000 sornyi adatot tartalmaz. 

### Mérés

A lefutás idejét Windows PowerShellben, a Measure-Command parancs segítségével mértem. Nyolcszor futtattam le egymás után a parancsot, íme az eredmény egy táblázatban. A lefutások átlagosan **1148 ms** hosszúak voltak. 

| Sorszám | Idő (ms) |
|---------|----------|
| 1       | 1187     |
| 2       | 1144     |
| 3       | 1052     |
| 4       | 1240     |
| 5       | 1124     |
| 6       | 1148     |
| 7       | 1133     |
| 8       | 1157     |

Összehasonlításként, egy `echo hi` parancs 5 ms alatt futott le. 
A projektben példaként megadott cars.csv fájlon (5 sort tartalmaz) szintén végrehajtottam 8 lefutást, ezek átlaga **540 ms** lett. 

### Kiértékelés

A futásidő a példa inputhoz képest durván megduplázódott a kb. 100 ezer extra sor hozzáadásával. Az eredmény átlagosnak mondható, nem száll el a lefutás ekkora inputtól, de kellően lassabbá válik ahhoz, hogy ne ezt a konvertert használjuk pármillió soros .csv fájlok esetén. 