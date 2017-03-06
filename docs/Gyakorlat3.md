# Gyakorlat 3. - OpenShift S2I

## Tudnivalók
[Fontos információk](Tudnivalok.md)

**Fontos:**
- OpenShift konvenviók:
 - Felhasználónevetek legyen: studentXY - ahol X Y a nevetek kezdőbetűi pl. studentNZ
 - Projektek nevei: gyakorlatNXY - N a gyakorlat száma, X, Y lsd. előbb, pl. gyakorlat2NZ
- Mindenki a saját userét használja ezután, hogy izoláltan dolgozzatok!


## Feladat 1. - OpenShift S2I
**Időtartam: ~30 perc**

### Célja, leírás
Ennek a feladatnak a célja, hogy egy saját GitHub account alatti alkalmazást deployoljatok a PaaS-ra.

1. Az előző feladatban létrehozott példa alkalmazás alapján készítsetek a saját GitHub accountok alá egy klónozott forrás struktúrát. Lsd. [itt](Tudnivalok.md)   
2. Az előző feladatot ismételjétek meg ezzel az új Git URL-el és ezúttal CLI parancsok használatával.
3. Kövesd végig a build és deploy folyamatot (nézd a console-on, vagy a logokat)
4. Próbáld ki, hogy változtatsz a forráson és újra deployolsz.

_Hint: git parancsok,  oc project, oc projects, oc new-app -o json, oc start-build, oc describe build, oc logs -f bc, stb._

### Jegyzőkönyvhöz
A használt oc parancsokat küldjétek el a jegyzőkönyvben. 
