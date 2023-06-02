
# Mise en ligne d'un repo .github.io 

---

## Création d'un repo github [vers le cours](https://kourou.oclock.io/ressources/fiche-recap/github-pages/)

D'un un premier temps il faut créer un ripo sur portant votre login Github suivi de .github.io (login.github.io)

---

## Création dossier parcel 

### cours DWA-saison 3 [vers le cours](https://kourou.oclock.io/ressources/recap-quotidien/dwa-1-e07-recap-ofig/)

>Démarrer un projet qui va utiliser Parcel de zéro

>Si l’on souhaite démarrer un projet de zéro et configurer Parcel, c’est possible. Bien sûr connaître la procédure par cœur ne présente pas grand intérêt, on se dirigera plutôt vers la documentation.

>N’étant pas encore très familiarisé avec NPM que nous détaillerons en module 6, il peut être pratique de noter cette procédure succinctement :

>On crée un projet contenant un dossier `src` (pour contenir notre code) et au minimum un fichier `index.html` à l’intérieur (parcel suivra ensuite les liens des balises html à l’intérieur pour trouver les autres fichiers)

>On crée un fichier `package.json` via la commande `npm init -y`

>On installe parcel via `npm install --save-dev parcel`

>Il est bon d’ajouter un fichier .gitignore et d’y inscrire `node_modules` pour ne pas surcharger notre dépôt inutilement. On peut aussi ajouter `parcel-cache`et `dist`

>On modifie le fichier "package.json" avec l’emplacement du point d’entrée html et les scripts nécessaires à parcel 

*Attention une différence avec le cours, dans le package.json inscrire les lignes si dessous*

    {
        "source": "/src/index.html",
        "scripts": {
            "start": "parcel",
            "clear": "rm -rf .parcel-cache dist",
            "build": "parcel build",
            "deploy": "gh-pages -d dist"
        },
        "devDependencies": {
            "@parcel/transformer-sass": "^2.8.3",
            "parcel": "^2.8.3",
        },
        "dependencies": {
            "gh-pages": "^5.0.0",
            "reset-css": "^5.0.1",
            "sass": "^1.57.1"
        }
    }

>On lance le serveur de développement via npm start et on code dans src

### Ton dossier est prêt à être modifier

---

## Mise en ligne du ripo 

### 1- Depuis ton local 

Une fois ton projet térmminé tu peux dans un premier temps creer une branch nommé "gh-pages" `git branch  gh-pages`

ensuite tu fais les commandes suivante :

`` git add"`` , ``git commit`` et `` git push" `` pour publier le commit 


puis pour le déployer et le publier sur la page

`npm run clear `

*Ce qui éxecute la commande `rm -rf .parcel-cache dist` soit vide dist avant de publier*

`npm run build`

*Ce qui éxecute la commande `parcel build` qui compile les fichiers afin d'être lu par le server de Github*

``npm run deploy``

*Ce qui éxecute la commande `gh-pages -d dist` deploie ton projet sur Github*

### 2-  Depuis ton Github

- Dans ton github sélectionne ton ripo .github.io puis "Paramètres"
- Dans la liste "Général" sélectionne "pages"
- Dans la section "branch" , choisi la branch "Gh-pages" et "/root" pour le dossier puis "save"
- patiente quelques seconde voir minutes (si tu as fait un projet de malade) 
---

## Et voilà ta page github.io est en ligne 🥳 il y a plus qu'à partager ✌️