# REST (Representational State Transfer) 

Style architectural utilisé dans la conception d'applications en réseau. Voici une feuille de triche de l'API REST de base pour vous aider à démarrer :

## 1. Méthodes HTTP (verbes) :

- GET : Récupère une ressource ou une liste de ressources.
- POST : créer une nouvelle ressource.
- PUT : mettre à jour une ressource existante ou en créer une nouvelle si elle n'existe pas.
- PATCH : mise à jour partielle d'une ressource existante.
- SUPPRIMER : supprimer une ressource.

## 2. Codes d'état HTTP :

- 200 OK : requête réussie.
- 201 Créé : ressource créée avec succès.
- 204 Aucun contenu : requête réussie, aucune donnée à renvoyer.
- 400 Bad Request : Requête ou paramètres de requête non valides.
- 404 Introuvable : la ressource demandée est introuvable (par exemple, ID utilisateur ou ID produit non valide).

---

## Exemples de requêtes 

### Requête GET (Récupérer une ressource ou une liste de ressources) :

- Récupérez une liste de tous les utilisateurs :GET /api/users
- Récupérer un utilisateur spécifique par ID :GET /api/users/{user_id}
- Récupérer une liste de produits :GET /api/products
- Récupérer un produit spécifique par ID :GET /api/products/{product_id}

### Requête POST (Créer une nouvelle ressource) :
- Créez un nouvel utilisateur : POST /api/users
- Corps de la requête :{ "name": "John Doe", "email": "john@example.com", "age": 30 }
- Créer un nouveau produit : POST /api/products
- Corps de la requête :{ "name": "Widget", "price": 19.99, "category": "Electronics" }

### Requête PUT (Mettre à jour une ressource existante ou en créer une nouvelle si elle n'existe pas) :
- ettre à jour un utilisateur existant : PUT /api/users/{user_id}
- Corps de la demande :{ "name": "Jane Smith", "email": "jane@example.com", "age": 35 }
- Créer ou mettre à jour un produit : PUT /api/products/{product_id}
- Corps de la demande :{ "name": "Updated Widget", "price": 24.99, "category": "Electronics" }

### Requête PATCH (mise à jour partielle d'une ressource existante) :
- Mettre à jour partiellement les détails d'un utilisateur : PATCH /api/users/{user_id}
- Corps de la requête :{ "age": 31 }

### Requête DELETE (Supprimer une ressource) :
- Supprimer un utilisateur :DELETE /api/users/{user_id}
- Supprimer un produit :DELETE /api/products/{product_id}