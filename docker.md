# DOCKER

## Gestion des conteneurs :

- ``docker run`` : Crée et exécute un nouveau conteneur
- ``docker run <image>`` : Crée et démarre un nouveau conteneur à partir de l'image 
- ``docker start`` : Démarre un ou plusieurs conteneurs arrêtés
- ``docker start <container>`` : Démarre un conteneur arrêté.
- ``docker stop`` : Arrête un ou plusieurs conteneurs en cours d'exécution
- ``docker stop <container>`` : Arrête un conteneur en cours d'exécution.
- ``docker restart`` : Redémarre un ou plusieurs conteneurs en cours d'exécution
- ``docker restart <container>`` : Redémarre un conteneur en cours d'exécution.
- ``docker pause`` : Met en pause l'exécution d'un ou plusieurs conteneurs
- ``docker unpause`` : Reprend l'exécution d'un ou plusieurs conteneurs en pause
- ``docker rm`` : Supprime un ou plusieurs conteneurs
- ``docker rm <container>`` : Supprime un conteneur.
- ``docker ps`` : Liste les conteneurs en cours d'exécution
- ``docker ps -a ``: Liste tous les conteneurs (en cours d'exécution et arrêtés)
- ``docker logs <container>`` : Affiche les journaux (logs) d'un conteneur.


## Gestion des images :

- ``docker images ``: Liste les images disponibles sur l'hôte
- ``docker pull <image>``: Télécharge une image depuis un registre Docker
- ``docker build <path>``: Construit une image à partir d'un fichier Dockerfile
- ``docker push <image>``: Publie une image vers un registre Docker
- ``docker rmi <image>``: Supprime une ou plusieurs images

## Gestion du réseau :

- ``docker network ls`` : Affiche la liste des réseaux Docker.
- ``docker network create <network>`` : Crée un nouveau réseau Docker.
- ``docker network connect <network> <container>`` : Connecte un conteneur à un réseau existant.
- ``docker network disconnect <network> <container> ``: Déconnecte un conteneur d'un réseau.

## Gestion du stockage :

- ``docker volume create <volume> ``: Crée un volume Docker
- ``docker volume ls ``: Liste les volumes Docker disponibles
- ``docker volume rm`` : Supprime un ou plusieurs volumes Docker
- ``docker volume inspect <volume>``: Affiche des informations détaillées sur un volume Docker


## Contrôle et gestion des ressources :

- ``docker stats`` : Affiche les statistiques en temps réel sur l'utilisation des ressources par les conteneurs
- ``docker top ``: Affiche les processus en cours d'exécution dans un conteneur

## Autres commandes utiles :

- ``docker exec <container> <command> ``: Exécute une commande à l'intérieur d'un conteneur en cours d'exécution
- ``docker attach <container>`` : Attache le terminal local à un conteneur en cours d'exécution
- ``docker cp <container>:<path> <host_path> ``: Copie des fichiers entre le système hôte et un conteneur.
- ``docker logs`` : Affiche les journaux d'un conteneur
- ``docker inspect`` : Affiche des informations détaillées sur un conteneur ou une image Docker