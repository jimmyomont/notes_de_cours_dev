# PRISMA

### 1. Installation

installer Prisma et les dépendances nécessaires dans votre projet. 

```bash
# Avec npm
npm install prisma

# Avec yarn
yarn add prisma
```

### 2. Configuration

Créez un fichier de configuration `schema.prisma` dans la racine de votre projet. 

```bash
npx prisma init
```

Modifiez le fichier `schema.prisma` selon vos besoins pour définir vos modèles de base de données.

### 3. Génération de modèles

Générez les modèles TypeScript à partir de votre schéma Prisma 

```bash
npx prisma generate
```

Cela générera des fichiers TypeScript dans le dossier `node_modules/.prisma/client`.

### 4. Création de migrations

Créez une migration pour appliquer vos modifications au schéma de la base de données.

```bash
npx prisma migrate dev
```

### 5. Utilisation dans votre application

Vous pouvez maintenant utiliser les modèles Prisma générés dans votre application Node.js pour effectuer des opérations de base de données.

Exemple :

```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function main() {
  const user = await prisma.user.create({
    data: {
      name: 'John Doe',
      email: 'johndoe@example.com',
    },
  });

  console.log(user);
}

main()
  .catch((e) => {
    throw e;
  })
  .finally(async () => {
    await prisma.$disconnect();
  });
```

importer les modèles Prisma appropriés et d'initialiser une instance Prisma pour accéder à la base de données.

### 6. Exécution de la commande Prisma

Vous pouvez également utiliser `npx prisma` pour exécuter diverses commandes Prisma directement depuis la ligne de commande, par exemple, pour créer des modèles, générer des migrations, ou effectuer d'autres opérations liées à la base de données.


## CRUD 

### 1. Créer un nouveau Post

```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function createPost() {
  const newPost = await prisma.post.create({
    data: {
      title: 'Mon premier post',
      content: 'Ceci est le contenu de mon post.',
    },
  });

  console.log('Nouveau post créé :', newPost);
}

createPost()
  .catch((error) => {
    console.error('Erreur lors de la création du post :', error);
  })
  .finally(async () => {
    await prisma.$disconnect();
  });
```

### 2. Lire un Post

```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function readPost(postId) {
  const post = await prisma.post.findUnique({
    where: {
      id: postId,
    },
  });

  if (post) {
    console.log('Post trouvé :', post);
  } else {
    console.log('Post non trouvé.');
  }
}

const postIdToRead = 1; // Remplacez par l'ID du post que vous voulez lire
readPost(postIdToRead)
  .catch((error) => {
    console.error('Erreur lors de la lecture du post :', error);
  })
  .finally(async () => {
    await prisma.$disconnect();
  });
```

### 3. Mettre à jour un Post

```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function updatePost(postId, newTitle) {
  const updatedPost = await prisma.post.update({
    where: {
      id: postId,
    },
    data: {
      title: newTitle,
    },
  });

  console.log('Post mis à jour :', updatedPost);
}

const postIdToUpdate = 1; // Remplacez par l'ID du post que vous voulez mettre à jour
const newTitle = 'Nouveau titre pour le post';
updatePost(postIdToUpdate, newTitle)
  .catch((error) => {
    console.error('Erreur lors de la mise à jour du post :', error);
  })
  .finally(async () => {
    await prisma.$disconnect();
  });
```

### 4. Supprimer un Post

```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function deletePost(postId) {
  const deletedPost = await prisma.post.delete({
    where: {
      id: postId,
    },
  });

  console.log('Post supprimé :', deletedPost);
}

const postIdToDelete = 1; // Remplacez par l'ID du post que vous voulez supprimer
deletePost(postIdToDelete)
  .catch((error) => {
    console.error('Erreur lors de la suppression du post :', error);
  })
  .finally(async () => {
    await prisma.$disconnect();
  });
```
