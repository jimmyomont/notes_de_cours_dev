``` js
sequelize.define('foo', {
  bar: {
    type: DataTypes.STRING,
    validate: {
      is: /^[a-z]+$/i,          // correspond à cette RegExp
      is: ["^[a-z]+$",'i'],     // comme ci-dessus, mais en construisant la RegExp à partir d'une chaîne
      not: /^[a-z]+$/i,         // ne correspond pas à cette RegExp
      not: ["^[a-z]+$",'i'],    // comme ci-dessus, mais en construisant la RegExp à partir d'une chaîne
      isEmail: true,            // vérifie le format de l'e-mail (foo@bar.com)
      isUrl: true,              // vérifie le format de l'URL (https://foo.com)
      isIP: true,               // vérifie le IPv4 (129.89.23.1) or IPv6 format
      isIPv4: true,             // vérifie le IPv4 (129.89.23.1)
      isIPv6: true,             // vérifie le IPv6 format
      isAlpha: true,            // n'autorisera que les lettres
      isAlphanumeric: true,     // n'autorisera que les caractères alphanumériques, donc "_abc" échouera
      isNumeric: true,          // n'autorisera que les nombres
      isInt: true,              // vérifie les entiers valides
      isFloat: true,            // vérifie les nombres à virgule flottante valides
      isDecimal: true,          // recherche tous les nombres
      isLowercase: true,        // vérifie les minuscules
      isUppercase: true,        // vérifie les majuscules
      notNull: true,            // n'autorisera pas null
      isNull: true,             // n'autorise que null
      notEmpty: true,           // ne pas autoriser les chaînes vides
      equals: 'specific value', // n'autoriser qu'une valeur spécifique
      contains: 'foo',          // forcer des sous-chaînes spécifiques
      notIn: [['foo', 'bar']],  // vérifier que la valeur n'en fait pas partie
      isIn: [['foo', 'bar']],   // vérifier que la valeur est l'une de celles-ci
      notContains: 'bar',       // ne pas autoriser les sous-chaînes spécifiques
      len: [2,10],              // autoriser uniquement les valeurs dont la longueur est comprise entre 2 et 10
      isUUID: 4,                // n'autoriser que les uuids
      isDate: true,             // n'autoriser que les chaînes de date
      isAfter: "2011-11-05",    // autoriser uniquement les chaînes de date après une date spécifique
      isBefore: "2011-11-05",   // autoriser uniquement les chaînes de date avant une date spécifique
      max: 23,                  // n'autoriser que les valeurs <= 23
      min: 23,                  // n'autoriser que les valeurs >= 23
      isCreditCard: true,       // vérifier les numéros de carte de crédit valides

    // Exemples de validateurs personnalisés :
      isEven(value) {
        if (parseInt(value) % 2 !== 0) {
          throw new Error('Only even values are allowed!');
        }
      }
      isGreaterThanOtherField(value) {
        if (parseInt(value) <= parseInt(this.otherField)) {
          throw new Error('Bar must be greater than otherField.');
        }
      }
    }
  }
});
```