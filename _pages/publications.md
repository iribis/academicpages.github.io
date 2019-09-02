---
layout: archive
title: "Projet Raytracing"
permalink: /raytracing/
author_profile: true
---


During my second year at ESIR school, I started working with my teammate on a raytracing renderer for one of our courses. It started with a simple ray casting with direct illumination and some acceleration structures. At this moment our main goal was to accelerate our renderer as fast as possible for an internal benchmark competition. We finished with a *15 000-time faster rendering from the starting project.

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/DiffuseSIA8571.jpg" /></div>
/* image de rendu direct*/

During my free time I continue the project and implement a simple and biased Monte Carlo path tracing integrator for global illumination. After that, we started working on global illumination in class that gave me a part a the knowledge that missed me and I unbiased a big part of my renderer. We also added area lights and direct lightning sampling.

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/DiffuseSIA8571.jpg" /></div>
/* Image d’Illumination gloable avec surface light*/

I also worked on a simple may to create micro-facets materials effects without slowing down the rendering time. I added to the renderer some physically based materials using Fresnel and Cok equations. (les critères d’arret)

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/PokeBoule603.jpg" /></div>
/* Les pokeBalls*/

Finally, I implemented another path tracing renderer with CUDA to speed up my rendering time and learn some basics about GPU programming. When I finally got a equivalent code on the GPU renderer compared to the CPU on, I started working on multi importance sampling and stratification.

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/DiffuseSIA8571.jpg" /></div>
/* avec multi/sans */

My next objective is to build a light tracing renderer and then a bi-directional path tracing.

//
En 2018 j'ai commencé à travailler sur un projet de moteur de Raytracing avec mon binome. C'est un projet qui a débuté avec les cours de lancé de rayon que j'ai eu lors de ma formation et sur lequel j'ai beaucoup travaillé. J'ai passé une grande partie de mon temps libre a travaillé sur ce sujet tout au long de l'année afin d'améliorer le rendu.

L'objectif du projet était de réaliser un moteur de lancé de rayon en C++, d'implémenter des structures d'accélération et estimateur de Monte-carlo pour l'illumination globale. Une grande partie de mon travail à été de réaliser d'un moteur le moins biaisé possible en m'appuyant sur les équations de rendu. 

Le moteur possède de nombreuses fonctionalités comme :
* La gestion des BRDF des matériaux
* Un critère d'arrêt intéligent basé sur la convergence de l'énergie de l'image
* Différentes PDF pour le sampling des rayons aléatoires
* Des structures d'accélération basées sur les Boonding Boxes

Pour la gestion des BRDF, nous avons fait le choix d'intégrer une librairie de BRDF. Avec cette amélioration, nous avons travaillé sur différentes types de BRDF. L'image suivante est un exemple de rendu avec différentes BRDF que nous avons intégré :

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/PokeBoule603.jpg" /></div>

Pour le critère d'arrêt, j'ai fais le choix de travailler avec une énergie donnée par l'écart entre la valeur d'un pixel et ses 4 voisins. De cette façon, le moteur s'arrête lorsque le bruit de l'image ne diminue plus. Avec cette méthode, j'ai obtenu des courbes de dessente d'énergie comme la suivante :

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/Boat151Energie.PNG" /></div>

En générale, on peut remarquer que la majorité de la perte d'énergie se fait dans les premières passes. On peut donc envisager que la majorité de l'information est obtenu avec ces premières passes.
