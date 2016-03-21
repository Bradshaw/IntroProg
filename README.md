# Notions de programmation


## Variables & Affectation

Une *variable*, est simplement une sorte d'étiquette pour des valeurs qu'on souhaite conserver.   
Par exemple:
```javascript
maValeur = 5
```   
Cette instruction s'appelle une *affectation*, on dit qu'on *affecte* la valeur 5 à une *variable* ```maValeur```.   
A partir de cette instruction, ```maValeur``` contient 5, on peut aussi dire qu'elle "vaut" 5.   

On peut donc utiliser ```maValeur```dans un calcul en tant que nombre:   
```javascript
var maValeur = 5
alert( maValeur + 10 ) // Affiche "15" dans une fenêtre
```

*L'opérateur d'affectation est le ```=```, il fonctionne en calculant la valeur de tout ce qui est à droite de lui, et en affectant cette valeur à la variable à gauche.*

Il existe d'autres opérateurs pour certains cas particuliers:

### ```+= -= *= /=```

Ces opérateurs sont ce qu'on appelle du *sucre syntaxique*, c'est à dire qu'ils sont équivalents à une autre écriture.
```javascript
a += 5
```
est équivalent à:
```javascript
a = a + 5
```
L'intérêt est de simplifier l'écriture lorsqu'on souhaite modifier la valeur d'une variable. Un peu comme sur votre calculatrice lorsque vous tapez ```4``` ```+``` ```5```, puis pour ajouter 5 à nouveau vous faites ```+``` ```5```.

### ```++ --```

Ces opérateurs sont aussi du *sucre syntaxique*:
```javascript
a++
```
équivaut à écrire:
```javascript
a = a + 1
```

Ils s'appellent *incrémentation* et *décrémentation*, ils servent à augmenter ou baisser la valeur d'un variable d'un "cran". Particulièrement utiles pour les *boucles*


## Les Boucles

Une boucle, c'est une écriture qui permet de répéter l'éxécution d'un *bloc* de code. Il y en a de deux sortes, le ```while``` et le ```for``` (appelées "Tant Que" et "Pour" en Français).

### ```while```

La boucle *while* continue tant que sa *condition* est *vraie*. Pour écrire une boucle *while* valide, il faut donner une condition qui cesse d'être vraie lors d'un tour de boucle.   
   
Dans l'exemple suivant, la condition est ```a < 16```. On voit que ```a``` est initialisée à ```1```, puis est multipliée par ```2``` à chaque tour, et donc sera égale à ```16``` après quatre tours de boucle.   

```javascript
var a = 1
var c = 0
while (a < 16){		// Tant que a est plus petit que 16
	console.log(a)	// Afficher la valeur de a dans la console
	a *= 2			// Multiplier a par deux
}
```

### ```for```

La boucle *for* a trois paramètres, l'*initialisation*, appellée avant de commencer, la *condition* vérifiée avant chaque tour de boucle (comme pour le *while*), et l'*incrémentation*, appellée après chaque tour de boucle.   
   
Dans l'exemple suivant, une boucle *for* utilise une variable appellée ```i```, pour effectuer ```5``` tours, affichant à chaque fois la valeur de ```i``` dans la console.

```javascript
for (var i = 0; i < 5; i++){	// Pour i allant de 0 à 4 (5 exclu)
	console.log(i)				// Afficher la valeur de i dans la console
}
```


## Les Fonctions

Une fonction est une serie d'instructions, souvent paramétrée, et qui peut renvoyer un resultat.   
L'intérêt des fonctions peut être de décomposer une solution complexe en plusieurs sous-solutions, ou alors de créer des bouts de code réutilisables.   
   
Voici quelques exemples de fonctions:   
```javascript
// Renvoit la somme des valeur de ses paramètres
function somme( a, b ){		// On déclare une fonction qui s'appelle "somme" et qui prend deux paramètres
	return a + b			// On utilise le mot-clé "return" pour renvoyer le résultat du calcul "a + b"
}

// Renvoit la valeur la plus grande entre a et b
function max(a, b){			// On déclare une fonction qui s'appelle "max" et qui prend deux paramètres
	if ( a > b ){			// Si "a" est plus grand que "b" ...
		return a			// ... on renvoit "a", ...
	} else {				// ... sinon ...
		return b			// ... on revoit "b"
	}
}
```
   
Une fois qu'une fonction est créée, on peut l'utiliser (ou *appeler*) quand on veut. Si la fonction renvoit un résultat (utilise le mot-clé```return```), on peut l'utiliser comme une valeur   
```javascript
// Affecte la valeur de l'appel de max(23, 45), soit 45, à myVariable
var myVariable = max(23, 45)
```
   
On peut même utiliser ces appels comme paramètre d'une autre fonction:   
```javascript
// Récupère les résultats des deux appels à max(a,b), et passe les résultats en paramètre à somme(a, b)
var myVariable = somme( max(13,10), max(40,32) )
```

## Les Tableaux

Les tableaux sont une sorte de "super-variable", servant à conserver une "liste" de valeurs à l'intérieur d'une seule variable. On crée un tableau avec les symboles ```[```et ```]```. On peut les pré-remplir avec des valeurs séparées par des virgules:   
```javascript
var a = []					// Un tableau vide, nommé a
var b = [23, 15, 42, 57]	// Un tableau contenant quatre nombres, nommé b
```

Ensuite pour accéder aux valeurs dans une tableau, on utilise à nouveau les ```[]```, avec un nombre entier indiquant le numéro de la case qu'on souhaite regarder ou modifier (les cases commencent à zéro).   
```javascript
// Ajouter deux valeurs dans a
a[0] = 130
a[1] = 21

// Modifier la troisième valeur de b
b[2] = 87

// Afficher la deuxième valeur de a
console.log( a[1] )
```

## Les Objets

Les objets sont une autre sorte de "super-variable" qui sert à représenter une donnée complexe. On peut les imaginer comme une façon de décrire des objets comme dans le monde réel. Ils sont créés avec les symboles ```{``` et ```}```.   
On peut les pré-remplir avec des associations clé valeur ```thing: 5```, séparés par des virgules:   
```javascript
// Un objet vide, nommé "truc"
var truc = {}

// Un objet initialisé, nommé "chose"
var chose = {
	nom: "Patrick",
	age: 23,
	taille: 187
}

```

On accède aux valeurs dans un objet avec l'opérateur ```.```, par exemple:
```javascript
// Ajouter trois champs à l'objet "truc"
truc.nom = "Aline"
truc.age = 32
true.taille: 172

// Modifier l'age de "chose"
chose.age = 24

// Afficher les noms de "truc" et de "chose"
console.log(truc.nom)
console.log(truc.nom)
```

# Turtle

Pour vous exercer, on vous propose le *Turtle*. Un exercice classique d'introduction à la programmation.   
Vous pouvez obtenir les sources d'un Turtle en JavaScript qui fonctionne dans le navigateur en cliquant [ici](http://is.gd/sigturtle).   

## Les fonctions du Turtle

### ```penUp()``` et ```penDown()```

Ces fonctions ne prennent pas de paramètre, et demandent respectivement à la tortue de lever ou de poser son style. Lorsque le stylo est posé, la tortue laissera une trace en se déplaçant.

### ```penColor()```

Cette fonction prend un paramètre sous forme d'une chaîne de caractères, et change la couleur du stylo de la tortue:   
```javascript
penColor("red")		// Le stylo devient rouge
penColor("#FF8800") // Le stylo devient orange
```

### ```turn()```

Cette fonction prend un angle en degrés, et fait tourner la tortue sur elle-même:   
```javascript
turn(90)			// Tourne vers la droite
```

### ```move()```

Cette fonction prend une distance en pixels, et fait avancer la tortue de cette distance (si le stylo est posé, cela laissera un trait):
```javascript
move(100)			// Avance de 100 pixels
```

## Exemple utilisant toutes les fonctionalités de programmation

```javascript
// Crée un tableau de trois objets que nous interpréterons comme déscriptions de polygone
var myPolygons = [
  {distance: 30, sides: 3, color: "blue"},
  {distance: 30, sides: 6, color: "green"},
  {distance: 30, sides: 4, color: "red"}
]

// Une fonction qui déssine un objet polygone passé en paramètre
function drawPoly(p) {
  penColor(p.color)						// Change la couleur du pinceau
  for (var i = 0; i < p.sides; i++) {	// Pour chaque coté ...
    move(p.distance)					// ... avancer de la distance demandée ...
    turn(360/p.sides)					// ... et tourner d'un angle permettant un tour complet au final.
  }
}

// Boucle qui déssine les polygones qui ont plus de trois faces
for (var i = 0; i < myPolygons.length; i++) {	// Pour chaque polygone ...
  if (myPolygons[i].sides>3){					// ... si le polygone a plus de trois faces ...
    drawPoly(myPolygons[i])						// ... déssine le polygone.
  }
}
```



