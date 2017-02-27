# Alerant - BME PaaS labor
# OpenShift áttekintés
A Docker konténerek önmagukban még nem alkalmasak arra, hogy egy PaaS megoldást nyújtsanak.
Egy PaaS teljeskörű és transzparens platformon nyújtja az alkalmazásszerver platformot.

Ehhez a következő problémákra kell még megoldás:
- A különböző konténerek összekapcsolása, management-je fapados.
- Nincs megoldva a skálázás, failover, high-availability.
- Alkalmazás fordítási, deployálási folyamatok támogatása.

Az OpenShift ezekre megoldást nyújt, ráépülve a Docker konténer technológiára.

# OpenShift Origin vs OpenShift Enterprise
![origin](../common/images/openshift_vs_origin.png)

# Alapfogalmak
- **Container, Image, Registry**: Az OpenShift a Docker-t használja konténer technológiaként ezért ezek pontosan a Docker foglamak.
- **Pod**: Egy vagy több konténer, közös tárterülettel, hálózattal. Telepítési, maanagement egység.
- **Node**: Podokat futtató gép.
- **Servive**: Belső terhelés elosztóként működnek. Egy hálózati portot reprezentál, amin elérhetőek a mögé bekötött POD-ok.
- **Build, BuildConfig**: Egy alkalmazás forráskódjából Docker image készül. Ez a folyamat a Build és ennek a paraméterezése a BuildConfig.
Az OpenShift alapegységei YAML ill. JSON formátumban is leírhatók. 

# OpenShift Architektúra
![origin](../common/images/openshift_arch2.png)

# Alkalmazásfejlesztés
![s2i](../common/images/s2i.png)
![s2i_2](../common/images/s2i_2.png)

## Build és ImageStream
Három módon témogatja az alkalmazások buildelését az OpenShift::
1. Docker: ez gyakorlatilag a Dockerfile alapú buildelési folyamat
2. S2I -Source to Image: a forráskód és egy Builder docker image alapján lefordítja, összeállítja a végterméket (itt is egy Docker image-et)
3. Custom build - Teljesen customizált build folyamat, saját Builder image-el.

**ImageStream**
Új image (pl. új verziójú build) elkészülése esetén szükség lehet követő tevékenységekre, pl. automatikus deployra.
Egy ilyen ImageStream egy nézetet biztosít egy vagy több Docker image-re a címkéken keresztül (pl. cimke a webszerveren, db-n,stb.)

**ImageStreamMapping**
Ha egy új Image kerül a registry-be, akkor készül egy metadata leíró, egy ImageStreamMapping

## Deployment, DeploymentConfiguration

# OpenShift adminisztráció
A master node-on fut, amelyet egy floating IP-n keresztül lehet elérni. A host neve nem a központi
https://bmepaas-master.openshift.local:8443

## OpenShift dashboard

## CLI parancsok
```shell
oc login            --belépés
oc new-app          --új alkalmazás létrehozása
```


# OpenShift skálázási lehetőségek
![scaling](../common/images/openshift_arch3.png)
## Replication Controller-ek
Felelősek, hogy mindig a meghatározott számú Pod fusson. Pl. ha leáll egy, akkor indít újat, stb.
Nem felelős azért, hogy mennyi is ez a Pod szám. Nem figyel forgalmat, terhelést, nem kalkulálja ki ezt a számot.

# OpenShift hálózati kommunikáció
A következő hálózati problémákra ad megoldást az OpenShift
- Routing: hogyan érhetőek el kívülről az alkalmazásaink
- Összetartozó Docker containerek (Pod-ok) hogyan kommunikáljanak egymással
- Újrainduló Pod-ok változó IP címeinek lekövetése.

![networking](../common/images/openshift_arch.png)
## Routing
A fő problémát az jelenti, hogy a különböző Node-okon létrejövő Pod-ok(akár több Docker container-rel)-ban futó alkalmazást, hogyan lehet kívülről elérni, használni.
A **Service** fogalom egy belső _Port_, ez kívülről még nem érhető el. 

Az OpenShift ezt úgy oldja meg, hogy egy Router komponens segítségével biztosít belépést a külső hívóknak.
Többféle Router is lehet, mi a HAProxy megoldást vizsgáljuk meg. 

Az egyes Node-okra kerül egy Router, egy HAProxy, amely fogadja a hálózati forgalmat és megkeresi a megfelelő Service-ket, amelyek felé delegálnia kell. 
Pl. a :80 -as porton érkező forgalmat a Router a "frontend" címkével rendelkező Service-ek felé irányítja, ahonnan már a megfelelő Pod-ok elérhetőek.

## Docker containerek közötti kommunikáció
A Kibernetes oldja meg, hogy egy Pod kap egy belső IP címet, mintha egy különálló Host géo lenne. Ezen a "virtualizált" hoston futnak a Docker containerek így azok képesek
kommunikálni egymással.
Pod-ok egymással nem (így) kommunikálnak. Pod-ok más Pod-okkal Service-en keresztül kommunikálnak.

## OpenShift DNS


