# Devoir 09 : UML-Is-Easy
Exercice de lecture et retranscription en Java d'informations fournies en UML.
## CONSIGNE :
- Regardez avec attention les schémas UML fournis ci-dessous.
- Retranscrivez ceux-ci avec précision en Java afin d'obtenir une application fonctionnelle.

Vous devriez obtenir une sortie console telle que celle-ci :
````
Blablabla bla bla bla.
Blablabla bla bla bla.
Blablabla bla bla bla.
````
# UML :
Ci-dessous le diagramme de classes UML pour l'ensemble de ce programme  :
```mermaid
---
title: D02-PersonneEtCopains
---
classDiagram
class Application {
    +main(String[] args)$ void
}

class Ecole {
   +int MAX_CLASSES_PAR_ECOLE$
   -String nom
   -Classe[] classes
   +Ecole(String nom)    
   +ajouteClasse(Classe classeAAjouter) boolean
   +supprimeClasse(Classe classeASupprimer) boolean
   +totalEleves() int
   +toString() String
}

class Classe {
   +int MAX_ELEVES_PAR_CLASSE$
   -String nom
   -Eleve[] eleves
   +Classe(String nom)
   +ajouteEleve(Eleve eleveAAjouter) boolean
   +supprimeEleve(Eleve eleveASupprimer) boolean
   +totalEleves() int
   +toString() String
}

class Eleve {
   +int MAX_COPAINS_PAR_ELEVE$
   -String nom
   -String prenom
   -Eleve[] amis
   +Eleve(String nom)
   +ajouteAmi(Eleve nouvelAmi) boolean
   +supprimeAmi(Eleve ancienAmi) boolean
   +toString() String
}
note for Eleve "MAX_COPAINS_PAR_ELEVE = 10"
note for Classe "MAX_ELEVES_PAR_CLASSE = 20"
note for Ecole "MAX_CLASSES_PAR_ECOLE = 16"
Eleve "1" o--> "0..n" Eleve : amis
Application ..> Ecole : utilise
```

## RESTITUTION :
1. Rendre ce devoir normalement par `push` GitHub
