# POO (La programmation orientée objet)

offre de nombreux avantages en matière d'organisation et de structuration du code. L'utilisation des principes de POO pour organiser la validation des données peut améliorer la lisibilité, la réutilisabilité et la maintenabilité de votre code.

---
## Voici quelques principes de POO que vous pouvez utiliser pour organiser la validation des données :

## Encapsulation : 

Encapsulez les données dans des classes qui ont des méthodes de validation. L'encapsulation permet de protéger les données contre les accès indésirables et facilite leur manipulation. Vous pouvez également utiliser des accesseurs pour accéder aux données encapsulées et pour les valider avant de les modifier.

Exemple : 

```js 
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty.");
        }
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age < 0 || age > 120) {
            throw new IllegalArgumentException("Age must be between 0 and 120.");
        }
        this.age = age;
    }
}
```

## Héritage : 

Utilisez l'héritage pour créer des classes de validation spécialisées qui héritent des méthodes de validation d'une classe de validation de base. Par exemple, vous pouvez créer une classe de validation de base qui contient des méthodes de validation communes pour les types de données courants tels que les chaînes, les nombres, les dates, etc. Vous pouvez ensuite créer des classes de validation spécialisées pour des types de données plus spécifiques, tels que les adresses email, les numéros de téléphone, etc.

Exemple : 

```js 
//Dans cet exemple, la classe Personencapsule les données nameet age, et les méthodes getName()et getAge()permet d'y accéder de manière sécurisée. Les méthodes setName()et setAge()effectuent également une validation des données avant de les modifier.

public class StringValidator {
    public boolean validate(String value) {
        return value != null && !value.isEmpty();
    }
}

public class EmailValidator extends StringValidator {
    public boolean validate(String value) {
        if (!super.validate(value)) {
            return false;
        }
        // Validation spécifique à l'adresse email
        return value.contains("@") && value.contains(".");
    }
}
```

## Polymorphisme : 

Utilisez le polymorphisme pour permettre à différentes méthodes de validation d'être appelées en fonction du type de données en entrée. Le polymorphisme permet de traiter des objets de différentes classes de manière uniforme, ce qui facilite l'écriture de code générique et réutilisable.

Exemple : 

```js 
//Dans cet exemple, la classe StringValidatorest une classe de validation de base pour les chaînes de caractères. La classe EmailValidatorhérite de StringValidatoret ajoute une validation spécifique à l'adresse email.

public class Validator {
    public boolean validate(Object value) {
        if (value instanceof String) {
            return new StringValidator().validate((String) value);
        } else if (value instanceof Integer) {
            return new IntegerValidator().validate((Integer) value);
        } else {
            throw new IllegalArgumentException("Unsupported type.");
        }
    }
}
```

## Interfaces : 

Définissez des interfaces pour les classes de validation et utilisez-les pour garantir que les classes implémentent les méthodes de validation accessibles. Les interfaces permettent de séparer la définition de l'interface de la mise en œuvre, ce qui facilite la création de classes de validation qui satisfont à des exigences spécifiques.

Exemple : 

```js 
//Dans cet exemple, la classe Validatorutilise le polymorphisme pour valider des objets de différents types. Les méthodes de validation spécifiques sont appelées en fonction du type de données en entrée.

public interface Validator<T> {
    boolean validate(T value);
}

public class StringValidator implements Validator<String> {
    public boolean validate(String value) {
        return value != null && !value.isEmpty();
    }
}

public class IntegerValidator implements Validator<Integer> {
    public boolean validate(Integer value) {
        return value != null && value >= 0;
    }
}
```

## Exceptions : 

Utilisez des exceptions pour gérer les erreurs de validation. Les exceptions permettent de séparer la logique de traitement des erreurs de la logique de validation, ce qui facilite la gestion des erreurs et améliore la lisibilité du code.

Exemple : 

```js 
//Dans cet exemple, la méthode validate()est appelée dans le constructeur et chaque méthode de modification pour valider les données. Si les données ne passent pas la validation, une exception IllegalArgumentExceptionest acquise.

public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
        validate();
    }

    private void validate() {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty.");
        }
        if (age < 0 || age > 120) {
            throw new IllegalArgumentException("Age must be between 0 and 120.");
        }
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
        validate();
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
        validate();
    }
}
```