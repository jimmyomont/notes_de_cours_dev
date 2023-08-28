# JAVASCRIPT 
---
## Fondamentaux : 

Déclarer le type (const, let ou var ) par un nom (l'index) avec l'attribution ( = )  d'une valeur ( fonction ,string, number, boléen, etc)
```js 
const index = valeur 
let valeur = 2 + 4 // console.log(valeur) affiche -> 6
var string = "ceci est un test !" // console.log(string) affiche -> ceci est un test !
```

---
## Variables et types de données :

- Déclaration de variables : let variableName = value;
- Types de données : Number, String, Boolean, Array, Object, Null, Undefined, Symbol
- Convertir une chaîne de caractères en nombre : parseInt(string)
- Convertir un nombre en chaîne de caractères : toString()
- Concaténer des chaînes de caractères : "string1" + "string2"
- Comparaison de valeurs : == pour comparer une valeur et === pour comparer la valeur et le type (chaîne de caractère, boléen etc )

---

## Opérateurs :

- Opérateurs mathématiques : + (addition), - (soustraction), * (multiplication), / (division), % (modulo)
- Opérateurs de comparaison : == (égal à valeur), === (égal à type/valeur) != (différent de), > (supérieur à), < (inférieur à), >= (supérieur ou égal à), <= (inférieur ou égal à)
- Opérateurs logiques : && (et), || (ou), ! (non)

---

## Boucles et conditions :

- Boucle for : for (let i = 0; i < array.length; i++) { }
- Boucle while : while (condition) { }
- Condition if : if (condition) { } else if (condition) { } else { }
- Switch :

``` javascript
switch(expression) {
  case x:
    // code à exécuter si expression === x
    break;
  case y:
    // code à exécuter si expression === y
    break;
  default:
    // code à exécuter si expression ne correspond à aucun cas
}
```
---

## Fonctions :

- Déclaration de fonction :
 ```javascript
function functionName(parameters) {
  // code à exécuter
}
```
- Appel de fonction : functionName(arguments)
- Fonction fléchée : (parameters) => { // code à exécuter }
- Fonction récursive :

```javascript
function recursiveFunction(parameter) {
  if (condition) {
    return value;
  } else {
    recursiveFunction(newParameter);
  }
}
```

---

## Objets et tableaux :
### Objet

- Déclaration d'un objet : 

```js
let objectName = { property1: value1, property2: value2 };
```

- Accéder à une propriété d'un objet : 

```js
objectName.propertyName ou objectName["propertyName"];
```

- Ajouter une propriété à un objet : 

```js
objectName.newProperty = value;
```

- Supprimer une propriété d'un objet :

 ```js
 delete objectName.propertyName;
  ```

### tableau

- Déclaration d'un tableau : 

```js
let arrayName = [value1, value2, value3]; 
```

- Ajouter un élément à un tableau : 

```js
arrayName.push(value);
```

- Supprimer le dernier élément d'un tableau : 

```js
arrayName.pop();
```

- Accéder à un élément d'un tableau : 

```js
arrayName[index]; 
```

