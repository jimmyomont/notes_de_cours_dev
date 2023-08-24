# [MySQL](https://dev.mysql.com/doc/)


1. **Se connecter à MySQL :** 

Entrez la commande suivante pour vous connecter à votre serveur MySQL. Vous devrez fournir le nom d'utilisateur et le mot de passe appropriés lorsque vous y serez invité.

```sql
mysql -u username -p
```

2. **Créez une base de données :** 

Une fois connecté, vous pouvez utiliser la commande `CREATE DATABASE` pour créer votre base de données. Remplacez `database_name` par le nom que vous souhaitez donner à votre base de données.

```sql
CREATE DATABASE database_name;
```

3. **Utilisez la nouvelle base de données :** 

Après avoir créé la base de données, vous pouvez l'utiliser en utilisant la commande `USE`.

```sql
USE database_name;
```

4. **Fermez MySQL :** 

Une fois que vous avez terminé, vous pouvez quitter le client MySQL en utilisant la commande :

```sql
EXIT;
```

---

## Les opérations courantes 


**Bases de données:**
```sql
-- Créer une base de données
CREATE DATABASE nom_de_la_base;

-- Sélectionner une base de données
USE nom_de_la_base;

-- Supprimer une base de données (attention, cette commande est irréversible)
DROP DATABASE nom_de_la_base;
```

**Tables:**
```sql
-- Créer une table
CREATE TABLE nom_de_la_table (
    id INT PRIMARY KEY,
    nom VARCHAR(50),
    age INT
);

-- Afficher les tables d'une base de données
SHOW TABLES;

-- Afficher la structure d'une table
DESCRIBE nom_de_la_table;

-- Supprimer une table
DROP TABLE nom_de_la_table;
```

**Insertion de données:**
```sql
-- Insérer une ligne dans une table
INSERT INTO nom_de_la_table (id, nom, age) VALUES (1, 'John', 25);
```

**Sélection de données:**
```sql
-- Sélectionner toutes les colonnes de toutes les lignes
SELECT * FROM nom_de_la_table;

-- Sélectionner des colonnes spécifiques avec une condition
SELECT nom, age FROM nom_de_la_table WHERE age > 30;

-- Utiliser l'opérateur LIKE pour les recherches partielles
SELECT * FROM nom_de_la_table WHERE nom LIKE 'J%';
```

**Mise à jour de données:**
```sql
-- Mettre à jour des valeurs dans une table
UPDATE nom_de_la_table SET age = 26 WHERE nom = 'John';
```

**Suppression de données:**
```sql
-- Supprimer des lignes d'une table
DELETE FROM nom_de_la_table WHERE age < 18;
```

**Opérations de jointure:**
```sql
-- Jointure interne entre deux tables
SELECT commandes.id, clients.nom
FROM commandes
JOIN clients ON commandes.client_id = clients.id;

-- Jointure externe gauche
SELECT clients.nom, commandes.id
FROM clients
LEFT JOIN commandes ON clients.id = commandes.client_id;
```

**Trier et limiter les résultats:**
```sql
-- Trier les résultats par ordre croissant
SELECT * FROM nom_de_la_table ORDER BY age ASC;

-- Trier les résultats par ordre décroissant
SELECT * FROM nom_de_la_table ORDER BY nom DESC;

-- Limiter le nombre de résultats
SELECT * FROM nom_de_la_table LIMIT 10;
```
