---
layout: archive
title: "Distributing Monte Carlo error as Blue noise"
permalink: /BlueNoise/
author_profile: true
---

<div style="text-align: justify"> 
During my end-of-study internship at Unity Labs in Grenoble with Eric Heitz and Laurent Belcour. I worked on the Monte Carlo error distribution at high frequencies. This type of distribution is called blue noise.
This type of distribution has very strong denoising properties and is generally more visually pleasing than purely random distributions. Originally widely used in the printing industry to give grayscale images from black and white dots, it is increasingly used in computer graphics.

Modern graphics rendering is based on Monte-Carlo integration for the management of emissive surfaces or global illumination. These integrals have converging properties but with a limited computing time lead to rendering errors.
Using purely random sequences gives error distributions where all frequencies are equally likely to occur. These distributions are not the most interesting ones and various algorithms have been developed in order to obtain better distributions.
</div>

<div style="text-align: justify"> 
One of the central issues in this field is the creation of blue noise dither. This is a vector image having the property of being distributed according to high frequencies. The following figure shows an example of dither generated from the algorithm of [Georgiev and Fajardo 2016] and its FFT.

</div>

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/dither.png" height="100%" width="100%"/></div>

<div style="text-align: justify"> 
  <br />
These vectors can be directly used as random sequences for monte carlo integration and allow to opt for a blue noise. On the other hand, this method remains limited because it requires large random vectors distributed according to a blue noise, which is still an unsolved problem. The following figure shows an example of a result obtained with this method. We can see that we obtain a visually much better result than with a classical distribution. It should be noted that this method does not add any extra computation cost since the sequences are pre-calculated.

</div>

<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/Georgiev_comp.png" height="100%" width="100%"/></div>

<div style="text-align: justify"> 
  <br />
The method proposed by [Heitz and Belcour 2019] is based on the use of seeds of random sequences rather than on the sequences themselves in order to simplify the problem. Here, the idea is to locally swap the seeds between 2 frames of rendering in order to obtain a blue noise error distribution. This method requires as learned that the integrade to compute is locally similar (which is often true) and that a seed is the only element determining the value of the result (ie the neighboring pixels have no impact). By applying an optimal transport algorithm between the values obtained by the renderer and the values of a 1D blue noise dither, we can locally optimize the position of seeds.
The idea is to try to put the seeds giving low values on the spot of low values of the dither and vice versa for the high values. The following figure shows the result comparison between a classical random rendering and the presented algorithm.
</div>
<div style="text-align:center"><img src="https://raw.githubusercontent.com/iribis/iribis.github.io/master/images/EGSR_comp.png" height="100%" width="100%"/></div>

<div style="text-align: justify"> 
  <br />
We can see that the visual quality is greatly improved compared to traditional random sequences. Moreover, it is a temporal algorithm that is easily usable and with a relatively low computational overhead compared to the visual improvement provided.
</div>


<div style="text-align: justify">
  <br />
Finally, during my internship, I worked on new methods allowing to opt for blue noise error distributions that will complete this page in the future.</div>
