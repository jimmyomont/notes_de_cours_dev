# Modèle Logique de Données (MLD) 
## Le Modèle Logique de Données est une représentation plus détaillée du MCD, qui décrit la structure des données de manière formelle, en utilisant des symboles et des règles de notation standardisés. Le MLD est utilisé pour les caractéristiques, les attributs, les relations et les contraintes associées aux données de manière précise. Il est généralement indépendant de tout système de gestion de base de données particulier.

### Exemple de Modèle Logique de Données (MLD) pour le projet de site internet de vente de vêtements :

### Utilisateur (ID_Utilisateur, Nom, Prenom, Email, MotDePasse, AdresseLivraison, AdresseFacturation)

- ID_Utilisateur : identifiant unique de l'utilisateur (clé primaire)
- Nom : nom de l'utilisateur
- Prénom : prénom de l'utilisateur
- Email : adresse e-mail de l'utilisateur
- MotDePasse : mot de passe de l'utilisateur
- AdresseLivraison : adresse de livraison de l'utilisateur
- AdresseFacturation : adresse de facturation de l'utilisateur
### Produit (ID_Produit, Nom, Description, Prix, Taille, Couleur, QuantiteStock)

- ID_Produit : identifiant unique du produit (clé primaire)
- Nom : nom du produit
- Description : description du produit
- Prix ​​: prix du produit
- Taille : taille du produit
- Couleur : couleur du produit
- QuantiteStock : quantité de stock du produit
### Commande (ID_Commande, DateCommande, MontantTotal, StatutCommande, ID_Utilisateur, AdresseLivraison, AdresseFacturation)

- ID_Commande : identifiant unique de la commande (clé primaire)
- DateCommande : date de la commande
- MontantTotal : montant total de la commande
- StatutCommande : statut de la commande (en attente, en cours de traitement, expédiée, livrée, annulée)
- ID_Utilisateur : identifiant de l'utilisateur ayant passé la commande (clé étrangère)
- AdresseLivraison : adresse de livraison de la commande
- AdresseFacturation : adresse de facturation de la commande
### ProduitCommande (ID_Produit, ID_Commande, Quantite)

- ID_Produit : identifiant du produit (clé étrangère)
- ID_Commande : identifiant de la commande (clé étrangère)
- Quantite : quantité commandée du produit
### atégorie (ID_Categorie, Nom, Description)

- ID_Categorie : identifiant unique de la catégorie (clé primaire)
- Nom : nom de la catégorie
- Description : description de la catégorie
### ProduitCategorie (ID_Produit, ID_Categorie)

- ID_Produit : identifiant du produit (clé étrangère)
- ID_Categorie : identifiant de la catégorie (clé étrangère)
### Marque (ID_Marque, Nom, Description)

- ID_Marque : identifiant unique de la marque (clé primaire)
- Nom : nom de la marque
- Description : description de la marque
### ProduitMarque (ID_Produit, ID_Marque)

- ID_Produit : identifiant du produit (clé étrangère)
- ID_Marque : identifiant de la marque (clé étrangère)

---
Dans ce MLD, chaque entité est représentée par une table et chaque attribut est représenté par une colonne dans la table. Les relations entre les entités sont représentées par des clés étrangères qui permettent de lier les tables entre elles. Par exemple, la table ProduitCommande permet de faire le lien entre les tables Produit et Commande grâce