---
layout: archive
title: "Projet Raytracing"
permalink: /raytracing/
author_profile: true
---

<img align="center" src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/DiffuseSIA8571.jpg" alt="Image_1">

![Image_Raytracing](https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/DiffuseSIA8571.jpg)


En 2018 j'ai commencé à travailler sur un projet de moteur de Raytracing avec mon binome. C'est un projet qui a débuté avec les cours de lancé de rayon que j'ai eu lors de ma formation et sur lequel j'ai beaucoup travaillé. J'ai passé une grande partie de mon temps libre a travaillé sur ce sujet tout au long de l'année afin d'améliorer le rendu.

L'objectif du projet était de réaliser un moteur de lancé de rayon en C++, d'implémenter des structures d'accélération et estimateur de Monte-carlo pour l'illumination globale. Une grande partie de mon travail à été de réaliser d'un moteur le moins biaisé possible en m'appuyant sur les équations de rendu. 

Le moteur possède de nombreuses fonctionalités comme :
* La gestion des BRDF des matériaux
* Un critère d'arrêt intéligent basé sur la convergence de l'énergie de l'image
* Différentes PDF pour le sampling des rayons aléatoires
* Des structures d'accélération basées sur les Boonding Boxes

Pour la gestion des BRDF, nous avons fait le choix d'intégrer une librairie de BRDF. Avec cette amélioration, nous avons travaillé sur différentes types de BRDF. L'image suivante est un exemple de rendu avec différentes BRDF que nous avons intégré :

![Image_Raytracing](https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/PokeBoule603.jpg)


Pour le critère d'arrêt, j'ai fais le choix de travailler avec une énergie donnée par l'écart entre la valeur d'un pixel et ses 4 voisins. De cette façon, le moteur s'arrête lorsque le bruit de l'image ne diminue plus. Avec cette méthode, j'ai obtenu des courbes de dessente d'énergie comme la suivante :

![Image_Raytracing](https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/Boat151Energie.PNG)

En générale, on peut remarquer que la majorité de la perte d'énergie se fait dans les premières passes. On peut donc envisager que la majorité de l'information est obtenu avec ces premières passes.
