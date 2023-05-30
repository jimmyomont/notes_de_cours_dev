# REACT 




## Création de composants :
````js
import React from 'react';

class MyComponent extends React.Component {
  render() {
    return <div>Hello, World!</div>;
  }
}

export default MyComponent;
````

## Composants fonctionnels :

```js
import React from 'react';

function MyComponent() {
  return <div>Hello, World!</div>;
}

export default MyComponent;
```

## Principes de base de JSX :

```js
const element = <h1>Hello, World!</h1>;
```

## Accessoires :
```js
function Greeting(props) {
  return <div>Hello, {props.name}!</div>;
}

// Usage:
<Greeting name="John" />
```

## État:
```js
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

## Gestion des événements:
```js
function Button() {
  const handleClick = () => {
    console.log('Button clicked!');
  };

  return <button onClick={handleClick}>Click me</button>;
}
```

## Rendu conditionnel :
```js
function Greeting(props) {
  if (props.isLoggedIn) {
    return <div>Welcome back, {props.user}!</div>;
  } else {
    return <div>Please log in.</div>;
  }
}
```

## Listes et clés :
```js
function MyList() {
  const items = ['Apple', 'Banana', 'Orange'];

  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}
```

## Cycle de vie des composants (composants de classe) :
```js
class MyComponent extends React.Component {
  componentDidMount() {
    console.log('Component did mount');
  }

  componentWillUnmount() {
    console.log('Component will unmount');
  }

  render() {
    return <div>Hello, World!</div>;
  }
}
```

## Crochets :
```js
import React, { useState, useEffect } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log('Component did mount or update');
    // Cleanup function
    return () => {
      console.log('Component will unmount');
    };
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```


## Formulaires et gestion des entrées :
```js
function MyForm() {
  const [inputValue, setInputValue] = useState('');

  const handleChange = (event) => {
    setInputValue(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    console.log('Submitted value:', inputValue);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" value={inputValue} onChange={handleChange} />
      <button type="submit">Submit</button>
    </form>
  );
}
```

## Communication composante (parent à enfant) :
```js
// Parent Component
function ParentComponent() {
  const message = 'Hello from parent!';

  return <ChildComponent message={message} />;
}

// Child Component
function ChildComponent(props) {
  return <div>{props.message}</div>;
}
```

## Communication composante (enfant à parent):
```js
// Parent Component
function ParentComponent() {
  const handleMessage = (message) => {
    console.log('Message from child:', message);
  };

  return <ChildComponent onMessage={handleMessage} />;
}

// Child Component
function ChildComponent(props) {
  const handleClick = () => {
    props.onMessage('Hello from child!');
  };

  return <button onClick={handleClick}>Send Message</button>;
}
```

## Communication des composants (composants frères) :
```js
// Parent Component
function ParentComponent() {
  const [message, setMessage] = useState('');

  const handleMessage = (message) => {
    setMessage(message);
  };

  return (
    <div>
      <ChildComponent1 onMessage={handleMessage} />
      <ChildComponent2 message={message} />
    </div>
  );
}

// Child Component 1
function ChildComponent1(props) {
  const handleClick = () => {
    props.onMessage('Hello from sibling!');
  };

  return <button onClick={handleClick}>Send Message</button>;
}

// Child Component 2
function ChildComponent2(props) {
  return <div>{props.message}</div>;
}
```

## Style CSS :
```js
function MyComponent() {
  return <div className="my-component">Styled Component</div>;
}
// CSS
.my-component {
  color: blue;
  font-size: 18px;
}
```


## Style CSS conditionnel :
```js
function MyComponent(props) {
  const isActive = props.isActive;

  return <div className={isActive ? 'active' : 'inactive'}>Styled Component</div>;
}

// CSS
.active {
  color: green;
}

.inactive {
  color: red;
}
```

## Récupération de données (à l'aide de fetch) :
```js
import React, { useState, useEffect } from 'react';

function DataFetching() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then((response) => response.json())
      .then((data) => setData(data))
      .catch((error) => console.log(error));
  }, []);

  return (
    <ul>
      {data.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}
```

## Routage (à l'aide du routeur React):
```js
import { BrowserRouter as Router, Switch, Route, Link } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/contact">Contact</Link>
            </li>
          </ul>
        </nav>

        <Switch>
          <Route path="/about">
            <About />
          </Route>
          <Route path="/contact">
            <Contact />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </Router>
  );
}
```
---
 React est une bibliothèque JavaScript utilisée pour créer des interfaces utilisateur interactives et réactives. Son principe de base repose sur la création de composants réutilisables qui encapsulent la logique et la structure d'une partie spécifique de l'interface utilisateur. Ces composants peuvent être imbriqués les uns dans les autres pour construire des complexes d'interfaces.

React utilise un modèle de programmation déclaratif, ce qui signifie que vous décrivez comment l'interface utilisateur doit se comporter en fonction de l'état actuel de l'application, et React se charge de mettre à jour l'interface utilisateur de manière efficace lorsque l'état change. Il utilise une technique appelée "Virtual DOM" qui permet de mettre à jour uniquement les parties de l'interface utilisateur qui ont été modifiées, ce qui améliore les performances de l'application.