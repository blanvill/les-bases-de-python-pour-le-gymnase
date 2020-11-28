<h1> <center>Compléments sur les chaines de caractères</center></h1>

# Constantes spécifiques aux chaines de caractères

Afin de ne pas avoir à initialiser des variables avec des valeurs bien connues, comme l'alphabet ou les chiffres de 0 à 9, Python nous en fournit.

En passant par le module `string` (qui signifie *suite* ou *chaîne*), nous pouvons disposer des constantes suivantes : 
+ ascii_letters : contient toutes les lettres de l'alphabet en majuscule et en minuscule.
+ ascii_lowercase : contient toutes les lettres de l'alphabet en minuscule uniquement.
+ ascii_uppercase : contient toutes les lettres de l'alphabet en majuscule uniquement.
+ digits : contient tous les chiffres de 0 à 9.
+ hexdigits : contient tous les chiffres de la base hexadécimale, de 0 à F. Les lettres sont présentes en minuscule et en majuscule.
+ whitespace : contient tous les caractères considérés comme des espaces. Sont inclus les caractères espace, tabulations, saut de ligne, retour du chariot, saut de page, et tabulation verticale.

[https://docs.python.org/fr/3.8/library/string.html?highlight=string#module-string]Lien vers la documentation du module string de Python (version 3.8).

# Fonctions spécifiques aux chaines de caractères

Ce sont des méthodes appliquées directement à une chaine de caractères.
La notation est un peu particulière : Le nom de la chaîne de caractères à traiter sera suivie d'un point suivi du nom de la méthode.

+ `chaine.find(sous_chaine)` : Donne l'indice de la première apparition de `sous_chaine` dans la `chaine`.
  ```python runnable
  texte = "J'ai posé ma brosse sur le bureau."
  print(texte.find("brosse"))
  print(texte.find("o"))
  ```
  **Attention**. Le premier caractère est toujours situé à l'indice numéro 0 ! 
  
  Dans la chaîne `texte`, le 'b' de brosse étant le 14e caractère, son indice est 13.
  Pour le deuxième exemple, on voit que le "o" de "brosse" n'est pas pris en compte. 
  La méthode `find` ne renvoie que l'indice du premier "o" qu'il rencontre.
  
+ `chaine.count(sous_chaine)` : Donne le nombre d'occurrences de la chaîne `sous_chaine` dans la `chaine`.
  ```python runnable
  texte = "J'ai posé ma brosse sur le bureau."
  print(texte.count("os"))
  print(texte.count("e"))
  ```
  Il y a deux fois "os" dans la chaîne `texte` et trois "e". 
  On remarquera que "é" n'est pas compté comme un "e".
  
+ `chaine.replace(ancienne, nouvelle)` : Remplace toutes les chaînes `ancienne` par la chaîne `nouvelle`.
  ```python runnable
  texte = "Une foncttttion ttttrès prattttique si vous répéttttez ttttrop les tttt."
  print(texte.replace("tttt","t"))
  ```

+ `chaine.lower()` : retourne une nouvelle chaîne de caractères où tous les caractères de `chaine` ont été transformé en minuscule.
  ```python runnable
  upcase_and_lowcase = "HeLlo WoRlD !"
  print(f"La chaîne '{upcase_and_lowcase}' en minuscule: {upcase_and_lowcase.lower()}")
  upcase = "HELLO WORLD !"
  print(f"La chaîne '{upcase}' en minuscule: {upcase.lower()}")
  lowcase = "hello world !"
  print(f"La chaîne '{lowcase}' en minuscule: {lowcase.lower()}")

+ `chaine.upper()` : retourne une nouvelle chaîne de caractères où tous les caractères de `chaine` ont été transformé en majuscule.
  ```python runnable
  upcase_and_lowcase = "HeLlo WoRlD !"
  print(f"La chaîne '{upcase_and_lowcase}' en majuscule: {upcase_and_lowcase.upper()}")
  upcase = "HELLO WORLD !"
  print(f"La chaîne '{upcase}' en majuscule: {upcase.upper()}")
  lowcase = "hello world !"
  print(f"La chaîne '{lowcase}' en majuscule: {lowcase.upper()}")
  

# QCM

Voici quelques QCM pour voir si vous avez bien compris. N'hésitez pas à relire ce qui précède si vous avez un doute.

###### QCM 1
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(...)
```  
?[Que faut-il mettre à la place des ... pour afficher le nombre de "e" dans ce texte ? ]
-[x] texte.count("e")
-[ ] count("e")
-[ ] count(texte,"e")
-[ ] texte.count(e)

---

###### QCM 2
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte.find("ch"))
```  
?[Que va afficher ce programme ? ]
-[x] 3
-[ ] 4
-[ ] 5
-[ ] 3, 13, 19, 39, 57

---

###### QCM 3
```python
texte = "Un chasseur sachant chasser doit savoir chasser sans son chien."
print(texte.replace("ss","ch"))
```  
?[Que va afficher ce programme ? ]
-[ ] "Un ssasseur sassant ssasser doit savoir ssasser sans son ssien."
-[ ] "Un chacheur sachant chacher doit savoir chacher sanchon chien."
-[ ] "Un chacheur chachant chacher doit chavoir chacher chanch chon chien."
-[x] "Un chacheur sachant chacher doit savoir chacher sans son chien."

# Entrainement 

### Exercice 1

Pour le texte donné dans la fenêtre ci-dessous, créer un programme qui affiche le code ASCII correspondant à chaque lettre.

Pour l'affichage, on utilisera `print` et les code ASCII seront affichés en allant à la ligne à chaque fois.

@[Exercice 1]({"stubs": ["Chaines_caracteres/Comp_chaine_exo_1.py"], "command": "python3 Chaines_caracteres/Comp_chaine_exo_1_Test.py"})

---

### Exercice 2

Pour le texte donné dans la fenêtre ci-dessous, créer un programme qui, pour chaque lettre du texte, affiche la lettre suivante dans l'alphabet. 

Quelques compléments : 
+ Pour le "z", on affichera "a". 
+ Le texte n'est composé que de lettres minuscules et sans accent.

Pour l'affichage, on utilisera `print` et chaque lettre sera affichée en allant à la ligne.

@[Exercice 2]({"stubs": ["Chaines_caracteres/Comp_chaine_exo_2.py"], "command": "python3 Chaines_caracteres/Comp_chaine_exo_2_Test.py"})

---

### Exercice 3

Pour le texte donné dans la fenêtre ci-dessous, créer un programme qui, pour chaque lettre du texte, affiche la lettre suivante dans l'alphabet. 

Quelques compléments : 
+ Pour le "z", on affichera "a". 
+ Les lettres du texte sont toutes sans accent mais ne sont pas toutes en minuscule.
+ La ponctuation et espaces devront rester inchangés.

Pour l'affichage, on utilisera `print` et chaque lettre sera affichée en allant à la ligne.

@[Exercice 3]({"stubs": ["Chaines_caracteres/Comp_chaine_exo_3.py"], "command": "python3 Chaines_caracteres/Comp_chaine_exo_3_Test.py"})
