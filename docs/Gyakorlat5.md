# Gyakorlat 5. - POD skálázás

## Tudnivalók
[Fontos információk](Tudnivalok.md)

**Fontos:**
- OpenShift konvenviók:
 - Felhasználónevetek legyen: studentxy - ahol x y a nevetek kezdőbetűi pl. studentnz (kisbetűk)
 - Projektek nevei: gyakorlatNxy - N a gyakorlat száma, x, y lsd. előbb, pl. gyakorlat2nz (kisbetűk)
- Mindenki a saját userét használja ezután, hogy izoláltan dolgozzatok!


## Feladat 1. - OpenShift skálázás, automatikus skálázás
**Időtartam: ~30 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy kipróbáljuk a POD-ok skálázását.

1. Telepíts egy tetszőleges olyan alkalmazást, amely HTTP forgalmat fogad, mindenképp legyen egy böngészőből megszólítható alkalmazásod a PaaS-ban. Lehet az előző feladatokból megmaradt alkalmazás!
2. Eddig 1 db POD-ot indított el a ReplicationController, próbáld ki, hogy manuálisan növelitek a POD számot (ReplicationController szinten).
- oc get rc, oc scale
3. Módosítsd a DeploymentConfig-ot, ahol megadod pl. a CPU request-et.
4. Állítsd be az autoscalinget (oc autoscale)
5. Generálj hálózati forgalmat:
```shell
ab -n 100000 -c 1 http://test-gyakorlat3xy.apps.openshift.local/
```
6. Figyeld mi történik
```shell
watch oc get pods
oc get hpa --watch
```

### Jegyzőkönyvhöz
Nincs feladat.
