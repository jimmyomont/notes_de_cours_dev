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


## Connexion à PostgreSQL

``psql -U <username> -d <database>``

## Afficher de l'aide

``\h``
## Lister les bases de données
``\l``

## Se connecter à une base de données spécifique
``\c <database>``

## Lister les tables
``\dt``

## Décrire une table
``\d <table>``

## Exécuter une requête SQL
``SELECT * FROM <table>;``

## Quitter psql
``\q``



## Créer une nouvelle table
``` SQL
CREATE TABLE <table> (
    <column1> <datatype> <constraints>,
    <column2> <datatype> <constraints>,
    ...
);
```
## Insérer des données dans une table
```sql
INSERT INTO <table> (<column1>, <column2>, ...) VALUES (<value1>, <value2>, ...);
```
## Mettre à jour des données dans une table
```sql
UPDATE <table> SET <column1> = <value1>, <column2> = <value2>, ... WHERE <condition>;
```

## Supprimer des données d'une table
```sql
DELETE FROM <table> WHERE <condition>;
```
