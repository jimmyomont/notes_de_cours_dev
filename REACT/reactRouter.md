# ROUTER REACT

## 1 : Installer React Router
```bash
npm install react-router-dom
```
## 2 : Importer les composants nécessaires
Dans votre fichier principal (généralement index.js ou app.js), importez les composants nécessaires depuis React Router :

```js
import React from 'react';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
```
## 3 : Créer les composants pour les pages

Créez des composants pour chaque page que vous souhaitez afficher dans votre application. 

Par exemple:
```js
import React from 'react';

const Accueil = () => <div>Page d'accueil</div>;
const APropos = () => <div>À propos de nous</div>;
const Contact = () => <div>Contactez-nous</div>;
```
## 4 : Définir les itinéraires
Dans le même fichier, utilisez vos itinéraires en utilisant le composant Switchqui permet de rendre uniquement le premier itinéraire qui correspond à l'URL. Utilisez le composant Routepour associer chaque URL à son composant correspondant :
```js
const App = () => (
  <Router>
    <Switch>
      <Route exact path="/" component={Accueil} />
      <Route path="/a-propos" component={APropos} />
      <Route path="/contact" component={Contact} />
    </Switch>
  </Router>
);
```
## 5 : Rendre l'application
Enfin, vous spécifiez que votre composant App est rendu dans votre fichier racine (index.js ou app.js) :
```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```
### Detail :
- ``BrowserRouterest`` utilisé pour fournir un contexte de routage à votre application. Vous pouvez également utiliser ``HashRouter`` si vous préférez des URL basées sur des hachages (#).

- ``Route`` est utilisé pour définir un itinéraire spécifique. L'attribut ``path`` indique le chemin de l'URL que vous souhaitez associer au composant, et ``component`` précise le composant à afficher lorsque l'URL correspond.

- ``Switch`` est utilisé pour rendre uniquement le premier itinéraire qui correspond à l'URL actuelle. Cela signifie que seul le composant de la page correspondant sera rendu et non tous les composants qui correspondent partiellement à l'URL.


## Exemple complet : 

```js
// Étape 1: Importer les dépendances nécessaires
import React from 'react';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

// Étape 2: Importer les composants que vous souhaitez afficher avec le Router
import Home from './components/Home';
import About from './components/About';
import Contact from './components/Contact';
import NotFound from './components/NotFound';

// Étape 3: Créer votre composant principal qui englobera le Router
const App = () => {
  return (
    <Router>
      {/* Étape 4: Utiliser le composant Switch pour assurer que seule la première route correspondante est rendue */}
      <Switch>
        {/* Étape 5: Définir vos routes en utilisant le composant Route */}
        {/* Remarque: L'ordre des routes est important, placez les routes spécifiques avant les routes génériques */}
        
        {/* Route pour la page d'accueil */}
        <Route exact path="/" component={Home} />
        
        {/* Route pour la page "À propos" */}
        <Route path="/about" component={About} />
        
        {/* Route pour la page "Contact" */}
        <Route path="/contact" component={Contact} />
        
        {/* Étape 6: Route pour les pages non trouvées (404) */}
        <Route component={NotFound} />
      </Switch>
    </Router>
  );
};

// Étape 7: Exporter le composant principal
export default App;
```