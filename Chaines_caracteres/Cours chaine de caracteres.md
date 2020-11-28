<h1> <center>Cours : Les chaines de caractères</center></h1>

# Présentation des chaines de caractères

Avec les nombres et les listes, les chaines de caractères sont les éléments informatiques qu'on utilise le plus couramment. 
Ce sont tout simplement des objets qui représentent du texte. Elles sont délimitées par des guillemets (ou apostrophes).
```python   
texte = "Ceci est une chaine de caractères"
calcul = "1 + 1"
addition = 1 + 1
```
Ainsi, `texte` et `calcul` sont de type chaines de caractères alors que `addition` est de type entier qui vaut 2.  

**Important**. En python, les chaînes de caractères sont des objets *immutables*, c'est-à-dire qu'il s'agit
d'objet que l'on ne peut pas modifier ! En effet, nous verrons que les différents traitements sur les chaines 
de caractères ne modifient jamais la chaîne de caractères elle-même, elles construisent une nouvelle chaîne de
caractères à partir de l'ancienne. 

Il y a énormément d'actions possibles sur les chaines de caractères, nous allons voir les principales.

# Les actions de base

+ `len(texte)` : Donne la longueur de la chaîne de caractères `texte`.
  ```python runnable
  print(len("une chaîne de caractères"))
  ```

+ `texte[n]` : Affiche le n-ième terme de la chaîne de caractères `texte`. 
  **Attention**. La première lettre commence à l'indice 0 !  
  **Astuce**. Si on veut commencer par la fin : `texte[-1]` est la dernière lettre, `texte[-2]` l'avant dernière, etc.
  ```python runnable
  print("Alea jacta est"[0])
  print("Alea jacta est"[5])
  print("Alea jacta est"[-1])
  ```
  
+ `texte[debut:fin]` : Affiche une partie de la chaîne de caractères. 
  La sous-chaîne de caractères commence à l'indice `debut` 
  et se termine à l'indice `fin-1`.  
  **Attention**. La première lettre de la chaîne `texte` correspond toujours à l'indice 0 et on ne prend pas la lettre d'indice `fin`.  
  **Astuce**. Si on veut commencer au début de la chaîne `texte`, on peut omettre l'indice de début : `texte[:fin]`. 
  De même, si on veut aller jusqu'à la fin de la chaîne `texte`, on peut omettre l'indice de fin : `texte[debut:]`.
  ```python runnable
  print("Alea jacta est"[5:10])
  print("Alea jacta est"[:4])
  print("Alea jacta est"[5:])
  ```
  
+ `texte1 + texte2` : Concatène les deux chaînes de caractères, c'est-à-dire les met bout à bout dans l'ordre d'apparition.
  ```python runnable
  texte = "Vive "
  suite = "les Mathématiques"
  print(texte + suite)
  ```
  On peut, bien sûr, enchainer les concaténations : `texte1 + texte2 + texte3 + ...`
  
+ `str(objet)` : Transforme (quand c'est possible) l'`objet` en chaîne de caractères. 
  Utile pour récupérer, par exemple, tous les chiffres d'un nombre séparément.
  ```python runnable
  # On récupère le chiffre d'indice 4, c'est-à-dire le cinquième :
  nombre = 133675184
  str_5e_chiffre = str(n)[4] 
  print(f"Le cinquième chiffre du nombre {nombre} est {str_5e_chiffre}.)
  ```
  Dans l'exemple, on transforme le nombre `nombre` en chaine de caractères 
  ce qui nous permet de récupérer les chiffres un à un sous forme de chaine de caractères. 
  Si on veut les retransformer en nombre pour pouvoir faire des calculs, par exemple, on pourra utiliser `int(str_5e_chiffre)`.
  
+ `texte * k` : Crée une chaine de caractères dans laquelle on répète la chaîne de caractères `texte` `k` fois.
  **Attention**. La variable `k` doit être de type entier !
  ```python runnable
  texte = "Monsieur, j'ai pas compris ! "
  print(texte * 5)
  ```
  
+ `sous_texte in texte` : Renvoie la valeur `True` si la chaine de caractère `sous_texte` est dans `texte` et `False` sinon.
  À utiliser, par exemple, comme condition avec une structure alternative `if`.
  ```python runnable
  texte = "C'est un trou de verdure où chante une rivière."
  print("chante" in texte)
  print("dur" in texte)
  print("eau" in texte)
  print("vers" in texte)
  print("chanter" in texte)
  ```
  On vérifie si les chaînes de caractères `"chante"`, `"dur"`, `"eau"`, `"vers"` et `"chanter"` sont dans la chaine de caractères stockée dans `texte`.
  
  Voici un exemple d'utilisation dans une structure conditionnelle : 
  ```python
  if lettre in "aeiouy":
    print(f"La lettre {lettre} est une voyelle.")
  else :
    print(f"La lettre {lettre} n'est pas une voyelle.")
  ```
  Ce code permettrait par exemple de vérifier si la variable {lettre} est une voyelle ou pas.
  
+ Comparaisons entre chaines de caractères : On peut comparer, comme pour les nombres, des chaines de caractères.
  Le résultat de la comparaison est une booléen : `True` ou `False`.
  Il peut donc s'utiliser comme condition avec une structure alternative `if` ou répétitive `while` .
  Voici les différentes comparaisons possibles :
  - `texte1 == texte2` : Renvoie `True` si la valeur des deux chaînes sont parfaitement identiques, `False` sinon.
  - `texte1 != texte2` : Renvoie `True` si la valeur des deux chaînes ont au moins un caractère différent, `False` sinon.
  - `texte1 < texte2` : Renvoie `True` si la valeur de la chaîne `texte1` précède la valeur de la chaîne `texte2` dans l'ordre lexicographique (l'ordre du dictionnaire).
  - `texte1 <= texte2` : Comme `<` mais la valeur des deux chaînes peuvent être les mêmes.
  - `texte1 > texte2` : Renvoie `True` si la valeur de la chaîne `texte1` suit la valeur de la chaîne `texte2` dans l'ordre lexicographique (l'ordre du dictionnaire).
  - `texte1 >= texte2` : Comme `<` mais la valeur des deux chaînes peuvent être les mêmes.

  Pour ranger dans l'ordre lexicographique, on compare les deux premiers caractères de chaque texte. S'ils sont égaux, on compare le deuxième, etc.
  Par exemple : `"azerty" < "azfa"` car les premiers termes de chaque chaîne sont égaux. De même pour le deuxième. Pour le troisième, comme `"e" < "f"`, 
  il en résultat que `"azerty" < "azfa"`. Il n'est pas nécessaire de regarder la suite.
  
  Ça fonctionne aussi pour les nombres dans une chaîne de caractères : `"1234" < "2"`. En effet, on les compare comme des chaines de caractères et non comme des nombres. On regarde le premier caractère : `"1" < "2"` donc `"1234" < "2"`.

  Pour être plus précis, pour comparer deux caractères, on compare en fait leur code ASCII. 
  Donc on a `"1" < "A" < "_" < "a"` par exemple.

# QCM

Voici quelques QCM pour voir si vous avez bien compris. N'hésitez pas à relire ce qui précède si vous avez un doute.

###### QCM 1
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte[5])
```  
?[Que va afficher ce programme ? ]
-[x] "a" 
-[ ] "s"
-[ ] "Un ch"
-[ ] "h"

---

###### QCM 2
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte[:5])
```  
?[Que va afficher ce programme ? ]
-[ ] "Un cha" 
-[ ] "Un chasseur sachant chasser doit"
-[x] "Un ch"
-[ ] "asseur sachant chasser doit savoir chasser sans son chien."

---

###### QCM 3
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte[5:10])
```  
?[Que va afficher ce programme ? ]
-[x] "asseu" 
-[ ] "hasseu"
-[ ] "asseur"
-[ ] "ar"

---

###### QCM 4
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte[-2])
```  
?[Que va afficher ce programme ? ]
-[ ] "i" 
-[ ] "e"
-[x] "n"
-[ ] "."

---

###### QCM 5
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte[:2] + texte[6:8])
```  
?[Que va afficher ce programme ? ]
-[ ] "Un sse" 
-[ ] "Un ss"
-[ ] "Unsse"
-[x] "Unss"

---

###### QCM 6
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(...)
```  
?[Que faut-il mettre à la place des ... pour afficher "sachant"? ]
-[ ] texte[12:18] 
-[ ] texte[11:18]
-[x] texte[12:19]
-[ ] texte[12]+texte[18]

---

###### QCM 7
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print("ch" in texte)
print("chant" in texte)
print("Un chien" in texte)
print("r s" in texte)
print("un" in texte)
```  
?[Cochez les cases correspondant au numéro des lignes qui vont afficher True ]
-[x] 2
-[x] 3
-[ ] 4
-[x] 5
-[ ] 6

# Entrainement 

### Exercice 1

Pour le nombre `n` donné dans la fenêtre ci-dessous, énumérez ses chiffres.

Pour l'affichage, on utilisera `print` et les chiffres seront affichés en allant à la ligne à chaque fois.

@[Exercice 1]({"stubs": ["Chaines_caracteres/chaine_exo_1bis.py"], "command": "python3 Chaines_caracteres/chaine_exo_1bis_Test.py"})

---

### Exercice 2

Pour le texte donné dans la fenêtre ci-dessous, créer un programme qui affiche le nombre de voyelles.

Pour l'affichage, on utilisera `print`.

@[Exercice 2]({"stubs": ["Chaines_caracteres/chaine_exo_2.py"], "command": "python3 Chaines_caracteres/chaine_exo_2_Test.py"})

---

### Exercice 3

Pour le texte donné dans la fenêtre ci-dessous, créer un programme qui affiche l'indice de tous les "e" dans ce texte.

Pour l'affichage, on utilisera `print` et les indices seront affichés en allant à la ligne à chaque fois.

@[Exercice 3]({"stubs": ["Chaines_caracteres/chaine_exo_1.py"], "command": "python3 Chaines_caracteres/chaine_exo_1_Test.py"})
