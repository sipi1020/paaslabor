# Gyakorlat 2. - OpenShift áttekintés

## Tudnivalók
[Fontos információk](Tudnivalok.md)

**Fontos:**
- **Felhasználóneveket a gyakorlatvezető osztjka ki: student1, student2, student3, ..... student25** 
- Mindenki a saját userét használja ezután, hogy izoláltan dolgozzatok!



## Telepített OpenShift áttekintése - vezetett bemutató
### Dashboard
- Belépés/Kilépés
- Új projekt létrehozása (projektnév egyedi!)
  - Javascript példa kiválasztása, Node.js
  - TryIt Git sample kiválasztása
  - Advanced részek áttekintése
- Build folyamat 
- Deployment folyamat
- Deployment Config
- Pod-ok (build és az alkalmazás)

_További dokumentáció: https://docs.openshift.org/latest/welcome/index.html_

```shell
oc login https://bmepaas-master.openshift.local:8443
oc project XXXX
```


### oc CLI, fő komponensek
```shell
 oc login https://bmepaas-master.openshift.local:8443    
```

Node-ok:
```shell
oc get nodes
NAME                             STATUS                     AGE
bmepaas-master.openshift.local   Ready,SchedulingDisabled   2d
bmepaas-node1.openshift.local    Ready                      2d
bmepaas-node2.openshift.local    Ready                      2d
```
_A master-re nem kerülhet Pod (SchedulingDisabled)_

Szolgáltatások:
```shell
oc get services
NAME               CLUSTER-IP       EXTERNAL-IP   PORT(S)                   AGE
docker-registry    172.30.238.160   <none>        5000/TCP                  2d
kubernetes         172.30.0.1       <none>        443/TCP,53/UDP,53/TCP     2d
registry-console   172.30.8.163     <none>        9000/TCP                  2d
router             172.30.117.243   <none>        80/TCP,443/TCP,1936/TCP   2d
```

A "gyári" Pod-ok:
```shell
oc get pods
NAME                       READY     STATUS    RESTARTS   AGE
docker-registry-2-8ejuy    1/1       Running   1          2d
registry-console-1-63wqa   1/1       Running   1          2d
router-1-2wth4             1/1       Running   1          2d
router-1-wksfx             1/1       Running   1          2d

oc adm manage-node bmepaas-node1.openshift.local --list-pods
Listing matched pods on node: bmepaas-node1.openshift.local
NAME                       READY     STATUS    RESTARTS   AGE
registry-console-1-63wqa   1/1       Running   1          2d
router-1-wksfx             1/1       Running   1          2d

```

## Segédlet

### A feladatokhoz szükséges CLI parancsok:
```shell
oc help
oc login https://bmepaas-master.openshift.local:8443
oc whoami
oc status
oc describe
oc new-app
```

## Feladat 1. - PaaS minta alkalmazás telepítése
**Időtartam: 30 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy kipróbáljátok a PaaS-t. Hozzatok létre a projteteken belül egy minta alkalmazást (választhattok technológiát a dashboard-ról).
 
Javasolt minta: NodeJS vagy Java
A következőkön haladjatok végig és a megjelölt adatokat gyűjtsétek be a jegyzőkönyvhöz:

1. Hozzatok létre egy alkalmazást a saját useretekkel a Dashboardon (egyszerű legyen, ne perzisztens alkalmazást válasszatok). A kiválasztott Git projektet nézzétek át a github-os linkjén.
2. Ellenőrizd, hogy böngészőből eléred az alkalmazást és működik-e!
3. A bemutató alapján nézd végig a Dashboard-on, hogy mik is jöttek létre, milyen információkat látsz.
4. Ugyanígy nézd át az oc CLI -vel is a projektetd, a POD-od, a service-t.
4. Derítsd ki, hogy melyik Node-ra (gépre) települt ki és milyen IP-n port-on hallagatózik
5. Nézd meg az adott Node-on, hogy a Docker-ben milyen container jött létre. 

_Hint: ezek a parancsok lesznek hasznotokra: oc new-app, docker images, docker inspect, oc get svc stb._

### Jegyzőkönyvhöz
A futó alkalmazás docker container részletes leírását (inspect) másoljátok ki, és majd illesszétek be a jegyzőkönyvbe.
