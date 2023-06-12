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
## diagramme des classes de l'application
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
   -Personne directeur
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
   -Personne[] eleves
   +Classe(String nom)
   +ajouteEleve(Personne eleveAAjouter) boolean
   +supprimeEleve(Personne eleveASupprimer) boolean
   +totalEleves() int
   +toString() String
}

class Personne {
   +int MAX_AMIS_PAR_PERSONNE$
   -String nom
   -String prenom
   -Personne[] amis
   +Personne(String nom)
   +ajouteAmi(Personne nouvelAmi) boolean
   +supprimeAmi(Personne ancienAmi) boolean
   +toString() String
}
note for Personne "MAX_AMIS_PAR_PERSONNE = 10"
note for Classe "MAX_ELEVES_PAR_CLASSE = 20"
note for Ecole "MAX_CLASSES_PAR_ECOLE = 16"
Ecole "1" o--> "0..n" Classe : classes
Ecole "1" o--> "1" Personne : directeur
Classe "1" o--> "0..n" Personne : eleves
Personne "1" o--> "0..n" Personne : amis
Application ..> Ecole : utilise
```

## RESTITUTION :
1. Rendre ce devoir normalement par `push` GitHub
