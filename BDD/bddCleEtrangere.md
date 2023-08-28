# CLE ETRANGERE

### 1 - **Base de données étrangère** : 

Une base de données étrangère est une base de données qui est référencée par une autre base de données (base de données principale) pour établir des relations entre les tables.

### 2 - **Clé primaire (Primary Key)** :

Une clé primaire est un attribut (ou un ensemble d'attributs) qui identifie de manière unique chaque enregistrement dans une table.
Elle garantit l'unicité des valeurs et empêche les doublons.
Dans une table, il ne peut y avoir qu'une seule clé primaire.

### 3 - **Clé étrangère (Foreign Key)** :

Une clé étrangère est un attribut dans une table qui établit une relation avec la clé primaire d'une autre table.
Elle permet d'établir des liaisons entre les enregistrements de différentes tables.
Habituellement, la clé étrangère dans une table est liée à la clé primaire d'une autre table.

### 4 - **Contrainte de clé étrangère** :

C'est une règle qui définit la relation entre la clé étrangère et la clé primaire.
Elle garantit également que les valeurs de la clé étrangère existent dans la table de la clé primaire ou qu'elles sont nulles (si autorisées).

### 5 - **Jointure (Rejoindre)** :

Une opération de jointure est utilisée pour combiner l'enregistrement de deux tables (ou plus) en fonction de la valeur de la clé étrangère et primaire.
Les types de joints courants sont : INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN.

### 6 - **Cascade de suppression (Cascade Delete)** :

Lorsqu'une relation parent-enfant est établie entre deux tables à l'aide de clés étrangères, la cascade de suppression spécifique que la suppression d'un enregistrement dans la table parent entraîne automatiquement la suppression de tous les enregistrés liés dans la table enfant.

### 5 - **Cascade de mise à jour (Cascade Update)** :

Lorsqu'une relation parent-enfant est établie entre deux tables à l'aide de clés étrangères, la cascade de mise à jour spécifique que la mise à jour de la valeur de la clé primaire dans la table parente sera automatiquement reflétée dans les relevés liés de la table enfant.

### 8 - **Indice** :

Un index est une structure de données utilisées pour accélérer la recherche d'enregistrements dans une table.
Il améliore les performances de la recherche en acceptant une liste triée des valeurs de colonnes spécifiques.

### 9 - **Transactions** :

Une transaction est une séquence d'opérations qui se déroulent comme une unité indivisible.
Les transactions tiennent compte de l'intégrité des données et garantissent que toutes les opérations sont effectuées de manière cohérente et fiable.

### 10 - **Sous-requêtes (Sous-requêtes)** :

Une sous-requête est une requête imbriquée dans une autre requête.
Elle est utilisée pour effectuer des opérations plus complexes, en utilisant les résultats d'une requête comme condition pour une autre.

## Exemple :


Supposons que nous ayons deux tables principales dans notre base de données :

### 1 - **Tableau "Livres"** :
colonnes : 

ID_livre (clé primaire), titre, auteur, année_publication, ID_genre (clé étrangère)

### 2 - **Tableau "Genres"** :

colonnes : 

ID_genre (clé primaire), nom_genre

Dans cette configuration, nous avons une relation entre les tables "Livres" et "Genres" grâce à la clé étrangère "ID_genre" dans la table "Livres", qui référence la clé primaire "ID_genre" dans la table "Genres".

Supposons que nos tables contiennent les données suivantes :

**Tableau "Livres"**

| ID_livre | titre                         | auteur           | année_publication | ID_genre |
| :------- | :---------------------------: | :--------------: | :---------------- | :--------|
| 1        | Harry Potter                  |JK Rowling        |1997               | Fantaisie|
| 2        | Le Seigneur des Anneaux       |J. R. R. Tolkien |1954                | Fantaisie|
| 3        | Tuer un oiseau moqueur        |Harper Lee       |1960                | Fiction  |


**Tableau "Genres"**

| ID_genre | nom_genre |
| :------- | :-------: |
|1	       |Fantaisie  |
|2	       |Fantaisie  |
|3	       |Fiction    |


Nous pouvons utiliser une jointure pour récupérer les informations des livres avec leurs genres associés. Par exemple, pour obtenir une liste de tous les livres avec leur nom de genre, nous pouvons effectuer la requête suivante :

```sql
SELECT Livres.ID_livre, Livres.titre, Livres.auteur, Livres.annee_publication, Genres.nom_genre
FROM Livres
JOIN Genres ON Livres.ID_genre = Genres.ID_genre;
```

**Résultat de la requête :**

|ID_livre |titre	                |auteur	          |année_publication |nom_genre|
|:--------|:-----------------------:|:---------------:|:----------------|:-------:|
|1	      |Harry Potter	            |JK Rowling       |	1997	         |Fantaisie|
|2	      |Le Seigneur des Anneaux	|J. R. R. Tolkien |1954	             |Fantaisie|
|3	      |Tuer un oiseau moqueur	|Harper Lee	      |1960	             |Fiction  |

Grâce à la jointure, nous avons pu combiner les informations des tables "Livres" et "Genres" pour afficher le nom du genre associé à chaque livre.

>Cet exemple illustre comment les clés étrangères et les jointures peuvent être utilisées pour établir des relations entre les tables d'une base de données et effectuer des requêtes complexes pour obtenir des informations précises.