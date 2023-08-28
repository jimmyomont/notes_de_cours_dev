# CSS 
---

- ## Sélecteur
```
selector { property: value; } : sélectionne un élément HTML et applique la propriété et la valeur données.
```
- ## Modèle de boîte
- ## Mise en page
- ## Typographie
- ## Arrière-plan et bordure
- ## Autres
---
# Model de boite

### Dimension :
- ``width``: permet de spécifier la largeur de l'élément.
- ``height``: permet de spécifier la hauteur de l'élément.
- ``max-width``: permet de qualifier la largeur maximale de l'élément.
- ``max-height``: permet de spécifier la hauteur maximale de l'élément.
- ``min-width``: permet de spécifier la largeur minimale de l'élément.
- ``min-height``: permet de spécifier la hauteur minimale de l'élément.
### Marge :
- ``margin``: permet de spécifier la marge autour de l'élément (en haut, à droite, en bas et à gauche).
- ``margin-to``p: permet de spécifier la marge supérieure de l'élément.
- ``margin-righ``t: permet de spécifier la marge droite de l'élément.
- ``margin-botto``m: permet de spécifier la marge inférieure de l'élément.
- ``margin-left``: permet de spécifier la marge gauche de l'élément.
### Bordure :
- ``border``: permet de spécifier la bordure autour de l'élément.
- ``border-width``: permet de spécifier la largeur de la bordure.
- ``border-style``: permet de spécifier le style de la bordure (par exemple, plein, pointillé, tireté, double, sillon, strié, encart, départ).
- ``border-color``: permet de spécifier la couleur de la bordure.
### marge exterieur :
- ``padding``: permet de spécifier le rembourrage à l'intérieur de la bordure de l'élément (en haut, à droite, en bas et à gauche).
- ``padding-top``: permet de spécifier le rembourrage supérieur de l'élément.
- ``padding-righ``t: permet de caractéristiques le rembourrage droit de l'élément.
- ``padding-bottom``: permet de caractériser le rembourrage inférieur de l'élément.
- ``padding-left``: permet de spécifier le rembourrage gauche de l'élément.
### Positionnement :
- ````position````: permet de caractériser le type de positionnement de l'élément (par exemple, statique, relatif, absolu, fixe, collant).
- ````top```` : permet de spécifier la distance entre le bord supérieur de l'élément et le bord supérieur de son conteneur désigné.
- ````right```` : permet de spécifier la distance entre le bord droit de l'élément et le bord droit de son conteneur désigné.
- ````bottom```` : permet de spécifier la distance entre le bord inférieur de l'élément et le bord inférieur de son conteneur désigné.
- ````left```` : permet de spécifier la distance entre le bord gauche de l'élément et le bord gauche de son conteneur désigné.
### Affichage :
- ``display``: permet de préciser le type d'affichage de l'élément (par exemple, block, inline, inline-block, none).
- ``visibility``: permet de caractéristiques si l'élément est visible ou caché.
### Autres :
- ``box-sizing`` : permet de spécifier si la largeur et la hauteur d'un élément incluent le remplissage et la bordure, ou non.

---
# Mise en page 

### Affichage des éléments : 

- ``display: block``: un élément de type bloc prend tout l'espace horizontal disponible et commence sur une nouvelle ligne.
- ``display: inline``: un élément en ligne ne commence pas sur une nouvelle ligne et ne prend que l'espace horizontal nécessaire.
- ``display: inline-block``: un élément en ligne-bloc se comporte comme un élément en ligne, mais permet de définir une largeur et une hauteur.
- ``display: flex``: permet de créer des mises en page flexibles avec des éléments alignés en ligne ou en colonne.
- ``display: grid``: permet de créer des mises en page en grille avec des éléments placés dans des cellules de grille.
- ``display: table``: permet de créer des mises en page en tableau avec des éléments placés dans des cellules de tableau.
- ``d- isplay: none``: masque l'élément et ne prend pas de place sur la page.

### Position :
- ``position: static``: l'élément est établi selon l'ordre normal du document.
- ``position: relative``: l'élément est établi par rapport à sa position normale.
- ``position: absolute``: l'élément est établi par rapport à son parent le plus proche qui a une position relative, absolue ou fixe.
- ``position: fixed``: l'élément est défini par rapport à la fenêtre d'affichage et reste à la même position même lorsque la page est défilée.
- ``position: sticky``: l'élément est établi par rapport à sa position normale jusqu'à ce qu'il atteint un seuil, puis reste collé à cette position.

### Flexbox :
- ``display: flex``: permet de créer un conteneur de boîtes flexibles.
- ``flex-direction``: permet de spécifier la direction des boîtes flexibles (par exemple, row, column, row-reverse, column-reverse).
- ``justify-content``: permet de spécifier l'alignement horizontal des boîtes flexibles (par exemple, flex-start, center, flex-end, space-between, - space-around).
- ``align-items``: permet de spécifier l'alignement vertical des boîtes flexibles (par exemple, flex-start, center, flex-end, stretch).
- ``align-self``: permet de spécifier l'alignement vertical d'une boîte flexible spécifique.
- ``flex-wrap``: permet de spécifier si les boîtes flexibles doivent être sur une ligne unique ou sur plusieurs lignes.
### Grid :
- ``display``: grid: permet de créer un conteneur de grille.
- ``grid-template-columns``: permet de spécifier la largeur des colonnes de grille.
- ``grid-template-rows``: permet de spécifier la hauteur des lignes de grille.
- ``grid-gap``: permet de spécifier l'espacement entre les cellules de la grille.
- ``grid-column``: permet de spécifier les cellules de grille sur lesquelles un élément doit être placé.
- ``grid-row``: permet de spécifier les cellules de grille sur lesquelles un élément doit être placé.
### Tableaux :
- ``border-collapse``: permet de spécifier comment les bordures des cellules de tableau se combinent.
- ``border-spacing``: permet de spécifier l'espacement entre les cellules de tableau.
- ``caption-side``: permet de spécifier l'emplacement de la légende d'un tableau.
### Float :
- ``float: left``: fait flotter l'élément sur le côté gauche de son conteneur.
- ``float: right``: fait flotter l'élément sur le côté droit de son conteneur.
- ``float: none``: désactive le flottement de l'élément.
### Clear :
- ``clear: left``: l'élément est déplacé en dessous de tous les éléments flottants à gauche.
- ``clear: right``: l'élément est déplacé en dessous de tous les éléments flottants à droite.
- ``clear: both``: l'élément est déplacé en dessous de tous les éléments flottants à gauche et à droite.
- ``clear: none``: ne déplace pas l'élément par rapport aux éléments flottants.
### Débordement : 
- ``overflow: visible``: le contenu qui dépasse la taille de l'élément est visible en dehors de la bordure.
- ``overflow: hidden``: le contenu qui dépasse la taille de l'élément est caché et ne peut pas être vu.
- ``overflow: scroll``: le contenu qui dépasse la taille de l'élément est affiché avec une barre de défilement.
- ``overflow: auto``: le navigateur décide automatiquement si une barre de défilement est nécessaire.
### Marge et rembourrage :
- ``margin``: définit la marge autour d'un élément. Les valeurs peuvent être indiquées pour chaque bordure (haut, droite, bas, gauche).
- ``padding``: permet de spécifier le rembourrage à l'intérieur de la bordure de l'élément (en haut, à droite, en bas et à gauche).

---
# Typographie 

### Police de caractères :
- ``font-family``: définit la police de caractères à utiliser.
- ``font-size``: définit la taille de la police de caractères.
- ``font-weight``: définit l'épaisseur de la police de caractères.
- ``font-style``: définit le style de la police de caractères (normal, italique, oblique, etc.).
- ``font-variant``: définit la variante de la police de caractères (normal, small-caps).
### Couleur de texte :
- ``color``: définit la couleur du texte.
### Alignement de texte :
- ``text-align``: définit l'alignement horizontal du texte (gauche, droite, centré, justifié).
- ``text-justify``: définit l'alignement justifié du texte.
- ``text-indent``: définit l'indentation du premier caractère de la première ligne d'un texte.
### Espacement de texte :
- ``letter-spacing``: définit l'espacement horizontal entre les caractères.
- ``word-spacing``: définit l'espacement horizontal entre les mots.
### Décoration de texte :
- ``text-decoration``: définit la décoration du texte (underline, overline, line-through, none).
- ``text-shadow``: définit l'ombre du texte.
### Casse de texte :
- ``text-transform``: définit la transformation de casse du texte (majuscule, minuscule, majuscule).
### Interligne :
- ``line-height``: définit la hauteur de ligne de texte.
- ``vertical-align``: définit l'alignement vertical d'un élément de texte.
### Autres :
- ``text-overflow``: spécifique ce qui doit se passer si le texte d'un élément dépasse sa taille.
- ``white-space``: définit la façon dont les espaces sont gérés dans le texte.
- ``direction``: définit la direction de l'écriture (ltr, rtl).
- ``unicode-bidi``: définit la direction d'écriture pour les langues qui utilisent des scripts non latins.

---
# Couleurs et arrière plan 

### Couleur de fond :
- ``background-color``: définit la couleur de fond d'un élément.
### Image de fond :
- ``background-image``: définit une image de fond pour un élément.
- ``background-repeat``: définit la répétition de l'image de fond.
- ``background-position`` : définit la position de l'image de fond.
- ``background-size``: définit la taille de l'image de fond.
### Gradient de fond :
- ``background``: définit un gradient de fond linéaire ou radial.
### Transparence :
- ``opacity``: définit l'opacité d'un élément.
### Couleur de texte :
- ``color``: définit la couleur du texte.
### Couleur de bordure :
- ``border-color``: définit la couleur de la bordure d'un élément.
- ``border-top-color``: définit la couleur de la bordure supérieure d'un élément.
- ``border-right-color``: définit la couleur de la bordure droite d'un élément.
- ``border-bottom-color``: définit la couleur de la bordure inférieure d'un élément.
- ``border-left-color``: définit la couleur de la bordure gauche d'un élément.
### Couleur de texte sélectionné :
- ``::selection ``: définit la couleur de texte lorsque du texte est sélectionné.

---
# Bordures et décoration
### Bordures : 
- ``border``: définit la bordure d'un élément (largeur, style et couleur).
- ``border-style``: définit le style de la bordure (solid, dashed, dotted, double, groove, ridge, inset, outset, none, hidden).
- ``border-width``: définit la largeur de la bordure.
- ``border-color``: définit la couleur de la bordure.
- ``border-top, border-right, border-bottom, border-left``: définit une bordure individuelle pour chaque côté de l'élément.
### Rayures et dégradés :
- ``background-image``: peut être utilisé pour créer des rayures et des dégradés en définissant une image de fond spéciale.
- ``linear-gradient()``: peut être utilisé pour créer un dégradé linéaire.
- ``repeating-linear-gradient()``: peut être utilisé pour créer un dégradé linéaire répété.
- ``radial-gradient()``: peut être utilisé pour créer un dégradé radial.
### Ombres :
- `` box-shadow``: définit l'ombre de l'élément (position, étendue, couleur).
- ``text-shadow``: définit l'ombre du texte (position, étendue, couleur).
### Autres décorations :
- ``text-decoration``: définit la décoration du texte (underline, overline, line-through, none).
- ``list-style``: définit le style de la liste (type de marqueur, position).
- ``outline``: définit une ligne autour de l'élément qui ne modifie pas sa taille ou sa position (style, largeur, couleur).
- ``outline-offset``: définit la distance entre l'élément et sa ligne de contour.

---

# Effets et animations
### Transformations :
- ``transform``: permet de déplacer, faire pivoter, agrandir/réduire et tordre des éléments.
- ``translate``: permet de déplacer un élément dans une direction spécifiée.
- ``rotate``: permet de faire pivoter un élément autour de son point d'origine.
- scale: permet de changer la taille d'un élément.
- ``skew``: permet de déformer un élément selon un angle spécifié.
### Transition :
- ``transition``: permet de définir une transition entre les états d'un élément, en spécifiant les propriétés CSS qui doivent changer, la durée de la - transition et la fonction de timing utilisée pour l'animation.
### Animation :
- ``@keyframes``: permet de définir une série d'étapes pour une animation.
- ``animation-name``: permet de spécifier le nom de l'animation définie avec @keyframes.
- ``animation-duration``: définit la durée de l'animation.
- ``animation-timing-function``: définit la fonction de timing pour l'animation.
- ``animation-dela``y: définit le délai avant le début de l'animation.
- ``animation-iteration-count``: définit le nombre de fois que l'animation doit être répétée.
- ``animation-direction``: définit la direction de l'animation (normal, reverse, alternate, alternate-reverse).
- ``animation-play-state``: permet de mettre en pause ou de reprendre une animation en cours.
### Effets visuels :
- ``box-shadow``: permet de créer une ombre autour d'un élément.
- ``text-shadow``:  permet de créer une ombre autour du texte.
- ``opacity``: permet de rendre un élément plus ou moins transparent.
- ``filter``: permet d'appliquer des effets visuels comme le flou, la saturation, la luminosité, etc.
- ``backdrop-filter``: permet d'appliquer des effets visuels au contenu derrière un élément.
- ``perspective``: permet de définir la perspective pour les transformations 3D.

---
# Interactivité
### Curseur :
- ``cursor``: permet de changer l'apparence du curseur de la souris lorsqu'il survole un élément (par exemple, pointer, main, wait, text, etc.).
### Sélection de texte :
- `` user-select``: permet de contrôler si un utilisateur peut sélectionner du texte sur une page Web (par exemple, none pour empêcher la sélection).
### Visibilité et affichage :
- ``visibility``: permet de contrôler la visibilité d'un élément (par exemple, hidden pour le masquer).
- ``display``: permet de contrôler comment un élément est affiché (par exemple, none pour le cacher complètement, block pour le transformer en un bloc, inline pour le transformer en une ligne).
### Positionnement :
- ``position``: permet de définir le type de positionnement utilisé pour un élément (par exemple, static, relative, absolute, fixed, sticky).
- top, right, bottom, left: permettent de définir les distances entre les bords de l'élément et les bords de son conteneur lorsque l'élément est positionné.
### Opacité et transparence :
- ``opacity``: permet de définir la transparence d'un élément (0 = complètement transparent, 1 = complètement opaque).
- ``backdrop-filter``: permet d'appliquer des effets visuels à l'arrière-plan derrière un élément (par exemple, flou).
### Actions :
- ``:hover``: permet de définir un style lorsque l'utilisateur survole un élément avec sa souris.
- :``active``: permet de définir un style lorsque l'utilisateur clique sur un élément.
- :``focus``: permet de définir un style lorsque l'utilisateur donne le focus à un élément (par exemple, avec la touche Tab).
### Autres :
- ``overflow``: permet de contrôler le comportement de dépassement du contenu d'un élément lorsqu'il dépasse ses limites.
- ``z-index``: permet de définir l'ordre d'empilement des éléments positionnés.

---
# Autres

### Multi-colonnes :
- ``column-count``: permet de spécifier le nombre de colonnes souhaité.
- ``column-gap``: permet de spécifier l'espacement entre les colonnes.
- ``column-width`` : permet de spécifier la largeur de chaque colonne.
### Variables CSS :
- ``--nom-variable``: valeur : permet de définir une variable CSS personnalisée.
- ``var(--nom-variable)``: permet d'utiliser une variable CSS personnalisée.