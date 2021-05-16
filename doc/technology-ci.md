# Build keretrendszer beüzemelése, ha még nincs + CI beüzemelése, ha még nincs

## Build keretrendszer

A projekten build keretrendszer már volt, mégpedig az Apache Ant.
Az _ant build dist_ parancs kiadásával történik meg a build, amihez szükség van az Ant telepítésére.

Ennek lépései egyszerűek, [le kell töltelni](https://ant.apache.org/bindownload.cgi) a megfelelő verizójú binary-kat, hozzáadni a rendszer PATH változójához, és használatra kész.

## Github Actions

A projekten korábban nem volt CI, így ennek beüzemelése következett.

Tesztek hiányában csak buildelni van lehetőség. Ehhez a Github által felajánlott Java With Maven-ből indultam ki, amelyben a

```
run: mvn -B package --file build.xml
```

sort kellett kicserélni a következőre:

```
run: ant -noinput -buildfile build.xml
```

Ezen kívül az Action és a step nevét változtattam meg, hogy egyezzen a használt build keretrendszerrel.

Pull request nyitása után az action lefutott, és a buildelés sikeres volt.

Így ezentúl nem lehetséges olyan kódot merge-lni, amelyik nem fordítható.
