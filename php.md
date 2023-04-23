# PHP
---
## Balise d'ouverture et de fermeture PHP :
La balise d'ouverture ``<?php`` et la balise de fermeture ``?>`` sont utilisées pour délimiter le code PHP à l'intérieur d'un fichier HTML. Tout le code PHP doit être compris entre ces balises.

Exemple :

```php
<!DOCTYPE html>
<html>
<head>
	<title>Exemple de page PHP</title>
</head>
<body>
	<?php
		// Code PHP ici
	?>
</body>
</html>
```
---

## Affichage de texte :

La fonction ``echo`` est utilisée pour afficher du texte ou des variables sur une page web et pour sauter une ligne utiliser l'annotation ``"\n"``.

Exemple :

```php 
<?php
	echo "Bonjour,\n monde!";
    //Sera ecrit comme suit : 
    bonjour,
    monde!

?>
```
---
## Déclaration de variables :
Les variables en PHP sont précédées du symbole ``$`` .

Exemple :

```php
<?php
	$message = "Bonjour, monde!";
	echo $message;
?>
```

---
## Structures conditionnelles :
Les structures conditionnelles permettent d'exécuter le code en fonction d'une condition.

Exemple :

```php
<?php
	$age = 18;

	if ($age >= 18) {
		echo "Vous êtes majeur.";
	} else {
		echo "Vous êtes mineur.";
	}
?>
```
---
## Boucles :
Les boucles permettent de répéter l'exécution d'un code un certain nombre de fois.

Exemple de boucle ``for`` :

```php
<?php
	for ($variable = 0; $variable < 10; $variable++) {
		echo $variable;
	}
?>
```

Exemple de boucle ``for-of`` soit ``foreach`` en "PHP" :

```php
$array = array(1, 2, 3, 4, 5);

foreach ($array as $value) {
  echo $value . "\n";
}
```


Exemple de boucle while :

```php
<?php
	$variable = 0;

	while ($variable < 10) {
		echo $variable;
		$variable++;
	}
?>
```
---
### Tableaux :
Les tableaux permettent de stocker plusieurs valeurs dans une seule variable.

Exemple :

```php
<?php
	$fruits = array("pomme", "banane", "orange");

	echo "Le deuxième fruit est " . $fruits[1];
?>
```
---
## Fonctions :
Les fonctions permettent de regrouper du code qui peut être appelé plusieurs fois dans un programme.

Exemple :

```php
<?php
	function addition($a, $b) {
		return $a + $b;
	}

	echo addition(2, 3); // Affiche 5
?>
```
---
## Traitement de formulaires :
Les formulaires permettent à l'utilisateur de saisir des données qui sont envoyées au serveur pour traitement. Les données sont récupérées en utilisant les superglobales ``$_GET`` ou ``$_POST``.

Exemple :

```php
<!DOCTYPE html>
<html>
<head>
	<title>Formulaire</title>
</head>
<body>
	<form method="POST" action="traitement.php">
		<label for="nom">Nom :</label>
		<input type="text" id="nom" name="nom"><br>

		<label for="prenom">Prénom :</label>
		<input type="text" id="prenom" name="prenom"><br>

		<input type="submit" value="Envoyer">
	</form>
</body>
</html>
```

Dans le fichier de traitement "traitement.php" :

```php
<?php
	$nom = $_POST['nom'];
	$prenom = $_POST['prenom'];

	echo "Bonjour $prenom $nom!";
?>
```
---

## Inclusion de fichiers :
La fonction ``include`` permet d'inclure le code provenant d'un autre fichier "PHP" dans le fichier courant.

Exemple :

```php 
<?php
	include 'config.php';

	// Utilisation des variables et fonctions définies dans un fichier config.php
?>
```
---
## Connexion à une base de données :
La fonction ``mysqli_connect`` permet de se connecter à une base de données "MySQL".

Exemple :

```php
<?php
	$serveur = "localhost";
	$utilisateur = "nom_utilisateur";
	$mot_de_passe = "mot_de_passe";
	$base_de_donnees = "nom_de_la_base";

	$connexion = mysqli_connect($serveur, $utilisateur, $mot_de_passe, $base_de_donnees);

	// Utilisation de la connexion à la base de données
?>
```
---
## Requêtes SQL :
Les requêtes "SQL" permettent de récupérer, ajouter, modifier ou supprimer des données dans une base de données.

Exemple de requête ``SELECT`` :

```php
<?php
	$resultat = mysqli_query($connexion, "SELECT * FROM utilisateurs");

	while ($ligne = mysqli_fetch_assoc($resultat)) {
		echo "Nom : " . $ligne['nom'] . ", prénom : " . $ligne['prenom'];
	}
?>
```

Exemple de requête ``INSERT`` :

```php
<?php
	$nom = "Dupont";
	$prenom = "Jean";

	mysqli_query($connexion, "INSERT INTO utilisateurs (nom, prenom) VALUES ('$nom', '$prenom')");
?>
```
---
## Gestion des erreurs :
La fonction ``mysqli_error`` permet de récupérer le message d'erreur renvoyé par "MySQL" en cas d'échec d'une requête.

Exemple :

```php
<?php
	$resultat = mysqli_query($connexion, "SELECT * FROM utilisateurs");

	if (!$resultat) {
		echo "Erreur : " . mysqli_error($connexion);
	}
?>
```
---
## Envoi de mails :
La fonction ``mail`` permet d'envoyer un mail en "PHP".

Exemple :

```php
<?php
	$destinataire = "adresse_destinataire@exemple.com";
	$sujet = "Test de mail";
	$message = "Bonjour, ceci est un test.";

	mail($destinataire, $sujet, $message);
?>
```
---
## Manipulation de fichiers :
Les fonctions ``fopen`` , ``fwrite`` et ``fclose`` permettent de créer et d'écrire dans un fichier en "PHP".

Exemple :

```php
<?php
	$fichier = fopen("fichier.txt", "w");
	fwrite($fichier, "Bonjour, monde!");
	fclose($fichier);
?>
```
---
## Session :
Les sessions permettent de stocker des variables qui sont accessibles sur plusieurs pages du site.

Exemple :

```php
<?php
	session_start();

	$_SESSION['nom_utilisateur'] = "Jean";

	// Utilisation de la variable de session
?>
```







