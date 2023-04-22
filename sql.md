# SQL



```sql 
SELECT * FROM  "table_name"
-- Selectionne toutes les colonnes qui se trouvent dans la table "table_name"
```


## CRUD 

- ### CREATE (creer)
```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

- ### READ (lire)
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE condition
```

- ### UPLOAD (modifier)
```sql
UPDATE table_name
SET column1 = new_value1, column2 = new_value2, ...
WHERE condition;
```

- ### DELETE (supprimer)
```sql
DELETE FROM table_name
WHERE condition;
```
---
## Condition

### Opérateurs de comparaison : 
les opérateurs de comparaison sont utilisés pour comparer des valeurs dans SQL

- ``=:`` égal à
- ``<>ou !=``: différent de
- ``<``: moins que
- ``>``: plus grand que
- ``<=``: inférieur ou égal à
- ``>=``: Plus grand ou égal à

Exemple : 
```sql
SELECT *
FROM user
WHERE age >= 18;
-- Affiche tout les "user" dont la valeur de "age" est inferieure ou égale à "18"
```

### Opérateurs logiques : 
les opérateurs logiques sont utilisés pour combiner plusieurs conditions dans SQL
- ``AND``: renvoie vrai si les deux conditions sont vraies
- ``OR``: renvoie vrai si l'une des conditions est vraie
- ``NOT``: annule une condition (renvoie vrai si la condition est fausse)

Exemple : 
```sql
SELECT *
FROM user
WHERE (age >= 18 AND age <= 25 ) OR age = 30;
-- Affiche tout les "user" ayant entre 18 et 25 ans ou 30 ans
```

### Opérateur IN :
L'opérateur ``IN`` est utilisé pour vérifier si une valeur existe dans une liste de valeurs.

Exemple : 
```sql
SELECT *
FROM user
WHERE pays IN ('USA', 'Canada', 'France');
-- Affiche tout les user dont le "pays" est égale à "USA", à "Canada" et à "France"
```

### Opérateur LIKE : 
L'opérateur ``LIKE`` est utilisé pour faire correspondre des modèles dans SQL. 

Le signe de pourcentage (%) est utilisé comme caractère générique.

Exemple : 
```sql
SELECT *
FROM user
WHERE prénom LIKE 'S%';
-- Affiche tout les "user" dont le "prénom commence par un "S" "
```

### Valeurs NULL : 
les valeurs ``NULL`` sont des valeurs spéciales qui indiquent l'absence d'une valeur. 

Vous pouvez vérifier les valeurs ``NULL`` à l'aide des opérateurs ``IS NULL`` et ``IS NOT NULL``.

Exemple : 
```sql
SELECT *
FROM user
WHERE téléphone IS NULL;
-- Affiche tout les "user" dont la valeur "téléphone" est vide ("NUL")
```
---
## SELECT 

### ALIAS : 
``AS`` permet d'attribuer un autre nom à une colonne dans une requête SQL.

Exemple : 
```sql 
SELECT email AS "Adresse mail"
FROM user;
-- Modifie le nom de la colonne 'email' par "Adresse mail"
```

### TRI :
``ORDER BY`` permet de trier dans l'orde ascendant en précisant avec ``ASC`` ou descendant avec ``DESC`` (par defaut l'ordre est ascendant)

Exemple 1 : 
```sql
SELECT *
FROM "user"
ORDER BY "nom" DESC;
-- Affiche toute la table par ordre descendant  de la liste des noms
```

Exemple 2 : 

```sql
SELECT *
FROM "user"
ORDER BY "nom" DESC, "age" ASC;
-- Avec plusieurs critères , si plusieurs même nom sont trouvés , la liste sera affiché dans un premier temps orde ``DESC`` pour les noms
-- et ensuite par ``ASC`` par les ages pour les mêmes noms
```

### LIMIT
Limiter le nombre de reusltats avec ``LIMIT`` et décaller le point de depart avec ``OFFSET``

Exemple : 

```sql
SELECT *
FROM "user"
LIMIT 2 OFFSET 4
-- Affiche 2 "user" à partir de la deuxième ligne
```

