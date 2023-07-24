# ETAPES POUR LA CONCEPTION D'UNE BASE DE DONNES

## 1. Définir les besoins : 
Avant de créer une base de données, il est essentiel de comprendre les besoins de l'application ou du projet. Quels types de données seront stockées ? Quelles opérations seront effectuées sur les données ? Quelles sont les contraintes de performance et de sécurité ?

## 2. Choisir le Système de Gestion de Base de Données (SGBD) : 
En fonction des besoins identifiés, choisissez un SGBD qui correspond le mieux à votre projet. Les SGBD populaires incluent MySQL, PostgreSQL, Microsoft SQL Server, Oracle, MongoDB, etc.

## 3. Concevoir le schéma de la base de données : 
créer le schéma de la base de données en définissant les tables, les colonnes, les relations et les contraintes. Cette étape est cruciale car elle détermine la structure de la base de données.

Schéma de notre base de données PostgreSQL :

- Tableau "tâches" :
    - id (clé primaire)
    - description (texte de la tâche)
    - terminé (booléen pour indiquer si la tâche est terminée)
    - createdAt (horodatage de création)
    - updatedAt (horodatage de mise à jour)

## 4. Créer la base de données : 
Utilisez le SGBD choisi pour créer physiquement la base de données en utilisant le schéma défini précédemment.

## 5. Établir une connexion : 
Pour utiliser la base de données dans votre application, vous devez établir une connexion entre l'application et la base de données. Généralement, cela implique de fournir des informations d'identification telles que le nom d'utilisateur, le mot de passe et l'emplacement de la base de données.

## 6. Créer des requêtes : 
Les requêtes sont utilisées pour interagir avec la base de données. Vous pouvez utiliser le langage de requête spécifique au SGBD (par exemple, SQL pour les bases de données relationnelles) pour effectuer des opérations telles que l'insertion, la mise à jour, la suppression et la récupération de données.

Dans notre backend (Node.js avec Express et Sequelize), nous créons des routes pour effectuer des opérations CRUD (Create, Read, Update, Delete) sur les tâches.

- POST /api/tasks : Pour ajouter une nouvelle tâche à la base de données.
- GET /api/tasks : Pour récupérer toutes les tâches existantes.
- PUT /api/tasks/:taskId : Pour marquer une tâche comme terminée.
- DELETE /api/tasks/:taskId : Pour supprimer une tâche.

## 7. Gérer la base de données : 
Gérer la base de données de manière appropriée en effectuant des sauvegardes régulières, en optimisant les performances et en garantissant la sécurité des données.

## 8. Tester et déboguer : 
Effectuez des tests exhaustifs pour vous assurer que la base de données fonctionne correctement et répond aux exigences requises. Déboguez les problèmes potentiels pour améliorer la fiabilité de la base de données.

