# EDITER UN COMMIT (SUPPRIMER , FUSIONNER , RENOMMER , ...)

### 1 . Clonez le référentiel :

```bash
git clone <URL_du_référentiel>
```

### 2 . Accédez au répertoire du référentiel :

```bash
cd <nom_du_référentiel>
```

### 3 . Vérifiez l'historique des commits en utilisant la commande suivante :

```bash
git log
```
Notez les identifiants des commits que vous souhaitez supprimer.

### 4 . Utilisez la commande interactive rebase pour nettoyer les commits :

```bash
git rebase -i <commit_de_base>
```

Remplacez ``<commit_de_base>`` par l'identifiant du commit à partir duquel vous souhaitez commencer la rebase. Cela ouvrira un éditeur de texte avec une liste des commits.

### 5 . Dans l'éditeur de texte, modifiez le mot-clé ``"pick"`` ``(ou "p")`` devant chaque commit que vous souhaitez supprimer en utilisant l'une des autres options fournies* (par exemple, "squash" pour fusionner le commit avec le précédent, "edit" pour modifier le commit, etc.).

### 6 . Enregistrez les modifications et fermez l'éditeur de texte.**

### 7 . Git appliquera les modifications et ouvrira un autre éditeur de texte pour vous permettre de modifier le message de commit si vous avez fusionné des commits.

### 8 . Enregistrez les modifications et fermez l'éditeur de texte.

### 9 . Si vous avez supprimé des commits qui ont déjà été poussés sur GitHub, vous devrez utiliser l'option force-push pour mettre à jour le référentiel distant :

```bash
git push --force
```
Notez que l'utilisation de ``--force`` peut modifier l'historique des commits du référentiel, donc utilisez cette option avec précaution.

### * Liste et detail des options fournies 

- ``reword (r)`` : Cette option vous permet de modifier le message de commit d'un commit spécifique. Lorsque vous remplacez "pick" par "reword" ou "r", Git applique le commit comme d'habitude, mais ouvre ensuite l'éditeur de texte pour vous permettre de modifier le message du commit. Vous pouvez modifier le message, enregistrer les modifications et fermer l'éditeur pour appliquer le commit modifié.

- ``edit (e)`` : L'option "edit" vous permet de mettre en pause le processus de rebase après avoir appliqué un commit spécifique. Lorsque vous remplacez "pick" par "edit" ou "e", Git applique le commit, puis vous permet de faire des modifications supplémentaires, telles que modifier le contenu du commit, ajouter ou supprimer des fichiers, etc. Une fois que vous avez terminé vos modifications, vous pouvez utiliser la commande git rebase --continue pour continuer le processus de rebase.

- ``squash ``: L'option "squash" vous permet de fusionner un commit avec le précédent commit et de combiner les messages de commit. Lorsque vous remplacez "pick" par "squash", Git applique le commit, puis ouvre l'éditeur de texte pour vous permettre de modifier le message de commit combiné. Vous pouvez modifier le message, enregistrer les modifications et fermer l'éditeur pour fusionner le commit avec le précédent.

- ``fixup`` : L'option "fixup" est similaire à "squash", mais elle fusionne le commit avec le précédent commit en ignorant le message de commit. Lorsque vous remplacez "pick" par "fixup", Git applique le commit et l'associe au précédent commit, mais ne conserve que le message de commit du commit précédent.

- ``exec`` : L'option "exec" vous permet d'exécuter une commande shell spécifique pour un commit donné. Lorsque vous remplacez "pick" par "exec", Git applique le commit et exécute la commande shell spécifiée. Cela peut être utile pour effectuer des actions personnalisées en fonction du commit.

- ``drop ``: L'option "drop" supprime complètement le commit du processus de rebase. Lorsque vous remplacez "pick" par "drop", Git ignore le commit et le supprime de l'historique.

### * Sauvegarder et quitter 

#### Dans l'éditeur Vim :

Appuyez sur la touche ``Esc`` pour passer en mode normal.

Tapez ``:wq ``pour sauvegarder et quitter l'éditeur.

#### Dans l'éditeur Nano :

Appuyez sur ``Ctrl + O`` pour enregistrer le fichier.

Appuyez sur ``Ctrl + X`` pour quitter l'éditeur.
