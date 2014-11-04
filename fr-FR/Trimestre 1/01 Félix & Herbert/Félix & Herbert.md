Niveau 1

#Felix & Herbert

__Introduction:__
On va jouer au chat et à la souris avec __Félix le chat__ et __Herbert__ la souris. C’est toi qui guides Herbert la souris avec ton pointeur de... souris et tu dois essayer de ne pas te faire attraper par Félix. Plus tu lui échappes longtemps, plus tu marqueras de points. Mais s’il t’attrape, tu perdras alors des points !

##Étape 1 : Félix suit le pointeur de souris

1. Commence un nouveau projet (“Fichier" dans le menu du haut, puis “Nouveau”).
2. Clique sur la scène près du chat et sélectionne l’onglet “Arrière-plans”. Clique ensuite sur l'icône "Choisir un arrière-plan dans la bibliothèque" et choisis "hall" dans la catégorie "Intérieur". Supprime ensuite l'arrière-plan vide d’origine. 
3. Dans la section "Lutins" clique sur le chat et clique sur le "i" qui se trouve en haut à gauche. Change son nom et appelle-le “Félix”.
4. Fais en sorte que Félix puisse seulement se retourner horizontalement, de gauche à droite, en cliquant sur ce bouton : Flèche horizontale à 2 pointes.
5. Crée le script suivant :

```scratch

	quand DRAPEAU pressé
	répéter indéfiniment
		s'orienter vers pointeur de souris
		avancer de 10 pixels
		costume suivant
		jouer du tambour 3 pour 0.3 temps
	(fin répéter indéfiniment)
```
		
###Teste ton projet
__Clique sur le drapeau vert.__
Est-ce que Félix suit bien le pointeur de ta souris? 
Est-ce qu’il a l’air de marcher quand il avance? 
Est-ce qu’il avance à la bonne vitesse?

Enregistre ton projet

##Étape 2: Félix poursuit Herbert

__Maintenant nous voulons que Félix poursuive Herbert plutôt que le pointeur de souris.__

1. Crée un nouveau lutin en cliquant sur le bouton “Choisir un lutin dans la bibliothèque” et choisis “Mouse1” dans la catégorie “Animaux”.
2. Change le nom du personnage pour qu’il s’appelle “Herbert”.
3. Dans l'onglet "Costumes" clique sur le costume qui se trouve dans l'éditeur. Une case apparait alors autours du cosutume. En déplaçant les coins, reduits la taille de Herbert pour qu'il soit plus petit que Félix.
4. Assure-toi que Herbert ne puisse se tourner que de manière horizontale, de gauche à droite en cliquant sur le bouton: Flèche horizontale à 2 pointes.
5. Créé le script suivant pour Herbert :


```scratch
	
	quand DRAPEAU pressé
	répéter indéfiniment
		aller à pointeur de souris
		s'orienter vers Félix
	(fin répéter indéfiniment)
```

###Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que Herbert bouge avec le pointeur de souris?
Est-ce que Félix poursuit Herbert?

Enregistre ton projet.

##Étape 3 : Félix parle quand il a attrapé Herbert

__On veut que Félix sache quand il a attrapé Herbert, et qu'il nous le dise.__


1. Change le script de Félix de la manière suivante :

```scratch
	
	quand drapeau pressé
	répéter indéfiniment
		s'orienter vers pointeur de souris
		avancer de 10 pixels
		costume suivant
		jouer du tambour 3 pour 0.3 temps
		si Herbert touché? alors
			dire Je t’ai attrapé! pendant 1 secondes
		(fin si)
	(fin répéter indéfiniment)
```

###Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que Félix dit quelque chose quand il touche Herbert?

Enregistre ton projet

##Étape 4 : Herbert se transforme en fantôme quand il se fait attraper

1. Modifie le script de Félix pour envoyer un message quand il attrape Herbert:

```scratch
	
	quand drapeau pressé
	répéter indéfiniment
		s'orienter vers pointeur de souris
		avancer de 10 pixels
		costume suivant
		jouer du tambour 3 pour 0.3 temps
		si Herbert touché 
			envoyer à tous attrapé
			jouer du tambour 17 pour 0.2 temps
			attendre 1 secondes
		(fin si)
	(fin répéter indéfiniment)
```
2. Ajoute un nouveau costume à Herbert en séléctionnat Herbert, va ensuite dans l'onglet "Costumes" et clique sur "Choisir un costume dans la bibliothèque". Choisis le costume "ghost2-a" dans la catégorie "Fantasie"
3. Rends le costume plus petit en cliquant sur le costume dans l'éditeur et en déplaçant ensuite les coins qui entourent le costume.
4. Renomme les costumes d’Herbert de façon à appeler le costume de la souris “vivant” et le costume du fantôme “mort”.
5. Crée le script suivant pour Herbert, pour le transformer en fantôme :

```scratch
	
	quand je reçois attrapé
	basculer sur costume mort
	attendre 1 secondes
	basculer sur costume vivant
```
	
###Teste ton projet
__Clique sur le drapeau vert.__

Est ce que Herbert devient un fantôme quand il se fait attraper? 
Est ce que Félix joue le bon son au bon moment? 
Est ce que Félix reste immobile assez longtemps pour que Herbert puisse s’échapper? 

Enregistre ton projet.

##Étape 5 : Compte les Points

Le score commencera à zéro et il sera augmenté d’un point par seconde. Si Félix attrape Herbert, le score devra diminuer de 100 points.

1. Crée une variable pour tous les lutins, appelée “Score” : choisis l’option “Données” dans l’onglet “Scripts”, puis clique sur “Créer une variable” assure-toi que la case "Pour tous les lutins" est coché.
2. Sélectionne la scène et crée les deux scripts suivants :

```scratch
	
	quand drapeau pressé
	mettre Score à 0
	répéter indéfiniment
		ajouter à Score 1
		attendre 1 secondes
	(fin répéter indéfiniment)
	
	quand je reçois Attrapé
	ajouter à Score -100
```
	
###Teste ton projet
__Clique sur le drapeau vert__

Est-ce que le score augmente d’un point par seconde? 
Est-ce que le score diminue de 100 points quand Herbert se fait attraper? 
Que se passe-t-il quand Herbert se fait attraper avant que le score n’atteigne 100? 
Est-ce que le score redémarre à zéro quand tu commences une nouvelle partie?

Enregistre ton projet

__Bravo, tu as fini ! Tu peux maintenant t’amuser !__
N’oublie pas que tu peux partager ton jeu avec tes amis et ta famille en cliquant sur le bouton __Partage__ en haut à droite. 
