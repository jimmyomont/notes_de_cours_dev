# C#
### **La Base**

#### **1. Introduction à C#**

Le langage C# est un langage de programmation polyvalent développé par Microsoft. Il est largement utilisé pour développer des applications Windows, des applications Web et des services.

#### **2. Hello, World!**


```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello, World!");
    }
}
```

**Commentaire :**
- `using System;` : C'est une directive qui permet d'utiliser les types définis dans l'espace de noms (namespace) `System`.
- `class Program` : Déclare une classe appelée `Program`.
- `static void Main()` : La méthode principale (point d'entrée) du programme.
- `Console.WriteLine("Hello, World!");` : Affiche "Hello, World!" dans la console.

#### **3. Types de Données**

```csharp
int age = 25;
float height = 1.75f;
string name = "John";
```

**Commentaire :**
- `int` : Type de données pour les entiers.
- `float` : Type de données pour les nombres à virgule flottante.
- `string` : Type de données pour les chaînes de caractères.

#### **4. Structures de Contrôle**

Utilisez des structures de contrôle pour gérer le flux d'exécution.

```csharp
if (age > 18)
{
    Console.WriteLine("Majeur");
}
else
{
    Console.WriteLine("Mineur");
}
```

**Commentaire :**
- `if (condition)` : Structure conditionnelle.
- `{ }` : Bloc de code exécuté si la condition est vraie.
- `else` : Bloc de code exécuté si la condition est fausse.

#### **5. Boucles**

Boucles pour répéter des blocs de code.

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

**Commentaire :**
- `for (initialisation; condition; itération)` : Boucle `for`.
- `Console.WriteLine(i);` : Affiche la valeur de `i` dans la console.

#### **6. Fonctions (Méthodes)**

Les fonctions regroupent des blocs de code réutilisables.

```csharp
int sum = Add(3, 5);
Console.WriteLine("Sum: " + sum);

int Add(int a, int b)
{
    return a + b;
}
```

**Commentaire :**
- `int Add(int a, int b)` : Déclaration d'une fonction qui prend deux entiers en paramètres et renvoie leur somme.

#### **7. Classes et Objets**

C# est orienté objet. Utilise des classes pour créer des objets.

```csharp
class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

Person person = new Person();
person.Name = "Alice";
person.Age = 30;
```

**Commentaire :**
- `class Person` : Définition d'une classe `Person` avec des propriétés `Name` et `Age`.
- `new Person()` : Création d'une nouvelle instance de la classe `Person`.
- `person.Name = "Alice";` : Attribution de valeurs aux propriétés de l'objet.

#### **8. Gestion d'Exceptions**

Utilise des blocs `try`, `catch`, et `finally` pour gérer les erreurs.

```csharp
try
{
    // Code qui pourrait générer une exception
}
catch (Exception ex)
{
    Console.WriteLine("Erreur : " + ex.Message);
}
```

**Commentaire :**
- `try` : Bloc contenant le code susceptible de générer une exception.
- `catch (Exception ex)` : Capture et gestion de l'exception.
- `finally` : Bloc exécuté quel que soit le résultat (optionnel).


#### **9. Propriétés et Accesseurs**

Utilise des propriétés pour encapsuler l'accès aux champs d'une classe.

```csharp
class Person
{
    private string _name; // Champ privé

    public string Name
    {
        get { return _name; }
        set { _name = value; }
    }
}

Person person = new Person();
person.Name = "Bob";
Console.WriteLine(person.Name);
```

**Commentaire :**
- `private string _name;` : Déclaration d'un champ privé.
- `public string Name { get; set; }` : Déclaration d'une propriété avec des accesseurs `get` et `set`.
- `person.Name = "Bob";` : Utilisation de l'accesseur `set`.
- `Console.WriteLine(person.Name);` : Utilisation de l'accesseur `get`.

#### **10. Méthodes Statiques**

Les méthodes statiques appartiennent à la classe plutôt qu'à une instance spécifique.

```csharp
class Calculator
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}

int result = Calculator.Add(10, 20);
Console.WriteLine(result);
```

**Commentaire :**
- `public static int Add(int a, int b)` : Déclaration d'une méthode statique dans la classe `Calculator`.
- `Calculator.Add(10, 20);` : Appel de la méthode sans créer d'instance de `Calculator`.

#### **11. Tableaux**

Utilise des tableaux pour stocker des collections d'éléments.

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
Console.WriteLine(numbers[2]); // Affiche 3
```

**Commentaire :**
- `int[] numbers` : Déclaration d'un tableau d'entiers.
- `numbers[2]` : Accès à l'élément à l'index 2.

#### **12. Enumérations**

Les énumérations permettent de définir des jeux de valeurs nommées.

```csharp
enum Days { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };

Days today = Days.Wednesday;
Console.WriteLine(today); // Affiche Wednesday
```

**Commentaire :**
- `enum Days` : Déclaration d'une énumération.
- `Days.Wednesday` : Utilisation des valeurs énumérées.

#### **13. Delegates et Événements**

Les délégués permettent de créer des références vers des méthodes.

```csharp
delegate void MyDelegate(string message);

class EventPublisher
{
    public event MyDelegate OnEvent;

    public void RaiseEvent(string message)
    {
        OnEvent?.Invoke(message);
    }
}

class EventHandler
{
    public void HandleEvent(string message)
    {
        Console.WriteLine("Event handled: " + message);
    }
}

EventPublisher publisher = new EventPublisher();
EventHandler handler = new EventHandler();

publisher.OnEvent += handler.HandleEvent;
publisher.RaiseEvent("Event message");
```

**Commentaire :**
- `delegate void MyDelegate(string message)` : Déclaration d'un délégué.
- `event MyDelegate OnEvent` : Déclaration d'un événement dans une classe.
- `OnEvent?.Invoke(message);` : Appel de l'événement.

