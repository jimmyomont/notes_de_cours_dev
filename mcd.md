# Modèle Conceptuel de Données (MCD) 

## Le Modèle Conceptuel de Données est utilisé pour modéliser les données du monde réel de manière abstraite. Il s'agit d'un modèle de haut niveau qui décrit les concepts, les relations et les contraintes associées aux données. L'objectif principal du MCD est de fournir une vue globale des données à partir desquelles un modèle plus détaillé peut être intégré.

### Exemple de MCD sur un projet de creation de site

### Le projet consiste à créer un site de vente en ligne de vêtements pour hommes et femmes. Voici les principales entités diffusées dans le MCD :

- Utilisateur : représente les utilisateurs du site internet. Cette entité comprend les attributs suivants : (ID), nom, prénom, adresse e-mail, mot de passe, adresse de livraison et adresse de facturation.

- Produit : représente les vêtements proposés à la vente sur le site internet. Cette entité identifiant comprend les attributs suivants : (ID), nom, description, prix, taille, couleur et quantité en stock.

- Commande : représente les commandes passées par les utilisateurs du site internet. Cette entité comprend les attributs suivants : identifiant (ID), date de commande, montant total, statut de la commande (en attente, en cours de traitement, expédiée, livrée, annulée), adresse de livraison et adresse de facturation.

- Panier : représente le panier d'achat de l'utilisateur. Cette entité comprend les attributs suivants : date de création, produits ajoutés au panier, quantité pour chaque produit et montant total.

- Catégorie : représente les catégories de vêtements proposées sur le site internet. Cette entité identifiant comprend les attributs suivants : (ID), nom et description.

- Marque : représente les marques des vêtements proposés sur le site internet. Cette entité identifiant comprend les attributs suivants : (ID), nom et description.

### Le MCD permet de visualiser les différentes entités du projet ainsi que leurs relations. Dans cet exemple, les relations peuvent être les suivantes :

- Un utilisateur peut passer une ou plusieurs commandes.
- Un produit peut être ajouté à un panier.
- Un panier peut contenir un ou plusieurs produits.
- Un produit peut appartenir à une ou plusieurs catégories.
- Un produit peut être associé à une marque.

```
Entité Utilisateur :

ID_Utilisateur (clé primaire)
Nom
Prénom
E-mail
Mot de passe
Adresse de livraison
Adresse de facturation

Entité Produit :

ID_Produit (clé primaire)
Nom
Description
prix
Taille
Couleur
Quantité en stock

Entité Commande :

ID_Commande (clé primaire)
Date de commande
Montant total
Statut de la commande
ID_Utilisateur (clé étrangère vers Utilisateur)
Adresse de livraison
Adresse de facturation

Entité ProduitCommande :

ID_Produit (clé étrangère vers Produit)
ID_Commande (clé étrangère vers Commande)
Quantité

Entité Catégorie :

ID_Catégorie (clé primaire)
Nom
Description

Entité ProduitCatégorie :

ID_Produit (clé étrangère vers Produit)
ID_Catégorie (clé étrangère vers Catégorie)

Entité Marque :

ID_Marque (clé primaire)
Nom
Description

Entité ProduitMarque :

ID_Produit (clé étrangère vers Produit)
ID_Marque (clé étrangère vers Marque)
```
---
En résumé, le MCD est une vue globale et abstraite des données, le MLD est une représentation formelle et détaillée de la structure des données, et le MPD est une représentation encore plus détaillée de la mise en œuvre physique des données. Ces modèles sont souvent utilisés dans le cadre de la conception de bases de données et de systèmes d'information pour assurer l'efficacité, la stabilité et la qualité des données diffusées.