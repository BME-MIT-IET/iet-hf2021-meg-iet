# Sonarqube

## Telepítés

A sonarqubeot dockerrel telepítettem, így a következő parancs futtatása után már elérhetővé is vált a localhost:9000 címen:

```
docker run -d --name sonarqube -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true -p 9000:9000 sonarqube:latest
```

Az új projekt hozzáadása során ant-es opció nem volt, így a sonar-scanner segítségével tudtam az elemzést elvégezni, melynek eredménye a következő:

![](images/sonar-qube-results.PNG)

Ezután Jakabos Csengével felváltva kezdtük el értelmezni és javítani a fellelt hibákat.
