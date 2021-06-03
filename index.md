---
layout: page
title: Steam Reviews Analysis
cover-img: "img/steam_big.jpg"
subtitle: A EPFL-Unil collaborative project
---

{% include konami.html %}

## Objectives

- Are the official tags relevant ?
- Can we classify games  by looking at the way players review them ?
- Does this classification bare resemblance to the commonly used tags ?
- Can Machine Learning help define a new classification ?

## State of the art du game classification

C'est très très le texte

## Dataset presentation

#### d'ou est-ce qu'il sort

#### que contient-il en data, metadata 

#### point de vue critique par rapport à son contenu (en gros les question adressée et reçue par Marko)


## Machine learning tools used: presentation

#### Word embedding

#### K-means

#### PCA

#### quels sont les input et comment ont-ils été sélectionnés/ajouté (tag manuellement ajouté par exemple)

## Résultats des petites questions statistiques
(Number of review per category available when hovered upon )
#### Average rating of the games in our dataset
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/average_all.html"></iframe>
discussions on this high number ?
#### Average rating of games received for free or not
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/recivedForFree.html"></iframe>
Surprisingly the same
#### Average rating of games played during early access or not
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/early.html"></iframe>
A bit more critical when game in early access
#### Average rating from users that posted a certain number of reviews
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/numReview.html"></iframe>
More critical when the user posts more reviews until a point
#### Average rating from users that own a certain number of games
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/owned.html"></iframe>
More critical when the user owns more games
#### Average rating from reviews with a certain number of words
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/words.html"></iframe>
To be redone, I'm not sure if "no text" review are possible, maybe bug of word counting

#### Repartition of tags along each PCA axes
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/tag_repartition.html"></iframe>
#### 1st dimension games projection
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/dim_games.html"></iframe>