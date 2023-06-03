# BOOTSTARP



Dans cet exemple les composants Bootstrap intégrés sont :

- Composant d'alerte  ``alert`` : affiche un message d'alerte stylisé.
- Composant de carte  ``card`` : affiche une carte avec une image, un titre, un contenu et un lien.
- Composant de menu déroulant  ``dropdown`` : affiche un bouton qui, lorsqu'il est cliqué, déclenche l'affichage d'un menu déroulant contenant des actions.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Exemples de composants Bootstrap</title>
    <!-- Lien vers les fichiers CSS de Bootstrap -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>

    <div class="container">
        <!-- Conteneur principal de la page -->

        <h1>Exemples de composants Bootstrap</h1>
        <!-- Titre principal de la page -->

        <div class="alert alert-primary" role="alert">
            <!-- Composant d'alerte -->

            <strong>C'est une alerte !</strong> Ceci est un message d'alerte Bootstrap.
            <!-- Contenu de l'alerte -->

        </div>

        <div class="card">
            <!-- Composant de carte -->

            <img src="image.jpg" class="card-img-top" alt="Image">
            <!-- Image de la carte avec la classe "card-img-top" pour la positionner en haut -->

            <div class="card-body">
                <!-- Contenu de la carte -->

                <h5 class="card-title">Titre de la carte</h5>
                <!-- Titre de la carte -->

                <p class="card-text">Contenu de la carte</p>
                <!-- Texte de la carte -->

                <a href="#" class="btn btn-primary">En savoir plus</a>
                <!-- Lien stylisé dans la carte -->

            </div>

        </div>

        <div class="dropdown">
            <!-- Composant de menu déroulant -->

            <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                Options
            </button>
            <!-- Bouton déclencheur du menu déroulant -->

            <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                <!-- Contenu du menu déroulant -->

                <a class="dropdown-item" href="#">Action 1</a>
                <a class="dropdown-item" href="#">Action 2</a>
                <a class="dropdown-item" href="#">Action 3</a>

            </div>

        </div>

    </div>

    <!-- Scripts JavaScript de Bootstrap (jQuery et Popper.js) -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>

</body>
</html>
```

le même exemple avec REACT 

```jsx
import React from 'react';
import 'bootstrap/dist/css/bootstrap.min.css';

function App() {
  return (
    <div className="container">
      <h1>Mon titre</h1>
      
      <div className="row">
        <div className="col-md-6">
          <p>Contenu de la colonne 1</p>
          <button className="btn btn-primary">Bouton</button>
        </div>

        <div className="col-md-6">
          <p>Contenu de la colonne 2</p>
          <img src="image.jpg" alt="Image" />
        </div>
      </div>

      <div className="jumbotron">
        <h2>Mon jumbotron</h2>
        <p>Contenu du jumbotron</p>
        <a href="#" className="btn btn-primary btn-lg">En savoir plus</a>
      </div>
    </div>
  );
}

export default App;

```