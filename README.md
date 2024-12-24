# ScriptAutomatisationGestionServeurs
Le but est de déployer un serveur Apache, Configurer des services comme fail2ban et automatiser certaines tâches comme le monitoring des logs


## 1. Configuration Réseau du Serveur

### Objectif  
Configurer une connexion réseau fonctionnelle pour accéder à Internet depuis la VM.

### Étapes Réalisées  

#### 1.1. Démarrage de la VM
- La VM a été configurée sur **Hyper-V** avec un commutateur réseau externe pour permettre l'accès au réseau.

#### 1.2. Vérification des interfaces réseau  
- Commande utilisée pour afficher les interfaces réseau et vérifier l'état de la connexion :  
  ```bash
  ip a
Résultat : Une adresse IP 172.27.106.186/20 a été attribuée à l'interface réseau eth0

#### 1.3. Vérification des routes réseau
- Commande utilisée
  ```bash
  ip r
#### Test de Connectivité
- Test de communication avec la passerelle
- A Internet via une adresse Ip
- Test de la résolution DNS
  ```bash
  ping -c 172.27.96.1
  ping -c 4 8.8.8.8
  ping -c 4 google.com



## 2. Installation du Serveur Apache

### Objectif  
Installer et configurer le serveur web Apache pour héberger une page web simple.

### Étapes Réalisées  

#### 2.1. Mise à jour des dépôts 
  ```bash
  sudo apt update
 ```
#### 2.2 Installation d'Apache
  ```bash
  sudo apt install apache2 -y
 ```
#### 2.3 Vérification du service 
  ```bash
  sudo systemctl status apache2
 ```
Si le service n'est pas actif alors il faut le démarrer avec : sudo systemctl start apache2
#### Test de l'accès via le naviigateur 
Ouvrir un navigateur web et entrer l'adresse IP du serveur (par exemple : http://172.27.106.186). Si Apache est installé correctement, la page d'accueil d'Apache s'affichera.
