![alerantlogo](http://alerant.hu/img/logo.svg) 
# BME PaaS labor 
## Tudnivalók
**Oktató:** Nagy Zoltán, [Alerant Informatikai Zrt.](http://alerant.hu)

**Labor email elérhetőség:** alerant.bme.paas.labor@gmail.com

[Minden további tudnivaló itt](docs/Tudnivalok.md)

## Jegyzőkönyv
Az értékelés/érdemjegy alapja, mindenki töltse ki és küldje el az email címével.
A jegyzőkönyvben tesztkérdések és a gyakorlatok anyagaiból felmásolandó feladatok is vannak. Érdemes menet közben tölteni és egy külön dokumentumban külön is tárolni, nehogy elvesszen!
 
[A jegyzőkönyvet itt töltsétek ki](https://goo.gl/forms/rKN2WAWNCjxpBulS2)

**A jegyzőkönyvet a labor napján küldjétek be!**

---
# Célkitűzés, tematika
A labor célja a következő témák áttekintése:
- Alapműveletek konténerben futtatott alkalmazásokkal: konténer létrehozása dockerfile vagy Docker Hub image alapján, Docker registry vizsgálata,  a hoszt és a konténer kapcsolódásának vizsgálata (folyamat-azonosítók, portok, névterek), parancs futtatása a konténerben
- OpenShift deploymentek kezelése: github-ra feltöltött egyszerű projektből OpenShift image és deployment fordítása, telepítése, a pod-ok vizsgálata, kommunikáció a külvilág és a PaaS-ra telepített alkalmazás között (service-ek és route-ok vizsgálata)
- OpenShift pod-ok skálázása: a PaaS-ra telepített alkalmazáshoz terhelést generálunk, majd megvizsgáljuk az automatikus és a manuális lehetőségeket az alkalmazásunkat futtató pod-ok skálázására.
- Hálózati kommunikáció vizsgálata az OpenShift pod-ok között: elemezzük az OpenShift Software Defined Network működését, Wireshark segítségével végigkövetjük egy adatcsomag útját két pod között, továbbá áttekintjük az érintett hálózati protokollokat és virtualizációs technikákat (pl. VXLAN)

---

# Elméleti áttekintés
## IaaS, PaaS, SaaS
[IaaS, PaaS, SaaS áttekintés](docs/Elmelet1.md)

## Docker
[Docker](docs/Elmelet2.md)
## OpenShift áttekintés
[OpenShift](docs/Elmelet3.md)

---

# Gyakorlatok
## Gyakorlat 1. - Docker
[A gyakorlat itt érhető el](docs/Gyakorlat1.md)
## Gyakorlat 2. - OpenShift alapműveletek, alapfogalmak a gyakorlatban
[A gyakorlat itt érhető el](docs/Gyakorlat2.md)
## Gyakorlat 3. - OpenShift S2I deployment
[A gyakorlat itt érhető el](docs/Gyakorlat3.md)
## Gyakorlat 4. - Hálózat
[A gyakorlat itt érhető el](docs/Gyakorlat4.md)

# Opcionális gyakorlatok
## Gyakorlat 5. - OpenShift Skálázási parancsok
[A gyakorlat itt érhető el](docs/Gyakorlat5.md)

# Értékelés
[Az értékelés nem kötelező, névtelen, itt tölthetitek ki](https://goo.gl/forms/ibs2e7X2sGViZgH93)
