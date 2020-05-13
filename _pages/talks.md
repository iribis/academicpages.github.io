---
layout: archive
title: "Optial Multiple Importance Sampling in BDPT"
permalink: /OptimalMIS/
author_profile: true
---
<div style="text-align: justify"> 
During my second year at ESIR school, I made with 3 other students a project about saillance models and dynamic blur for video games in unity. The objective was to build a saillance model usable in simple video game made with unity. We choose to work with post-processing methods that seems to be the easiest way to insert blur in the model. We choose to work with two images: one blurred with a simple convolution and the original one.  the two images are then mixed based on a saillance map to creat the output frame.
</div>

<div style="text-align: justify"> 
With this method, we propose 2 simple saillance models, one based on camera depth and distance to the center of the camera and a second one based a colorimetric saillance. 
The first example is distance to the center of the screen based blur.
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/VilleSaillanceCentrale.PNG?raw=true" height="70%" width="70%"/></div>
</div>

<div style="text-align: justify"> 
The second method is the color based saillance. We use the histogramme distribution to found color self-information and build a saillance map on it. The more a color is present in the image, the more it will be blur. This model is based on the fact that uncommon colors are more likely saillante that common color in an image.
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/Dessin%20sans%20titre%20(7).jpg?raw=true" height="70%" width="70%"/></div>
</div>

<div style="text-align: justify"> 
This is the saillance map from the last image :
<div style="text-align:center"><img src="https://github.com/iribis/iribis.github.io/blob/master/images/Dessin%20sans%20titre%20(8).jpg?raw=true" height="70%" width="70%"/></div>
</div>
