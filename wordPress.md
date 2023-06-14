# WORDPRESS

## Comprendre WordPress :

### Installation : 

Pour commencer avec WordPress, vous devez installer le logiciel sur un serveur web. 
La plupart des hébergeurs proposent des installations en un clic pour WordPress. 
Une fois installé, vous pouvez accéder à votre site via l'URL de votre domaine.

### Interface d'administration : 

WordPress propose une interface d'administration conviviale, accessible via le lien "/wp-admin" ajouté à votre URL de site.
À partir de là, vous pouvez gérer tous les aspects de votre site web, y compris la création et l'édition de contenu, l'installation de thèmes et de plugins, la personnalisation du design, etc.

### Contenu : 

Dans WordPress, vous pouvez créer différents types de contenu, tels que des articles (pour les articles de blog) et des pages (pour les pages statiques comme la page d'accueil, la page À proposer, etc.). 
Vous pouvez ajouter du texte, des images, des vidéos et d'autres médias à votre contenu.

Thèmes : Les thèmes déterminent l'apparence et la mise en page de votre site. WordPress propose une grande variété de thèmes gratuits et premium que vous pouvez utiliser pour personnaliser l'apparence de votre site. 
Vous pouvez également créer votre propre thème si vous avez des compétences en développement web.

### Plugins : 

Les plugins sont des extensions qui ajoutent des fonctionnalités supplémentaires à votre site WordPress. 
Ils vous permettent d'ajouter des formulaires de contact, des galeries d'images, des fonctionnalités de commerce électronique, des optimisations de référencement, et bien plus encore. 
Il existe des milliers de plugins disponibles dans la bibliothèque officielle de WordPress.

### Personnalisation : 

WordPress propose de nombreuses options de personnalisation pour modifier l'apparence et les fonctionnalités de votre site. Vous pouvez personnaliser le thème, les widgets, les menus, les couleurs, les politiques, etc. selon vos préférences.

### SEO : 

WordPress est réputé pour être convivial en termes de référencement (SEO). 
Il propose des fonctionnalités intégrées pour optimiser votre contenu et améliorer la visibilité de votre site sur les moteurs de recherche.
 De plus, il existe des plugins SEO spécialisés tels que Yoast SEO et All in One SEO Pack pour vous aider dans votre stratégie de référencement.


---

## Commandes et de fonctionnalités courantes :

### Commandes de base :

``wp-admin`` : Accéder à l'interface d'administration de WordPress.

``wp-login.php`` : Page de connexion de WordPress.

``wp-config.php`` : Fichier de configuration de WordPress.


### Gestion des plugins :

``wp plugin install [nom-du-plugin]`` : Installer un plugin.

``wp plugin activate [nom-du-plugin]`` : Activer un plugin.

``wp plugin deactivate [nom-du-plugin]`` : Désactive un plugin.

``wp plugin list`` : Afficher la liste des plugins installés.

``wp plugin update [nom-du-plugin]`` : Mettre à jour un plugin.

### Gestion des thèmes :

``wp theme install [nom-du-theme]`` : Installer un thème.

``wp theme activate [nom-du-theme]`` : Activer un thème.

``wp theme list`` : Afficher la liste des thèmes installés.

``wp theme update [nom-du-theme]`` : Mettre à jour un thème.

### Gestion des utilisateurs :

``wp user create [nom-d'utilisateur] [email] --role=[role]`` : Créer un nouvel utilisateur.

``wp user list`` : Afficher la liste des utilisateurs.

``wp user delete [ID-utilisateur]`` : Supprimer un utilisateur.

``wp user update [ID-utilisateur]`` --user_pass=[mot-de-passe] : Mettre à jour le mot de passe d'un utilisateur.

### Gestion du contenu :

``wp post create --post_type=[type]`` --post_title=[titre] --post_status=[statut] : Créer un nouvel article.

``wp post list`` : Afficher la liste des articles.

``wp post delete [ID-article]`` : Supprimer un article.

``wp post update [ID-article]`` --post_title=[nouveau-titre] : Mettre à jour le titre d'un article.

### Réglages généraux :

``wp option get [nom-de-l'option]`` : Afficher la valeur d'une option.

``wp option update [nom-de-l'option] [nouvelle-valeur]`` : Mettre à jour la valeur d'une option.