# Analogique vs numérique
- Analogique:  
Les valeurs ne sont pas séparées par des sauts: entre deux valeurs A
et B il existe un nombre infini d'autres valeurs

-  Digitale (numérique):  
Une valeur est représentée par une chaîne finie de symboles
appelés digits.  
Il est impossible de représenter digitalement tous les nombres
existants entre deux points d'une échelle analogique
# Big endian vs little endian

- big endian:  
le byte de poids fort est mis à l'adresse inférieure (le mot commence par
le byte de poids fort)
- little endian:  
le byte de poids faible est mis à l'adresse inférieure (le mot commence
par le byte de poids faible). Utilisé par les processeurs x86 de Intel

# Système logique
- Système combinatoire:
	- la valeur des sorties à un moment donné dépend uniquement des
	- valeurs des entrées à cet instant
	- le comportement est entièrement décrit par une table, la table de
 vérité, où pour chaque combinaison des entrées on donne la valeur
 des sorties
	- pour n entrées, la table de vérité comporte 2ⁿ lignes
	- la sortie est immédiate
- Système séquentiel:
	- la valeur des sorties dépend de l'histoire des entrées, de leur séquence
	- dans le temps
	- l'obtention d'un résultat peut demander plusieurs pas
	- le système doit se rappeler des résultats intermédiaires: il faut une
mémoire

# Notations 

- Equation minimale :  
MAJ(a,b,c) = ab + bc + ac
-  Forme canonique algébrique (sans simplification):  
	MAJ(a,b,c) = a'bc + ab'c + abc' + abc  
	Comment y arriver ?  
	MAJ(a,b,c) = ab + bc + ac  
	= ab(c + c') + bc(a + a') + ac(b + b')  
	= abc + abc' + abc + a'bc + abc + ab'c  
	= a'bc + ab'c + abc' + abc
- Forme canonique décimale (dépend de la table de vérité):  
	MAJ(a,b,c) = ∑ 3,5,6,7

# Table de karnaugh

- Tables à 2,3,4 variables:  
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/karnaugh.png?token=AF7-YsVdbOGEIXul0ox9ypdfo25yzy8tks5VMNbDwA%3D%3D)
- Table à 5 variables:  
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/karnaugh5.png?token=AF7-Yv-h5tPywzA00m1EnuuGQCMjFg8rks5VMNXMwA%3D%3D)
- Table à 6 variables:  
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/karnaugh6.png?token=AF7-YgPgUNiAcX_ITYf-UGDnWbFf6Yegks5VMNbdwA%3D%3D)

## Définitions :
- Impliquant d’une fonction:  
produit des variables de la fonction.  
Chaque impliquant est représenté dans la table de Karnaugh par
un groupe de cases contiguës, en un nombre égal à une puissance
de deux
- Impliquant premier:  
impliquant qui n'est pas inclus dans un autre impliquant plus grand.
La solution minimale d'une fonction est formée seulement
d'impliquants premiers. Mais tous les impliquants premiers ne font
nécessairement pas partie de la solution minimale
- Impliquant premier essentiel:  
impliquant premier qui contient au moins un minterme qui n'est pas
inclus dans un autre impliquant premier. Un impliquant premier
essentiel fait toujours partie de la solution minimale

## Méthode de minimalisation
-  Dresser la liste de tous les impliquants premiers de la fonction
-  Dresser la liste de tous les impliquants premiers essentiels
-  Tous les impliquants premiers essentiels font partie de la solution minimale
- Couvrir les mintermes restants avec un nombre minimal
d’impliquants premiers

## Fonction incomplètement définie
-  Une fonction est incomplètement définie si la valeur de l'état de
sortie n'est pas définie pour les 2ⁿ états d'entrée possibles
- L'état d'entrée où la sortie n'est pas définie est un état ∅ ou
condition indifférente (en anglais, "don't happen" ou "don't care")
- Pour un état ∅ la sortie peut prendre la valeur 0 ou 1: plusieurs
solutions existent donc pour une même fonction, selon les valeurs
choisies pour les états ∅
- La méthode de minimisation d'une fonction par la table de
Karnaugh s'applique également aux fonctions incomplètement
définies: tous les états ∅ sont mis à 1 et l'on cherche la solution
minimale pour cette borne supérieure de la fonction; bien entendu,
les impliquants composés seulement d’états sont éliminés

## Conversion en portes NAND et NOR
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/nandToNor.png?token=AF7-YiuNfC85RONt4CIcJk5ZyEKtCKTnks5VMNb2wA%3D%3D)
# Quelques dispositifs combinatoires

## Le décodeur
- Un décodeur convertit des symboles d’un code à un autre
- Exemple: le décodeur de binaire à 7 segments utilisé dans les
affichages à LEDs
- Toutefois, lorsque le mot décodeur est utilisé tout seul, il se réfère à un
dispositif combinatoire à n entrées et m sorties, où m⩽2ⁿ et où au
maximum un seul bit de sortie est 1 à un moment donné
- On parle alors d’un décodeur n → m

## Le multiplexeur
- Un multiplexeur n 1 est un dispositif combinatoire avec n entrées de
données, m entrées de contrôle (avec m=log 2 n) et une sortie
- A tout moment, la valeur de la sortie est égale à l’entrée choisie par les
variables de contrôle. Un multiplexeur sélectionne donc une entrée
pour l’envoyer à la sortie

## L’encodeur
- L’encodeur est un dispositif combinatoire réalisant la fonction inverse
d’un décodeur: il accepte n bits d’entrée (avec une seule entrée égale à
1 à tout moment) et produit m bits de sortie, avec m=⎡log2n⎤. On parle
alors d’un encodeur n → m

## Le comparateur
- Le comparateur accepte deux entrées a et b à n bits et produit une
sortie indiquant si a=b

# Eléments de mémoire
## Latch
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/latch.png?token=AF7-YjYS35dAH6ZEandgSWUt2l5vjMxFks5VMNcpwA%3D%3D)
## Flip-flop
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/flip-flop.png?token=AF7-YncJ_0RmkDB_HiJiUPgPJTrcTPBGks5VMNcowA%3D%3D)
## Le registre
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/registre.png?token=AF7-YgL2V1w-M4ZQLIfM1RbeXpw7AJQzks5VMNcrwA%3D%3D)
# Systèmes séquentiels
Deux type de machines :
- Machine de Mealy
	- Si les valeurs des variables de sortie dépendent de l'état présent et des
variables d'entrée, le système séquentiel est appelé une machine de Mealy
	- Dans ce cas, le changement des sorties n'est pas synchrone: il se fait avec le
changement des entrées
- Machine de Moore
	- Si les valeurs des variables de sortie dépendent uniquement de l'état
présent, le système séquentiel est appelé une machine de Moore
	- Dans ce cas, le changement des sorties est synchrone: il se fait avec le
changement des états

- Sauf contraintes de type physique spécifiées dans le cahier des charges, tout
problème peut être résolu par une machine de type Mealy ou Moore,
indifféremment
- Normalement, pour un même problème, une machine de Moore demande
plus d'états que la machine de Mealy équivalente
- Toutefois, assez souvent on préfère la solution de type machine de Moore. En
effet, les sorties d'une machine Mealy ne sont pas synchronisées avec
l'horloge, pouvant changer en même temps qu'une entrée externe. Cet
asynchronisme amène comme conséquence des durées quelconques pour
les sorties
- Comme les sorties des machines de type Moore sont synchronisées, leur
durée est toujours un multiple de la période du signal d'horloge

## Mealy vs Moore
![Alt text](https://raw.githubusercontent.com/sriak/dotfiles/master/gistImages/mealyVSmoore.png?token=AF7-YmBwoq241GrLJThGGHl1Avtp0Wdoks5VMNcqwA%3D%3D)
# Codage 1 parmi M
- Si le nombre d'états du système est M, ce type de codage utilise M
variables internes, de telle sorte qu'une seule variable interne vaut 1
pour chaque état
- Des 2ᴹ états possibles, seulement M états sont réellement utilisés: il y a
2ᴹ-M états ∅

