# CLAUSES DE REQUETES SQL

## SELECT :
 Sélectionnez les colonnes requises dans la requête.

## FROM :
 Indique la table à partir de laquelle récupère les données.

## WHERE :
 Filtre les résultats en fonction d'une condition désignée.

## GROUP BY :
 Regroupe les résultats en fonction d'une ou plusieurs colonnes.

## AYANT :
 Filtre les résultats regroupés en fonction d'une condition désignée.

## ORDER BY :
 Trie les résultats en fonction d'une ou plusieurs colonnes.

## JOIN :
 Combine les lignes de deux ou plusieurs tables en fonction d'une condition de jointure.

## INNER JOIN :
 Retourne uniquement les lignes qui ont une correspondance dans les deux tables.

## LEFT JOIN (ou LEFT OUTER JOIN) :
 Retourne toutes les lignes de la table de gauche et les lignes correspondantes de la table de droite.

## RIGHT JOIN (ou RIGHT OUTER JOIN) :
 Retourne toutes les lignes de la table de droite et les lignes correspondantes de la table de gauche.

## FULL JOIN (ou FULL OUTER JOIN) :
 Retourne toutes les lignes des deux tables, avec correspondance s'il y a et NULL sinon.

## UNION :
 Combinez les résultats de deux ou plusieurs requêtes en un seul ensemble de résultats.

## INSERT INTO :
 Insère de nouvelles lignes dans une table.

## UPDATE :
 Met à jour les enregistrements existants dans une table.

## DELETE FROM :
 Supprime les enregistrements d'une table.

## LIMIT :
 Limite le nombre de résultats renvoyés par la requête.

## OFFSET :
 Indique le nombre de lignes à ignorer lors de l'utilisation de LIMIT.

## DISTINCT :
 Renvoie uniquement les valeurs uniques des colonnes désignées.

## AS :
 Renommez une colonne ou une table dans le résultat de la requête à l'aide d'un alias.

## IN :
 Vérifier si une valeur est présente dans un ensemble de valeurs spécifiées.

## NOT IN :
 Vérifiez si une valeur n'est pas présente dans un ensemble de valeurs spécifié.

## EXISTE :
 Vérifiez si une sous-requête renvoie des résultats.

## NOT EXISTS :
 Vérifiez si une sous-requête ne renvoie pas de résultats.

## ENTRE :
 Vérifiez si une valeur se situe entre deux valeurs désignées.

## LIKE :
 Recherche des valeurs correspondant à un modèle spécifié.

## CAS :
 Effectue une évaluation conditionnelle dans une requête.

## COUNT :
 Compte le nombre de lignes ou de valeurs dans une colonne.

## SUM :
 Calcule la somme des valeurs dans une colonne.

## AVG :
 Calcule la moyenne des valeurs dans une colonne.

## MAX :
 Renvoie la valeur maximale d'une colonne.

## MIN :
 Renvoie la valeur minimale d'une colonne.

 ----

 ### Exemple

 ```sql
 -- Création d'une table pour stocker des informations sur des produits
CREATE TABLE Produits (
    id INTEGER PRIMARY KEY,       -- Clé primaire, identifiant unique du produit
    nom VARCHAR(100),             -- Nom du produit (chaîne de caractères jusqu'à 100 caractères)
    prix FLOAT,                   -- Prix du produit (nombre décimal)
    categorie VARCHAR(50)         -- Catégorie du produit (chaîne de caractères jusqu'à 50 caractères)
);

-- Insertion de données dans la table Produits
INSERT INTO Produits (id, nom, prix, categorie)
VALUES (1, 'Ordinateur portable', 1200.50, 'Informatique');

INSERT INTO Produits (id, nom, prix, categorie)
VALUES (2, 'Smartphone', 800.75, 'Téléphonie');

INSERT INTO Produits (id, nom, prix, categorie)
VALUES (3, 'Casque sans fil', 99.99, 'Audio');

-- Sélection des produits dont le prix est supérieur à 100, triés par prix décroissant
SELECT id, nom, prix, categorie
FROM Produits
WHERE prix > 100
ORDER BY prix DESC;

-- Mise à jour du prix du produit avec l'id 3
UPDATE Produits SET prix = 109.99 WHERE id = 3;

-- Suppression du produit avec l'id 2
DELETE FROM Produits WHERE id = 2;

-- Utilisation de la clause BETWEEN pour sélectionner les produits dont le prix est compris entre 50 et 200
SELECT id, nom, prix, categorie
FROM Produits
WHERE prix BETWEEN 50 AND 200;

-- Utilisation de la clause LIKE pour sélectionner les produits dont le nom contient "casque"
SELECT id, nom, prix, categorie
FROM Produits
WHERE nom LIKE '%casque%';

-- Utilisation de la clause GROUP BY pour regrouper les produits par catégorie et calculer le prix moyen dans chaque catégorie
SELECT categorie, AVG(prix) AS prix_moyen
FROM Produits
GROUP BY categorie;

-- Utilisation de la clause HAVING pour filtrer les catégories ayant un prix moyen supérieur à 100
SELECT categorie, AVG(prix) AS prix_moyen
FROM Produits
GROUP BY categorie
HAVING AVG(prix) > 100;

-- Utilisation de la clause INNER JOIN pour joindre la table Produits avec une autre table Categories
-- afin d'obtenir les produits avec leur catégorie correspondante
SELECT p.id, p.nom, p.prix, c.nom AS categorie
FROM Produits p
INNER JOIN Categories c ON p.categorie_id = c.id;

-- Utilisation de la clause LEFT JOIN pour obtenir tous les produits, même ceux sans catégorie correspondante
SELECT p.id, p.nom, p.prix, c.nom AS categorie
FROM Produits p
LEFT JOIN Categories c ON p.categorie_id = c.id;

-- Utilisation de la clause UNION pour combiner les résultats de deux requêtes SELECT en un seul résultat
SELECT id, nom, prix, categorie
FROM Produits
WHERE prix > 100
UNION
SELECT id, nom, prix, categorie
FROM Produits
WHERE categorie = 'Audio';

-- Utilisation de la clause IN pour sélectionner les produits de certaines catégories spécifiées
SELECT id, nom, prix, categorie
FROM Produits
WHERE categorie IN ('Informatique', 'Téléphonie');

-- Utilisation de la clause LIMIT pour limiter le nombre de résultats renvoyés
SELECT id, nom, prix, categorie
FROM Produits
ORDER BY prix DESC
LIMIT 5;

-- Utilisation de la clause DISTINCT pour éliminer les doublons et renvoyer uniquement les catégories distinctes
SELECT DISTINCT categorie
FROM Produits;

 ```