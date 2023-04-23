# ALGORITHME 
---

## Variables :
```js
// Déclare une variable pour stocker l'âge
let age = 25;
// Déclare une constante pour stocker le nom
const name = "John";
// Déclare une variable booléenne pour indiquer si l'utilisateur est un étudiant
var isStudent = true;

```
## Structures de données :
```js
// Déclare un tableau de nombres
let numbers = [2, 5, 1, 8, 4];
// Déclare un tableau de chaînes de caractères
let fruits = ["apple", "banana", "orange"];
// Déclare une pile vide
let stack = [];
// Ajoute deux éléments à la pile
stack.push(1);
stack.push(2);
// Déclare une file vide
let queue = [];
// Ajoute deux éléments à la file
queue.push(3);
queue.push(4);
```
## Conditions :
```js
// Déclare une variable pour stocker un nombre
let x = 10;
// Vérifie si x est positif
if (x > 0) {
  console.log("x is positive");
// Vérifie si x est négatif
} else if (x < 0) {
  console.log("x is negative");
// Si x n'est ni positif ni négatif, il est zéro
} else {
  console.log("x is zero");
}
```
## Boucles :
```js
// Boucle for qui affiche les nombres de 0 à 4
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// Boucle while qui affiche les nombres de 0 à 4
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
// Boucle do-while qui affiche les nombres de 0 à 4
let j = 0;
do {
  console.log(j);
  j++;
} while (j < 5);
```
## Fonctions :
```js
// Déclare une fonction qui ajoute deux nombres
function addNumbers(a, b) {
  return a + b;
}
// Appelle la fonction et stocke le résultat dans une variable
let sum = addNumbers(2, 3);
// Affiche le résultat
console.log(sum);
```
## Algorithme de tri 
```js
// Déclare un tableau de nombres
let numbers = [2, 5, 1, 8, 4];
// Trie le tableau par ordre croissant
numbers.sort(function(a, b){return a - b});
// Affiche le tableau trié
console.log(numbers);
```
## Recherche d'algorithmes :
```js
// Déclare un tableau de nombres
let numbers = [2, 5, 1, 8, 4];
// Recherche l'index du nombre 5 dans le tableau
let index = numbers.indexOf(5);
// Affiche l'index
console.log(index);
```
## Récursivité :
```js
// Déclare une fonction qui calcule le factoriel d'un nombre
function factorial(n) {
  // Cas de base : si n est inférieur ou égal à 1, retourne 1
  if (n <= 1) {
    return 1;
  // Cas récursif : multiplie n par le factoriel de n-1
  } else {
    return n * factorial(n - 1);
  }
}
// Appelle la fonction avec le nombre 5
let result = factorial(5);
// Affiche le résultat
console.log(result);
```
## Complexité algorithmique :
```js
// Déclare un tableau de nombres non triés
let numbers = [5, 2, 8, 1, 4];
// Trie le tableau dans l'ordre croissant
numbers.
numbers
sort((a, b) => a - b);
// Affiche le tableau trié
console.log(numbers);
```
## Programmation orientée objet :
```js
// Définit une classe Person
class Person {
  // Définit un constructeur qui prend un nom et un âge en argument
  constructor(name, age) {
    // Définit les propriétés name et age de l'objet créé
    this.name = name;
    this.age = age;
  }
  // Définit une méthode sayHello qui affiche un message de salutation
  sayHello() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

// Crée un nouvel objet Person avec le nom "John" et l'âge 25
let john = new Person("John", 25);

// Appelle la méthode sayHello sur l'objet john
john.sayHello();
// ce qui affiche le message : "Bonjour, je m'appelle Jean et j'ai 25 ans."
```
