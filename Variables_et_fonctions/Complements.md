<h1> <center>Compléments : Variables et opérations </center></h1>

Cette page est un complément du cours sur les variables et opérations pour approfondir ce qui a déjà été vu. 

Tout ce qui suit constitue des connaissances à avoir sur Python pour 
+ soit gagner en temps et en lisibilité 
+ soit pour éviter des erreurs difficiles à déceler. 

# Partie I
## Affectation de variables

Nous avons déjà vu comment affecter à des variables des valeurs. Il y a plusieurs façons d'améliorer ces affectations selon la situation.

+ **Incrémentation**. Il va nous arriver très souvent de vouloir augmenter une variable d'une certaine valeur. Une façon de faire pour ajouter 3 à une variable `x` est :
  ```python
  x = x + 3
  ```
  Mais on peut synthétiser cette écriture sous la forme :
  ```python
  x += 3
  ```
  Cela peut sembler anecdotique mais quand on a beaucoup de variables avec des noms longs et peu agréables à écrire, on savoure le plaisir de n'avoir à les écrire qu'une fois grâce à cette notation.  

  Cette notation existe pour beaucoup d'opérations classiques. On peut : 
  + soustraire une valeur à une variable (avec `-=`), 
  + multiplier (`\*=`), 
  + diviser (`/=`), 
  + mettre à la puissance (`\*\*=`), 
  + effectuer la division euclidienne (`//=`),
  + calculer le reste de la division d'un nombre par un autre (`%=`).  
  
  **Exemples**.
  Vous pouvez modifier les exemples pour tester par vous-même.
  ```python runnable
  x = 3
  x += 4
  print(x)
  x -= 1
  print(x)
  x *= 2
  print(x)
  x //= 3
  print(x)
  x **= 2
  print(x)
  ```
+ **Affectation multiple**. Supposons maintenant que nous voulions affecter à `a`, `b` et `c` des valeurs différentes. On a vu qu'on pouvait écrire :
  ```python
  a = 3
  b = 7
  c = 1
  ```
  Mais on a, en Python, la possibilité de regrouper ces affectations en une seule en écrivant : 
  ```python
  a, b, c = 3, 7, 1
  ```
  Python affecte à la première variable la première valeur, à la deuxième variable la deuxième valeur, etc.

  On peut améliorer encore cette dernière technique en stockant dans des variables des calculs utilisant ces mêmes variables. 
  
  **Exemple**. Supposons que `x = 1` et `y = 4` et qu'on veuille maintenant stocker dans `x` le résultat de `x + y` et dans `y` le résultat de `x - y`. Pour cela, on écrirait simplement : 
  ```python
  x, y = 1, 4
  x, y = x + y, x - y
  ```
  Remarque importante : Ce que l'on vient de faire est très différent de :
  ```python
  x = 1
  y = 4
  x = x + y
  y = x - y
  ```
  Vous pouvez le constater en appuyant sur Run et observer les résultats :
  ```python runnable
  x, y = 1, 4
  x, y = x + y, x - y
  print(f"Résultat dans le premier cas : {x = } et {y = }")
  x = 1
  y = 4
  x = x + y
  y = x - y
  print(f"Résultat dans le second cas : {x = } et {y = }")
  ```
  **Explication**. Dans le premier cas, Python calcule `x + y` et `x - y` puis les stocke en mémoire. Dans le second cas, on calcule d'abord `x + y` et on stocke le résultat dans `x` ce qui veut dire que `x` vaut maintenant 5. Puis python calcule `x - y` (avec `x = 5`) puis stocke le résultat dans la variable `y`. Le résultat n'est donc pas le même !

  Cette technique est très pratique par exemple pour intervertir les valeurs de certaines variables. Il suffit d'écrire `x, y = y, x`.

# Partie II
## Utilisation avancée de la fonction `print()`

Nous avons vu comment afficher la valeur d'une variable en utilisant la fonction `print`. Nous allons voir que nous pouvons améliorer cette affichage.

+ **Afficher du texte**. 
  Pour Python, tout ce qui est contenu entre guillemets  (ou apostrophes) est considéré comme une chaine de caractère. Donc si on veut afficher un texte, il suffit de le mettre entre guillemets et demander à la fonction `print()` de l'affciher.
  
  **Exemple**. 
  ```python runnable
  print("Bonjour")
  print("Hello World !")
  ```
+ **Afficher sans retour à la ligne**. 
  Dans l'exemple précédent, on remarque que Python passe à la ligne à chaque appel de la fonction `print()`. Il s'agit du comportement par défaut de la fonction `print()`. À la fin de l'affichage, elle ajoute un *saut de ligne*.
  
  Pour préciser à la fonction `print()` de rester sur la même ligne, il faut préciser autre chose qu'un saut de ligne à ajouter à la fin de l'affichage.
  
  Cela se fait en précisant le paramètre `end=` à la fonction `print()` :
  
  `print("Le texte ou des variables", end="Ce qu'on veut mettre à la fin")`. 
  
  Par défaut, le paramètre `end="\n"` car `\n` dans une chaîne de caractères est remplacé automatiquement par un retour à la ligne. Donc si on n'en veut pas, il suffit d'affecter au paramètre `end` n'importe quelle autre valeur.

  **Exemple**. 
  Si on veut coller deux résultats pour n'afficher qu'un nombre :
  ```python runnable
  debut = 12
  fin = 345
  print(debut, end="")
  print(fin)
  ```
  
  **Exemples**. 
  Modification de fin de phrase avec `print()` et d'utilisation de `"\n"` dans une chaîne de caractères :
  ```python runnable
  print("ABC\nDE", end=" *hic!*\n")
  print("FG\nHI", end=" *hic!*\n")
  print("J\nK\nL\nM\nN\nO", end=" *hic!*\n")
  print("PQRSTUVWXYZ", end =" *BOUM !*")
  ```

# Partie III
## Formatage de chaîne de caractères

>**Remarque**. Depuis la version 3.8 de Python, les f-string ajoutent une petite fonctionnalité intéressante. Entre accolade, si vous ajoutez un signe égal `=` juste après le nom de la variable, le nom de la variable sera affiché en même temps que ça valeur. Pour aider au débogage de son code, c'est assez utile et surtout en demandant un minimum d'ajout.
```python runnable
x = 25
y = 14
print(f"L'abscisse {x = } et l'ordonnée {y = }")
```

>**Remarque**. Depuis la version 3.6 de Python, les **f-string** font leur apparition. Elles sont une nouvelle façon, plus condensée, de formater des chaînes de caractères. Il s'agit, en fait, d'une version simplifiée et plus lisible de l'utilisation de `format()`.
```python runnable
x = 25
y = 14
print(f"L'abscisse x: {x} et l'ordonnée y: {y}")
```

Le formatage avec la méthode `format()` s'applique comme un texte à trous que l'on complète avec des données que l'on veut formater. 

**Exemple**. 
On veut afficher les valeurs de trois variables dans une chaîne :
```python runnable
a = 0.5
b = 2
c = 1 / 3
# Avec la méthode format()
print("Dans 'b' il y a la valeur {1}, dans 'a' il y a la valeur {0} et dans 'c' la valeur {2}".format(a, b, c))
# Avec la f-string
print(f"Dans 'b' il y a la valeur {b}, dans 'a' il y a la valeur {a} et dans 'c' la valeur {c}")
```
La méthode `format()` va remplacer les accolades par les variables en respectant l'ordre : 
+ `{0}` sera remplacée par la valeur de la première variable donnée (ici, `a`),
+ `{1}` par la valeur de `b`,
+ `{2}` par la valeur de `c`. 

La **f-string** commence par un `f` situé juste avant le premier guillemet. Entre accolades, on écrit simplement le nom de la variable que l'on veut voir afficher à cet endroit.

### Arrondi de nombres décimaux

La méthode `format()` permet d'afficher un nombre arrondi à plusieurs chiffres significatifs après la virgule.

#### Arrondi simple

La méthode `format()` permet, par exemple, d'afficher un nombre arrondi à deux chiffres significatifs après la virgule. Pour cela, il suffit d'ajouter `:.2g` dans les accolades concernées. 
```python runnable
a = 0.5
b = 2
c = 1 / 3
# Avec la méthode format()
print("Dans 'b', il y a la valeur {1:.2g}, dans 'a' il y a la valeur {0:.2g} et dans 'c' la valeur {2:.2g}".format(a, b, c))
# Avec la f-string
print(f"Dans 'b', il y a la valeur {b:.2g}, dans 'a' il y a la valeur {a:.2g} et dans 'c' la valeur {c:.2g}".format(a, b, c))
```

#### Arrondi forcé

Si on veut arrondir à deux chiffres après la virgule *en gardant les zéros inutiles*, comme pour les prix par exemple, on utilise de la même façon `:.2f`.
```python runnable
a = 0.5
b = 2
c = 1 / 3
# Avec la méthode format()
print("Dans 'b' il y a la valeur {1:.2f}, dans 'a' il y a la valeur {0:.2f} et dans 'c' la valeur {2:.2f}".format(a,b,c))
# Avec la f-string
print(f"Dans 'b' il y a la valeur {b:.2f}, dans 'a' il y a la valeur {a:.2f} et dans 'c' la valeur {c:.2f}"
```

# Partie III
## Questionnaire QCM

Voici quelques QCM pour voir si vous avez bien compris. N'hésitez pas à relire ce qui précède si vous avez un doute.

###### QCM 1
```python
a, b = 5, 2
b, a = a+1, b-a
print(a, b)
```  
?[Quelles valeurs sera affichée si on execute le programme ci-dessus ? ]
-[ ] 6 -3
-[ ] -4 6
-[ ] 3 -3 
-[x] -3 6

---

###### QCM 2
```python
a = 4
b = 2
b *= 3
a += b
print(a)
```  
?[Quelle valeur sera affichée si on execute le programme ci-dessus ? ]
-[x] 10
-[ ] 3
-[ ] 9
-[ ] 6

---

###### QCM 3
```python
a = b = 3
c = 2
b **= 2
b, c, a = a + c, a + b, b + c
print(a)
```
?[Quelle valeur sera affichée si on execute le programme ci-dessus ? ]
-[ ] 5
-[ ] 8
-[x] 11
-[ ] 17 

---

# A vous !

###### Exercice 1 :

Le but de cet exercice est de suivre un programme de calcul en partant d'un entier ***n*** qui sera donné automatiquement.

Appuyez sur Run et suivez les instructions qui s'affichent.

N'effacez pas ce que vous avez fait juste. Il faut rajouter au fur et à mesure en dessous.

Quand on demande d'afficher, c'est avec `print`.

@[Programme de calcul]({"stubs": ["Variables_et_fonctions/Programme_calcul3.py"], "command": "python3 Variables_et_fonctions/Programme_calcul3_Test.py"})

