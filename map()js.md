# METHODE MAP()

## La méthode ``map()`` est utilisée pour créer un nouveau tableau en appliquant une fonction à chaque élément d'un tableau existant. Elle retourne un nouveau tableau avec les résultats des appels à la fonction pour chaque élément du tableau d'origine.

### Syntaxe :
```js
const nouveauTableau = tableau.map((élémentCourant, index, tableau) => {
  // Code à exécuter pour chaque élément du tableau
  return résultat;
});
```

### Paramètre :

``élémentCourant``: L'élément en cours de traitement dans le tableau.

``index``: L'index de l'élément en cours de traitement dans le tableau.

``tableau``: Le tableau sur lequel map()a été appelé.

``Valeur de retour`` : 
Un nouveau tableau contenant les résultats des appels de la fonction pour chaque élément du tableau d'origine.

### Remarque :
map() ne modifiez pas le tableau d'origine, il retourne plutôt un nouveau tableau.

Exemple de code :

Supposons que nous ayons un tableau contenant des nombres et que nous voulions créer un nouveau tableau contenant le carré de chaque nombre.

```js
const nombres = [1, 2, 3, 4, 5];

// Utilisation de map() pour créer un nouveau tableau contenant le carré de chaque nombre
const carres = nombres.map((nombre) => {
  return nombre * nombre;
});

console.log(carres); // Résultat : [1, 4, 9, 16, 25]

//si nous voulons afficher le double 

const nombres = [1, 2, 3, 4, 5];

// Utilisation de map() pour créer un nouveau tableau contenant le carré de chaque nombre
const double = nombres.map((nombre) => {
  return nombre * 2;
});

console.log(double); // Résultat : [1, 4, 6, 8, 10]
```


## Autres exemples 


### Exemple simple avec un élémentCourant

```js
// Supposons que nous ayons un tableau de prénoms en minuscules
const prenomsMinuscules = ['alice', 'bob', 'caroline', 'david'];

// Utilisation de map() pour créer un nouveau tableau avec les prénoms en majuscules
const prenomsMajuscules = prenomsMinuscules.map((prenom) => {
  // La fonction fléchée prend chaque prénom (en minuscules) comme argument
  // et retourne le prénom en majuscules
  return prenom.toUpperCase();
});

console.log(prenomsMajuscules);
// Résultat : ['ALICE', 'BOB', 'CAROLINE', 'DAVID']
```
### Explications étape par étape :
1 - Nous avons un tableau ``prenomsMinuscules`` contenant des prénoms en minuscules.

2 - Nous utilisons la méthode ``map()`` pour créer un nouveau tableau appelé ``prenomsMajuscules``.

3 - ``map()`` itère sur chaque élément du tableau ``prenomsMinuscules``.

4 - Pour chaque prénom ( prenom) dans ``prenomsMinuscules``, la fonction fléchée est exécutée.

5 - La fonction prenom.toUpperCase()est utilisée pour convertir chaque prénom en majuscules.

6 - Le résultat de chaque appel de la fonction (prénom en majuscules) est ajouté au nouveau tableau ``prenomsMajuscules``.

7 - Une fois qu'a ``map()`` terminé de parcourir tous les éléments de ``prenomsMinuscules``, il renvoie un nouveau tableau contenant les prénoms en majuscules.

8 - Enfin, nous affichons ``prenomsMajuscules``dans la console, qui contient les prénoms transformés en majuscules.

### Exemple avec courant , index & tableau

```js
// Supposons que nous ayons un tableau de prénoms en minuscules
const prenomsMinuscules = ['alice', 'bob', 'caroline', 'david'];

// Utilisation de map() pour créer un nouveau tableau avec les prénoms en majuscules et leur longueur
const prenomsMajusculesEtLongueur = prenomsMinuscules.map((prenom, index, tableau) => {
  // La fonction de rappel prend trois arguments : prenom, index et tableau

  // prenom : élément courant (prénom en minuscules) en cours de traitement par map()
  // index : index de l'élément courant dans le tableau
  // tableau : le tableau d'origine (prenomsMinuscules) sur lequel map() a été appelé

  // Transformation du prénom en majuscules
  const prenomMajuscules = prenom.toUpperCase();

  // Calcul de la longueur du prénom
  const longueurPrenom = prenom.length;

  // Retourne un objet contenant le prénom en majuscules et sa longueur
  return {
    prenom: prenomMajuscules,
    longueur: longueurPrenom,
    index: index, // On ajoute également l'index à l'objet retourné
    tableauOriginal: tableau // On ajoute le tableau d'origine à l'objet retourné
  };
});

console.log(prenomsMajusculesEtLongueur);
// Résultat :
// [
//   { prenom: 'ALICE', longueur: 5, index: 0, tableauOriginal: ['alice', 'bob', 'caroline', 'david'] },
//   { prenom: 'BOB', longueur: 3, index: 1, tableauOriginal: ['alice', 'bob', 'caroline', 'david'] },
//   { prenom: 'CAROLINE', longueur: 8, index: 2, tableauOriginal: ['alice', 'bob', 'caroline', 'david'] },
//   { prenom: 'DAVID', longueur: 5, index: 3, tableauOriginal: ['alice', 'bob', 'caroline', 'david'] }
// ]

```

### Explications étape par étape :

1 - Nous avons un tableau prenomsMinusculescontenant des prénoms en minuscules.

2 - Nous utilisons la méthode map()pour créer un nouveau tableau prenomsMajusculesEtLongueur.

3 - map()itère sur chaque élément du tableau prenomsMinuscules.

4 - Pour chaque prénom ( prenom) dans prenomsMinuscules, la fonction de rappel est exécutée.

5 - Dans la fonction de rappel, nous utilisons prenompour obtenir l'élément courant (le prénom en minuscules).

6 - Nous l'utilisons également indexpour obtenir l'index de l'élément courant dans le tableau.

7 - tableaucontient le tableau d'origine ( prenomsMinuscules) sur lequel map()a été appelé.

8 - Nous transformons le prénom en majuscules et calculons sa longueur.

9 - Nous retournons un objet contenant le prénom en majuscules, sa longueur, l'index de l'élément et le tableau d'origine.

10 - map()ajoute chaque objet retourné au nouveau tableau prenomsMajusculesEtLongueur.

11 - Une fois qu'a map()terminé de parcourir tous les éléments de prenomsMinuscules, il renvoie le nouveau tableau prenomsMajusculesEtLongueurcontenant les objets avec les prénoms en majuscules, leur longueur, leur index et le tableau d'origine.