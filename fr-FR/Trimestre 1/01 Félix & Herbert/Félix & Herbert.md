---
title: Félix & Herbert
level: Niveau 1
language: fr-FR
stylesheet: scratch
embeds: "*.png"
materials: ["Félix & Herbert.sb2"]
...

# Introduction { .intro }

On va jouer au chat et à la souris avec __Félix le chat__ et __Herbert__ la souris. C’est toi qui guides Herbert la souris avec ton pointeur de... souris et tu dois essayer de ne pas te faire attraper par Félix. Plus tu lui échappes longtemps, plus tu marqueras de points. Mais s’il t’attrape, tu perdras alors des points!

![screenshot](felixherbert_screenshot.png)

# Étape 1 : Félix suit le pointeur de souris { .activity }

## Liste d'activités { .check }

+ Commence un nouveau projet (`Fichier` dans le menu du haut, puis `Nouveau`).
+ Clique sur la **scène** près du chat et sélectionne l’onglet `Arrière-plans`. Clique ensuite sur l'icône `Choisir un arrière-plan dans la bibliothèque` et choisis **hall** dans la catégorie **Intérieur**. Supprime ensuite l'arrière-plan vide d’origine. 
+ Dans la section Lutins clique sur le chat et clique sur le `i` qui se trouve en haut à gauche. Change son nom et appelle-le **Félix**.
+ Fais en sorte que Félix puisse seulement se retourner horizontalement, de gauche à droite, en cliquant sur ce bouton : <img alt="" class="inline" src="flip_arrows.png">
+ Crée le script suivant:
```scratch
	quand le DRAPEAU VERT pressé
	répéter indéfiniment
		se diriger vers [pointeur de souris v]
		avancer de (10) pas
		costume suivant
		jouer du tambour [3 v] pendant (0.3) temps
```
		
## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est-ce que Félix suit bien le pointeur de ta souris? 
+ Est-ce qu’il a l’air de marcher quand il avance? 
+ Est-ce qu’il avance à la bonne vitesse?

## Enregistre ton projet { .save }

# Étape 2: Félix poursuit Herbert { .activity }

Maintenant, nous voulons que Félix poursuive Herbert plutôt que le pointeur de souris.

## Liste d'activités { .check }

+ Crée un nouveau lutin en cliquant sur le bouton `Choisir un lutin dans la bibliothèque` { .blockgrey } et choisis **Mouse1** dans la catégorie **Animaux**.
+ Change le nom du personnage pour qu’il s’appelle **Herbert**.
+ Dans l'onglet __Costumes__ clique sur le costume qui se trouve dans l'éditeur. Une case apparait alors autours du costume. En déplaçant les coins, reduits la taille de Herbert pour qu'il soit plus petit que Félix.
+ Assure-toi que Herbert ne puisse se tourner que de manière horizontale, de gauche à droite en cliquant sur le bouton: <img alt="" class="inline" src="flip_arrows.png">
+ 
+ **Créé le script suivant pour Herbert:**
```scratch
	quand le DRAPEAU VERT pressé
	répéter indéfiniment
		aller à [pointeur de souris v]
		se diriger vers [Félix v]
```

## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est-ce que Herbert bouge avec le pointeur de souris?
+ Est-ce que Félix poursuit Herbert?

## Enregistre ton projet { .save }

# Étape 3 : Félix parle quand il a attrapé Herbert

On veut que Félix sache quand il a attrapé Herbert, et qu'il nous le dise.

## Liste d'activités { .check }

+ Change le script de Félix de la manière suivante:

```scratch
	quand le DRAPEAU VERT pressé
	répéter indéfiniment
		se diriger vers [pointeur de souris v]
		avancer de (10) pas
		costume suivant
		jouer du tambour [3 v] pendant (0.3) temps
		si <[Herbert v] touché?> alors
			dire [Je t’ai attrapé!] pendant (1) secondes

```

## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est-ce que Félix dit quelque chose quand il touche Herbert?

## Enregistre ton projet { .save }

# Étape 4 : Herbert se transforme en fantôme quand il se fait attraper

On veut que Herbert sache quand il se fait attraper et se transforme en fantôme.

## Liste d'activités { .check }

+ Modifie le script de Félix pour envoyer un message quand il attrape Herbert:
```scratch
	quand le DRAPEAU VERT pressé
	répéter indéfiniment
		se diriger vers [pointeur de souris v]
		avancer de (10) pas
		costume suivant
		jouer du tambour [3 v] pendant (0.3) temps
		si <[Herbert v] touché?> alors 
			envoyer à tous [attrapé v]
			jouer du tambour [17 v] pendant (0.2) temps
			attendre (1) secondes

```
+ Ajoute un nouveau costume à Herbert en séléctionnat Herbert, va ensuite dans l'onglet __Costumes__ et clique sur `Choisir un costume dans la bibliothèque` { .blocklightgrey }. Choisis le costume **ghost2-a** dans la catégorie **Fantasie**.
+ Rends le costume plus petit en cliquant sur le costume dans l'éditeur et en déplaçant ensuite les coins qui entourent le costume.
+ Renomme les costumes d’Herbert de façon à appeler le costume de la souris “vivant” et le costume du fantôme “mort”.
+ Crée le script suivant pour Herbert, pour le transformer en fantôme :

```scratch
	quand je reçois [attrapé v]
	basculer sur costume [mort v]
	attendre (1) secondes
	basculer sur costume [vivant v]
```
	
## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est ce que Herbert devient un fantôme quand il se fait attraper? 
+ Est ce que Félix joue le bon son au bon moment? 
+ Est ce que Félix reste immobile assez longtemps pour que Herbert puisse s’échapper? 

## Enregistre ton projet { .save }

# Étape 5 : Compte les Points

Le score commencera à zéro et il sera augmenté d’un point par seconde. Si Félix attrape Herbert, le score devra diminuer de 100 points.

## Liste d'activités { .check }

+ Crée une variable pour tous les lutins, nommée Score. Choisis pour cela `Données` { .blockorange } dans l’onglet `Scripts`, puis clique sur `Créer une variable`, appelle-la `Score` { .blockorange } et assure-toi que la case "Pour tous les lutins" est bien coché.
+ Sélectionne la scène et crée les deux scripts suivants:
```scratch
	quand le DRAPEAU VERT pressé
	mettre [Score v] à [0]
	répéter indéfiniment
		ajouter à [Score v] (1)
		attendre (1) secondes
	
	quand je reçois [Attrapé v]
	ajouter à [Score v] (-100)
```
	
## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est-ce que le score augmente d’un point par seconde? 
+ Est-ce que le score diminue de 100 points quand Herbert se fait attraper? 
+ Que se passe-t-il quand Herbert se fait attraper avant que le score n’atteigne 100? 
+ Est-ce que le score redémarre à zéro quand tu commences une nouvelle partie?

## Enregistre ton projet { .save }

Bravo, tu as fini ! Tu peux maintenant t’amuser !
N’oublie pas que tu peux partager ton jeu avec tes amis et ta famille en cliquant sur le bouton **Partage** en haut à droite. 
