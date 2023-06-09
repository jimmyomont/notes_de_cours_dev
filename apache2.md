# APACHE 2

## Commandes de base

 
- ``sudo service apache2 start``: Démarrer Apache

- ``sudo service apache2 stop`` : Arrêter Apache

- ``sudo service apache2 restart``: Redémarrer Apache

- ``sudo service apache2 reload``:Recharger la configuration d'Apache 

- ``sudo service apache2 status``: Vérifier le statut d'Apache



## Configuration

- ``sudo nano /etc/apache2/apache2.conf ``: Modifier la configuration principale
- ``sudo nano /etc/apache2/sites-available/monsite.conf ``: Créer ou éditer un fichier de configuration de site


# Hôtes virtuels

- ``sudo a2ensite monsite.conf`` : Activer un site
- ``sudo a2dissite monsite.conf` : Désactiver un site


# Modules

- ``sudo a2enmod nom_du_module`` : Activer un module
- ``sudo a2dismod nom_du_module`` : Désactiver un module
- ``sudo apache2ctl -M`` : Afficher la liste des modules chargés


# Erreurs et journaux

- ``sudo tail -f /var/log/apache2/error.log`` : Afficher les erreurs d'Apache en temps réel
- ``sudo tail -f /var/log/apache2/access.log`` : Afficher les journaux d'accès en temps réel


# Redirection

- ``Redirect /ancien-chemin /nouveau-chemin`` : Rediriger une URL vers une autre


# Réécriture d'URL

- ``sudo a2enmod rewrite`` : Activer le module de réécriture d'URL
- ``sudo service apache2 restart`` : Redémarrer Apache après l'activation du module
- ``sudo nano /etc/apache2/apache2.conf`` : Modifier la configuration principale pour permettre la réécriture
