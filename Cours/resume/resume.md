**CEQU’ILFAUTSAVOIRDEPYTHONENSECONDE PAGE2/NUMPAGES7![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.001.png)**

1  **Principesdebase**
- Pythonpeutfonctionneren **modeinteractif** :une **console** (ou **shell** )afficheune *invitedecommande* (reconnaissable aux *tripleschevrons* >>>).Onsaisitdes **instructions** qui,unefois **validées** parunappuisurlatouche ,sont **aussitôt exécutées![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.002.png)**, et leur **éventuel résultataffiché**.
- Python sait **exécuter** des **programmes(ou scripts )enregistrésdansdesfichiersportantl’extension .py**.
- Onréservel’utilisationdelaconsoleauxtestsrapides: **uncodequidépassequelqueslignesseraenregistréetexé- cutédepuisunfichier** (les modifications sont simplifiées).
- **Onmetuneinstructionparligne:** des lignes courtes sont plus *lisibles*.
- **Lesinstructionss’enchaînentligneàligne,séquentiellement,** delapremièreàladernière,saufsil’ordred’exécution est modifié par une *structure de contrôle* (voir plus loin les boucles et les tests).
2  **Lesvariables**
- **Unevariable permetdemémoriseruneinformation** ,qu’onpourraensuiteréutilisergrâceàsonnom.Cenom **doit** débuter par une lettre, et peut comporter d’autres lettres, des chiffres ou le caractère «\_» (touche   ).![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.003.png)
- Lorsqu’on mémorise une valeur à l’aide d’une variable, on parle d’**affectation** : l’instruction Python **taille = 175.2 affectelavaleur 175.2 àlavariablenommée taille.**
- **Dansun [algorithme ,](https://fr.wikipedia.org/wiki/Algorithme)l’affectations’écritsouvent a ![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.004.png)2**. Cette ligne,et l’instruction Python **a = 2**, se traduisenten français par *«la variable* **a** *prend la valeur* **2***»*.
- **⚠ UnevariablenedoitJAMAISporterunnomdéjàréservéparPython**
- **Les variables peuvent «changer de valeur» au cours du temps**. Elles permettent de mémoriser des nombres mais aussidutexte,parexemple: vente = """Ça coûte 10 €""" ; **print**(vente).Notezles3guillemetsdepartetd’autre du texte : ils le délimitent. L’ensemble se nomme une **chaînedecaractères**.
- On peut «fairedes choses» avecdes variables,notamment calculer : lesopérationshabituellessontdisponibles(utiliserlesparenthèseslorsquec’estnécessaire).Notezquel’addition



permet de «coller» des chaînes de caractères(on dit «concaténer» : **print**("""Ça""" + """va ?"""));

la puissance est représentée par deux étoiles \*\* :a = 2\*\*10 ; **print**(a) calculera 210 puis affichera 1024;



la division standard donne un résultat *décimal* :b = 9/4 ; **print**(b) calculera puis affichera 2.25 ;



la division *entière* existe. L’opérateur associé est le «double *slash* »// :c = 9//4 ; **print**(c) affichera 2;



le *reste de la division entière* est donné par l’opérateur «modulo» %. On a la relation a = ( a//b) × b + (a%b) : 

avec a = 7 et b = 2 , on a 7 = 2 × 3 + 1, et a // b donnera 3 tandis que a%bdonnera 1.

- Ces exemples montrent des données de différentes *natures* : on parle de **type d’une donnée** et, par extension, **de la variable** qui la désigne. Entre autres, il y a le type entier int, flottant (ou décimal) float, et chaîne de caractères str.
- **Optionnel** *On peut convertir une variable d’un type à un autre.Ainsi :*

*l’instruction* texte = str(3.14) *mémorisera la* chaîne de caractères "3.14" via *la variable nommée* texte *;![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.005.png)*



*l’instruction* entier = int(3.14) *mémorisera la valeur* entière 3 via *la variable nommée* entier *;*



*l’instruction* entier = int("3") *mémorisera la valeur* entière 3 via *la variable nommée* entier *;*



*l’instruction* dec = float("3.14") *mémorisera la valeur* décimale 3.14 via *la variable nommée* dec*.*



- **Optionnel** *Unprogrammepeutinteragiravecl’utilisateur.L’instruction* nom = input("""Saisir votre nom : """) ![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.006.png)*mémorisera dans la variable* nom*une chaîne de caractères censée contenir le nom de l’utilisateur.*

**Exemples:**

1  >>> valeur = 10 // 3 + 7 % 5 # Ceci est un commentaire, utile aux humains. Python les ignore.![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.007.png)
1  >>> **print**(valeur) # Affichera 5
1  >>> valeur = valeur - 3 # Écriture surprenante, non ?
1  >>> **print**(valeur) # Affichera 2

L’instruction ligne 3 ressemble à une équation qui n’aurait *aucune* solution. En informatique, elle signifie *«récupére la valeur désignée par la variable* valeur*,retranche lui* 3*,puis affecte le résultat à la variable* valeur *»*.

**CEQU’ILFAUTSAVOIRDEPYTHONENSECONDE 2/[4**](#_page3_x28.48_y28.48)**

3  **ÉtendrelesfonctionnalitésdePython**

Python ne connaît de base qu’un petit nombre d’opérations et fonctions (par exemple, il ignore comment calculer

un sinus). Pour étendre ses capacités, on dispose de *bibliothèques* de fonctions additionnelles, ou **modules**. Pour importer un module, la syntaxe est **from module import** \*. On remplacera le plus souvent **module**par :

- [**math**](https://docs.python.org/fr/3/library/math.html): donne accès aux *fonctions mathématiques*, comme sqrt (racine carrée), sin (sinus), la constante pi, etc.;
- [**random**](https://docs.python.org/fr/3/library/random.html): donne accès aux *fonctions aléatoires*. En particulier :

random: chaque fois que la commande alea = random() sera exécutée, la variable alea désignera une valeur 

*décimale* prise au hasard entre 0 *inclus* et 1 *exclus*.

 randint : chaque fois que la commande alea = randint(1,6) sera exécutée, la variable alea désignera une valeur *entière* prise au hasard entre 1 et 6 *inclus* (valeurs à adapter selon les besoins).

- [**turtle** ](https://docs.python.org/fr/3/library/turtle.html): donne accès à des fonctions permettant de réaliser simplement des *tracés*.
4  **Structuredecontrôlen o1:lafonction**

Ilestfréquentquedesportionsdecodesserépètent:aulieuderecopierlecode, **ondéfinitunefonction** ,qu’onpeut ensuite **appeler** chaque fois que c’est utile. La définition d’une nouvelle fonction doit respecter les règles suivantes :

**Optionnel :** *paramètres de la*

*Mot-clef «* **def** *» pour Nom de la fonction fonction, séparés par des virgules![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.008.png)![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.009.png)*

*introduire une fonction***  distance(xA, yA, xB, yB): **Obligatoire :** *parenthèse***s![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.010.png)**

AB= ( (xB-xA)\*\*2 + (yB-yA)\*\*2 )\*\*0.5 *et deux-points «* **:***»*

*4 espaces pour délimiter* **return** AB *Mot-clef «***return** *» suivi de la le corps de la fonction variable «valeur de retour»*

- La déclaration d’une fonction est la ligne débutant par **def**, suivi d’une espace, puis du **nom** de la fonction, puis de **parenthèses** qui entourent les *éventuels* noms de ses *arguments*, séparés par des virgules s’il y en a plusieurs.
- Le**corps** delafonctionsuit,avecundécalagede4espacespourl’ensembledesinstructionsquilecomposent.Ilprend fin lorsque le décalage de 4 caractères s’arrête (sauter une ligne vide pour plus de lisibilité!).
- Si la fonction doit **renvoyer une valeur**, utiliser le mot-clé **return** suivi de la **valeur de retour** (souvent un nom de variable). Il ne devrait y avoir qu’au plus un **return** par fonction (utiliser une variable, qu’on renvoie à la fin).
- **Appeler** ou **exécuter** unefonctionsefaitenutilisantsonnomsuivideparenthèses: ma\_fonction() (insérerleséven- tuels arguments entre les parenthèses). **Unefonctiondoitêtredéfinie avant qu’onyfasseappel!**

**Exemple:** voici une définition de fonction pour un usage *purement* mathématique.

**def** f(x):![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.011.png)

**return** x\*\*2-3\*x+4

resultat = f(-2) # La variable nommée « resultat » mémorisera la valeur 14

5  **Structuredecontrôlen o2:laboucle«POUR»**

Une fonction permet de «factoriser» le code : c’est une sorte de raccourci. Mais si l’on veut exécuter 10 fois de suite

les mêmes instructions, il faudra recopier les 10 appels de fonctions : cela reste fastidieux! On peut faire mieux avec

une **boucle«POUR»**: un moyen simple de **répéterdesinstructionsunnombredéfini defois.** En voici la syntaxe :

*Nom de la variable «compteur»* **Obligatoires :** *mot-clef «* **in** *» et «***:***» final*

*Mot-clef «***for** *» pour introduire*

|compteur **in**|
| - |
|instruction1 instruction2 ...|

range(debut, fin, pas):

*Instruction «* range *» : voir les détails plus loin*

*la boucle «POUR»*

*4 espaces pour délimiter le corps de la boucle*

*Corps de la boucle : autant d’instructions que l’on veut*
**CEQU’ILFAUTSAVOIRDEPYTHONENSECONDE PAGE7/NUMPAGES7![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.001.png)**

L’instruction « range » admet 3 variantes, selon le nombre de paramètres, **tousentiers** , qu’on lui passe. Exemples :

- **for** compteur **in** range(5):

*La variable nommée* compteur *prendra successivement les valeurs* 0*,*1*,*2*,*3 *et* 4 *:* 5 *est donc la* **premièrevaleurqui NE sera PASprise** *par la variable* compteur*.*

- **for** compteur **in** range(-3, 2): compteur *prendrasuccessivementlesvaleurs* -3*,* -2*,* -1*,* 0*,*1*:* -3 *estdoncla* **premièrevaleurPRISE** *par* compteur*,* 2*est la* **premièrevaleurqui NEsera PASprise** *par* compteur*.*
- **for** compteur **in** range(8,1,-2):

compteur *prendra successivement les valeurs* 8*,*6*,*4 *et* 2 *:* 8 *est donc la* **première valeur PRISE** *par* compteur*,* 1 *est la* **premièrevaleurqui NEsera PASprise** *par* compteur*,et* **lesvaleurschangentparsautsdelongueur -2.**

- *Avec*«**for** compteur **in** range(1,8,2): »*,*compteur *prendra successivement les valeurs* 1*,*3*,*5 *et* 7*.*

**Exemples:**

Les codes ci-dessous produisent les tracés à leurs droites.

**from turtle import** \* ![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.012.png)![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.013.png)![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.014.png)![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.015.png)![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.016.png)**from turtle import** \* 

speed(0) 

**for** i **in** range(5): 

**for** i **in** range(20,480,5): left(144) 

forward(i) forward(300) 

left(91) 

6  **Structuredecontrôlen o3:testsetstructuresconditionnelles**

Untest(ou *structureconditionnelle* )permetde **[modifierlefluxd’exécutiond’unprogramme** ](https://fr.wikipedia.org/wiki/Structure_de_contr%C3%B4le)**(qui,autrement,s’exé- cute *séquentiellement*,desapremièreligneàsadernièreligne).Ildéclenchel’exécutiond’unblocd’instructionssiune condition est vérifiée. Plusieurs tests peuvent s’enchaîner.Voici la structure générale d’un test.

*Mot-clef «***if** *» pour Différentes conditions du test (voir détails plus bas)![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.017.png)*

*introduire un test***  condition1: **Obligatoires :**

*Mot-clef «***elif** *» pour* instruction1 **deux-points « :»** *Instruction(s) exécutée(s) ajouter un 2 e test* ... *si* condition1 *est vérifiée*

*(puis un 3 e, un 4 e...)***  condition2: *Instruction(s) exécutée(s) 4 espaces pour délimiter les* instruction2 *si* condition2 *est vérifiée*

*instructions liées aux tests* ... *Instruction(s) exécutée(s) Mot-clef «***else** *» pour*** : *si aucune condition*

*les autres possibilités* instructionAutre *n’est vérifiée*

**Lesconditionssontlecœurdutest:** ellesimpliquentlacomparaisonentreunevariable(oulerésultatd’unappelde fonction) et une valeur, ou entre deux variables. **Lesopérateursdecomparaisonessentielssont:**

**==** pour l’égalité *(il s’agit bien d’un «double égal»!)*:a == 2sera vrai si la variable nommée a désigne la valeur 2. **!=** pour la différence : a != 2 sera vrai si la variable nommée a désigne une valeur *autre* que 2;

**>** pour la supériorité stricte, **>=**pour la supériorité large : a >= 2sera vrai si a ⩾ 2;

**<** pour l’infériorité stricte, **<=**pour l’infériorité large : a <= 2sera vrai si a ⩽ 2.

Python comprend des tests tels que 2 < a <= 3, et on peut combiner des tests avec les opérateurs logiques :

**not** pour le contraire : **not** (a > 2) sera vrai lorsque a ⩽ 2;

**and** pour «et» : (a > 2) **and** (a < 3) sera vrai lorsque 2 < a < 3 , et sera donc équivalent au test 2 < a < 3;

**or** pour «ou» : (a < 2) **or** (a > 3) sera vrai lorsque a < 2 ou a > 3 , soit a ∈] − ∞;2[∪]3;+∞[.

**Optionnel** *Le résultat d’un test est une valeur appelée booléen (de type* bool*).Il n’existe que deux valeurs booléennes :![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.018.png)*

True *(«vrai») et* False *(«faux»). Évidemment* **not** True *donne* False*, et donc* **not** True == False *donne* True ©*! Attention aux surprises néanmoins :* 0.1\*3 == 0.3 *donnera* False *(pourquoi? réponse en spécialité NSI* ©*!)*

**Optionnel** *On teste l’appartenance à une chaîne de caractères avec le mot-clef* **in** *:*"BA" **in** "ABBA"*vaudra* True *!![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.019.png)*

**Exemple:** voici une définition de fonction reposant sur un test. Elle donne l’issue d’un examen selon le résultat.

**def** issue\_examen(moyenne): On utilise cette fonction de la façon suivante :![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.020.png)

1 **if** moyenne < 8: resultat = "Vous êtes " + issue\_examen(11.5)

2 **return** """refusé""" **print**(resultat) # Affichera « Vous êtes admis » 3564 : """admis""" place à l’intérieur de la clause **else**, afin de n’être effec-![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.021.png)

**elif**

8 <= moyenne"""au rattrapage"""< 10: On pourrait ajouter d’autres tests pour tenir compte des

**return**

mentions (ces tests complémentaires devraient prendre **else**

**return**

7 tués que s’ils sont réellement utiles).

7  **Structuredecontrôlen o4:laboucle«TANTQUE»**

Si la boucle «POUR» permet de répéter des instructions un nombre de fois *connu à l’avance* , **la boucle «TANT QUE» répétera des instructions TANT QU’une condition reste vraie.** La boucle sera quittée dès que la condition ne sera

plus vérifée : **uneboucle«TANTQUE»impliquedoncuntest!** En voici la structure.

**Condition de répétition** *de la boucle![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.022.png)*

*Mot-clef «***while** *»*

*pour introduire la***  condition: *deux-points***Obligatoir***«***e ::***»*

*boucle «TANT QUE»* instruction1

*4 espaces pour délimiter* instruction2 *Corps de la boucle : autant le corps de la boucle* ... *d’instructions que l’on veut*

**Laconditionpeutêtren’importequeltestconvenablementrédigé** (ycomprisuntestcomposé,faisantappelàdes opérateurs logiques) : tant qu’elle reste vraie, les instructions contenues dans le corps de la boucle seront répétées (éventuellementindéfiniment,sil’onn’yprendpasgarde!).Ilestdonc *important* queletestdecetteconditionporte sur une variable qui *évolue* (qui désigne une valeur qui change) au cours des passages dans la boucle!

**Optionnel** *On peut quitter une boucle «de force» avec le mot-clef* **break** *(mais c’est une pratique considérée comme ![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.023.png)inélégante,il est donc préférable de l’éviter).*

**Exemple:** la[` `**conjecturedeCOLLATZ**.](https://www.youtube.com/watch?v=BP2G28694z8) Prenez un nombre entier positif, et appliquez lui le traitement suivant :

- s’il est pair, vous le divisez par 2; ▶ s’il est impair, vous le multipliez par 3 et ajoutez 1.

Vous obtenez alors un nouveau nombre, sur lequel vous répétez la procédure. Et ainsi de suite... La [conjecture de SYRACUSE](https://scienceetonnante.com/2011/06/27/la-conjecture-de-syracuse/)[(l’un de ses autres noms) s](https://fr.wikipedia.org/wiki/Conjecture_de_Syracuse)’énonce ainsi : quel que soit l’entier choisi au départ, on finira par obtenir 1. [**Aucun mathématicienn’estenmesuredeprouversavéracité** ,](http://revue.sesamath.net/spip.php?article930)àl’heureactuelle(mêmesionlapenseexacte)!Voici une fonction, impliquant une boucle «TANT QUE» (ainsi que des tests), permettant de débuter son exploration.

1 **def** verifie\_collatz(n):![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.024.png)

2 **while** n != 1: # Tant que n est différent de 1...

3 **print**(n) # On affiche n (/!\ rien à voir avec la valeur renvoyée par la fonction)

4 **if** n % 2 == 0: # n%2 est le reste de la division entière de n par 2. S'il est nul alors

5 n = n // 2 # n est pair et on peut diviser n par 2.

6 **else**: # Sinon n est impair et le nouveau nombre à considérer, toujours désigné 7 n = 3\*n + 1 # par la variable n, est le triple du nombre n précédent augmenté de 1.

8 **return** True # Si on arrive ici, la fonction renvoie le booléen True (« vrai »).

On utilise cette fonction de la façon suivante :

n = 31![](Aspose.Words.490e7295-3fe6-497a-b3a2-334716dce2d7.025.png)

**if** verifie\_collatz(n):

**print**("""C'est bon pour """ + str(n))

**Remarque :** *vous noterez que, d’un point de vue logique, nous ne sommes pas du tout assurés que l’exécution de cette fonction puisse systématiquement s’achever (car si la conjecture de SYRACUSE était fausse...).*
