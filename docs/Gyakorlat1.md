# Alerant - BME PaaS labor 
# Gyakorlat 1. - Docker

## Tudnivalók
[Fontos információk](Tudnivalok.md)
## Segédlet
## Docker parancsok
```shell
docker help
docker CMD --help
docker --debug CMD
```
[Legfontosabb Docker parancsok](https://www.cheatography.com/tobix10/cheat-sheets/docker-commands/)

## Hasznos linux parancsok
```shell
brctl show
ifconfig
ip link show
```


### Nginx
/usr/share/nginx/html alatt a főoldal
/etc/init.d/nginx stop|start|restart|status paranccsal lehet leállítani

## Feladat 1. - Docker alapműveletek
### Célja, leírás
Ennek a feladatnak a célja, hogy a legfontosabb Docker parancsokat megismerjétek.
1. Listázd az elérhető Docker parancsokat, ismerkedj meg a help-jével, hogy könnyen megtalálj majd mindent a későbbiekben. (pl. a debug opció mindig jól jön)
2. Nézd meg milyen image-ek vannak már lehúzva a helyi registry-be.
3. Húzz le egy cirros image-et. Próbáld ki az image keresést is. (docker.io/cirros)
4. Indítsd el az előbbi cirros image-ből készített container-t
4.1 Lépj be rá egy terminálba /bin/sh shell-be és győződj meg róla, hogy valóban egy izolált containerben vagy!
4.2 Hasonlítsd össze a futó processzeket a containerben és a host gépen.
5. Ellenőrizd a következőket a futó containerben
5.1 Mi a container host neve?
5.2 Milyen nameserver van beállítva?
5.3 Milyen hálózati interfészek vannak? Mi a gateway? Milyen IP-t kapott?
5.4 Milyen a routing table?
6. Fusson a cirros konténer és nyomozd ki, hogy milyen MAC address-t kapott!

_Hint: ezek a parancsok lesznek hasznotokra: docker search, docker pull, docker run -it, docker ps, netstat -nr, stb...._
### Jegyzőkönyvhöz
A jegyzőkönyvhöz másold ki egy text fájlba az utolsó pontban használt parancsot és a kimenetelét!

## Feladat 2.
### Célja, leírás
Ennek a feladatnak a célja, hogy egy futó konténernek valahogy a hasznát is vegyük. 
A feladat, hogy futtassatok Docker containerben egy web szervert. A host gépen megnyitva egy Firefoxot ezen az URL-en http://localhost írja ki, hogy Hello BME Paas labor!

Javasolt web szerver: nginx
A következőket biztosan meg kell oldani:
1. A konténer belső portjának megnyitása a host felé
2. Figyeljétek meg a konténer státuszát! élettartamát! Ha megváltoztattok benne pl. egy index.html-et és leállítjátok, akkor következő indításnál már nem lesz ott.
3. (Opcionális) Esetleg köteg becsatolással is megoldható (docker run -v ...).

_Hint: ezek a parancsok lesznek hasznotokra: docker run -p, stb.
### Jegyzőkönyvhöz
A kulcs parancsokkal együtt egy 2-3 mondatos leírás legyen, hogy hogyan oldottátok meg.

## Feladat 3.
### Célja, leírás
Futtassuk az előbbi konténert, ami kinyitja a 80-as portot és ellenőrizzük a hálózati működést.
1. Állítsd le az összes futó konténert.
2. Ellenőrizd a host gépen, hogy milyen hálózati interfészek vannak.
3. Indítsd el pl. az előbbi feladat konténerét úgy, hogy nyisson egy portot a hoszton.
4. Ellenőrizd a host gépen, hogy milyen hálózati interfészek vannak. Mi változott? Ellenőrizd a bridge-ket is!
5. Próbáld ki a docker network inspect parancsot. Figyeld meg, hogy milyen konténerek csatlakoznak.
6. (Opcionális) Akár több konténert is indíthatsz és az előbbi pontokat megnézheted ismét.

_Hint: ezek a parancsok lesznek hasznotokra: docker network, brctl, ifconfig_
### Jegyzőkönyvhöz
Nincs feladat.

## Feladat 4.
### Célja, leírás
Ennek a feladatnak a célja, hogy az előbb létrehozott containereket, image-ket takarítsuk ki.
**Előtte győződj meg róla, hogy minden begyűjtöttél a jegyzőkönyvhöz!**

1. Listázd a futó konténereket és töröld azokat, amiket Te indítottál.
2. Listázd az image-ket és töröld azokat, amiket Te töltöttél le.
_Hint: ezek a parancsok lesznek hasznotokra: docker rmi, docker rm, docker rm -v $(docker ps -a -q -f status=exited)_
### Jegyzőkönyvhöz
Nincs feladat.
