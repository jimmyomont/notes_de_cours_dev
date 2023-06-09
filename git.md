# GIT ( commandes)

## configutration 

- ``git config --global user.name "Votre nom"`` : Définit votre nom d'utilisateur Git.
- ``git config --global user.email "votre@email.com"`` : Définit votre adresse e-mail Git.

## Création et clonage :

- ``git init ``: Initialise un nouveau référentiel Git dans le répertoire actuel.
- ``git clone <url> ``: Clone un référentiel distant dans un nouveau répertoire.

## Sauvegarde (commit) :

- ``git status ``: Affiche l'état actuel du référentiel Git, montrant les fichiers modifiés/non suivis.
- ``git add <fichier> ``: Ajoute un fichier spécifique à l'index de Git pour préparation à la validation.
- ``git add . ``: Ajoute tous les fichiers modifiés et nouveaux de manière récursive à l'index de Git.
- ``git commit -m "message" ``: Valide les modifications ajoutées à l'index avec un message de validation.

## Branches :

- ``git branch ``: Affiche la liste des branches du référentiel, mettant en évidence la branche actuelle.
- ``git branch <nom_branche> ``: Crée une nouvelle branche.
- ``git checkout <nom_branche> ``: Permet de basculer vers une branche spécifique dans le référentiel.
- ``git merge <nom_branche> ``: Fusionne une branche spécifique dans la branche actuelle.
- ``git branch -d <nom_branche> ``: Supprime une branche locale.

## Récupération (pull) et envoi (push) :

- ``git pull ``: Récupère les modifications depuis un référentiel distant et les fusionne avec la branche actuelle.
- ``git push ``: Pousse les modifications locales vers un référentiel distant.
- ``git push <nom_dépôt> <branche> ``: Envoie les modifications locales vers un dépôt distant.

## Historique et information du contenu dossiers:

- ``git log ``: Affiche l'historique des validations effectuées dans le référentiel.
- ``git diff ``: Affiche les différences entre les modifications de fichiers qui ne sont pas encore ajoutées à l'index.
- ``git show <identifiant_commit> ``: Affiche les détails d'un commit spécifique.
- ``ls ``: Liste les fichiers et les répertoires du répertoire actuel.

## Suppression : 
- ``git reset ``: Annule les modifications en les supprimant de l'index, tout en conservant les modifications locales.
- ``git rm <fichier> ``: Supprime un fichier de l'index et du répertoire de travail.
- ``rm <fichier> ``: Supprime un fichier du système de fichiers.
- ``rm -f <fichier> ``: Supprime un fichier sans demander de confirmation.