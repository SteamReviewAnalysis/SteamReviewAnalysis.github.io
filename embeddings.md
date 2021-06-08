---
title: Embedding projector
layout: page
---

### Little explanation for the Embedding projector<br>

This page is all about the <a href="http://projector.tensorflow.org/?config=https://gist.githubusercontent.com/dmizr/6ed0d83d738a86a3d57e7a8455efe83f/raw/6b7aed45e8d7d5eec7d4f5fb0f71d9c74f0423e8/projector_config_all.json">Embedding projector</a>.


Every point you see correspont to a game projected on a 3D space. 
If you click on any of the floating points you will get some information on the closest neighbors.
Keep in mind that the "closest neighbors" are calculated in the 100 dimensions space, so it will not forcefully correspond to the nearest points in your visualisation.
You can move around the projection by clicking and dragging across the central space.

<figure>
    <img src="../img/tensorflow_1.png">
    <figcaption></figcaption>
</figure>

- 1 : By clicking on this box you can select between 3 datasets :<br>
The Game embeddings, that will show the cloud of games.<br>
The Tag embeddings, that will show the cloud of some of the most popular user defined tags.<br>
The Genre embeddings, that will show the cloud of the official Steam tags.<br>

- 2 : With the option number 2 you can color the games depending on if they possess the indicated tag in the drop down. The red dots are the games possessing the tag.

- 3 : In the option 3 you can select which axes from PCA you want to show, or even switch to 2D. You can also use other projection methods like UMAP or T-SNE, don't be shy!

- 4 : At number 4 you can enter a game's name to locate it automatically.

<figure>
    <img src="../img/tensorflow_2.png">
    <figcaption></figcaption>
</figure>

- 5 : When a game is selected, the closest points are displayed in the section 5. Different distance metrics are available, try them both to see which one you understand the best.

- 6 : If you click on this rectangle when a point is selected, there will be a dropdown showing which tags (from Steam or the users) are attributed to this game.