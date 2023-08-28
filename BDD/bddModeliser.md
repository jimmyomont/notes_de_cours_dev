# MODELMISER UNE BASE DE DONNEES RELATIONNELLE

### 1- Identifier les entités principales de votre système.

Une entité représente un objet du monde réel, comme un client, un produit ou une commande.

### 2 - Identifier les attributs de chaque entité.

Les attributs privilégiés les caractéristiques des entités, comme le nom, l'âge, l'adresse pour un client, ou le nom, la description et le prix pour un produit.

### 3 - Identifier les clés primaires de chaque entité.

Une clé primaire est un attribut unique qui identifie de manière univoque chaque enregistrement de l'entité. Par exemple, l'ID du client peut être une clé primaire.

### 4 - Identifier les relations entre les entités.

Les relations délicates les liens entre différentes entités. Par exemple, une commande est liée à un client, et une commande peut contenir plusieurs produits.

### 5 - Identifier les cardinalités des relations.

Les cardinalités généreuses le nombre d'entités avec une entité est associée via une relation. Par exemple, un client peut passer zéro ou plusieurs commandes, tandis qu'une commande est liée exactement à un client.

### 6 - Créer un schéma entité-association.

Dessiner un diagramme représentant toutes les entités, les attributs, les clés primaires et les relations avec leurs cardinalités.

### 7 - Convertir le schéma ERM en modèle de base de données relationnelle.

Transformer chaque entité en une table de base de données, chaque attribut en colonne, et chaque relation en clé étrangère.

### 8 - Normalisation de la base de données.

Appliquer les règles de normalisation pour éliminer les redondances et les anomalies de mise à jour.

### 9 - Implémentation du modèle.

Utiliser un système de gestion de base de données (SGBD) pour créer les tables, définir les contraintes d'intégrité et interroger les données.

### 10 - Entretien et amélioration.

Surveiller les performances de la base de données, effectuer des sauvegardes régulières et optimiser la structure en fonction des besoins du système.

>la modélisation d'une base de données est un processus itératif, et qu'elle peut évaluer avec l'évolution des besoins de votre application. Assurer-vous de bien comprendre les spécifications et les exigences du système avant de commencer la conception de la base de données.

## Exemple par étapes 

### Étape 1 :

#### Identifier les entités principales

Entités : 

- Livre, Auteur, Emprunteur

### Étape 2 : 

#### Identifiez les attributs de chaque entité

Livre : 

- ISBN (clé primaire), titre, genre, année de publication

Auteur : 

- ID (clé primaire), nom, date de naissance, nationalité

Emprunteur : 
- ID (clé primaire), nom, adresse, adresse e-mail

### Étape 3 : 
### Identifier les clés primaires de chaque entité

Pour chaque entité, la clé primaire est indiquée entre parenthèses.

### Étape 4 : 
#### Identifier les relations entre les entités

Un livre peut avoir plusieurs auteurs.

Un livre peut être emprunté par plusieurs emprunteurs.

### Étape 5 : 
#### Identifier les cardinalités des relations

Livre-Auteur : 
- Un livre peut avoir un ou plusieurs auteurs. Un auteur peut avoir écrit un ou plusieurs livres.
Livre-Emprunteur : 
- Un livre peut être emprunté par zéro ou plusieurs emprunteurs. Un emprunteur peut emprunter zéro ou plusieurs livres.

### Étape 6 : 
#### Créer un schéma entité-association (diagramme ERM)

```scss
+----------------+      +-------------------+      +---------------+
|    Livre       |      |    Auteur         |      |  Emprunteur   |
+----------------+      +-------------------+      +---------------+
| ISBN (PK)      |      | ID (PK)           |      | ID (PK)       |
| Titre          |      | Nom               |      | Nom           |
| Genre          |      | Date de naissance |      | Adresse       |
| Année Pub.     |      | Nationalité       |      | Adresse Email |
+----------------+      +-------------------+      +---------------+
      |                       |                         |
      |                       |                         |
      |                       |                         |
      |                       |                         |
      |                       |                         |
      |                       |                         |
+-------------------+   +-------------------+   +------------------+
|  Livre_Auteur     |   |  Livre_Emprunteur |   | Auteur_Emprunteur|
+-------------------+   +-------------------+   +------------------+
| ID_Livre (FK)     |   | ID_Livre (FK)     |   | ID_Auteur (FK)   |
| ID_Auteur (FK)    |   | ID_Emprunteur (FK)|   | ID_Emprunteur(FK)|
+-------------------+   +-------------------+   +------------------+

```

### Étape 7 : 
#### Convertir le schéma ERM en modèle de base de données relationnelle

Tableau Livre :
```sql
CREATE TABLE Livre (
    ISBN INT PRIMARY KEY,
    Titre VARCHAR(255),
    Genre VARCHAR(100),
    AnneePublication INT
);

```
Auteur du tableau :
```sql
CREATE TABLE Auteur (
    ID INT PRIMARY KEY,
    Nom VARCHAR(100),
    DateNaissance DATE,
    Nationalite VARCHAR(100)
);

```
Table Emprunteur :
```sql
CREATE TABLE Emprunteur (
    ID INT PRIMARY KEY,
    Nom VARCHAR(100),
    Adresse VARCHAR(200),
    AdresseEmail VARCHAR(100)
);
```

Tableau Livre_Auteur :
```sql
CREATE TABLE Livre_Auteur (
    ID_Livre INT,
    ID_Auteur INT,
    PRIMARY KEY (ID_Livre, ID_Auteur),
    FOREIGN KEY (ID_Livre) REFERENCES Livre(ISBN),
    FOREIGN KEY (ID_Auteur) REFERENCES Auteur(ID)
);

```
Table Livre_Emprunteur :
```sql
CREATE TABLE Livre_Emprunteur (
    ID_Livre INT,
    ID_Emprunteur INT,
    DateEmprunt DATE,
    PRIMARY KEY (ID_Livre, ID_Emprunteur),
    FOREIGN KEY (ID_Livre) REFERENCES Livre(ISBN),
    FOREIGN KEY (ID_Emprunteur) REFERENCES Emprunteur(ID)
);

```
Tableau Auteur_Emprunteur :
```sql
CREATE TABLE Auteur_Emprunteur (
    ID_Auteur INT,
    ID_Emprunteur INT,
    PRIMARY KEY (ID_Auteur, ID_Emprunteur),
    FOREIGN KEY (ID_Auteur) REFERENCES Auteur(ID),
    FOREIGN KEY (ID_Emprunteur) REFERENCES Emprunteur(ID)
);

```
>Cet exemple montre comment modéliser les entités, les attributs, les clés primaires et les relations dans une base de données relationnelle à l'aide du langage ERM et comment traduire cela en instructions SQL pour créer les tables de la base de données.