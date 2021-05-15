# Teljesítmény tesztek

A program nem-funkcionális jellemzők közül az egyik legfontosabb a futási idő.
Ennek méréséhez a prgramot kiegészítettem egy az alábbi pár sorral, amely a futás elejétől a végéig eltelt időt méri ezredmásodpercben.

```
long start = System.currentTimeMillis();
Cli.<Runnable> builder("csv2rdf").withDescription("Converts a CSV file to RDF based on a given template")
.withDefaultCommand(CSV2RDF.class).withCommand(CSV2RDF.class).withCommand(Help.class)
.build().parse(args).run();
long finish = System.currentTimeMillis();
System.out.println("Elapsed time in milliseconds " + (finish - start));

```

Ezután változó méretű csv fájlok konvertállását futtattam, változó bonyolultságú template-ek mellett.
A teszteléshez használt csv fájlok, a használt template-ek és a generált output-ok a performance-tests mappában találhatóak.

## 1. teszt: Szélerőművek

### Input

A performance-tests/wind.csv fájl egy szélerőmű óránkénti termelését tartalmazza. Minden oszlop egy év adatait jelenti. A fájlban összesen 5 év adata van (2016-2020, 8,760 sor).

### A lefuttatott parancs

`java -jar dist/lib/csv2rdf.jar convert --no-header stress-test/wind-template.ttl stress-test/wind.csv stress-test/wind-output.ttl`

### Output a standard kimeneten

```
Template: stress-test\wind-template.ttl
Output  : stress-test\wind-output.ttl
Converted 8,760 rows to 131,400 triples
Elapsed time in milliseconds 517
```
