# JSX (JavaScript XML)


Extension de syntaxe utilisée principalement avec React pour décrire la structure des interfaces utilisateur. Il permet de mélanger le code JavaScript avec le code HTML de manière plus expressive et facile à comprendre.

Voici un exemple simple de JSX :

```jsx
import React from 'react';

function App() {
  const name = 'John Doe';

  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>Welcome to my website.</p>
    </div>
  );
}
export default App
```

;
Dans cet exemple, nous avons une fonction ``App`` qui retourne du JSX. Le JSX est entouré par des parenthèses et peut contenir du code JavaScript entre des accolades ``{}``.

Le JSX ressemble beaucoup au code HTML, mais il peut inclure des expressions JavaScript. Dans cet exemple, nous avons la variable ``name`` qui est utilisée pour afficher le nom dynamiquement dans le titre ( ``<h1>``). Le texte statique est également présent dans les balises ``<p>``.

Notez que le JSX doit être compilé en JavaScript valide avant d'être effectué par le navigateur. Cela se fait généralement à l'aide d'un outil tel que Babel.

Lorsque le JSX est exécuté, il est transformé en appels de fonctions React pour créer les éléments correspondants DOM. Dans cet exemple, le JSX ``<div>`` est transformé en ``React.createElement('div', null, ...)``.

En utilisant JSX, il devient plus facile de créer des composants réutilisables et de maintenir la structure de l'interface utilisateur dans une syntaxe familière et lisible.

---
## résumé des principaux éléments de la syntaxe :


Création d'éléments :
```jsx
const element = <div>Hello, world!</div>;
```

Utilisation d'attributs :
```jsx
const element = <img src={imageUrl} alt="description" />;
```

Utilisation de variables et d'expressions JavaScript :
```jsx
const name = 'John';
const element = <h1>Hello, {name}!</h1>;
```

Utilisation des structures de contrôle de flux :
```jsx
const isLoggedIn = false;
const element = isLoggedIn ? <LogoutButton /> : <LoginButton />;
```

Utilisation de listes et de clés :
```jsx
const items = ['apple', 'banana', 'orange'];
const element = (
  <ul>
    {items.map((item) => (
      <li key={item}>{item}</li>
    ))}
  </ul>
);
```

Utilisation de composants :
```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

const element = <Greeting name="John" />;
```



Utilisation des propriétés enfants :
```js
function Button(props) {
  return <button>{props.children}</button>;
}

const element = <Button>Click me!</Button>;
```

Utilisation des styles :
```js
const style = { color: 'red', fontWeight: 'bold' };
const element = <p style={style}>Hello, world!</p>;
```
