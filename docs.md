# Programmation orientée-objet

Chaque langage de programmation appartient à une “famille” de langages définissant une ap- proche ou une méthodologie générale de programmation. Par exemple, le langage C est un langage de programmation procédurale car il suppose que le programmeur s’intéresse en priorité aux trai- tements que son programme devra effectuer. Un programmeur C commencera par identifier ces traitements pour écrire les fonctions qui les réalisent sur des données prises comme paramètres d’entrée.
La programmation orientée-objet (introduite par le langage SmallTalk) propose une métho- dologie centrée sur les données. Le programmeur Java va d’abord identifier un ensemble d’objets, tel que chaque objet représente un élément qui doit être utilisé ou manipulé par le programme, sous la forme d’ensembles de données. Ce n’est que dans un deuxième temps, que le program- meur va écrire les traitements, en associant chaque traitement à un objet donné. Un objet peut être vu comme une entité regroupant un ensemble de données et de méthodes (l’équivalent d’une fonction en C) de traitement.

## Les classes

Un objet est une variable (presque) comme les autres. Il faut notamment qu’il soit déclaré avec son type. Le type d’un objet est un type complexe (par opposition aux types primitifs entier, caractère, ...) qu’on appelle une classe.
Une classe regroupe un ensemble de données (qui peuvent être des variables primitives ou des objets) et un ensemble de méthodes de traitement de ces données et/ou de données extérieures à la classe. On parle d’encapsulation pour désigner le regroupement de données dans une classe.
Par exemple, une classe Rectangle utilisée pour instancier des objets représentant des rec- tangles, encapsule  entiers : la longueur et la largeur du rectangle ainsi que la position en abscisse et en ordonnée de l’origine du rectangle (par exemple, le coin en haut à gauche). On peut alors imaginer que la classe Rectangle implémente une méthode permettant de déplacer le rectangle qui nécessite en entrée deux entiers indiquant la distance de déplacement en abscisse et en ordonnée. L’accès aux positions de l’origine du rectangle se fait directement (i.e. sans passage de paramètre) lorsque les données sont encapsulées dans la classe où est définie la méthode.

```
class Rectangle {
int longueur; int largeur; int origine_x; int origine_y;
void deplace(int x, int y) { 
    this.origine_x = this.origine_x + x; 
    this.origine_y = this.origine_y + y;
}
int surface() {
return this.longueur * this.largeur;
} }
```

 