 # SYNCHRONE & ASYNCHRONE

## Programmation Synchrone :

- Dans la programmation synchrone, les instructions se déroulent les unes après les autres, de manière séquentielle.
- Chaque instruction doit être terminée avant que l'instruction suivante puisse être exécutée.
- Les opérations bloquantes, comme les appels réseaux ou les opérations I/O (Input/Output), peuvent provoquer des temps d'attente et ralentir l'exécution du programme.
- Les avantages de la programmation synchrone résidente dans sa simplicité et sa facilité à raisonner sur le flux d'exécution.

## Programmation Asynchrone :

- Dans la programmation asynchrone, les instructions ne s'exécutent pas séquentiellement les unes après les autres.
- Le programme peut lancer une tâche et continuer immédiatement avec les instructions suivantes sans attendre la fin de cette tâche.
- Les tâches asynchrones s'exécutent en arrière-plan et peuvent signaler leur achèvement ou leurs erreurs par le biais de callbacks, de promesses (promises) ou de mots-clés tels que "async/wait".
- L'asynchronisme est utile pour les opérations qui consomment du temps, comme les requêtes réseau ou les lectures/écritures de fichiers, car cela permet d'éviter les blocages et de maintenir une réactivité élevée de l'application.
- Exemple de programmation asynchrone en JavaScript avec "async/await" :
```js
async function fetchUserData() {
  try {
    const response = await fetch('https://api.example.com/user');
    const userData = await response.json();
    console.log(userData);
  } catch (error) {
    console.error('Une erreur est survenue :', error);
  }
}
```

``fetchUserData()`` effectue une requête asynchrone vers une API, récupère les données de l'utilisateur et les affiches dans la console. Grâce à l'utilisation de ``async/await``, le code reste facile à lire et à comprendre malgré son caractère asynchrone.