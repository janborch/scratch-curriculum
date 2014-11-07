---
title: La chasse aux fantômes
level: Level 1
language: fr-FR
stylesheet: scratch
...

# Introduction { .intro }

Ce projet est comme le jeu du __Tir aux Pigeons__. Tu gagnes des points en touchant les fantômes qui apparaissent à l’écran. Le but du jeu est de gagner le plus de points possibles en 30 secondes!

# Étape 1 : Crée un fantôme volant { .activity }

## Liste d'activitées { .check }

+ Démarre un nouveau projet Scratch
+ Enlève le lutin chat et remplace l’arrière plan de la scène par l’arrière plan **woods** dans la catégorie **Dehors**.
+ Clique sur le bouton `Choisir un lutin dans la bibliothèque` pour ajouter un nouveau lutin au projet (utilise le costume **fantasie\ghost1**).
+ Nous voulons faire bouger notre fantôme. Ajoute une `Variable`pour ce lutin uniquement et nomme-la `vitesse` { .blockorange }.
+ Sur la **scène**, tu dois voir écrit __Ghost1: vitesse__. S'il est écrit seulement “vitesse”, supprime la variable et recommence. Lors de la création, il faut s’assurer de cliquer sur le bouton `Pour ce lutin uniquement`. Décoche la case à gauche de la variable vitesse dans **Données**. La variable vitesse va contrôler la vitesse de déplacement du fantôme. Nous allons utiliser cette variable pour pouvoir changer la vitesse au cours du jeu.
+ Nous voulons que le fantôme commence à bouger quand le jeu démarre. __Écris donc un script comme ceci__ :
```blocks
    quand le DRAPEAU VERT pressé
        mettre [vitesse v] à [5]
        répéter indéfiniment
            avancer de (vitesse) pas
```
		
## Teste ton projet { .flag }
Clique sur le drapeau vert et regarde ce que fait le fantôme.
Pourquoi reste-t-il collé dans le coin de l’écran?

## Enregistre ton projet { .save }

## Liste d'activitées { .check }

+ Pour décoller le fantôme nous devons le faire partir dans l’autre sens quand il touche le bord de l’écran. Au niveau de ton script, ajoute le bloc `rebondir si le bord est atteint` { .blockblue } aprés ton bloc `avancer de`{ .blockblue }`vitesse`{ .blockorange }`pixels`{ .blockblue }.
```blocks
    quand le DRAPEAU VERT pressé
        mettre [vitesse v] à [5]
        répéter indéfiniment
            avancer de (vitesse) pas
            rebondir si le bord est atteint
```
+ Pour que le fantôme n'ait pas la tête en bas quand il touche le bord, clique sur le bouton `Flèche horizontale à 2 pointes`. 

## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est ce que la sorcière se déplace d’un bord à l’autre de l’écran ?

## Enregistre ton projet { .save }

## A essayer { .try }

+ Essaie de changer la valeur de la variable “vitesse” pour faire voler le fantôme plus rapidement ou plus lentement.
+ Comment ferais-tu pour que le fantôme bouge de plus en plus vite? (C’est une tâche délicate. Ne t’inquiète pas si tu n’arrives pas à le faire. Tu vas avoir plus d’indices en continuant le projet.)

# Étape 2 : Fais apparaître et disparaître la sorcière de manière aléatoire { .activity .new-page }

Pour rendre le jeu plus amusant, nous voulons faire apparaître et disparaître le fantôme de manière aléatoire. Nous ferons ça avec un autre script qui va tourner en même temps que celui du mouvement du fantôme. Ce script doit faire disparaître le fantôme pendant un temps aléatoire, puis le faire apparaître de nouveau pour un temps alétoire. Et recommencer indéfiniment (ou jusqu’à la fin du jeu).

## Liste d'activitées { .check }

+ Crée ce script pour le fantôme :
```blocks
    quand le DRAPEAU VERT pressé
    répéter indéfiniment
	cacher
        attendre (nombre aléatoire entre (2) et (5)) secondes
        montrer
        attendre (nombre aléatoire entre (3) et (5)) secondes
```

## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est-ce que le fantôme se déplace d’un bord à l’autre de l’écran, apparaît et disparaît d’une manière aléatoire?

## Enregistre ton projet. { .save }

## A essayer { .try }

+ Essaie de changer les limites des nombres aléatoires. Qu’est ce qui se passe si tu choisis de grands nombres ou de petits nombres? (Est-ce que ça te donne plus d’indices sur la manière d’accélerer la vitesse du fantômee au fur et à mesure du jeu ?)

# Étape 3 : Fais disparaître la sorcière quand on clique dessus { .activity }

Pour transformer notre projet en jeu, il faut donner aux joueurs quelque chose à faire. Ils ont besoin de cliquer sur le fantôme pour le faire disparaître. Quand ils le touchent, nous voulons qu’il disparaisse tout en jouant un son.

## Liste d'activitées { .check }

+ Dans l’onglet **Sons**, ajoute le son **electronique\fairydust** en utilisant le bouton `Choisis un son dans la bibliothèque`. 
+ Ajoute ce script au fantôme:
```blocks
    quand ce lutin est cliqué
    	cacher
	jouer le son [Fairydust v]
```
## Teste ton projet { .flag }
Clique sur le drapeau vert.

+ Est-ce que le fantôme disparaît et joue un son quand tu cliques dessus?

## Enregistre ton projet { .save }

## A essayer { .try }

+ Demande si tu peux enregistrer toi même ta voix.

# Étape 4 : Ajoute un score et un chronomètre { .activity .new-page }

Nous avons notre fantôme, mais nous voulons réaliser un vrai jeu! Nous voulons marquer des points à chaque fois que nous cliquons sur le fantôme, ainsi qu’un temps de jeu limité. On va utiliser une variable pour le score et une pour le chronomètre.

## Liste d'activitées { .check }

+ Crée une nouvelle `variable`, appelle-la **score**. Change ensuite le script du fantôme  pour que le score augmente d’un point chaque fois qu’il est cliqué. 
```blocks
	quand ce lutin est cliqué
    	cacher
	   jouer le son [Fairydust v]
	   ajouter à [score v] (1)
```

+ Clique sur la **scène** et crée une **nouvelle variable**, appelle-la **temps_restant**. 
+ Ajoute un nouveau script qui s’exécute quand on appuie sur le drapeau vert. Le script met `temps_restant` { .blockorange } à **30** et remet le score à **0**. Ensuite, utilise le bloc `répéter jusqu’à` { .blockyellow } pour attendre une seconde puis diminuer le `temps_restant` { .blockorange } de 1. Il faut répéter tout ça jusqu’à ce que le chronomètre soit à 0, à ce moment là, utilise le bloc `stop tout` { .blockyellow } pour arrêter le jeu. 
```blocks
	quand le DRAPEAU VERT pressé
    	mettre [temps_restant v] à (30)
    	mettre [score v] à (0)
    	répéter jusqu'à <(temps_restant) = [0]>
    		attendre (1) secondes
    		ajouter à [temps_restant v](-1)
    	fin
    	stop [tout v]
```

## Teste ton projet { .flag }
Clique sur le drapeau vert.

## Enregistre ton travail { .save }

## A essayer { .try }
+ Comment tu peux faire bouger le fantôme de plus en plus vite?


Très bien. Tu as terminé le jeu de base. Mais tu peux encore améliorer le jeu. Relève ces défis!

## Défi : ajoute d’autres fantômes { .challenge }

Un fantôme, c'est bien. Plus de fantômes, c’est encore mieux ! Ajoutons deux autres fantômes volants.

1. Duplique le fantôme en **cliquant dessus avec le bouton droit** de la souris dans la zone des lutins (la zone inférieure droite de l’écran) 
2. **Change la taille de chaque lutin** pour avoir des fantômes de differentes tailles.
3. Pour chaque fantôme, change **la variable vitesse** pour avoir des fantômes qui volent à des vitesses différentes.
4. Déplace les fantômes dans differents endroits de la scène, pour qu'ils ne soient pas tous dans un tas.

## Teste ton projet { .flag }
Clique sur le drapeau vert. 

+ Est-ce que tu as plusieurs fantômes qui se déplacent d’un côté à l’autre de la scène?
+ Est-ce qu’ils apparaissent et disparaissent d’une manière aléatoire? 
+ Est-ce qu’ils disparaissent quand tu cliques dessus? 

## Enregistre ton travail { .save }

## A essayer { .try }

+ Quel est un bon nombre de fantômes pour le jeu?
+ Est-ce que tu peux changer l’apparence des fantômes? Tu pourrais éditer leurs costumes, ou bien utiliser des blocs de la palette “Apparence” pour les changer.
+ Que penses-tu de faire que le plus rapide (et le plus petit) fantôme soit celui qui donne 10 points ?


Bravo ! Tu as terminé. Maintenant, tu peux t’amuser avec le jeu.
N’oublie pas que tu peux partager ton jeu avec tous tes amis et ta famille en cliquant sur le bouton **Partage** dans la barre des menus.
