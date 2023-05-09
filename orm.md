# ORM (object-relational mapping)


Choisissir un ORM qui correspond à vos besoins (par exemple Sequelize, TypeORM, Hibernate, Django ORM, etc.)
Installez l'ORM et toutes les dépendances requises
Créez une connexion à votre base de données en utilisant les options de configuration de l'ORM


Exemple d'utilisation de Sequelize dans Node.js :

```js
const { Sequelize } = require('sequelize');

const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: 'mysql'
});
```

### Définition d'un modèle :

Définir un modèle ou une classe qui représente une table dans votre base de données
Spécifiez les champs ou les colonnes de la table, leurs types de données et toutes les contraintes ou validations
Définir toute relation ou association avec d'autres tables


Exemple d'utilisation de Sequelize dans Node.js :

```js
const { Sequelize, DataTypes } = require('sequelize');

const User = sequelize.define('User', {
  // Define the fields/columns of the User table
  id: {
    type: DataTypes.INTEGER,
    autoIncrement: true,
    primaryKey: true
  },
  firstName: {
    type: DataTypes.STRING,
    allowNull: false
  },
  lastName: {
    type: DataTypes.STRING,
    allowNull: false
  },
  email: {
    type: DataTypes.STRING,
    allowNull: false,
    unique: true,
    validate: {
      isEmail: true
    }
  }
}, {
  // Define any additional options for the User model
  tableName: 'users',
  timestamps: true,
  underscored: true
});
```

### Synchronisation du modèle avec la base de données :
Utilisez l'outil de migration de l'ORM pour créer ou modifier le schéma de table en fonction de la définition du modèle
Cela générera du code SQL pour créer ou modifier la table, les index et les contraintes

Exemple d'utilisation de Sequelize dans Node.js :

```js
  .then(() => console.log('User table created'))
  .catch((err) => console.error('Error creating User table: ', err));
  User.sync()
```


### Interrogation de la base de données :
Utiliser le générateur de requêtes de l'ORM ou DSL (Domain-Specific Language) pour construire des requêtes
Utiliser le modèle ou la classe pour interroger la base de données et récupérer les résultats sous forme d'objets ou d'instances
Utilisez les options de l'ORM pour filtrer, trier, limiter et paginer les résultats

Exemple d'utilisation de Sequelize dans Node.js :

```js
// Retrieve all users
User.findAll()
  .then(users => console.log(users))
  .catch(err => console.error('Error retrieving users: ', err));

// Retrieve users where firstName is 'John'
User.findAll({
  where: {
    firstName: 'John'
  }
}).then(users => console.log(users));

// Retrieve users where age is greater than 18
User.findAll({
  where: {
    age: {
      [Op.gt]: 18
    }
  }
}).then(users => console.log(users));
```

### Création d'un nouvel enregistrement :
Créer une nouvelle instance du modèle ou de la classe
Définir les propriétés ou les champs de l'instance
Utilisez la méthode save ou create de l'ORM pour conserver l'instance dans la base de données

Exemple d'utilisation de Sequelize dans Node.js :

```js
const john = User.build({
  firstName: 'John',
  lastName: 'Doe',
  email: 'john.doe@example.com'
});

john.save()
  .then(() => console.log('User created'))
  .catch(err => console.error('Error creating user: ', err));
```


### Mise à jour d'un enregistrement :
Récupérer une instance du modèle ou de la classe à partir de la base de données
Modifier les propriétés ou les champs de l'instance
Utilisez la méthode de sauvegarde ou de mise à jour de l'ORM pour mettre à jour l'instance dans la base de données

Exemple d'utilisation de Sequelize dans Node.js :

```js
// Retrieve a user with id = 1
User.findByPk(1)
  .then(user => {
    // Update the user's email address
    user.email = 'new.email@example.com';
    return user.save();
  })
  .then(() => console.log('User updated'))
  .catch(err => console.error('Error updating user: ', err));
```

### Suppression d'un enregistrement :
Récupérer une instance du modèle ou de la classe à partir de la base de données
Utilisez la méthode destroy de l'ORM pour supprimer l'instance de la base de données

Exemple d'utilisation de Sequelize dans Node.js :

```js
// Retrieve a user with id = 1
User.findByPk(1)
  .then(user => user.destroy())
  .then(() => console.log('User deleted'))
  .catch(err => console.error('Error deleting user: ', err));
```

### Travailler avec des associations :
Définir des relations ou des associations entre des modèles ou des classes à l'aide des méthodes d'association de l'ORM
Utilisez l'option d'inclusion de l'ORM pour charger avec impatience les données associées lors de l'interrogation de la base de données

Exemple d'utilisation de Sequelize dans Node.js :

```js
const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false
  }
}, {
  tableName: 'posts',
  timestamps: true,
  underscored: true
});
// Define a one-to-many association between User and Post
User.hasMany(Post);
Post.belongsTo(User);

// Retrieve all users and their posts
User.findAll({
  include: Post
}).then(users => console.log(users));
```


