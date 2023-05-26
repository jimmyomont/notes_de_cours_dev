# UseState

``useState`` est l'un des hooks fondamentaux introduits dans React 16.8. Il permet aux composants fonctionnels de React de gérer l'état local, ce qui était auparavant réservé aux composants de classe et vous permet de déclarer des variables d'état et de leur associer des fonctions pour les mettre à jour. L'utilisation de useState rend le code plus concis et plus facile à comprendre.

## Utilisation
Pour utiliser useState, vous devez d'abord l'importer depuis le module React :

```js
import React, { useState } from 'react';
```
Ensuite, vous pouvez déclarer une variable d'état et sa fonction de mise à jour en utilisant la syntaxe suivante :

```js 
const [state, setState] = useState(initialValue);
```

Explications :

``state`` est le nom de la variable d'état.
``setState`` est la fonction qui sera utilisée pour mettre à jour la valeur de state.
``initialValue`` est la valeur initiale de state.
Lorsque vous appelez ``useState(initialValue)``, la fonction useStateretourne un tableau avec deux éléments : la valeur actuelle de l'état ``(state)`` et la fonction pour mettre à jour cette valeur ``(setState)``.

Vous pouvez ensuite utiliser statedans votre composant pour accéder à la valeur de l'état, et setStatepour mettre à jour cette valeur.

Exemples d'utilisation

Exemple 1 : Compteur simple

```js
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Compteur : {count}</p>
      <button onClick={increment}>Incrémenter</button>
    </div>
  );
}
```

Dans cet exemple, nous utilisons ``useState`` pour déclarer une variable d'état countavec une valeur initiale de 0. Lorsque le bouton est cliqué, la fonction incrementest appelée, ce qui met à jour la valeur du compteur counten l'augmentant de 1.

Exemple 2 : Formulaire avec entrée contrôlée

```js
import React, { useState } from 'react';

function Form() {
  const [name, setName] = useState('');

  const handleChange = (event) => {
    setName(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(`Nom soumis : ${name}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Nom :
        <input type="text" value={name} onChange={handleChange} />
      </label>
      <button type="submit">Soumettre</button>
    </form>
  );
}
```

Dans cet exemple, nous utilisons ``useState`` pour déclarer une variable d'état nameavec une valeur initiale vide. L'entrée est une "entrée contrôlée", ce qui signifie que sa valeur est liée à la variable d'état nameet que la fonction handleChangeest appelée à chaque modification de l'entrée. Lorsque le formulaire est soumis, la fonction ``handleSubmit`` est désignée, permet une alerte avec le nom soumis.

Ces exemples illustrent l'utilisation ``useState`` pour gérer l'état local dans les composants fonctionnels de React. Vous pouvez créer autant de variables d'état que nécessaire dans un composant en utilisant ``useState`` plusieurs fois.