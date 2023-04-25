# Modèle Physique de Données (MPD)
## Le Modèle Physique de Données est une représentation encore plus détaillée du MLD, qui commente spécifiquement les données sont capables physiquement dans une base de données. Le MPD décrit les tables, les colonnes, les index, les clés, les contraintes et autres détails liés à la mise en œuvre physique des données.

### Exemple de Modèle Physique de Données (MPD) pour le projet de site internet de vente de vêtements :

### Tableau Utilisateur

```
ID_Utilisateur INT NON NULL CLE PRIMAIRE
Nom VARCHAR(50) NOT NULL
Prénom VARCHAR(50) NOT NULL
Email VARCHAR(255) NOT NULL UNIQUE
MotDePasse VARCHAR(255) NOT NULL
AdresseLivraison VARCHAR(255) NOT NULL
AdresseFacturation VARCHAR(255) NOT NULL
Tableau Produit


ID_Produit INT NOT NULL CLÉ PRIMAIRE
Nom VARCHAR(100) NON NULL
Description TEXTE NON NULL
Prix ​​DECIMAL(10,2) NOT NULL
Taille VARCHAR(10) NOT NULL
Couleur VARCHAR(50) NOT NULL
QuantiteStock INT NOT NULL
Tableau Commande

ID_Commande INT NOT NULL CLÉ PRIMAIRE
DateCommande DATE NON NULLE
MontantTotal DECIMAL(10,2) NOT NULL
StatutCommande VARCHAR(50) NOT NULL
ID_Utilisateur INT NOT NULL
AdresseLivraison VARCHAR(255) NOT NULL
AdresseFacturation VARCHAR(255) NOT NULL
CLÉ ÉTRANGÈRE (ID_Utilisateur) RÉFÉRENCES Utilisateur(ID_Utilisateur)
Tableau ProduitCommande

ID_Produit INT NOT NULL
ID_Commande INT NOT NULL
Quantite INT NOT NULL
CLE PRIMAIRE (ID_Produit, ID_Commande)
CLÉ ÉTRANGÈRE (ID_Produit) RÉFÉRENCES Produit(ID_Produit)
CLÉ ÉTRANGÈRE (ID_Commande) RÉFÉRENCES Commande(ID_Commande)
Catégorie de tableau

ID_Categorie INT NOT NULL CLÉ PRIMAIRE
Nom VARCHAR(100) NON NULL
Description TEXTE NON NULL
Tableau ProduitCatégorie

ID_Produit INT NOT NULL
ID_Categorie INT NOT NULL
CLÉ PRIMAIRE (ID_Produit, ID_Catégorie)
CLÉ ÉTRANGÈRE (ID_Produit) RÉFÉRENCES Produit(ID_Produit)
CLÉ ÉTRANGÈRE (ID_Categorie) RÉFÉRENCES Catégorie(ID_Categorie)
Marque de table

ID_Marque INT NOT NULL CLÉ PRIMAIRE
Nom VARCHAR(100) NON NULL
Description TEXTE NON NULL
Table ProduitMarque

ID_Produit INT NOT NULL
ID_Marque INT NOT NULL
CLÉ PRIMAIRE (ID_Produit, ID_Marque)
CLÉ ÉTRANGÈRE (ID_Produit) RÉFÉRENCES Produit(ID_Produit)
CLÉ ÉTRANGÈRE (ID_Marque) RÉFÉRENCES Marque(ID_Marque)
```

---
Dans ce MPD, les entités sont représentées par des tables et les attributs sont représentés par des colonnes dans les tables. Les contraintes de clé primaire, de clé étrangère et d'unicité sont ajoutées pour garantir l'intégrité des données. Les types de données sont également précisés pour chaque attribut. Par exemple, l'attribut Prix dans la table Produit est de type DECIMAL(10,2), ce qui signifie qu'il peut contenir un nombre décimal avec 10 au total dont 2 chiffres après la virgule.

---
```sql
CREATE TABLE Utilisateur (
    ID_Utilisateur INT NOT NULL AUTO_INCREMENT,
    Nom VARCHAR(50) NOT NULL,
    Prenom VARCHAR(50) NOT NULL,
    Email VARCHAR(100) NOT NULL,
    MotDePasse VARCHAR(50) NOT NULL,
    AdresseLivraison VARCHAR(100) NOT NULL,
    AdresseFacturation VARCHAR(100) NOT NULL,
    PRIMARY KEY (ID_Utilisateur)
);

CREATE TABLE Produit (
    ID_Produit INT NOT NULL AUTO_INCREMENT,
    Nom VARCHAR(100) NOT NULL,
    Description TEXT,
    Prix DECIMAL(10, 2) NOT NULL,
    Taille VARCHAR(10) NOT NULL,
    Couleur VARCHAR(50) NOT NULL,
    QuantiteStock INT NOT NULL,
    PRIMARY KEY (ID_Produit)
);

CREATE TABLE Commande (
    ID_Commande INT NOT NULL AUTO_INCREMENT,
    DateCommande DATE NOT NULL,
    MontantTotal DECIMAL(10, 2) NOT NULL,
    StatutCommande VARCHAR(50) NOT NULL,
    ID_Utilisateur INT NOT NULL,
    AdresseLivraison VARCHAR(100) NOT NULL,
    AdresseFacturation VARCHAR(100) NOT NULL,
    PRIMARY KEY (ID_Commande),
    FOREIGN KEY (ID_Utilisateur) REFERENCES Utilisateur(ID_Utilisateur)
);

CREATE TABLE ProduitCommande (
    ID_Produit INT NOT NULL,
    ID_Commande INT NOT NULL,
    Quantite INT NOT NULL,
    PRIMARY KEY (ID_Produit, ID_Commande),
    FOREIGN KEY (ID_Produit) REFERENCES Produit(ID_Produit),
    FOREIGN KEY (ID_Commande) REFERENCES Commande(ID_Commande)
);

CREATE TABLE Categorie (
    ID_Categorie INT NOT NULL AUTO_INCREMENT,
    Nom VARCHAR(50) NOT NULL,
    Description TEXT,
    PRIMARY KEY (ID_Categorie)
);

CREATE TABLE ProduitCategorie (
    ID_Produit INT NOT NULL,
    ID_Categorie INT NOT NULL,
    PRIMARY KEY (ID_Produit, ID_Categorie),
    FOREIGN KEY (ID_Produit) REFERENCES Produit(ID_Produit),
    FOREIGN KEY (ID_Categorie) REFERENCES Categorie(ID_Categorie)
);

CREATE TABLE Marque (
    ID_Marque INT NOT NULL AUTO_INCREMENT,
    Nom VARCHAR(50) NOT NULL,
    Description TEXT,
    PRIMARY KEY (ID_Marque)
);

CREATE TABLE ProduitMarque (
    ID_Produit INT NOT NULL,
    ID_Marque INT NOT NULL,
    PRIMARY KEY (ID_Produit, ID_Marque),
    FOREIGN KEY (ID_Produit) REFERENCES Produit(ID_Produit),
    FOREIGN KEY (ID_Marque) REFERENCES Marque(ID_Marque)
);
```