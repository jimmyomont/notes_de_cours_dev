# PSQL
---

## Connexion session PSQL 

``psql -U postgres``

``mot de passe utilisateur``

## Créer un nouvel utilisateur avec password

```sql
CREATE USER utilisteur WITH PASSWORD 'mot_de_passe'; 
```

## Créer une nouvelle base de données associer à cet nouvel utilisateur

```sql
CREATE DATABASE name_data WITH OWNER utilisateur;
```

## Modifier ou supprimer un élément 

``ALTER`` pour modifier et ``DROP`` pour supprimer

## Quitter pour se conecter au nouvel utilistateur 

``\q``

## Connexion nouvel utilisateur 

``psql  -U utilisateur -d name_data``

---
## Créer une nouvelle table
``` SQL
CREATE TABLE "name_table" (
  "id" INTEGER GENERATED ALWAYS AS IDENTITY PRIMARY KEY, -- Un identifiant unique généré par le RDBMS
  "nom" TEXT NOT NULL, -- il est obligatoire
  "age" INTEGER NOT NULL, -- obligatoire aussi
  "adresse" TEXT,
  "date de création de compte" TIMESTAMPTZ NOT NULL DEFAULT NOW(), -- on veut savoir quand un film a été ajouté dans la base et on défini la valeur par défaut comme étant maintenant       (c'est a dire au moment ou le film sera ajouté)
  "date de modification de compte" TIMESTAMPTZ
)
```

## Insérer des données dans une table

```sql
INSERT INTO <table_name> (<column1>, <column2>, ...) VALUES (<value1>, <value2>, ...);
```
## Mettre à jour des données dans une table
```sql
UPDATE <table_name> SET <column1> = <value1>, <column2> = <value2>, ... WHERE <condition>;
```

## Supprimer des données d'une table
```sql
DELETE FROM <table_nam> WHERE <condition>;
```

### Le but étant de facilité les choses en faisant les table dans des script ``.js``
---
### Afficher de l'aide

- ``\h``
### Lister les bases de données
- ``\l``

### Se connecter à une base de données spécifique
- ``\c <database>``

### Lister les tables
- ``\dt``

### Décrire une table
- ``\d <table>``

### Exécuter une requête SQL
- ``SELECT * FROM <table>;``

### Quitter psql
- ``\q``
