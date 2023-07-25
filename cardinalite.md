# CARDINALITE

## One-to-Many (Un à plusieurs) :
- Exemple 1  : Un auteur peut avoir écrit plusieurs livres, mais chaque livre n'a qu'un seul auteur.
    - Entités : Auteur, Livre
    - Relation : Un auteur peut écrire plusieurs livres, mais chaque livre est écrit par un seul auteur.

- Exemple 2 : Un pays peut avoir plusieurs villes, mais chaque ville est située dans un seul pays.
    -Entités : Pays, Ville
    - Relation : Un pays peut avoir plusieurs villes, mais chaque ville appartient à un seul pays.

## Many-to-One (Plusieurs à un) :
- Exemple 1: Plusieurs étudiants peuvent appartenir à la même classe, mais chaque étudiant n'appartient qu'à une seule classe.

    - Entités : Étudiant, Classe
    - Relation :Plusieurs étudiants peuvent appartenir à une même classe, mais chaque étudiant appartient à une seule classe.

- Exemple 2 : Plusieurs produits peuvent être catégorisés dans la même catégorie, mais chaque produit appartient à une seule catégorie.
    - Entités : Produit, Catégorie
    - Relation : Plusieurs produits peuvent être dans la même catégorie, mais chaque produit appartient à une seule catégorie.

## Many à many (Plusieurs à plusieurs) :

- Exemple 1 : Plusieurs étudiants peuvent être inscrits à plusieurs cours, et chaque cours peut avoir plusieurs étudiants inscrits.
    - Entités : Étudiant, Cours
    - Relation :Un étudiant peut être inscrit à plusieurs cours, et chaque cours peut avoir plusieurs étudiants inscrits.

- Exemple 2 : Plusieurs acteurs peuvent jouer dans plusieurs films, et chaque film peut avoir plusieurs acteurs.
    - Entités : Acteur, Film
    - Relation : Un acteur peut jouer dans plusieurs films, et chaque film peut avoir plusieurs acteurs.