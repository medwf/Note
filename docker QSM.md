### QSM (Questions à Choix Multiples) sur le Module 1 : Introduction à Docker

#### 1. Qu'est-ce que Docker ?
a) Un système d'exploitation virtuel  
b) Une plateforme de conteneurisation pour créer, tester et déployer des solutions logicielles  
c) Un langage de programmation  
d) Un outil de gestion de bases de données  

---
#### 2. Qu'est-ce qu'un conteneur Docker ?
a) Une machine virtuelle avec son propre système d'exploitation  
b) Une instance en cours d'exécution d'une image Docker, encapsulant le code et ses dépendances  
c) Un serveur physique isolé  
d) Un outil de surveillance réseau  

---
#### 3. Quelle est la principale différence entre un conteneur Docker et une machine virtuelle ?
a) Les conteneurs partagent le noyau du système hôte, tandis que les machines virtuelles virtualisent le matériel  
b) Les conteneurs nécessitent plus de ressources que les machines virtuelles  
c) Les machines virtuelles sont plus légères que les conteneurs  
d) Les conteneurs ne peuvent pas être utilisés dans le cloud  

---
#### 4. Parmi les avantages de Docker, lequel est incorrect ?
a) Fournit un environnement informatique cohérent  
b) Alternative légère et plus rapide aux machines virtuelles  
c) Nécessite toujours un système d'exploitation distinct pour chaque conteneur  
d) Fonctionne aussi bien sur site que dans le cloud  

---
#### 5. Quelle technologie Docker a remplacé à partir de la version 0.9 en 2014 ?
a) Kubernetes  
b) LXC (Linux Containers)  
c) FreeBSD Jails  
d) OpenShift  

---
#### 6. Quel langage de programmation a été utilisé pour écrire la bibliothèque libcontainer de Docker ?
a) Python  
b) Java  
c) Go  
d) C++  

---
#### 7. Parmi les solutions concurrentes à Docker, laquelle a été lancée en 2000 ?
a) LXD  
b) FreeBSD Jails 
c) Kubernetes  
d) OpenShift  

---
#### 8. Pourquoi Docker est-il largement adopté par les fournisseurs de cloud public ?
a) Parce qu'il est propriétaire et coûteux  
b) Parce qu'il est open source, compatible avec plusieurs systèmes et bien intégré avec des outils d'orchestration comme Kubernetes  
c) Parce qu'il ne fonctionne que sur Linux  
d) Parce qu'il nécessite des ressources matérielles importantes  

---
#### 9. Quelle entreprise est un contributeur majeur de Docker ?
a) Apple  
b) Oracle  
c) Google  
d) Tesla  

---
#### 10. Quel est l'objectif principal des conteneurs Docker ?
a) Virtualiser le matériel physique  
b) Fournir une abstraction de la couche application avec isolation légère  
c) Remplacer complètement les machines virtuelles  
d) Limiter l'accès aux ressources réseau  



**Réponse correcte : b) Une plateforme de conteneurisation pour créer, tester et déployer des solutions logicielles**
**Réponse correcte : b) Une instance en cours d'exécution d'une image Docker, encapsulant le code et ses dépendances**
**Réponse correcte : a) Les conteneurs partagent le noyau du système hôte, tandis que les machines virtuelles virtualisent le matériel**
**Réponse correcte : c) Nécessite toujours un système d'exploitation distinct pour chaque conteneur**
**Réponse correcte : b) LXC (Linux Containers)**
**Réponse correcte : c) Go**
**Réponse correcte : b) FreeBSD Jails**
**Réponse correcte : b) Parce qu'il est open source, compatible avec plusieurs systèmes et bien intégré avec des outils d'orchestration comme Kubernetes**
**Réponse correcte : c) Google**
**Réponse correcte : b) Fournir une abstraction de la couche application avec isolation légère**


---
### QSM (Questions à Choix Multiples) - Module 2 : Comprendre Docker

  

#### **1. Quels sont les composants principaux du moteur Docker ?**

a) Docker Hub, Docker Compose, Docker Swarm

b) Un démon (dockerd), une API REST, un client CLI

c) Hyperviseur, noyau Linux, machines virtuelles

d) Registre privé, volumes, réseaux

  
  

---

  

#### **2. Qu'est-ce qu'une image Docker ?**

a) Une instance active d'une application

b) Un modèle en lecture seule pour créer des conteneurs

c) Un système de fichiers partagé entre conteneurs

d) Un outil de virtualisation matérielle

  
  

---

  

#### **3. Comment crée-t-on une image Docker personnalisée ?**

a) En modifiant directement une VM

b) Via un Dockerfile ou la commande `docker commit`

c) En clonant un conteneur existant

d) En utilisant uniquement Docker Hub

  
  

---

  

#### **4. Quelle est la différence clé entre un conteneur et une machine virtuelle ?**

a) Les conteneurs virtualisent le matériel, pas les VM

b) Les conteneurs partagent le noyau de l'hôte, les VM ont leur propre OS

c) Les VM sont plus légères que les conteneurs

d) Les conteneurs ne peuvent pas exécuter plusieurs processus

  
  

---

  

#### **5. Que permet un Union File System (UnionFS) dans Docker ?**

a) Virtualiser le CPU pour les conteneurs

b) Combiner plusieurs répertoires en une seule vue unifiée

c) Isoler les réseaux entre conteneurs

d) Sauvegarder automatiquement les données

  
  

---

  

#### **6. Quel composant Docker est responsable de la persistance des données ?**

a) Les réseaux

b) Les volumes

c) Les registres

d) Les services

  
  

---

  

#### **7. Pourquoi les conteneurs démarrent-ils plus vite que les VM ?**

a) Ils utilisent moins de RAM

b) Ils n'ont pas besoin de système d'exploitation

c) Ils partagent le noyau de l'hôte et évitent le démarrage d'un OS complet

d) Ils ne supportent pas les applications monolithiques

  
  

---

  

#### **8. Quel outil Docker permet de gérer des déploiements multi-hôtes ?**

a) Docker Hub

b) Docker Swarm

c) UnionFS

d) Libcontainer

  
  

---

  

#### **9. Que se passe-t-il lorsqu'un conteneur est supprimé ?**

a) L'image de base est également supprimée

b) La couche modifiable (writable layer) est perdue

c) Les volumes attachés sont automatiquement sauvegardés

d) Le réseau de l'hôte est réinitialisé

  
  

---

  

#### **10. Quel avantage offre la conteneurisation pour l'architecture logicielle ?**

a) Elle impose une architecture monolithique

b) Elle facilite les microservices grâce à l'isolation légère

c) Elle nécessite des ressources matérielles dédiées

d) Elle remplace complètement les load balancers

  
  

---

  

### **Fin du QSM**

Ces questions couvrent les concepts clés du **Module 2** :

- Architecture Docker (démon, API, CLI)

- Images vs conteneurs

- Différences VM/conteneurs

- Écosystème (orchestration, volumes, réseaux)





**Réponse correcte : b) Un démon (dockerd), une API REST, un client CLI** *(Page 1)*

**Réponse correcte : b) Un modèle en lecture seule pour créer des conteneurs** *(Page 2)*

**Réponse correcte : b) Via un Dockerfile ou la commande `docker commit`** *(Page 4)*

**Réponse correcte : b) Les conteneurs partagent le noyau de l'hôte, les VM ont leur propre OS** *(Page 6-7)*

**Réponse correcte : b) Combiner plusieurs répertoires en une seule vue unifiée** *(Page 3)*

**Réponse correcte : b) Les volumes** *(Page 2)*

**Réponse correcte : c) Ils partagent le noyau de l'hôte et évitent le démarrage d'un OS complet** *(Page 7)*

**Réponse correcte : b) Docker Swarm** *(Page 9)*

**Réponse correcte : b) La couche modifiable (writable layer) est perdue** *(Page 5)*

**Réponse correcte : b) Elle facilite les microservices grâce à l'isolation légère** *(Page 8)*


### QSM Supplémentaire (Questions à Choix Multiples) - Module 2 : Comprendre Docker

  

#### **11. Quel est le rôle des espaces de noms (namespaces) dans Docker ?**

  

a) Virtualiser le matériel physique

b) Limiter la vue du système pour un conteneur (isolation des processus, réseau, etc.)

c) Augmenter la vitesse de démarrage des VM

d) Gérer les sauvegardes automatiques

  

---

  

#### **12. Que permettent les groupes de contrôle (cgroups) ?**

  

a) Partager des ressources matérielles (CPU, mémoire) entre conteneurs

b) Créer des images Docker plus légères

c) Connecter des conteneurs à des réseaux externes

d) Exécuter des machines virtuelles dans Docker

  

---

  

#### **13. Quelle commande permet de distribuer une image Docker ?**

  

a) `docker push`

b) `docker build`

c) `docker start`

d) `docker network create`

  

---

  

#### **14. Pourquoi les images Docker sont-elles considérées comme "portables" ?**

  

a) Elles contiennent un OS complet

b) Elles incluent toutes les dépendances nécessaires pour l’application

c) Elles ne fonctionnent que sur un seul type de système

d) Elles nécessitent des VM pour s’exécuter

  

---

  

#### **15. Quel est l’avantage des couches (layers) dans les images Docker ?**

  

a) Elles rendent les images plus lourdes

b) Elles permettent de réutiliser des couches existantes, optimisant l’espace

c) Elles isolent chaque conteneur dans une VM

d) Elles empêchent la persistance des données

  

---

  

#### **16. Que signifie "libcontainer" ?**

  

a) Un outil de virtualisation pour Windows

b) Le format par défaut des conteneurs Docker (remplaçant LXC)

c) Un langage de programmation pour écrire des Dockerfiles

d) Un registre d’images privé

  

---

  

#### **17. Quel composant Docker permet de connecter des conteneurs à des réseaux externes ?**

  

a) Volumes

b) Images

c) Réseaux (Networks)

d) Services

  

---

  

#### **18. Quelle est la principale limitation des conteneurs comparés aux VM ?**

  

a) Ils consomment plus de ressources

b) Ils offrent une isolation moins forte (partage du noyau hôte)

c) Ils ne peuvent pas être sauvegardés

d) Ils ne fonctionnent pas dans le cloud

  

---

  

#### **19. À quoi sert un "load balancer" dans l’écosystème Docker ?**

  

a) À compiler des images Docker

b) À équilibrer le trafic entre plusieurs conteneurs/serveurs

c) À créer des volumes persistants

d) À isoler des espaces de noms

  

---

  

#### **20. Quel outil n’est PAS un moteur d’orchestration Docker ?**

  

a) Kubernetes

b) Docker Swarm

c) Apache Mesos

d) UnionFS

  

**Réponse correcte : b) Limiter la vue du système pour un conteneur** _(Page 3)_

**Réponse correcte : a) Partager des ressources matérielles (CPU, mémoire) entre conteneurs** _(Page 3)_

**Réponse correcte : a) `docker push`** _(Page 4, impliqué par la distribution via Docker Hub)_

**Réponse correcte : b) Elles incluent toutes les dépendances nécessaires pour l’application** _(Page 4)_

**Réponse correcte : b) Elles permettent de réutiliser des couches existantes, optimisant l’espace** _(Page 5)_

**Réponse correcte : b) Le format par défaut des conteneurs Docker (remplaçant LXC)** _(Page 3)_

**Réponse correcte : c) Réseaux (Networks)** _(Page 2)_

**Réponse correcte : b) Ils offrent une isolation moins forte (partage du noyau hôte)** _(Page 7)_

**Réponse correcte : b) À équilibrer le trafic entre plusieurs conteneurs/serveurs** _(Page 9)_

**Réponse correcte : d) UnionFS** _(Page 9, UnionFS est un système de fichiers, pas un outil d’orchestration)_

### **QSM (Questions à Choix Multiples) - Module 3 : Docker CE sur Linux**

  

#### **1. Quelle est la différence entre Docker CE et Docker EE ?**

  

a) Docker CE est pour les entreprises, Docker EE pour les développeurs

b) Docker CE est pour les développeurs et petites équipes, Docker EE pour les entreprises

c) Docker CE ne fonctionne que sur Windows

d) Docker EE est une version gratuite de Docker

  

---

  

#### **2. Quels sont les canaux de mise à jour de Docker CE ?**

  

a) Stable, Beta, Nightly

b) General, Test, Experimental

c) Main, Edge, Legacy

d) Production, Development, Archive

  

---

  

#### **3. Quelle version minimale du noyau Linux est requise pour Docker ?**

  

a) 2.6+

b) 3.10+

c) 4.0+

d) 5.0+

  

---

  

#### **4. Quelle commande permet d'ajouter un utilisateur au groupe docker ?**

  

a) `sudo useradd docker "nom_utilisateur"`

b) `sudo usermod -aG docker "nom_utilisateur"`

c) `sudo groupadd docker "nom_utilisateur"`

d) `sudo chown docker "nom_utilisateur"`

  

---

  

#### **5. Pourquoi faut-il éviter d'exécuter Docker en tant que root ?**

  

a) Pour améliorer les performances

b) Pour des raisons de sécurité (équivalent à accorder des privilèges root)

c) Docker ne fonctionne pas en mode root

d) Seul le groupe "docker" peut utiliser les conteneurs

  

---

  

#### **6. Quels packages sont nécessaires pour installer Docker sur CentOS ?**

  

a) `yum-utils`, `device-mapper-persistent-data`, `lvm2`

b) `docker-ce`, `docker-cli`, `containerd.io`

c) `python3`, `git`, `gcc`

d) `kernel-devel`, `gpg`, `curl`

  

---

  

#### **7. Comment vérifier que Docker est correctement installé ?**

  

a) `docker --version`

b) `docker info`

c) `systemctl status docker`

d) Toutes les réponses ci-dessus

  

---

  

#### **8. Quelle architecture est prise en charge par Docker ?**

  

a) 32 bits (x86)

b) 64 bits (x86_64/amd64)

c) ARM uniquement

d) Toutes les architectures

  

---

  

#### **9. Quel pilote de stockage est mentionné pour Docker sur CentOS ?**

  

a) AUFS

b) devicemapper

c) overlay2

d) btrfs

  

---

  

#### **10. Comment installer Docker de manière non interactive ?**

  

a) Via `yum install docker-ce`

b) En utilisant un script de `get.docker.com`

c) En compilant le code source

d) Avec `apt-get install docker.io`

  

---

  

### **Section Pratique : Commandes Docker**

  

#### **11. Quelle commande permet de démarrer un conteneur ?**

  

a) `docker run`

b) `docker start`

c) `docker create`

d) `docker exec`

  

---

  

#### **12. Comment lister tous les conteneurs (y compris arrêtés) ?**

  

a) `docker ps`

b) `docker ps -a`

c) `docker list`

d) `docker containers --all`

  

---

  
  
  

**Réponse correcte : b) Docker CE est pour les développeurs et petites équipes, Docker EE pour les entreprises** _(Page 1)_

**Réponse correcte : a) Stable, Beta, Nightly** _(Page 1)_

**Réponse correcte : b) 3.10+** _(Page 2)_

**Réponse correcte : b) `sudo usermod -aG docker "nom_utilisateur"`** _(Page 3)_

**Réponse correcte : b) Pour des raisons de sécurité (équivalent à accorder des privilèges root)** _(Page 3)_

**Réponse correcte : a) `yum-utils`, `device-mapper-persistent-data`, `lvm2`** _(Page 2)_

**Réponse correcte : d) Toutes les réponses ci-dessus** _(Pages 2-3, implicite)_

**Réponse correcte : b) 64 bits (x86_64/amd64)** _(Page 2)_

**Réponse correcte : b) devicemapper** _(Page 2)_

**Réponse correcte : b) En utilisant un script de `get.docker.com`** _(Page 3)_

**Réponse correcte : a) `docker run`** _(Hors PDF, mais essentiel pour le module)_

**Réponse correcte : b) `docker ps -a`** _(Hors PDF, mais lié aux objectifs du module)_

### **QSM (Questions à Choix Multiples) - Module 4 : Réseaux Docker**

  

#### **1. Quels sont les réseaux Docker disponibles par défaut ?**

  

a) `bridge`, `host`, `none`, `overlay`

b) `nat`, `public`, `private`, `dmz`

c) `eth0`, `wlan0`, `docker0`, `vlan`

d) `default`, `custom`, `external`, `internal`

  

---

  

#### **2. Quel réseau Docker utilise NAT pour partager l'adresse IP de l'hôte ?**

  

a) `host`

b) `none`

c) `bridge`

d) `overlay`

  

---

  

#### **3. Quelle commande permet d'inspecter un réseau Docker ?**

  

a) `docker inspect network`

b) `docker network inspect`

c) `docker net --details`

d) `docker show network`

  

---

  

#### **4. Quel réseau Docker supprime toute interface réseau pour un conteneur ?**

  

a) `bridge`

b) `host`

c) `none`

d) `overlay`

  

---

  

#### **5. Comment lancer un conteneur Nginx dans le réseau `host` ?**

  

a) `docker run --net=host nginx`

b) `docker run --network=none nginx`

c) `docker run --net=bridge nginx`

d) `docker run --network=overlay nginx`

  

---

  

#### **6. Quel réseau permet à des conteneurs sur différents hôtes Docker de communiquer ?**

  

a) `bridge`

b) `host`

c) `none`

d) `overlay`

  

---

  

#### **7. Quelle commande crée un réseau bridge personnalisé avec un sous-réseau spécifique ?**

  

a) `docker network create --driver=bridge --subnet=172.99.11.0/24 new_bridge`

b) `docker create network --type=bridge --ip=172.99.11.0/24 new_bridge`

c) `docker net add bridge --subnet=172.99.11.0/24 new_bridge`

d) `docker network new --driver=bridge --range=172.99.11.0/24 new_bridge`

  

---

  

#### **8. Comment connecter un conteneur existant à un nouveau réseau ?**

  

a) `docker attach network <nom_réseau> <conteneur>`

b) `docker network connect <nom_réseau> <conteneur>`

c) `docker connect <conteneur> <nom_réseau>`

d) `docker net join <nom_réseau> <conteneur>`

  

---

  

#### **9. Quelle commande supprime tous les réseaux inutilisés ?**

  

a) `docker network clean`

b) `docker network rm --all`

c) `docker network prune`

d) `docker net delete unused`

  

---

  

#### **10. Que se passe-t-il si un conteneur est démarré avec `--net=none` ?**

  

a) Il partage le réseau de l'hôte.

b) Il n'a aucune connectivité réseau.

c) Il utilise automatiquement le réseau `bridge`.

d) Il crée un nouveau réseau overlay.

  

---

  

### **Section Pratique : Commandes Réseau**

  

#### **11. Comment lister tous les réseaux Docker disponibles ?**

  

a) `docker net ls`

b) `docker network list`

c) `docker network ls`

d) `docker list networks`

  

---

  

#### **12. Comment supprimer un réseau personnalisé nommé `my_network` ?**

  

a) `docker network delete my_network`

b) `docker net rm my_network`

c) `docker network rm my_network`

d) `docker remove network my_network`

  

---

  

### **Concepts couverts :**

  

- Types de réseaux Docker (`bridge`, `host`, `none`, `overlay`)

- Commandes clés (`inspect`, `create`, `connect`, `prune`)

- Isolation réseau et communication multi-hôtes

  

**Réponse correcte : a) `bridge`, `host`, `none`, `overlay`** _(Page 1)_

**Réponse correcte : c) `bridge`** _(Page 2)_

**Réponse correcte : b) `docker network inspect`** _(Page 2)_

**Réponse correcte : c) `none`** _(Page 4)_

**Réponse correcte : a) `docker run --net=host nginx`** _(Page 3)_

**Réponse correcte : d) `overlay`** _(Page 5)_

**Réponse correcte : a) `docker network create --driver=bridge --subnet=172.99.11.0/24 new_bridge`** _(Page 5)_

**Réponse correcte : b) `docker network connect <nom_réseau> <conteneur>`** _(Page 6)_

**Réponse correcte : c) `docker network prune`** _(Page 6)_

**Réponse correcte : b) Il n'a aucune connectivité réseau.** _(Page 4)_

**Réponse correcte : c) `docker network ls`** _(Page 1, implicite)_

**Réponse correcte : c) `docker network rm my_network`** _(Page 6)_

### **QSM (Questions à Choix Multiples) - Module 5 : Images Docker**

  

#### **1. Qu'est-ce qu'une image Docker ?**

  

a) Une instance active d'une application en cours d'exécution

b) Un modèle en lecture seule pour créer des conteneurs

c) Un système de fichiers partagé entre plusieurs conteneurs

d) Un outil de virtualisation matérielle

  

---

  

#### **2. Où sont stockées les images Docker ?**

  

a) Dans des registres (comme Docker Hub)

b) Uniquement sur le système de fichiers local

c) Dans des machines virtuelles

d) Dans des bases de données relationnelles

  

---

  

#### **3. Quelle commande permet d'extraire une image depuis Docker Hub ?**

  

a) `docker pull`

b) `docker fetch`

c) `docker extract`

d) `docker get`

  

---

  

#### **4. Quel fichier est utilisé pour construire une image personnalisée ?**

  

a) `Dockerfile`

b) `docker-compose.yml`

c) `Dockerimage.conf`

d) `docker-build.sh`

  

---

  

#### **5. Quelle instruction Dockerfile est utilisée pour définir l'image de base ?**

  

a) `FROM`

b) `BASE`

c) `IMAGE`

d) `RUN`

  

---

  

#### **6. Comment créer une image à partir d'un conteneur modifié ?**

  

a) `docker save`

b) `docker commit`

c) `docker export`

d) `docker create`

  

---

  

#### **7. Quelle commande permet d'envoyer une image vers Docker Hub ?**

  

a) `docker push`

b) `docker upload`

c) `docker send`

d) `docker publish`

  

---

  

#### **8. Quelle couche d'une image Docker est modifiable ?**

  

a) La couche de base (base layer)

b) La couche inscriptible (writable layer) du conteneur

c) Toutes les couches sont en lecture seule

d) Seule la couche réseau

  

---

  

#### **9. Quel est l'avantage des images Docker en couches ?**

  

a) Elles augmentent la taille totale de l'image

b) Elles permettent de réutiliser des couches existantes, optimisant l'espace

c) Elles rendent les conteneurs plus lents à démarrer

d) Elles nécessitent un système de fichiers spécial

  

---

  

#### **10. Quelle instruction Dockerfile exécute des commandes pendant la construction de l'image ?**

  

a) `CMD`

b) `RUN`

c) `EXEC`

d) `START`

  

---

  

### **Section Pratique : Dockerfile**

  

#### **11. Quelle instruction définit la commande par défaut d'un conteneur ?**

  

a) `RUN`

b) `CMD`

c) `ENTRYPOINT`

d) `DEFAULT`

  

---

  

#### **12. Comment lister toutes les images locales ?**

  

a) `docker images`

b) `docker list`

c) `docker ps -a`

d) `docker show images`

  

---

  

**Réponse correcte : b) Un modèle en lecture seule pour créer des conteneurs** _(Page 1)_

**Réponse correcte : a) Dans des registres (comme Docker Hub)** _(Page 1, implicite via "Registre stocke les référentiels")_

**Réponse correcte : a) `docker pull`** _(Hors PDF, mais essentiel pour le module)_

**Réponse correcte : a) `Dockerfile`** _(Page 1, section III)_

**Réponse correcte : a) `FROM`** _(Hors PDF, mais couramment utilisée)_

**Réponse correcte : b) `docker commit`** _(Page 1, section IV)_

**Réponse correcte : a) `docker push`** _(Page 1, section V)_

**Réponse correcte : b) La couche inscriptible (writable layer) du conteneur** _(Page 1, "Une couche inscriptible est créée...")_

**Réponse correcte : b) Elles permettent de réutiliser des couches existantes, optimisant l'espace** _(Hors PDF, mais concept clé lié aux couches)_

**Réponse correcte : b) `RUN`** _(Hors PDF, mais essentielle pour Dockerfile)_

**Réponse correcte : b) `CMD`** _(Hors PDF, mais liée aux instructions courantes)_

**Réponse correcte : a) `docker images`** _(Hors PDF, mais fondamentale pour la gestion des images)_

### **QSM (Questions à Choix Multiples) - Module 6 : Stockage Docker et Volumes**

  

#### **1. Quels sont les trois types de stockage dans Docker ?**

  

a) **Stockage local pour conteneur**, **Stockage de données persistant**, **Stockage d'images statiques**

b) Stockage RAM, Stockage SSD, Stockage réseau

c) Volumes, Bind Mounts, Stockage cloud

d) Images, Conteneurs, Réseaux

  

---

  

#### **2. Quel est le pilote de stockage recommandé par Docker ?**

  

a) `AUFS`

b) `Overlay 2`

c) `DeviceMapper`

d) `ZFS`

  

---

  

#### **3. Quelle commande permet de vérifier l’espace disque utilisé par Docker ?**

  

a) `docker ps -s`

b) `docker system df`

c) `docker volume ls`

d) `docker info`

  

---

  

#### **4. Pourquoi éviter de stocker des données dans la couche inscriptible d’un conteneur ?**

  

a) Les données persistent après la suppression du conteneur

b) **Les données sont perdues si le conteneur est supprimé**

c) Cela améliore les performances

d) C’est le seul moyen de partager des données entre conteneurs

  

---

  

#### **5. Quelle méthode de stockage persistant est gérée par Docker et isolée du système hôte ?**

  

a) **Volumes**

b) Bind Mounts

c) tmpfs Mounts

d) Réseaux overlay

  

---

  

#### **6. Comment créer un volume Docker ?**

  

a) `docker volume create`

b) `docker create --volume`

c) `docker storage new`

d) `docker mount volume`

  

---

  

#### **7. Quelle option permet de monter un répertoire hôte dans un conteneur ?**

  

a) `--volume` ou `--mount` (Bind Mounts)

b) `--tmpfs`

c) `--network`

d) `--storage`

  

---

  

#### **8. Quel est l’avantage des volumes par rapport aux Bind Mounts ?**

  

a) **Ils sont gérés par Docker et plus portables**

b) Ils offrent un accès direct aux fichiers système critiques

c) Ils sont plus rapides car stockés en RAM

d) Ils ne nécessitent pas de configuration

  

---

  

#### **9. Quelle commande supprime tous les volumes inutilisés ?**

  

a) `docker volume rm all`

b) **`docker volume prune`**

c) `docker system cleanup`

d) `docker storage reset`

  

---

  

#### **10. À quoi sert un montage `tmpfs` ?**

  

a) **Stocker des données temporaires en RAM**

b) Partager des fichiers avec d’autres conteneurs

c) Sauvegarder des données sur le disque dur

d) Monter un réseau distant

  

---

  

### **Section Pratique**

  

#### **11. Comment lister tous les volumes Docker ?**

  

a) `docker volumes`

b) **`docker volume ls`**

c) `docker list volumes`

d) `docker storage list`

  

---

  

#### **12. Quel fichier configure le pilote de stockage par défaut ?**

  

a) `/etc/docker/daemon.json`

b) `/var/lib/docker/config.json`

c) `~/.docker/config`

d) `/usr/bin/dockerd.conf`

  

**Réponse correcte : a)** _(Page 1)_

**Réponse correcte : b) `Overlay 2`** _(Page 3)_

**Réponse correcte : b) `docker system df`** _(Page 2)_

**Réponse correcte : b)** _(Page 4)_

**Réponse correcte : a) Volumes** _(Page 5)_

**Réponse correcte : a) `docker volume create`** _(Hors PDF, mais standard)_

**Réponse correcte : a)** _(Page 6)_

**Réponse correcte : a)** _(Pages 5-6)_

**Réponse correcte : b)** _(Page 5)_

**Réponse correcte : a)** _(Page 5)_

**Réponse correcte : b)** _(Standard Docker CLI)_

**Réponse correcte : a)** _(Page 3)_