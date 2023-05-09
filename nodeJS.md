
## Gestionnaire de packages : 

### npm est le gestionnaire de packages de facto de Node.js. Il permet d'installer et de gérer des packages et des dépendances dans votre projet.

### Initialise un nouveau projet Node.js
```
npm init 
``` 
### Installe un package
```
npm install <package> 
```
### Installe un package globalement
```
npm install -g <package>
 ```
### Installe un package et l'ajoute aux dépendances de votre projet
```
npm install --save <package>
```
### Installe un package et l'ajoute aux dépendances de développement de votre projet
```
npm install --save-dev <package> 
```

---

## Modules 
### Les modules permettent d'organiser et de partager du code dans une application Node.js.

### Importer un module dans un fichier JavaScript

Exemple :
```js
const express = require('express');

```


### Exporter un module depuis un fichier JavaScript

Exemple :

```js
module.exports = {
  add: function(a, b) {
    return a + b;
  }
};
```

---


## Processus 

Node.js est capable de gérer des processus et des threads en interne.

``process.argv`` Récupère les arguments de la ligne de commande

```js
const args = process.argv.slice(2);
console.log(args);
```

``process.exit()`` Termine le processus en cours

```js
process.exit(1);
```

``process.cwd()`` Récupère le répertoire de travail en cours

```js
process.cwd()
```

``process.env`` Donne accès aux variables d'environnement

```js
console.log(process.env.PORT);
```

---

``Fonctions asynchrones`` : Node.js est conçu pour être performant en utilisant des fonctions asynchrones.

```js
function getUserData(id, callback) {
  setTimeout(() => {
    const user = { id: id, name: "John Doe" };
    callback(user);
  }, 1000);
}
```

``Callbacks`` : Utilisés pour retourner des résultats asynchrones

```js
getUserData(123, (user) => {
  console.log(user);
});
```

``Promesses`` : Utilisées pour simplifier la gestion des résultats asynchrones

```js
function getUserData(id) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const user = { id: id, name: "John Doe" };
      resolve(user);
    }, 1000);
  });
}

getUserData(123).then((user) => {
  console.log(user);
}).catch((error) => {
  console.error(error);
});
```

``async/await`` : Une façon plus élégante de gérer les résultats asynchrones en utilisant des fonctions asynchrones.

```js
async function main() {
  try {
    const user = await getUserData(123);
    console.log(user);
  } catch (error) {
    console.error(error);
  }
}
main();
```

---

## Serveurs
Node.js est souvent utilisé pour créer des serveurs Web 

``http.createServer()`` : Créer un serveur HTTP

```js 
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello World!');
});

server.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

``app.listen()`` : Ecoutez les connexions entrantes sur un port spécifié

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000, () => {
  console.log('Serveur démarré sur le port 3000');
});
```

``Express.js`` : Un framework populaire pour créer des serveurs Web en Node.js.

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```



``Routage`` : Gérer les différentes requêtes HTTP en fonction de leur chemin d'accès

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Accueil');
});

app.get('/users', (req, res) => {
  res.send('Liste des utilisateurs');
});

app.get('/users/:id', (req, res) => {
  res.send('Utilisateur avec l\'ID ' + req.params.id);
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

``Middleware`` : Des fonctions qui peuvent être exécutées avant ou après le traitement de la requête

```js
const express = require('express');
const app = express();

app.use(express.json());

app.use((req, res, next) => {
  console.log(req.method + ' ' + req.url);
  next();
});

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

``Templates`` : Des moteurs de template pour générer du contenu HTML dynamique

Exemple avec EJS :

```js 
const express = require('express');
const app = express();
const ejs = require('ejs');

app.set('view engine', 'ejs');

app.get('/', (req, res) => {
  res.render('index', { title: 'Accueil', message: 'Hello World!' });
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```
``Middleware`` de gestion des erreurs : Des fonctions qui peuvent être utilisées pour gérer les erreurs dans l'application

```js
const express = require('express');
const app = express();

app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});

app.get('/', (req, res) => {
  throw new Error('Something went wrong!');
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```


---
## Gestion des fichiers 

Node.js est également capable de gérer les fichiers et les répertoires.

``fs.readFile()`` : Lit un fichier

```js 
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

``fs.writeFile()`` : Ecrit dans un fichier
```js 
const fs = require('fs');

fs.writeFile('monFichier.txt', 'Contenu du fichier', (err) => {
  if (err) throw err;
  console.log('Le fichier a été sauvegardé !');
});
```
``fs.mkdir()`` : Créer un répertoire
```js 
const fs = require('fs');

fs.mkdir('nouveau_repertoire', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Répertoire créé avec succès !');
});
```
``fs.readdir()`` : Lit le contenu d'un répertoire
```js 
const fs = require('fs');

fs.readdir('./mon-repertoire', (err, files) => {
  if (err) {
    console.error(err);
    return;
  }

  // Le contenu du répertoire est stocké dans le tableau 'files'
  console.log(files);
});
```

``fs.appendFile()`` : Mettre à jour un fichier 

```js 
const fs = require('fs');

fs.appendFile('monFichier.txt', '\nNouveau contenu', (err) => {
  if (err) throw err;
  console.log('Le fichier a été mis à jour !');
});
```
``fs.unlink()`` : Supprime un fichier 

```js 
const fs = require('fs');

fs.unlink('monFichier.txt', (err) => {
  if (err) throw err;
  console.log('Le fichier a été supprimé !');
});
```