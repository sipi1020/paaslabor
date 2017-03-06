# Tudnivalók

## VirtualBox CentOS információk
- VirtualBox-ban indítsd el a CentOS image-et és ebben dolgozz!
- itt aláljátok meg az image-et, amit importáljatok VirtualBox-ba:D:\VPCImages\PAAS
- CentOS Login: **BME Paas user / jelszó: openshift2017**
- sudo használható (óvatosan azért :))
- ha szükséged van esetleg a Linuxon valami package-re: sudo yum install -y XXXXXXXX
- host gép könyvtárának mountolása: 1. hozz létre a VirtualBox-ban Devices/Shared Folders -ben egy foldert pl. host néven, majd a CentOS-ben ezt mountolhatod: sudo mount -t vboxsf host /media  (host a share neve)
- Firefox a böngésző
- érdemes beállítani VirtualBox-ban a bidirectional clipboard-ot hogy a copy-paste működjön
- serice-ek statusa, újraindítása pl.: sudo systemctl restart NetworkManager
- készítsetek magatoknak egy munkakönyvtárat és abban dolgozzatok

## GitHub

Mindenkinek készítenie kell egy GitHub-os account-ot, vagy a meglévőt használjátok!

1. https://github.com/
2. Sign Up
3. username pl. alerantbmexy, stb...., meg kell erősíteni a regisztrációt emailben kapott linken
4. GitHub-on start project, pl. gyakorlat2

A CentOS image-ben a ~/git könyvtárban tudtok dolgozni (több projekt is lesz)

Git fontos parancsok:
```shell
echo "# gyakorlat2" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/alerantbmexy/gyakorlat2.git
git push -u origin master
```

Gyakorlatokban így klónozz le példákat:
```shell
# példa Java OpenShift Wildfly alkalmazás klónozása
git clone https://github.com/bparees/openshift-jee-sample gyakorlat2

# ne az eredeti helyre tegyük vissza
git remote set-url origin https://github.com/alerantbmenz/gyakorlat2.git

# módosítások
git commit -a -m 'Some commit message'
# feltöltjük az új helyre a saját accountunk alá
git push origin master
```
Ekkor a saját GitHub URL alapján már lehet saját kódbázison új proktet létrehozni.

Ilyen a könvítárstruktúra:
```shell
[bmepaasuser@localhost ~]$ tree git/
git/
└── gyakorlat2
    ├── pom.xml
    ├── README.md
    └── src
        └── main
            ├── java
            ├── resources
            └── webapp
                ├── images
                │   └── jbosscorp_logo.png
                ├── index.html
                └── snoop.jsp

```


## DNS és hosts fájl
- Az openshift-es alkalmazások core komponensek alapvetően IP-vel érhetőek el, de az /etc/hosts fájlban fel vannak véve a FQDN-ek
- A gépeken dnsmasqd is telepítve van, amely segítségével működik a wildcard DNS is, tehát pl. az XXX.apps.openshift.local is feloldódik a megfelelő IP-re

dnsmasq config fájl: /etc/NetworkManager/dnsmasq.d

## IP-k
```shell
192.168.30.11	bmepaas-master.openshift.local
192.168.30.12	bmepaas-node1.openshift.local
192.168.30.13	bmepaas-node2.openshift.local
```


## Elérések

## Docker témához
- Vannak már Docker image-ek a lokális gépen, azt próbáljátok használni elsősorban és ne újakat töltsetek le!

## OpenShift témához
- OpenShift dashboard: https://bmepaas-master.openshift.local:8443
- Node1 gépen nézelődés: ssh student@bmepaas-node1.openshift.local (jelszó: student)
- Node2 gépen nézelődés: ssh student@bmepaas-node2.openshift.local (jelszó: student)

**Node1, Node2 gépeken csak a readonly docker parancsokat használd!!!**


## Jegyzőkönyv

**A jegyzőkönyvhöz menet közben gyűjtsd az anyagokat (külön jelölve van, hogy mikor mit), hogy a kitöltésnél már minden infó meglegyen.**
