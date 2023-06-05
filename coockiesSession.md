# COOCKIES DE SESSION (php)

### Utilisés pour stocker des informations spécifisque pour maintenir l'etat d'une session utilisateur 

## Créer, définir et accéder aux cookies de session en PHP :

### 1 - Démarrer une session : 

Avant de pouvoir utiliser les cookies de session, vous devez d'abord démarrer une session en utilisant la fonction session_start(). 
Cela initialise une nouvelle session ou restaure une session existante si elle existe déjà.

```php
session_start();
```


### 2 - Définir un cookie de session : 

Une fois la session démarrée, vous pouvez définir des variables de session qui seront stockées dans un cookie sur le navigateur de l'utilisateur.
Utilisez simplement la syntaxe ``$_SESSION['nom_variable'] = valeur`` pour définir une variable de session.

Exemple :

```php
$_SESSION['utilisateur'] = 'John';
```


### 3 - Accéder à un cookie de session : 

Pour accéder à une variable de session, utilisez la même syntaxe ``$_SESSION['nom_variable']``.

Exemple :

```php
echo $_SESSION['utilisateur']; // Affiche "John"
```


### 4 - Supprimer un cookie de session : 

Pour supprimer une variable de session, vous pouvez utiliser la fonction ``unset()``.

Exemple :

```php
unset($_SESSION['utilisateur']);
```


### 5 - Détruire une session : 
Si vous souhaitez détruire complètement une session et supprimer tous les cookies de session, vous pouvez utiliser la fonction ``session_destroy()``.

Exemple :

```php
session_destroy();
```

