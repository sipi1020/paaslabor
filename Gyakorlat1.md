# Alerant - BME PaaS labor 
# Gyakorlat 1. - Docker

## Tudnivalók
- VirtualBox-ban indítsd el a CentOS image-et és ebben dolgozz!
- CentOS Login: **BME Paas user / jelszó: openshift2017**
- sudo használható (óvatosan azért :))
- ha szükséged van esetleg a Linuxon valami package-re: sudo yum install -y XXXXXXXX
- Firefox a böngésző
- érdemes beállítani VirtualBox-ban a bidirectional clipboard-ot hogy a copy-paste működjön
- Ez az anyag elérhető a ~/Labor könyvtár alatt

**A jegyzőkönyvhöz menet közben gyűjtsd az anyagokat (külön jelölve van, hogy mikor mit), hogy a végén meglegyen minden.**
## Segédlet
 
[Legfontosabb Docker parancsok](https://www.cheatography.com/tobix10/cheat-sheets/docker-commands/)
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
_Hint: ezek a parancsok lesznek hasznotokra: docker search, docker pull, docker run -it, docker ps_
### Jegyzőkönyvhöz
A jegyzőkönyvhöz másold ki egy text fájlba az utolsó pontban használt parancsot és a kimenetelét!
## Feladat 2.
## Feladat 3.
## Feladat 4.
