# CRUD

CRUD signifie créer, lire, mettre à jour et supprimer. Ce sont les quatre opérations fondamentales utilisées dans les systèmes de gestion de bases de données et la conception d'API. Chaque opération correspond à une action spécifique sur les données :

## Créer (Create) :

- Objectif : 
    - Insertion de nouvelles données dans le système.
- Équivalent de la base de données : 
    - instruction SQL INSERT.
- Méthode HTTP de l'API : 
    - POST
- Exemple de point de terminaison d'API : 
    - ``POST /api/users``(pour créer un nouvel utilisateur)

## Lire (Read) :

Objectif : 
    - Récupération des données du système.
- Équivalent de la base de données : 
    - instruction SQL SELECT.
- Méthode HTTP de l'API : 
    - GET
- Exemple de point de terminaison d'API : 
    - ``GET /api/users``(pour obtenir une liste d'utilisateurs)

## Mise à jour (UpDate) :

- Objet : 
    - Modification des données existantes dans le système.
- Équivalent de la base de données : 
    - instruction SQL UPDATE.
- Méthode API HTTP : 
    - PUT ou PATCH
- Exemple de point de terminaison d'API : 
    - ``PUT /api/users/{id}``(pour mettre à jour un utilisateur spécifique) ou ``PATCH /api/users/{id}``(pour mettre à jour - partiellement un utilisateur spécifique)

## Supprimer (Delete) :

- Objectif : 
    - supprimer des données du système.
- Équivalent de la base de données : 
    - instruction SQL DELETE.
- Méthode HTTP de l'API : 
    - SUPPRIMER
- Exemple de point de terminaison d'API : 
    - ``DELETE /api/users/{id}``(pour supprimer un utilisateur spécifique)


>Les points de terminaison API et les méthodes HTTP réels peuvent varier en fonction de la conception et des conventions de votre application ou API. De plus, s'assurer toujours que les mécanismes d'authentification et d'autorisation appropriés sont en place pour protéger les données sensibles et empêcher tout accès non autorisé aux opérations CRUD.