# TinyMCE

#### Editeur de texte JavaScript qui permet d'intégrer facilement des fonctionnalités de traitement de texte dans les applications web.

#### Installation de TinyMCE

1. **Téléchargement** : [site officiel de TinyMCE](https://www.tiny.cloud/get-tiny/) et télécharger la dernière version de TinyMCE.

2. **Intégration** :
   - Décompresser l'archive téléchargée.
   - Copiez le dossier `tinymce` dans votre projet web.

3. **Configuration** :
   - Dans la section `<head>` de vos pages HTML, ajouter le lien vers le script TinyMCE :
     ```html
     <script src="chemin/vers/tinymce/tinymce.min.js"></script>
     ```

4. **Utilisation** :
   - Utiliser le sélecteur pour cibler les éléments que vous souhaiter convertir en éditeurs TinyMCE :
     ```html
     <textarea id="myTextarea"></textarea>
     <script>
       tinymce.init({
         selector: '#myTextarea'
       });
     </script>
     ```

#### Configuration de base de TinyMCE

Configuration de base pour TinyMCE :

```javascript
tinymce.init({
  selector: 'textarea',
  plugins: 'autolink lists link image',
  toolbar: 'undo redo | formatselect | bold italic | alignleft aligncenter alignright | bullist numlist outdent indent | link image',
  height: 500
});
```

#### Personnalisation de la Barre d'Outils

Modifier la propriété `toolbar` pour personnaliser la barre d'outils de TinyMCE selon vos besoins.

#### Gestion des Événements

Utiliser la méthode `setup` pour gérer les événements de TinyMCE. Par exemple :

```javascript
tinymce.init({
  selector: 'textarea',
  setup: function(editor) {
    editor.on('change', function(e) {
      console.log('Contenu modifié : ', e.target.getContent());
    });
  }
});
```

#### Documentation

[documentation officielle de TinyMCE](https://www.tiny.cloud/docs/) pour plus d'informations et de détails sur la configuration et l'utilisation avancée.

---

### TinyMCE : Configuration et Personnalisation Avancée

#### Configuration de base

```javascript
tinymce.init({
  selector: 'textarea', // Sélecteur de l'élément textarea à convertir en éditeur TinyMCE
  plugins: 'autolink lists link image charmap print preview anchor',
  toolbar: 'undo redo | formatselect | bold italic | alignleft aligncenter alignright | bullist numlist outdent indent | link image',
  height: 500 // Hauteur de l'éditeur
});
```
#### Configuration Avancée de TinyMCE

1. **Chemin vers les Fichiers** :
   - Utilisez les options `base_url` et `suffix` pour spécifier le chemin vers les fichiers TinyMCE :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       base_url: '/chemin/vers/tinymce/',
       suffix: '.min'
     });
     ```

2. **Langue** :
   - Définissez la langue de l'éditeur avec l'option `language` :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       language: 'fr_FR'
     });
     ```

3. **Formats de Texte** :
   - Personnalisez les formats de texte avec l'option `formats` :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       formats: {
         bold: { inline: 'span', styles: { fontWeight: 'bold' }},
         italic: { inline: 'span', styles: { fontStyle: 'italic' }}
       }
     });
     ```

#### Personnalisation Avancée de l'Interface

1. **Styles** :
   - Définissez des styles personnalisés avec l'option `style_formats` :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       style_formats: [
         { title: 'Custom Style', inline: 'span', styles: { color: '#ff0000' }},
         { title: 'Another Style', block: 'div', classes: 'another-style' }
       ]
     });
     ```

2. **Boutons Personnalisés** :
   - Ajoutez des boutons personnalisés à la barre d'outils avec la méthode `editor.ui.registry.addButton` :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       setup: function(editor) {
         editor.ui.registry.addButton('customButton', {
           text: 'Custom Button',
           onAction: function(_) {
             // Action du bouton personnalisé
           }
         });
       }
     });
     ```

3. **Formats de Blocs** :
   - Créez des formats de blocs personnalisés avec l'option `block_formats` :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       block_formats: 'Paragraph=p;Header 1=h1;Header 2=h2'
     });
     ```

#### Gestion des Événements Avancée

1. **Gestion des Événements** :
   - Utilisez la méthode `editor.on` pour gérer les événements de TinyMCE :
     ```javascript
     tinymce.init({
       selector: 'textarea',
       setup: function(editor) {
         editor.on('init', function() {
           console.log('Éditeur initialisé');
         });
         editor.on('change', function(e) {
           console.log('Contenu modifié : ', e.target.getContent());
         });
       }
     });
     ```

#### Personnalisation de la barre d'outils

```javascript
toolbar: 'undo redo | styleselect | bold italic | alignleft aligncenter alignright alignjustify | bullist numlist outdent indent | link image',
```

#### Personnalisation des formats

```javascript
formats: {
  bold: { inline: 'span', styles: { fontWeight: 'bold' }},
  italic: { inline: 'span', styles: { fontStyle: 'italic' }},
  underline: { inline: 'span', styles: { textDecoration: 'underline' }},
  strikethrough: { inline: 'span', styles: { textDecoration: 'line-through' }},
  customFormat: { block: 'h2', attributes: { class: 'custom-format' }}
},
```

#### Personnalisation des styles

```javascript
style_formats: [
  { title: 'Custom Style', inline: 'span', styles: { color: '#ff0000' }},
  { title: 'Another Style', block: 'div', classes: 'another-style' }
],
```

#### Gestion des événements

```javascript
tinymce.init({
  selector: 'textarea',
  setup: function(editor) {
    editor.on('init', function() {
      console.log('Éditeur initialisé');
    });
    editor.on('change', function(e) {
      console.log('Contenu modifié : ', e.target.getContent());
    });
  }
});
```

#### Personnalisation avancée

```javascript
tinymce.init({
  selector: 'textarea',
  skin_url: '/path/to/skin',
  content_css: '/path/to/content.css',
  extended_valid_elements: 'span[class|style]',
  branding: false // Désactive le branding TinyMCE
});
```

#### Personnalisation des boutons

```javascript
tinymce.init({
  selector: 'textarea',
  toolbar: 'customButton1 customButton2',
  setup: function(editor) {
    editor.ui.registry.addButton('customButton1', {
      text: 'Custom Button 1',
      onAction: function(_) {
        // Action du bouton personnalisé 1
      }
    });
    editor.ui.registry.addButton('customButton2', {
      text: 'Custom Button 2',
      onAction: function(_) {
        // Action du bouton personnalisé 2
      }
    });
  }
});
```
