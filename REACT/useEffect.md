# UseEffect

``useEffect`` est un autre hook essentiel introduit dans React 16.8. Il permet aux composants fonctionnels de réagir d'effectuer des opérations de gestion des effets de bord et d'accéder au cycle de vie des composants, ce qui était auparavant réservé aux composants de classe. ``useEffect`` vous permet de paramétrer des effets à exécuter après le rendu du composant ou lorsque des dépendances changent.

Utilisation de``useEffect`` 
Pour utiliser ``useEffect`` , vous devez d'abord l'importer depuis le module React :

```js
import React, { useEffect } from 'react';
```
Ensuite, vous pouvez déclarer un effet en utilisant la syntaxe suivante :

```js
useEffect(() => {
  // Code à exécuter après le rendu ou lorsque les dépendances changent
  return () => {
    // Code de nettoyage à exécuter avant la suppression de l'effet
  };
}, [dependency1, dependency2, ...]);
```

Explications :

La fonction passée à ``useEffect`` est l'effet à exécuter. Elle sera appelée après chaque rendu du composant, au moins que les dépendances indiquées ne changent pas.
La fonction de nettoyage facultatif renvoyée par ``useEffect`` sera exécutée avant la suppression de l'effet, par exemple lorsque le composant est démonté ou lorsque les dépendances changent.
Les dépendances sont un tableau optionnel spécifié en deuxième argument. Si l'une des dépendances change entre les rendus, l'effet sera effectué à nouveau.
L'effet peut être utilisé pour effectuer des opérations telles que la manipulation du DOM, l'abonnement à des événements, l'appel d'API, la mise à jour de l'état, etc.

Exemples d'utilisation 
Exemple 1 : Mise à jour du titre de la page
```js
// Importation des hooks useEffect et useState depuis le module React
import React, { useEffect, useState } from 'react';

// Définition du composant Page
function Page() {
  // Déclaration de l'état local "count" avec une valeur initiale de 0 et la fonction "setCount" pour le mettre à jour
  const [count, setCount] = useState(0);

  // Utilisation de useEffect pour définir un effet
  useEffect(() => {
    // L'effet est exécuté après chaque rendu du composant et lorsque la dépendance "count" change

    // Mise à jour du titre de la page avec la valeur du compteur "count"
    document.title = `Compteur : ${count}`;

    // Fonction de nettoyage facultative retournée par useEffect
    // Cette fonction sera exécutée avant la suppression de l'effet
    // Ici, nous n'avons pas besoin de nettoyage, donc rien n'est spécifié
  }, [count]); // Spécification de la dépendance "count"

  // Fonction de gestion de l'événement pour augmenter le compteur
  const increment = () => {
    // Mise à jour de la valeur du compteur "count" en ajoutant 1
    setCount(count + 1);
  };

  // Rendu du composant
  return (
    <div>
      <p>Compteur : {count}</p>
      <button onClick={increment}>Incrémenter</button>
    </div>
  );
}
```

Dans cet exemple, nous utilisons ``useEffect`` pour mettre à jour le titre de la page avec la valeur du compteur ``count``. L'effet sera effectué chaque fois que ``count`` change, ce qui fera à jour le titre de la page.

Exemple 2 : Appel à une API

```js
import React, { useEffect, useState } from 'react';

function PostList() {
  // Déclaration de l'état local "posts" avec une valeur initiale vide
  const [posts, setPosts] = useState([]);

  // Utilisation de useEffect pour effectuer un appel à une API lors du premier rendu du composant
  useEffect(() => {
    // Appel à l'API pour récupérer les données des posts
    fetch('https://api.example.com/posts')
      .then(response => response.json())
      .then(data => {
        // Mise à jour de l'état "posts" avec les données obtenues de l'API
        setPosts(data);
      });
  }, []);

  return (
    <ul>
      {/* Mapping des posts pour les afficher sous forme de liste */}
      {posts.map(post => (
        <li key={post.id}>{post.title}</li>
      ))}
    </ul>
  );
}
```

Dans cet exemple, nous utilisons ``useEffect`` pour effectuer un appel à une API et mettre à jour l'état ``posts`` avec les données reçues. L'effet sera appliqué une seule fois, après le premier rendu du composant (grâce à un tableau de dépendances vide []). Les données récupérées sont ensuite utilisées pour afficher une liste de publications.

Ces exemples illustrent l'utilisation ``useEffect`` pour gérer les effets de bord dans les composants fonctionnels de React. Vous pouvez autant d'effets que nécessaire dans un composant en utilisant ``useEffect`` plusieurs fois.