# ACCESSIBILITE NUMERIQUE

## Les bonnes pratiques 

1 - Utilisez des descriptions alternatives pour les images Les descriptions alternatives aident les utilisateurs aveugles et malvoyants à comprendre le contenu des images. Utilisez l'attribut ``alt`` pour inclure une description alternative pour toutes les images, y compris les images décoratives. 

```HTML
<img src="mon-image.jpg" alt="Description alternative de l'image">
```


2 - Utilisez les titres et les balises de structure pour améliorer la navigation Utilisez les titres et les balises de structure (comme les balises ``<h1>`` à ``<h6>`` ) pour créer une structure de contenu claire et logique. Cela aide les utilisateurs à comprendre la hiérarchie du contenu et à naviguer plus facilement dans la page. 

Exemple de code :
```HTML
<h1>Titre principal</h1>
<h2>Sous-titre</h2>
<p>Contenu...</p>
```

3 - Utilisez des couleurs contrastées assurez-vous que les couleurs de votre site Web offrent un contraste suffisant pour être facilement lisibles. Un rapport de contraste de 4,5:1 est recommandé pour la plupart des textes. 

Exemple de code CSS :
```CSS
body {
  color: #333;
  background-color: #fff;
}

h1 {
  color: #000;
  background-color: #fff;
  border: 2px solid #000;
}
```

4 - Évitez les vidéos et les animations qui clignotent Les personnes atteintes d'épilepsie peuvent être sensibles aux vidéos et les animations qui clignotent rapidement. Évitez les vidéos et les animations qui clignotent, ou fournissez une alternative pour les utilisateurs qui pourraient être sensibles. 

Exemple de code CSS :
```css
video {
  animation: none;
}

@media (prefers-reduced-motion: reduce) {
  video {
    display: none;
  }
}
```

5 - L'utilisation des formulaires accessibles vous permet d'accéder à vos formulaires en incluant des étiquettes pour tous les champs, en utilisant des messages d'erreur clairs et en fournissant des instructions pour les utilisateurs qui utilisent des technologies d'assistance. 

Exemple de code HTML :
```html
<label for="nom">Nom :</label>
<input type="text" id="nom" name="nom" required>
```

6 - Assurez-vous que votre site Web est utilisable sans souris Certains utilisateurs ne peuvent pas utiliser une souris, il est donc important de s'assurer que votre site Web peut être navigué à l'aide du clavier. Vérifiez-vous que tous les éléments interactifs peuvent être sélectionnés et activés à l'aide de la touche Tab. 

Exemple de code HTML et CSS:
```html
<a href="#" class="bouton">Cliquez ici</a>
```
```css
.bouton {
  display: inline-block;
  padding: 10px 20px;
  background-color: #ccc;
  color: #fff;
}

.bouton:focus {
  outline: 2px solid blue;
}
```

7 - Fournissez des sous-titres pour les vidéos et les enregistrements audio Les sous-titres pour les vidéos et les enregistrements audio aident les utilisateurs sourds ou malentendants à comprendre le contenu. Utilisez des sous-titres synchronisés avec la vidéo ou l'audio pour assurer une expérience cohérente et compréhensible pour tous les utilisateurs. 

Exemple de code HTML:
```html
<video controls>
  <source src="ma-video.mp4" type="video/mp4">
  <track src="sous-titres.vtt" kind="subtitles" srclang="fr" label="Français">
</video>
```

8 - Évitez d'utiliser uniquement la couleur pour transmettre des informations. Les utilisateurs qui ne peuvent pas distinguer certaines couleurs peuvent manquer des informations importantes si celles-ci sont uniquement transmises par la couleur. Utilisez des symboles, des étiquettes ou un autre moyen pour transmettre les informations. 

Exemple de code HTML :
```html
<div class="alerte" role="alert">
  <span class="icone" aria-hidden="true">!</span>
  <p>Message d'alerte</p>
</div>
```

9 - Utilisez des polices lisibles et évitez les styles de police excessifs Utilisez des polices lisibles pour le contenu principal et évitez d'utiliser des styles de police excessifs tels que les lettres en majuscules ou les styles de police fantaisistes qui peuvent rendre le contenu difficile à lire. 

Exemple de code CSS :
```css
body {
  font-family: Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
}

h1 {
  font-size: 32px;
  font-weight: bold;
  margin-bottom: 20px;
}
```

10 - Testez votre site Web avec des outils d'accessibilité et des utilisateurs réels Il est important de tester régulièrement votre site Web pour vous assurer qu'il est accessible à tous les utilisateurs. Utilisez des outils d'accessibilité tels que WAVE ou Lighthouse pour identifier les problèmes d'accessibilité et faites tester votre site par des utilisateurs réels pour obtenir des commentaires supplémentaires.

---
## Les balises 

1 -Balise ``title`` pour les privilèges La balise ``title`` est utilisée pour fournir une description supplémentaire pour les privilèges. Elle est également utilisée par les lecteurs d'écran pour aider les utilisateurs à comprendre le contexte du lien. 

Exemple de code HTML:
```html
<a href="https://mon-site-web.com" title="Visitez mon site Web">Mon site Web</a>
```

2 - Balise ``aria-label`` pour les éléments sans texte explicite La balise ``aria-label`` est utilisée pour fournir une étiquette explicite pour les éléments qui n'ont pas de texte explicite, tels que les icônes ou les images. 

Exemple de code HTML:
```html
<button aria-label="Ouvrir le menu">
  <i class="fa fa-bars"></i>
</button>
```

3 - Balise ``role`` pour les éléments personnalisés La balise ``role`` est utilisée pour décrire le rôle de l'élément dans la page Web, notamment pour les éléments personnalisés tels que les menus déroulants. 

Exemple de code HTML:
```html
<nav role="navigation">
  <ul>
    <li><a href="#">Accueil</a></li>
    <li><a href="#">À propos</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

4 - Balise ``tabindex`` pour la navigation au clavier La balise ``tabindex`` est utilisée pour définir l'ordre de tabulation des éléments au clavier. Elle permet aux utilisateurs qui naviguent avec le clavier de se déplacer facilement sur le site. 

Exemple de code HTML:
```html
<div tabindex="0">Je suis un élément de navigation</div>
```

5 - Balise ``lang`` pour la langue du contenu La balise ``lang`` est utilisée pour indiquer la langue du contenu sur la page Web. Cela aide les lecteurs d'écran à prononcer correctement le contenu pour les utilisateurs qui parlent une autre langue que la langue principale de la page. 

Exemple de code HTML:
```html
<html lang="fr">
  <head>
    <title>Mon site Web</title>
  </head>
  <body>
    <h1>Bienvenue sur mon site Web</h1>
    <p>Le contenu de cette page est en français.</p>
  </body>
</html>
```

---

## Les balises Aria 

1 - ``aria-labelledby`` Cet attribut est utilisé pour indiquer l'ID d'un élément qui décrit le contenu de l'élément actuel. Il est utilisé pour fournir une description plus détaillée de l'élément. 

Exemple :
```html
<button id="titre-description" aria-labelledby="titre-description">Cliquez ici</button>
<p id="titre-description">Ce bouton vous permet de valider votre commande.</p>
```

2 - ``aria-describedby`` Cet attribut est utilisé pour indiquer l'ID d'un élément qui décrit le contenu de l'élément actuel. Il est utilisé pour fournir des informations supplémentaires sur l'élément. 

Exemple :
```html
<input type="text" id="nom" aria-describedby="info-nom">
<p id="info-nom">Veuillez entrer votre nom et prénom.</p>
```

3 - ``aria-label`` Cet attribut est utilisé pour fournir une étiquette à un élément qui n'a pas de texte visible. Il est utilisé pour rendre l'élément compréhensible pour les technologies d'assistance. 

Exemple :
```html
<button aria-label="Ouvrir le menu">Menu</button>
```

4 - ``aria-hidden`` Cet attribut est utilisé pour masquer un élément de la page Web aux technologies d'assistance. Il est utilisé pour masquer des éléments décoratifs ou redondants. 

Exemple :
```html
<div class="icone" aria-hidden="true">...</div>
```

5 - ``aria-disabled`` Cet attribut est utilisé pour indiquer qu'un élément est désactivé. Il est utilisé pour indiquer qu'un bouton ou un champ de formulaire ne peut pas être utilisé. 

Exemple :
```html
<button aria-disabled="true">Valider</button>
```

6 - ``aria-selected`` Cet attribut est utilisé pour indiquer qu'un élément a été sélectionné. Il est utilisé pour les listes déroulantes ou les menus. 

Exemple :
```html
<select aria-selected="true">
  <option value="1">Option 1</option>
  <option value="2">Option 2</option>
  <option value="3">Option 3</option>
</select>
```

7 - ``aria-haspopup`` Cet attribut est utilisé pour indiquer qu'un élément a un menu déroulant ou une fenêtre contextuelle. Il est utilisé pour indiquer qu'un clic sur l'élément ouvre une fenêtre contextuelle. 

Exemple :
```css
<button aria-haspopup="true">Menu</button>
```

8 - ``aria-controls`` Cet attribut est utilisé pour indiquer l'ID de l'élément contrôlé par l'élément actuel. Il est utilisé pour relier des éléments tels que les onglets et leur contenu associé. 

Exemple :
```html
<div id="contenu-onglet-1" aria-labelledby="onglet-1">Contenu de l'onglet 1</div>
<button id="onglet-1" aria-controls="contenu-onglet-1">Onglet 1</button>
```


