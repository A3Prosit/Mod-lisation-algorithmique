
# Modélisation algorithmique

## Mots-clés :

- Théorie des graphes*

- Cycles Eulérien ou Hamiltonien*

- L’arbre couvrant minimal*

- Itinéraire optimal*

- Algorithme

- Promenade* : chemin eulérien

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

![](https://image.noelshack.com/fichiers/2019/23/2/1559635301-capture.png)
### Graphe eulérien (Arrêtes)
- Un chemin eurélien est un chemin dans le graphe qui passe par toutes les **arrêtes** une seule fois. Si le chemin est fermé, c'est un cycle eurélien.
	- Il faut que chaque point ai un nombre pair d'arrêtes (sinon impossible) == aucun sommet de degré impair #Théorème Euler
	- 
### Graphe Hamiltonien (Sommets)
- Un chemin hamiltonien est un chemin qui passe par toutes les **sommets**  une et une seule fois. Si le chemin est fermé, c'est un cycle hamiltonien. et aussi un graphe hamiltonien.
	- Théorème Dirac
	- Théorème Ore
	- Théorème Posa
	- Bondy et Chvatal
1 - Calculer l'ordre
2 - Calculer les valeurs des degrés des paires de sommets qui ne sont pas reliés par une arrête directement
3 - Si un couple < ordre : Pas hamiltonien sinon Hamiltonien

## Arbre couvrant minimum

- Utilisé dans plusieurs types de réseaux (téléphoniques / distributions / partitionnement de données / traitement d'image).
- Nécessité d'un graphe non orienté connexe et pondéré.
- Sous ensemble qui est un arbre et qui connecte tous les sommets ensemble, dont la somme des poids des arrêtes est minimale.
- Algorithme de Krustal & Algorithme de Prim (classique) : Tous deux des algo "glouton" càd qu'ils cherchent localement à chaque fois la meilleure solution. C'est parfois trop grand.
- Algorithme Tarjan (1983 - USA) : 
	- Colier en bleu des coupes et choisir le poid minimum ==> Donnera l'arbre couvrant minimum
	- Cololier en rouge des cycles et prendre le poid maximum
- Algorithme Kruskal  (1956 - USA) :
	- Parcours les poids de manière croissante. Il ne doit pas faire de cycle.
## Rappels de la théorie des graphes

### Notions de base :
- Sommets : Points identifiés par des lettres
- Arrêtes : Relie les sommets

- **Graphes non orientés** : Arrêtes relient deux sommets de manière symétriques
	![](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Undirected.svg/1024px-Undirected.svg.png)
- **Graphes orientés  :** Arrêtes (appellés flèche) relients deux sommets de manières asymétrique
	![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Directed.svg/1024px-Directed.svg.png)
- **Graphe mixte :** Mélange entre orienté et non orienté
- **Graphe pondéré :** Chaque arrête porte un nombre (son poid). Le poid peut représenter des coûts, des longueurs, des capacités...


### Types de graphe :

- **Graphe asymétrique (ou orentié)** : ??
- **Graphe réguliger :** Graphe non orienté où tous les sommets ont un même degré.
- **Graphe complet** : Graphe  simple dont tous les sommets sont tous adjacents les uns aux autres. ![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Complete_graph_K7.svg/1024px-Complete_graph_K7.svg.png)
- **Graphe fini** : Ensemble des sommets est fini. (Sinon infinis). Généralement c'est bien expliqué si c'est infini.
- **Graphe connexe :** Non orienté, quel que soient les sommets, il existe une chaîne les reliants.  (ici 3 connexes)
![](https://zestedesavoir.com/media/galleries/912/69efbede-6af0-49be-bf23-4d04310f355a.gif.960x960_q85.png)- **Graphe biparti :** Graphe dont l'ensemble des sommets peut-être partitionné en deux ensembles. Chaque arrête doit être comprise dans les deux ensembles :
![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Simple-bipartite-graph.svg/1024px-Simple-bipartite-graph.svg.png)
- **Graphe planaire** : Graphe qui a la particularitéde pouvoir se représenter sur un plan sans qu'aucune arrêten'en croise une autre, même en modifiant la position des sommets. (Ex : Si on met le 4 dans le triangle 123)
	![](https://upload.wikimedia.org/wikipedia/commons/3/30/Graphe_planaire.png)
	![](https://upload.wikimedia.org/wikipedia/commons/e/e7/Graphe_K4.png)
-  **Graphe cycle :** Connexe non orienté, chacun de ses sommets est de degré 2. (2-régulier) Permet de relier un noeud à lui même sans jamais passer deux fois par la même arrête.
![](https://upload.wikimedia.org/wikipedia/commons/9/98/Intercpunetring.png)

- **Graphe en arbre :** Graphe orienté acyclique (inverse cyclique) et connexe. 
	- Abre simple / binaires / généraux (analyse algorithme / combinatoire annalythique)
	- Ensemble d'arbre s'appelle une forêt
	- Sommets : Feuilles (degré 1) && Sommets internes (degré > 1)
	- La *formule de Cayley* permet de définir le nombre d'arbres que l'on peut construire sur n sommets*
![](https://zestedesavoir.com/media/galleries/912/766f0052-fd0e-4484-9be7-3c51e9c58209.png.960x960_q85.png)

### Autres notions :
-  **degrés :** Le degré (ou valence) est le nombre de liens (arrêts) reliés à ce sommet, avec les boucles, comptés deux fois.

- **densité :** Paramètre associé à un graphe pour dire si le graphe à beaucoup d'arrêtes. C'est le rapport entre le nombre d'arêtes et le nombre d'arêtes possibles. C'est donc un réeel compris entre 0 et 1. Selon la densité,si elevé : on passera par une matrice (beaucoup d'arrêtes), sinon on pourra faire une liste.

- **Matrice adjacente** : C'est une matrice de dimension (= nombre de sommets), et où pour chaque ligne correspond à un sommet. On va indiquer pour chacune des colonnes (les autres sommets), si il existe une liaison avec notre ligne.
![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/28/6n-graph2.svg/220px-6n-graph2.svg.png)![](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a801c1edd8efe61bcadfcb174cf8d9a487dd00a)⇒ Basé sur ça, on peut faire plusieurs calculs comme trouver le nombre de chaîne possbile de longueur n reliant deux points d'un graphe...

**- Chaîne:** Suite finie d'arrêtes consécutives. Dans un graphe orienté, on parle de chemin

**- Homogène :** Les noeuds sont de mêmes natures.

## Applications &  algorithmes : 
- **Sortir d'un labyrinthe : [PARCOURS]** Algorithme en profondeur/largeur
- **Paver des rues en utilisant le moins de pavés possible :[ACM]** Utiliser des arbres couvrants minimum (ACM) :
	- Algorithme de Krustal 
	- Algorithme de Prim
- **Trouver le plus court chemin :** Dijkstra
- **Visiter toutes les villes sans jamais repasser par une ville  (bandits)** : Hamiltoniens #Sommets
- **Groudronner les rues en passant et une une seule fois par rues, en autorisant les croisements :** Eulériens #Arrêtes

## Workshop



```python
  
######################################################LISTE####################################################  
  
HeadZoneA = [1,3,5,7,11,15,17,19,23,25,27,29]; # Header  
SuccZoneA = [2,4,1,5,4,8,1,3,5,9,2,4,6,8,5,11,8,10,3,7,5,9,4,8,7,11,6,10]; # Sucesseurs  
# n'oubliez pas de cliquer sur "Exécuter pour que ces deux listes soient exploitables pour la suite du Workshop  
  
  
def degreSommetsGraphe(Head, Succ):  
    sommet = 1  
  indiceParcours = 0  
  while (sommet < len(Head)):  
        indiceEnCours = Head[sommet - 1]  
        indiceSuivant = Head[sommet]  
  
        # calcul du degré et création du message à afficher  
  degre = indiceSuivant - indiceEnCours;  
  
        message = "Le sommet " + str(sommet) + " est de degré " + str(degre) + " ( voisins : "  
  
  # ajout de la liste des voisins dans le message  
  
  print(message)  
        indiceMax = 0  
  for i in Succ: ## Pour tous les élements de Succ  
  indiceMax = indiceMax + 1  
  if indiceMax > degre:  
                break  
 else:  
                print(Succ[indiceParcours])  
                indiceParcours = indiceParcours + 1  
  sommet = sommet + 1  
  return;  
  
  
print("### Degré des sommets du graphe de la Zone A ###")  
degreSommetsGraphe(HeadZoneA, SuccZoneA)  
  
Head7Ponts = [1,4,9,12,15]; # Header  
Succ7Ponts = [2,2,3,1,1,3,4,4,1,2,4,2,2,3]; # Sucesseurs  
print("### Degré des sommets du graphe des 7 ponts de Könisgberg ###")  
degreSommetsGraphe(Head7Ponts, Succ7Ponts)



matrixZoneA = [  
#### 1 2 3 4 5 6 7 8 9 10 11  
  [0,1,0,1,0,0,0,0,0,0,0],#1  
  [1,0,0,0,1,0,0,0,0,0,0],#2  
  [0,0,0,1,0,0,0,1,0,0,0],#3  
  [1,0,1,0,1,0,0,0,1,0,0],#4  
  [0,1,0,1,0,1,0,1,0,0,0],#5  
  [0,0,0,0,1,0,0,0,0,0,1],#6  
  [0,0,0,0,0,0,0,1,0,1,0],#7  
  [0,0,1,0,1,0,1,0,1,0,0],#8  
  [0,0,0,1,0,0,0,1,0,0,0],#9  
  [0,0,0,0,0,0,1,0,0,0,1],#10  
  [0,0,0,0,0,1,0,0,0,1,0]#11  
]  
  
  
  
  
def degreSommetsGrapheMatrice(matrice):  
    sommet = 1  
  indiceVoisins = 0  
  for liste in matrice:  
        cpt = 0  
  voisins = []  
        degre = 0  
  
  for i in liste:  
            if i == 1:  
                voisins.insert(indiceVoisins,cpt+1)  
                degre = degre+1  
  indiceVoisins = indiceVoisins + 1  
  elif i > 1 :  
                y = 0  
  for y in range(0,i):  
                    voisins.insert(indiceVoisins, cpt + 1)  
                    degre = degre + 1  
  indiceVoisins = indiceVoisins + 1  
  cpt = cpt+1  
  
  message = "Le sommet " + str(sommet) + " est de degré " + str(degre) + " ( voisins : "  
  for voisin in voisins:  
            message = message + str(voisin) + " "  
  message = message + ")"  
  print(message)  
  
        sommet = sommet + 1  
  return;  
  
  
print("### Degré des sommets du graphe de la Zone A ###")  
degreSommetsGrapheMatrice(matrixZoneA)  
  
  
  
matrix7Ponts = [  
#    1 2 3 4  
  [0,2,1,0],#1  
  [2,0,1,2],#2  
  [1,1,0,1],#3  
  [0,2,1,0] #4  
]  
  
print("### Degré des sommets du graphe des 7 ponts de Könisgberg ###")  
degreSommetsGrapheMatrice(matrix7Ponts)  
  
  
  
def existeCycleEulerien(matrice):  
    for sommet in matrice:  
        total = 0  
  for i in sommet:  
            if i == 1:  
                total = total +1  
  elif i > 1:  
                y = 0  
  for y in range(0,i):  
                    total = total + y  
        if (total%2 != 0): return False;  
    return True;  
  
print("### Il existe un cycle Eulérien dans le graphe de la Zone A ? ###")  
print(existeCycleEulerien(matrixZoneA));  
  
print("### Il existe un cycle Eulérien dans le graphe des 7 ponts de Könisgberg ? ###")  
print(existeCycleEulerien(matrix7Ponts))  
  
  
def cycleEulerien(matrice):  
    n = len(matrice)  
  
    cycle = list()  # cycle est notre cycle à construire  
  stack = list()  # stack est une liste de sommets à traiter  
  cur = 0 # cur est notre sommet courant : le 1er noeud traité est le premier noeud de la matrice  
  
 # on boucle tant qu'il y a des sommets à traiter dans notre stack # ou que notre sommet courant possède bien au moins 1 voisin non traité  while (stack != [] or sum(matrice[cur]) != 0):  
  
        # si le sommet courant ne possède aucun voisin  
 # on l'ajoute à notre cycle et on revient au sommet ajouté précédemment dans la stack (backtracking) # qui devient notre nouveau sommet courant  if (sum(matrice[cur]) == 0):  
            cycle.append(cur + 1)  
            cur = stack.pop(-1)  
  
        # si il a au moins 1 voisin  
 # on l'ajoute à notre stack pour y revenir plus tard (backtracking) # on retire l'arête qu'il partage avec ce voisin # qui devient le sommet courant  else:  
            for i in range(n):  
                if matrice[cur][i] == 1:  
                    stack.append(cur)  
                    matrice[cur][i] = 0  
  matrice[i][cur] = 0  
  cur = i  
                    break  
  
  # affichage du cycle  
  for ele in cycle:  
        print(ele, "-> ", end='')  
    print(cur + 1)  
  
    return;  
  
  
print("### Calcul d'un cycle Eulérien du graphe de la Zone A ###")  
cycleEulerien(matrixZoneA)


```
