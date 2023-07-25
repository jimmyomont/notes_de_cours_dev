# CARDINALITE

## One-to-Many (1 -> 0,N) (Un à plusieurs) : 
- Exemple 1  : Un auteur peut avoir écrit plusieurs livres, mais chaque livre n'a qu'un seul auteur.
    - Entités : Auteur, Livre
    - Relation : Un auteur peut écrire plusieurs livres, mais chaque livre est écrit par un seul auteur.
    - Relation : Un auteur peut écrire 0 ou N livres, mais chaque livre est écrit par exactement 1 auteur.
    - Représentation : Auteur(1) -> Livre(0,N)

- Exemple 2 : Un pays peut avoir plusieurs villes, mais chaque ville est située dans un seul pays.
    -Entités : Pays, Ville
    - Relation : Un pays peut avoir plusieurs villes, mais chaque ville appartient à un seul pays.
    - Relation : Un pays peut avoir 0 ou N villes, mais chaque ville appartient à exactement 1 pays.
    - Représentation : Pays(1) -> Ville(0,N)

## Many-to-One (0,N -> 1) (Plusieurs à un) :
- Exemple 1: Plusieurs étudiants peuvent appartenir à la même classe, mais chaque étudiant n'appartient qu'à une seule classe.

    - Entités : Étudiant, Classe
    - Relation :Plusieurs étudiants peuvent appartenir à une même classe, mais chaque étudiant appartient à une seule classe.
    - Représentation : Étudiant(0,N) -> Classe(1)

- Exemple 2 : Plusieurs produits peuvent être catégorisés dans la même catégorie, mais chaque produit appartient à une seule catégorie.
    - Entités : Produit, Catégorie
    - Relation : Plusieurs produits peuvent être dans la même catégorie, mais chaque produit appartient à une seule catégorie.
    - Représentation : Produit(0,N) -> Catégorie(1)

## Many à many (0,N -> 0,N) (Plusieurs à plusieurs) :

- Exemple 1 : Plusieurs étudiants peuvent être inscrits à plusieurs cours, et chaque cours peut avoir plusieurs étudiants inscrits.
    - Entités : Étudiant, Cours
    - Relation :Un étudiant peut être inscrit à plusieurs cours, et chaque cours peut avoir plusieurs étudiants inscrits.
    - Relation : Un étudiant peut être inscrit à 0 ou N cours, et chaque cours peut avoir 0 ou N étudiants inscrits.
    - Représentation : Étudiant(0,N) <- Inscription -> Cours(0,N)

- Exemple 2 : Plusieurs acteurs peuvent jouer dans plusieurs films, et chaque film peut avoir plusieurs acteurs.
    - Entités : Acteur, Film
    - Relation : Un acteur peut jouer dans plusieurs films, et chaque film peut avoir plusieurs acteurs.
    - Relation : Un acteur peut jouer dans 0 ou N films, et chaque film peut avoir 0 ou N acteurs.
    - Représentation : Acteur(0,N) <- Joue -> Film(0,N)

## One-to-One (1 -> 1):
- Exemple 1 :
    - Entités : Étudiant, Carte d'identité
    - Relation : Chaque étudiant possède exactement 1 carte d'identité, et chaque carte d'identité appartient à un seul étudiant.
    - Représentation :Étudiant(1) <- Possède -> Carte d'identité(1)

- Exemple 2 :
    - Entités : Employé, Badge d'accès
    - Relation : Chaque employé a exactement 1 badge d'accès, et chaque badge d'accès est associé à un seul employé.
    - Représentation : Employé(1) <- Possède -> Badge d'accès(1)