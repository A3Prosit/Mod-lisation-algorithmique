
# Modélisation algorithmique

## Mots-clés :

- Théorie des graphes*

- Cycles Eulérien ou Hamiltonien*

- L’arbre couvrant minimal*

- Itinéraire optimal*

- Algorithme

- Promenade*

## Contexte :

Quoi ?

Concevoir un programme permettant d’optimiser les trajets

Comment ?

Théorie des graphes

Pourquoi ?

Gagner du temps

Contraintes :

- 2 jours

- Cycle Eulérien ou Hamiltonien

## Problématique :

Comment optimiser le trajet en utilisant la théorie des graphes

Comment trouver une promenade optimale en utilisant la théorie des graphes

## Généralisation :

Optimisation / Modélisation

## Hypothèses :

On peut utiliser la caractéristique d’Euler pour les promenades optimales

Promenade = Passer une seule fois par tous les points

Promenade = Passer une seule fois par tous les points et arrêtes

L’arbre couvrant minimal permet de passer par tous les points de manière la plus courte

Promenade essaie d’avoir des points équidistants

## Plan d'action :

## Eulérien, Hamiltonien

théorème d'Euler

cycle eulérien si graph connexe et aucun sommet de degré impair
chaîne eulérienne si connexe et i t j sont les seuls sommet de degré impair

random walk:

une chaîne hamiltonienne est une chaîne passant une et une seule fois par tous les sommets du graphe. Si le sommet initial et le sommet final sont confondus, on parle alors de cycle eulérien.

Théorème (Ore) Soit G = (X,A) un graphe simple d’ordre n ≥ 3 . Si pour toute paire de sommets {x, y}non adjacents, on a d(x) + d(y) > |X | alors G est hamiltonien. 

Corollaire (Dirac) Soit G = (X,A) un graphe simple d’ordre 3 n ≥ Si pour tout sommet x de G on a 2 ( ) n d x ≥ alors G est hamiltonien.


## Arbre couvrant minimum
minimum spanning tree : 
, étant donné un graphe non orienté connexe dont les arêtes sont pondérées, un **arbre couvrant de poids minimal**(**ACM**) de ce graphe est un arbre couvrant (sous-ensemble qui est un arbre  et qui connecte tous les sommets ensemble) dont la somme des poids des arêtes est minimale (c'est-à-dire de poids est inférieur ou égal à celui de tous les autres arbres couvrants du graphe)

couvre tous les sommet avec la somme de poids minimale 
peut ête calculé avec Kruskal, Prim et Boruvka

ex: utilisé par STP en réseau (spanning tree protocol) pour éviter de créer des boucles sur un réseau 
## Rappels de la théorie des graphes

un graphe g est constitué de 2 ensembles V et E, V ensembl nn vide des sommets, E ensemble des paires de sommets de V (arêtes)
on peut écrire G = (V,E) pour représenter le graphe
Dans un graphe orienté on ne parle plus d'arêtes mais d'arcs

- adjacence:
 deux arcs sont adjacents s'ils ont une extrémité commune; deux sommets sont adjacents s'il existe un arc, ou une arête, les reliant
- arc :
 couple (x,y) dans un graphe orienté 
- arête:
 nom d'un arc, dans un graphe non orienté 
- boucle :
 arc reliant un sommet à lui-même
- chaîne:
 Nom d'un chemin dans un graphe non orienté ; séquence d’arcs avec une extrémité commune dans un graphe orienté. 
- chemin:
 suite d'arcs connexes reliant un sommet à un autre. Par exemple (a;b) (b;c) (c;d) (d;b) (b;e) est un chemin reliant a à e ; on le note (a,b,c,d,b,e). Un chemin est une chaîne, la réciproque étant fausse 
- chemin eulérien:
 désigne un chemin simple passant une fois et une seule par toutes les arêtes du graphe ; il n’existe pas toujours… - chemin hamiltonien: 
  désigne un chemin simple qui passe une fois et une seule par chaque sommet
- circuit :
chemin dont l'origine et l'extrémité sont identiques
- cycle : circuit dans un graphe non orienté
- diagraphe : graphe orienté
- diamètre :  plus grande chaîne du graphe
- distance: distance entre deux sommets = plus petite longueur des chaînes ou chemin les reliant
- graphe simple: non orienté, sans boucle, pas plus d'1 arête reliant 2 sommets
-ordre d'un grpahe : nb de sommets
- rang: le rang d’un sommet est la plus grande longueur des arcs se terminant à ce sommet
- Sommets, arrêtes
- Stable : soit un graphe G (E ; R), et F un sous-ensemble de sommets. On dit que F est un sous ensemble stable de E s’il n’existe aucun arc du graphe reliant deux sommets de F.
- sommet pendant: de degré 1
- pont : arête dont la supression déconnecte le graphe
- demi-degré intérieur aka d^+(x) : nb d'arcs entrants
- demi-degré extérieur aka d^-(x): nb d'arcs sortants
- Graphe partiel Soit G = (V, E) un graphe. Le graphe G' = (V, E') est un graphe partiel de G, si E' est inclus dans E.


- Arbres, types, degrés, densité

- Matrice adjacente
- mtrice d'incidence c'est une matrice de n*m où n est le nb de sommet et m le nb d'arêtes on met un 1 si le sommet et l'arête sont liés
## Liste d'adjacense

liste d'adjacense = 2 tableaux
un head et un succ
head est de taille nbNode+1, Succ de taille nbEdge
head commence a 1 à la case 0 et dans chaque case suivante on met nb dans la case actuel + nb de successeurs que le vertex d'index de la case actuel a.
succ est ensuite dans l'ordre les sucesseurs (tous ceux de 1, puis tous ceux de 2, etc)
DONC: par exemple 

pour head

|1 | 2 | 4 | 7 |
veut dire
  1   2   3   4
| 1 | 2 | 5 | 7 |

entre l'index 0 et 1 du tableau on a fait +1, donc le vertex 1 a un successeur, entre 1 et 2 +3 donc le vertex 2 a 3 successeurs et entre 2 et 3 +2 donc v3 a 2 enfants

on a ensuite le tableau succ

| 2 | 1 | 2 | 3 | 1 | 2

ça correspond au graph
```
		 ___
  <---- |   |
1 ----> 2 <-|
 <\	   | ^
    \  v |
	   3
```
- Pondération

- Applications, algorithmes

- Répondre à la question

- Go dev (pour une fois)

## Workshop



objectifs :

Modélisation d’un problème concret à l’aide d’un graphe

-   _Présenter des problèmes concrets pouvant être modélisés par un graphe (ordonnancement, tournée de véhicule, réseaux…)_
-   _Présenter différentes représentations possibles d’un graphe (sagittale, liste d’adjacence, matrice d’adjacence)_
-   _Modéliser les données d’un problème concret dans les différentes représentations possibles d’un graphe (sagittale, liste d’adjacence, matrice d’adjacence)_

Graphes Eulériens et Hamiltoniens

-   _Présenter les notions de cycle Eulérien, de chaîne Eulérienne et de graphe Eulérien_
-   _Présenter les différences entre graphe Eulérien et graphe Hamiltonien_
-   _Démontrer qu’un graphe est Eulérien (Théorème d’Euler)_

Résolution d’un problème concret à l’aide d’un graphe

-   _Présenter l’algorithme de recherche d’un cycle Eulérien_
-   _Présenter l’algorithme du postier chinois_
-   _Réaliser un programme permettant de trouver la solution « optimale » à un problème concret modélisé par un graphe_
