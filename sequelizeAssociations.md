# ASSOCIATIONS SEQUELIZE

>Sequelize est un mappage objet-relationnel (ORM) pour Node.js qui vous permet d'interagir avec des bases de données relationnelles de manière orientée objet. 

Aperçu des quatre principaux types d'associations dans Sequelize :

## hasMany():

- Définit une association ``ONE-TO-MANY`` entre deux modèles.
- Un modèle source peut avoir plusieurs instances du modèle cible.
- Le modèle cible appartient au modèle source.

Exemple:
```js
const User = sequelize.define('User', {
  // User model attributes
});

const Post = sequelize.define('Post', {
  // Post model attributes
});

User.hasMany(Post);

```
----
## belongsTo():

- Définit une association `ONE-TO-ONE` ou ``ONE-TO-MANY`` entre deux modèles.
- Le modèle source appartient au modèle cible.

Exemple:
```js
const Post = sequelize.define('Post', {
  // Post model attributes
});

const User = sequelize.define('User', {
  // User model attributes
});

Post.belongsTo(User);

```
----
## hasOne():

- Définit une association ``ONE-TO-ONE`` entre deux modèles.
- Le modèle source peut avoir une instance du modèle cible.

Exemple:
```js
const User = sequelize.define('User', {
  // User model attributes
});

const UserProfile = sequelize.define('UserProfile', {
  // UserProfile model attributes
});

User.hasOne(UserProfile);

```
----
## belongsToMany():

- Définit une association ``MANY-TO-MANY`` entre deux modèles à l'aide d'une table de jonction.
- Les deux modèles peuvent avoir plusieurs instances l'un de l'autre.

Exemple:
```js
const Student = sequelize.define('Student', {
  // Student model attributes
});

const Course = sequelize.define('Course', {
  // Course model attributes
});

Student.belongsToMany(Course, { through: 'StudentCourse' });
Course.belongsToMany(Student, { through: 'StudentCourse' });

```