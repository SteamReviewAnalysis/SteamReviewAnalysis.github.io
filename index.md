---
layout: page
title: Steam Reviews Analysis
cover-img: "img/steam_big.jpg"
subtitle: A EPFL-Unil collaborative project
---

{% include konami.html %}

## Objectives
With this project we tried to answer the following questions:

- Are the game categories used usually relevant?
- Can we classify games by looking at the way players review them?
- More specifically, can Machine Learning help define a new classification?
- Does this classification bare resemblance to the traditionnal categories?

## State of the art du game classification

C'est très très le texte

## Dataset presentation
For this project we used a huge dataset of steam reviews compiled in 2021 available on Kaggle[^1]. 

#### Contents
It contains 21 million user reviews, 10 million of which are in english, from around 300 different games.
For each review there is the text and the recommendation, but also additionnal metadata such as the number of games owned by the author,
the number of review they posted, if they received the game for free or if it was during early access. 

#### Source caveats
Because only a subset of all reviews from Steam were kept for this collection, potential biases were introduced.
We asked the author for more information on the selection of the games. They said: *"The games were picked by hand without stringent criteria. I did, however, pay attention to a few aspects and made an effort to include: both mainstream titles as well as indie titles, largely positively reviewed games as well as largely negatively reviewed games, and some older titles alongside newer titles, though you'll find most of the dataset is comprised of games released in 2017 and later."*.
They also added: *"I attempted to collect all the reviews at the time (Jan. 2021) for every title, and as such, no reviews were left out intentionally. I did observe there were some reviews missing but I do not have an exact number. If I remember correctly it was usually something like 1% of a game's reviews that was missing."*

#### Game tags
To complete our analysis, we gathered the official tags from steam (also called genres) and the most popular user-defined tags. This procedure was made manually and some tags were either broken down into subparts or ignored to avoid synonyms while staying general.
For example, FPS was broken down into 'First person' and 'Shooter', and 'Tactics' was ignored for the more frequent 'Strategy' was already taken. The decision to avoid/brake or not the different tags was highly subjective but mostly done by one person so whole distinction should at least be coherent.

## Game embeddings
To transform the huge quantity of reviews into a more usable material, we created game embeddings in a 100-dimensional space. This allowed us to later manipulate our 200 games with other machine learning techniques.
We hoped the results of those embeddings, carrying information from the way users talk about their games, would allow to reconstruct a classification similar to the way games are tagged.
<figure>
    <img src="img/Embeddings_method.jpg">
    <figcaption>First, reviews are treated as sentences and used to create sentence embeddings. Each game is then "embedded" as the mean vector formed by its most relevant reviews.</figcaption>
</figure>
The final game embeddings and similarly made tag embeddings can be visualized with tensorflow <a href="http://projector.tensorflow.org/?config=https://gist.githubusercontent.com/dmizr/6ed0d83d738a86a3d57e7a8455efe83f/raw/6b7aed45e8d7d5eec7d4f5fb0f71d9c74f0423e8/projector_config_all.json">here</a>.
With this visualization you can select a game on the point cloud or by typing its name and the program will return a list of the closest games. Keep in mind that the "proximity" is calculated on 100 dimensions, this is why although close in reality, games may not appear next to each other in the 3D projection. 
The closer games are to each other, the more similar are the ways their respective base of player talk about them. 
Although their is a loss of information when reducing a game to the average of its review vectors, we hope to still be able to classify the games by this kind of proximity.

## Classification with K-means clustering
We used K-means to make a simple classification from our game embeddings. After a bit of trial and error with different seeds and cluster number, we settled on a 20 cluster classification that produced fairly satisfying results. We used the silhouette score to determine the good number of clusters, but we also chose a high number for more variety.
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/clusters.html"></iframe>
If you know your games well, you see that the classification worked pretty well, but there are undoubtedly some oddities. 

## Machine learning tools used: presentation

#### Word embedding

#### K-means

#### PCA

#### quels sont les input et comment ont-ils été sélectionnés/ajouté (tag manuellement ajouté par exemple)

## Résultats des petites questions statistiques

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

The more there are words, the more critical the reviews become. We also found that positive reviews had an average of 35 words, with the median lenght being 10 words. For negative reviews we have an average of 76 words with a median length of 28 words.

#### Repartition of tags along each PCA axes
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/tag_repartition.html"></iframe>

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="500" src="/html/dim_games.html"></iframe>

## References

[^1]: [Kaggle, *Steam Reviews Dataset 2021*, 2021](https://www.kaggle.com/najzeko/steam-reviews-2021)