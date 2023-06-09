# UBUNTU 

## Navigation dans le terminal :

- ``cd [répertoire] ``: Change de répertoire.
- ``ls ``: Affiche le contenu du répertoire actuel.
- ``pwd ``: Affiche le chemin absolu du répertoire actuel.
- ``mkdir [nom du répertoire] ``: Crée un nouveau répertoire.
- ``rm [fichier] ``: Supprime un fichier.
- ``rm -r [répertoire] ``: Supprime un répertoire et son contenu récursivement.

## Gestion des paquets :

- ``sudo apt update ``: Met à jour la liste des paquets disponibles.
- ``sudo apt upgrade ``: Met à jour tous les paquets installés.
- ``sudo apt install [nom du paquet] ``: Installe un nouveau paquet.
- ``sudo apt remove [nom du paquet] ``: Supprime un paquet installé.
- ``sudo apt autoremove ``: Supprime les paquets inutilisés.

## Gestion des processus :

- ``ps ``: Affiche les processus en cours d'exécution.
- ``top ``: Affiche les processus en cours d'exécution en temps réel.
- ``kill [PID] ``: Termine un processus spécifié par son ID de processus.

## Gestion des utilisateurs et des permissions :

- ``sudo adduser [nom d'utilisateur] ``: Crée un nouvel utilisateur.
- ``sudo deluser [nom d'utilisateur] ``: Supprime un utilisateur.
- ``sudo visudo ``: Ouvre le fichier sudoers pour éditer les permissions des utilisateurs.

## Réseau :

- ``ifconfig ``: Affiche les informations sur les interfaces réseau.
- ``ping [adresse IP ou nom d'hôte] ``: Envoie des paquets ICMP à une adresse IP ou un nom d'hôte.
- ``ssh [nom d'utilisateur]@[adresse IP] ``: Se connecte à une machine distante via SSH.

Pour afficher le manuel, utiliser la commande ``man`` suivie du nom de la commande. Par exemple, ``man cd`` affiche le manuel pour la commande ``cd``.