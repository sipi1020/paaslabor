# Alerant - BME PaaS labor 
# Gyakorlat 2. - OpenShift áttekintés

## Tudnivalók
[Fontos információk](Tudnivalok.md)

## Telepített OpenShift áttekintése

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

## Feladat 1.


## Feladat 2.
## Feladat 3.
## Feladat 4.
