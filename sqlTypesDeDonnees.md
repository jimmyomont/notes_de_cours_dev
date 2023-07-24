# LES TYPES DE DONNEES 

## INTEGER (ENTIER) : 
Nombre entier sans virgule, qui peut être positif, négatif ou nul. Par exemple, 10, -25, 0.

## FLOAT (VIRGULE FLOTTANTE) : 
Nombre décimal avec une précision à virgule flottante. Par exemple, 3.14, -0.75, 1.618.

## CHAR (CARACTÈRE) : 
Chaîne de caractères de longueur fixe. La longueur est appropriée lors de la création de la colonne.

 Par exemple, 'Bonjour', 'A', 'XYZ'.

## VARCHAR (CARACTÈRES VARIABLES) : 
Chaîne de caractères de longueur variable. La longueur est indiquée lors de la création de la colonne, mais peut varier en fonction des données. 

Par exemple, 'Données', 'SQL'.

## DATE (DATE) : 
Date au format 'AAAA-MM-JJ'. 

Par exemple, '2023-07-24'.

## TIME (HEURE) : 

Heure au format 'HH:MM:SS'. 

Par exemple, '12:30:45'.

## DATETIME (DATE ET HEURE) : 
Combinaison de date et d'heure au format 'AAAA-MM-JJ HH:MM:SS'. 

Par exemple, '2023-07-24 12:30:45'.

## BOOLEAN (BOOLÉEN) : 
Type de donnée logique pouvant avoir deux valeurs : VRAI (true) ou FAUX (false).

## DECIMAL (DÉCIMAL) : 
Nombre décimal précis avec une échelle et une précision désignées. 

Par exemple, 12.345, -987.65.

## BLOB (BLOB) : 

Champ binaire pour stocker de gros volumes de données binaires, comme des images ou des fichiers.

## TEXT (TEXTE) : 
Champ de texte pour stocker de grandes quantités de texte.

## ENUM (ÉNUMÉRATION) : 
Type spécial qui permet de définir une liste de valeurs possibles pour une colonne. Les valeurs autorisées sont définies lors de la création de la colonne.

----

### Exemple 
```sql
-- Création d'une table pour stocker des informations sur des utilisateurs
CREATE TABLE Utilisateurs (
    id INTEGER PRIMARY KEY,       -- Clé primaire, identifiant unique de l'utilisateur
    nom VARCHAR(50),              -- Nom de l'utilisateur (chaîne de caractères jusqu'à 50 caractères)
    age INTEGER,                  -- Âge de l'utilisateur (nombre entier)
    date_inscription DATE,        -- Date d'inscription de l'utilisateur (format 'AAAA-MM-JJ')
    est_actif BOOLEAN             -- Indique si l'utilisateur est actif (VRAI ou FAUX)
);

-- Insertion de données dans la table Utilisateurs
INSERT INTO Utilisateurs (id, nom, age, date_inscription, est_actif)
VALUES (1, 'Jean Dupont', 30, '1993-05-15', TRUE);   -- Insertion d'un utilisateur actif

INSERT INTO Utilisateurs (id, nom, age, date_inscription, est_actif)
VALUES (2, 'Marie Martin', 25, '1998-11-02', TRUE);  -- Insertion d'un autre utilisateur actif

INSERT INTO Utilisateurs (id, nom, age, date_inscription, est_actif)
VALUES (3, 'Paul Durand', 22, '2001-09-10', FALSE);  -- Insertion d'un utilisateur inactif

-- Sélection de tous les utilisateurs actifs
SELECT * FROM Utilisateurs WHERE est_actif = TRUE;

-- Mise à jour de l'âge de l'utilisateur avec l'id 1
UPDATE Utilisateurs SET age = 31 WHERE id = 1;

-- Suppression de l'utilisateur avec l'id 3
DELETE FROM Utilisateurs WHERE id = 3;
```