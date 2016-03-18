# IntroProg
Cours d'introduction à la programmation


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
while (a < 16){ // Tant que a est plus petit que 16
  a *= 2        // Multiplier a par deux
  c ++          // Augmenter c de un
}
```

### ```for```

La boucle *for* a trois paramètres, l'*initialisation*, appellée avant de commencer, la *condition* vérifiée avant chaque tour de boucle (comme pour le *while*), et l'*incrémentation*, appellée après chaque tour de boucle.   
   
Dans l'exemple suivant, une boucle *for* utilise une variable appellée ```i```, pour effectuer ```5``` tours, affichant à chaque fois la valeur de ```i``` dans la console.

```javascript
for (var i = 0; i < 5; i++){
	console.log(i)	
}
```
