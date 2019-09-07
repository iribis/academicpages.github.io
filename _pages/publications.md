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

