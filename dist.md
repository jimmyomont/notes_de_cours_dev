# DOSSIER DIST (DISTRIBUTION)

>Le dossier 'dist' est utilisé pour stocker les fichiers statiques du projet. Le terme "dist" est généralement une abréviation de "distribution", ce qui signifie qu'il s'agit du répertoire où vous stockez les fichiers prêts à être distribués ou déployés sur un serveur de production.

1. Fichiers statiques :

Dans le contexte d'une application web, les fichiers statiques font référence à des fichiers qui ne changent pas dynamiquement en fonction des requêtes des utilisateurs. Ceux-ci incluent généralement des fichiers tels que des fichiers HTML, des images, des fichiers CSS, des fichiers JavaScript, etc.

2. Processus de construction :

Dans de nombreux projets JavaScript modernes, en particulier ceux qui utilisent des outils de build tels que Webpack, Babel, ou Parcel, le code source est souvent divisé en plusieurs fichiers. Ces fichiers peuvent être écrits en utilisant des fonctionnalités du langage JavaScript ou des modules qui ne sont pas encore pris en charge par tous les navigateurs.
Avant de réussir une application sur un serveur de production, il est courant de "compiler" ou de "transpiler" ces fichiers sources en versions compatibles avec les navigateurs et de les regrouper en fichiers plus petits et optimisés. Le processus de génération de ces fichiers optimisés est souvent appelé "construction" (ou "build" en anglais).

3. Dossier 'dist' :

Le dossier 'dist' est l'endroit où ces fichiers générés ou intégrés sont placés après le processus de construction. Il contient généralement les fichiers finaux et prêts à être utilisés dans un environnement de production.
Les fichiers du dossier 'dist' sont souvent minifiés, ce qui signifie qu'ils sont compressés pour réduire leur taille en supprimant les espaces et les commentaires inutiles.
Le code JavaScript peut également être transpilé pour être compatible avec des versions plus anciennes des navigateurs qui ne prennent pas en charge les dernières fonctionnalités du langage.

4. Déploiement :

Une fois que le dossier 'dist' est généré, il peut être déployé sur un serveur web de production. Le serveur web peut être configuré pour servir les fichiers statiques directement à partir du dossier 'dist' aux utilisateurs qui accèdent au site via leur navigateur.

>En résumé, le dossier 'dist' contient les fichiers finaux et optimisés d'une application web après le processus de construction. Il est utilisé pour la version prête à être utilisée de l'application sur un serveur de production afin que les utilisateurs puissent accéder aux fonctionnalités de l'application de manière efficace et rapide.
