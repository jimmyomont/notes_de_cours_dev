#FONCTIONS PYTHON

## **Fonctions Intégrées de Python :**

1. **`print(...)` :**
   - Affiche des informations à la console.

   Exemple :
   ```python
   print("Hello, World!")
   ```

2. **`len(...)` :**
   - Retourne la longueur d'un objet (par exemple, une chaîne de caractères, une liste).

   Exemple :
   ```python
   longueur = len("Python")
   ```

3. **`type(...)` :**
   - Retourne le type d'un objet.

   Exemple :
   ```python
   type_entier = type(42)
   ```

4. **`input(...)` :**
   - Demande à l'utilisateur de saisir une valeur.

   Exemple :
   ```python
   nom_utilisateur = input("Entrez votre nom : ")
   ```

5. **`int(...)` :**
   - Convertit une valeur en entier.

   Exemple :
   ```python
   entier = int("42")
   ```

6. **`str(...)` :**
   - Convertit une valeur en chaîne de caractères.

   Exemple :
   ```python
   texte = str(42)
   ```

7. **`float(...)` :**
   - Convertit une valeur en nombre à virgule flottante.

   Exemple :
   ```python
   nombre_flottant = float("3.14")
   ```

8. **`max(...)` :**
   - Retourne la valeur la plus élevée d'une séquence (liste, tuple, etc.).

   Exemple :
   ```python
   maximum = max(4, 7, 2)
   ```

9. **`min(...)` :**
   - Retourne la valeur la plus basse d'une séquence.

   Exemple :
   ```python
   minimum = min(4, 7, 2)
   ```

10. **`sum(...)` :**
    - Retourne la somme des éléments d'une séquence.

    Exemple :
    ```python
    somme = sum([1, 2, 3, 4, 5])
    ```

11. **`abs(...)` :**
    - Retourne la valeur absolue d'un nombre.

    Exemple :
    ```python
    absolu = abs(-5)
    ```

12. **`round(...)` :**
    - Arrondit un nombre à la décimale spécifiée.

    Exemple :
    ```python
    arrondi = round(3.14159, 2)
    ```

13. **`range(...)` :**
    - Génère une séquence de nombres.

    Exemple :
    ```python
    sequence = range(5)
    ```


14. **`sorted(...)` :**
    - Retourne une nouvelle liste triée à partir des éléments d'une séquence.

    Exemple :
    ```python
    liste_non_triee = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
    liste_triee = sorted(liste_non_triee)
    ```

15. **`sum(...)` :**
    - Retourne la somme des éléments d'une séquence.

    Exemple :
    ```python
    somme = sum([1, 2, 3, 4, 5])
    ```

16. **`enumerate(...)` :**
    - Retourne une énumération (index et élément) pour chaque élément d'une séquence.

    Exemple :
    ```python
    fruits = ['pomme', 'banane', 'orange']
    for index, fruit in enumerate(fruits):
        print(f"Index {index}: {fruit}")
    ```

17. **`zip(...)` :**
    - Agrège les éléments de plusieurs séquences en une seule séquence.

    Exemple :
    ```python
    liste_nombres = [1, 2, 3]
    liste_l ettres = ['a', 'b', 'c']
    couples = zip(liste_nombres, liste_lettres)
    ```

18. **`any(...)` et `all(...)` :**
    - `any()` retourne True si au moins un élément d'une séquence est True.
    - `all()` retourne True si tous les éléments d'une séquence sont True.

    Exemple :
    ```python
    booleens = [True, False, True]
    est_tout_vrai = all(booleens)
    est_un_vrai = any(booleens)
    ```

19. **`reversed(...)` :**
    - Retourne une séquence inversée.

    Exemple :
    ```python
    inverser_liste = list(reversed([1, 2, 3, 4, 5]))
    ```

20. **`chr(...)` et `ord(...)` :**
    - `chr()` retourne le caractère représenté par un nombre Unicode.
    - `ord()` retourne le code Unicode d'un caractère.

    Exemple :
    ```python
    caractere = chr(65)
    code_unicode = ord('A')
    ```

21. **`map(...)` :**
    - Applique une fonction à chaque élément d'une séquence.

    Exemple :
    ```python
    nombres = [1, 2, 3, 4, 5]
    carres = list(map(lambda x: x**2, nombres))
    ```

22. **`filter(...)` :**
    - Filtre les éléments d'une séquence en fonction d'une fonction de test.

    Exemple :
    ```python
    nombres = [1, 2, 3, 4, 5]
    impairs = list(filter(lambda x: x % 2 != 0, nombres))
    ```
