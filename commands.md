# Commandes utilisées pour la configuration du serveur

### 1. Mise à jour des paquets et installation des dépendances
sudo apt update && sudo apt upgrade -y

### 2. Installation de Glances
sudo apt install glances -y

### 3. Démarrer Glances en mode web (sur le port 61208)
glances -w

### 4. Vérification des interfaces réseau
ip a

### 5. Vérification des routes réseau
ip r

### 6. Test de connectivité réseau (ping à la passerelle, à Google, etc.)
ping -c 4 172.27.96.1
ping -c 4 8.8.8.8
ping -c 4 google.com

### 7. Installation de Apache
sudo apt install apache2 -y

### 8. Vérification que Apache fonctionne
sudo systemctl status apache2

### 9. Démarrage d'Apache si nécessaire
sudo systemctl start apache2

### 10. Activation d'Apache au démarrage
sudo systemctl enable apache2

### 11. Installation de Fail2Ban
sudo apt install fail2ban -y

### 12. Vérification de l'état de Fail2Ban
sudo systemctl status fail2ban

### 13. Démarrage de Fail2Ban si nécessaire
sudo systemctl start fail2ban

### 14. Activation de Fail2Ban au démarrage
sudo systemctl enable fail2ban

### 15. Modification du fichier de configuration Fail2Ban pour Apache
sudo nano /etc/fail2ban/jail.local

### 16. Redémarrage de Fail2Ban après modification
sudo systemctl restart fail2ban

### 17. Vérification du statut de Fail2Ban après modification
sudo fail2ban-client status apache

### 18. Configuration d'un script d'automatisation (par exemple, pour envoyer un rapport toutes les 10 minutes)
crontab -e

### Exemple de ligne à ajouter dans le crontab pour exécuter un script toutes les 10 minutes
#*/10 * * * * /path/to/automation.sh

### 19. Test d'email avec mailx (pour tester l'envoi de mails)
echo "Test email" | mail -s "Test" user@example.com

### 20. Vérification du port utilisé par Glances (par exemple, 61208)
sudo netstat -tuln | grep ":61208"

### 21. Vérification que le port HTTP (80) est bien accessible localement
curl -s -o /dev/null -w "%{http_code}" http://localhost | grep -q "200"

### 22. Création d'un script bash pour automatiser la surveillance (test des services, etc.)
#!/bin/bash
### test_suite.sh - Script pour tester le bon fonctionnement des configurations

### Fonction pour afficher les résultats
test_result() {
  if [ $1 -eq 0 ]; then
    echo -e "[OK] $2"
  else
    echo -e "[FAIL] $2"
  fi
}


