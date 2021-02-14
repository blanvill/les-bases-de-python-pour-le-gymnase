<h1> <center>Cours : Les Tuples </center></h1>

Auparavant, nous avons déjà rencontré un type de donnée construit : les tableaux,  implémentés par le type `list` en Python. Il existe d'autres séquences en Python : les __tuples__ en sont un exemple.


# Définition et points communs avec les listes Python

> 📢 Un __tuple__ (ou __n-uplets__) est un collection ordonnée de n objets séparés par des virgules.  

```python runnable
t = (1, 2)
type(t)
```
On peut tout à fait créer un tuple sans utiliser les parenthèses mais leur présence facilite la lecture. De plus ils peuvent contenir des données de nature différente.
```python runnable
t = 'a', 4
print(t)
```

* Il est possible que le tuple ne contienne aucun élément ou encore un seul élément 

```python
>>> t = ()
>>> t = (1, )  # on pourrait aussi écrire   1, sans les parenthéses
```

* Comme pour les listes, les tuples sont des séquences ordonnées. __On peut accéder aux éléments par leur indice de position__ (le premier élément à toujours l'indice 0) ou encore accéder aux nombres d'éléments présents.

```python runnable
t = (5, 'a', 2020)
t[1]
len(t)
```

* On peut également accéder à des tranches du tuple avec la même notation que celle vue pour les chaînes de caractères ou les listes


```python
>>> t = ('a', 'c', 4, 'f')
>>> t[1:]
('c', 4, 'f')
```

* On peut bien évidemment les parcourir.

```python
>>> t = ('n', 's', 'i')
>>> for e in t :
        print(e, end=" ")

 n s i 
```

D'autres propriétés sont communes aux listes, aux chaînes de caractères et aux tuples : la création par compréhension, et beaucoup des méthodes déjà rencontrées (à condition qu'elles ne modifient pas le tuple)

# Particularités des tuples

> 📢 Les __tuples__ peuvent être considérés comme des listes __non modifiables__ (_immuables_)

* Une fois le tuple créé, il est impossible de changer un élément présent à l'intérieur

```python
>>> t = ('a', 'b', 'd')
>>> t[2] = 'e'
 Traceback (most recent call last):
    File "<pyshell>", line 1, in <module>
 TypeError: 'tuple' object does not support item assignment
```

* Il est cependant possible de __concaténer des tuples__ 

```python
>>> (1, 2) + (3, 4)
(1, 2, 3, 4)
```

* On peut également __disperser un tuple__ c'est à dire le "casser" en plusieurs variables. C'est une propriété très pratique notamment pour réaliser des affectations multiples

```python
>>> x, y, z = (15, 50, 20)
>>> x
15
>>> y
50
>>> z
20
```

# Pourquoi utiliser un tuple plutôt qu'une liste?

* __Lorsque les données ne doivent pas être modifiées : un tuple est plus judicieux.__  

Imaginons des données personnelles immuables concernant un individu (nom, prenom, date de naissance) : on ne souhaite pas qu'elles soient modifiées par inavertance. Rappelez vous de la mutabilité des listes, aucune chance que cela ne se produise avec un tuple


_Rappel : mutabilité des listes en Python_

```python
>>> tableau = [4, 5]
>>> tableau_bis = tableau
>>> tableau[0]= 10
>>> tableau
[10, 5]
>>> tableau_bis  # tableau_bis et tableau pointe vers le même emplacement mémoire : ce sont des alias
[10, 5]
```

_non mutabilité des tuples_

```python
>>> t = (4, 5)
>>> t_bis = t
>>> t[0]= 10  # La modification d'une donnée présente dans le tuple est impossible
Traceback (most recent call last):
  File "<pyshell>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

* __Lorsqu'on souhaite calculer plusieurs valeurs dans une fonction__ le tuple peut être un type de données utilsé comme valeur de retour.

_Exemple de la division euclidienne_

```python
def division (a, b):
""" Effectue la division euclidienne de a par b
:param int a: dividende
:param int b: diviseur
:return: un couple (quotient, reste)
"""
    return (a // b, a % b)

quotient, reste = division(5, 2)
```

Ici la valeur de retour est un tuple. Lorsqu'on appelle la fonction, il suffit de disperser le tuple pour récupérer le `quotient` et le `reste` dans deux variables indépendantes.


