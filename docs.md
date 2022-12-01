# Programmation orientée-objet

Chaque langage de programmation appartient à une “famille” de langages définissant une approche ou une méthodologie générale de programmation. Par exemple, le langage C est un langage de programmation procédurale car il suppose que le programmeur s’intéresse en priorité aux trai- tements que son programme devra effectuer. Un programmeur C commencera par identifier ces traitements pour écrire les fonctions qui les réalisent sur des données prises comme paramètres d’entrée.
La programmation orientée-objet (introduite par le langage SmallTalk) propose une méthodologie centrée sur les données. Le programmeur Java va d’abord identifier un ensemble d’objets, tel que chaque objet représente un élément qui doit être utilisé ou manipulé par le programme, sous la forme d’ensembles de données. Ce n’est que dans un deuxième temps, que le programmeur va écrire les traitements, en associant chaque traitement à un objet donné. Un objet peut être vu comme une entité regroupant un ensemble de données et de méthodes (l’équivalent d’une fonction en C) de traitement.

## Les utilisateur
- Les langages dits de POO « purs », où tout est traité comme un objet, depuis les primitives telles que les caractères et la ponctuation, jusqu’aux classes, prototypes, blocs, modules. Ils ont été conçus spécifiquement pour faciliter, voire imposer, les méthodes orientés objet.  Ex: Ruby, Scala, Smalltalk, Eiffel, Emerald, JADE, Self, Raku.

 - Les langages conçus principalement pour la programmation OO, mais avec quelques éléments procéduraux. Ex : Java, Python, C++, C#, Delphi/Object Pascal, VB.NET.

- Les langages qui sont historiquement des langages procéduraux, mais qui ont été étendus avec certaines caractéristiques orientées objets. Ex : PHP, Perl, Visual Basic (dérivé de BASIC), MATLAB, C++, C#, COBOL 2002, Fortran 2003, ABAP, Ada 95, Pascal.

- Les langages possédant la plupart des caractéristiques des objets (classes, méthodes, héritage), mais sous une forme nettement originale. Ex: Oberon (Oberon-1 ou Oberon-2).

- Les langages avec support de types de données abstraits qui peuvent être utilisés pour ressembler à la programmation OO, mais sans toutes les caractéristiques de l’orienté  objet Ex : JavaScript, Lua, Modula-2, CLU.

## Les classes

Un objet est une variable (presque) comme les autres. Il faut notamment qu’il soit déclaré avec son type. Le type d’un objet est un type complexe (par opposition aux types primitifs entier, caractère, ...) qu’on appelle une classe.
Une classe regroupe un ensemble de données (qui peuvent être des variables primitives ou des objets) et un ensemble de méthodes de traitement de ces données et/ou de données extérieures à la classe. On parle d’encapsulation pour désigner le regroupement de données dans une classe.
Par exemple, une classe Rectangle utilisée pour instancier des objets représentant des rectangles, encapsule entiers : la longueur et la largeur du rectangle ainsi que la position en abscisse et en ordonnée de l’origine du rectangle (par exemple, le coin en haut à gauche). On peut alors imaginer que la classe Rectangle implémente une méthode permettant de déplacer le rectangle qui nécessite en entrée deux entiers indiquant la distance de déplacement en abscisse et en ordonnée. L’accès aux positions de l’origine du rectangle se fait directement (i.e. sans passage de paramètre) lorsque les données sont encapsulées dans la classe où est définie la méthode.Un exemple, écrit en Java, de la classe Rectangle est donné ci-dessous :

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
## Attributs
Les données d'une classe sont contenues dans des variables nommées propriétés ou attributs. Ce sont des variables qui peuvent être des variables d'instances, des variables de classes ou des constantes.

## Methodes
Les méthodes sont des fonctions qui implémentent les traitements de la classe.
## Les Objets

Les objets contiennent des attributs et des méthodes. Les attributs sont des variables ou des objets nécessaires au fonctionnement de l'objet. En Java, une application est un objet. La classe est la description d'un objet. Un objet est une instance d'une classe. Pour chaque instance d'une classe, le code est le même, seules les données sont différentes à chaque objet.

## Encapsulation

Lors de la conception d’un programme orienté-objet, le programmeur doit identifier les objets et les données appartenant à chaque objet mais aussi des droits d’accès qu’ont les autres objets sur ces données. L’encapsulation de données dans un objet permet de cacher ou non leur existence aux autres objets du programme. Une donnée peut être déclarée en accès :
- public : les autres objets peuvent accéder à la valeur de cette donnée ainsi que la modifier
- privé : les autres objets n’ont pas le droit d’accéder directement à la valeur de cette donnée (ni de la modifier).

## Association
une association modélise une relation entre classes de type "a un" ou "a plusieurs". Un compte bancaire a un titulaire, un livre a plusieurs pages, etc.

## Agregation

En programmation informatique et plus précisément en programmation orientée objet, l'agrégation permet de définir une entité comme étant liée à plusieurs entités de classe différentes. C'est une généralisation de la composition, qui n’entraîne pas l'appartenance.

Par exemple, une université est composée de plusieurs facultés, et chaque faculté est un agrégat de plusieurs professeurs. La destruction de l'université implique la destruction des facultés qui la composent, alors que la destruction d'une faculté n'implique pas la destruction des professeurs liés à cette faculté par une relation d'agrégation. 

## Composition 

La programmation orientée objet se base sur le concept d'objets et le principe de l'encapsulation pour structurer les données et les opérations associées. La composition d'objet consiste alors à définir des objets ou des types composés en combinant des objets ou des types plus simples tout en respectant leur interface et en ignorant tout de leur fonctionnement interne.
 
 ## Principe de l’héritage
L’idée principale de l’héritage est d’organiser les classes de manière hiérarchique. La relation d’héritage est unidirectionnelle et, si une classe B hérite d’une classe A, on dira que B est une sous- classe de A. Cette notion de sous-classe signifie que la classe B est un cas particulier de la classe A et donc que les objets instanciant la classe B instancient également la classe A.
Prenons comme exemple des classes Carre, Rectangle et Cercle.

La classe Rectangle héritant d’une classe vide, elle ne peut profiter d’aucun de ses attributs et doit définir toutes ses variables et méthodes. Une relation d’héritage se définit en Java par le mot-clé extends utilisé comme dans l’exemple suivant :

```
public class Rectangle extends Forme { private int largeur;
private int longueur;
public Rectangle(int x, int y) { this.largeur = x; this.longueur = y;
}
public int getLargeur() { return this.largeur;
}
public int getLongueur() { return this.longueur;
}
public int surface() {
return this.longueur * this.largeur;
}
public void affiche() {
System.out.println(”rectangle ” + longueur + ”x” + largeur);
} }
```
En revanche, la classe Carre peut bénéficier de la classe Rectangle et ne nécessite pas la ré- écriture de ces méthodes si celles-ci conviennent à la sous-classe. Toutes les méthodes et variables de la classe Rectangle ne sont néanmoins pas accessibles dans la classe Carre. Pour qu’un attribut puisse être utilisé dans une sous-classe, il faut que son type d’accès soit public ou protected, ou, si les deux classes sont situées dans le même package, qu’il utilise le type d’accès par défaut. Dans cet exemple, les variables longueur et largeur ne sont pas accessibles dans la class Carre qui doit passer par les méthodes getLargeur() et getLongueur(), déclarées comme publiques.


## Polymorphisme
Le polymorphisme est la faculté attribuée à un objet d’être une instance de plusieurs classes. Il a une seule classe “réelle” qui est celle dont le constructeur a été appelé en premier (c’est-à-dire la classe figurant après le new) mais il peut aussi être déclaré avec une classe supérieure à sa classe réelle. Cette propriété est très utile pour la création d’ensembles regroupant des objets de classes différentes
