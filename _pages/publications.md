---
layout: archive
title: "Projet Raytracing"
permalink: /raytracing/
author_profile: true
---

<div style="text-align: justify"> 
During my second year at ESIR school, I started working with my teammate on a raytracing renderer for one of our courses. It started with a simple ray casting with direct illumination and some acceleration structures. We implemented a BVH acceleration structure with SAH heuristic.
  
</div>

<div style="text-align: justify"> 
During my free time I continue the project and implement a simple and biased Monte Carlo path tracing integrator for global illumination. After that, we started working on global illumination in class that gave me a part a the knowledge that missed me and I unbiased a big part of my renderer. We also added area lights and direct lightning sampling.
  
</div>

<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/BoatDirect.jpg?raw=true" height="40%" width="40%"/><img src="https://github.com/iribis/iribis.github.io/blob/master/images/boat3500.jpg?raw=true" height="40%" width="40%"/></div>
<div style="text-align: justify"> 
  the left image is a direct rendering from our first renderer and le right image a global illuminated rendering for the same scene.
  
</div>
<div style="text-align: justify"> 
  
To create more realistic materials, we implemented new BRDF for materials based on differents models based on Fresnel and Cok equations or simple equations that have render metalics effects on materials. I also work on a simple implementation of micro-facets effects that we add on some materials. In the image below you can see some of our results. It shows differents types of materials for a same object. The main idea was to work on BRDF models and then work on some basic importance sampling that match with the BSDF.
</div>

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/PokeBoule603.jpg" height="55%" width="55%"/></div>

<div style="text-align: justify"> 
Finally, I worked on an intelligent criterion to stop raytracing recursion. We know that estimator variance decrease proportional to the square root of the number of samples, in that way we determine when the difference of result between a number of samples is still important or if we can consider the result close to converged. We based our criteria on evolution of global image energie that have the following evolution with the number of samples:
</div>
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/Boat151Energie.PNG?raw=true" height="40%" width="40%"/></div>

<div style="text-align: justify"> 
When I finished my CPU implementation of a path tracer, I wanted to work on a GPU implementation. I worked with CUDA C++ to create a similar renderer to my CPU one. It was a really interesting part for me because GPU programming is not part of my education. With the increase of performance, I added commands to moove the camera in the scene. We can see 2 points of view of the same scene:
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel.JPG?raw=false" height="50%" width="50%"/><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel2.JPG?raw=false" height="50%" width="50%"/></div>
</div>


<div style="text-align: justify"> 
Since october, I started working on unbiaised rendering for a research project. I started by a MIS path tracing with balance and power heuristique on direct lightning. The MIS is a very usefull technique to reduce noise and optimise the combination of diffrent sampling techniques. You can see below 2 diffrents light sampling techniques and the final result with MIS between the two strategies.
</div>
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel.JPG?raw=false" height="50%" width="50%"/><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel2.JPG?raw=false" height="50%" width="50%"/><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel2.JPG?raw=false" height="50%" width="50%"/></div>

<div style="text-align: justify"> 
I also worked on an unbised ligth tracing renderer and started working on bi-directional path tracing. You can see the result from ligth tracing and MIS path tracing below for a same scene.
</div>
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel.JPG?raw=false" height="50%" width="50%"/><img src="https://github.com/iribis/iribis.github.io/blob/master/images/GPUcornel2.JPG?raw=false" height="50%" width="50%"/></div>

I'm cuurently working on bi-directional path tracing using pbrt implementation for a school research project.
