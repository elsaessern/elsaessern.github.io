---
title: 'Principal component analysis for differentiating gasotransmitters'
date: 2025-04-01
permalink: /posts/2025/04/blog-post-PCA/
tags:
  - PCA
  - Machine learning
  - Applied math
---

The following post is based on work done in *Georganna Benedetto, Robert M. Stolz, Zheng Meng, Elissa Shehayeb, Colin T. Morrell, Yu Man Chan, Gbenga Fabusola, Nikolaus Elsaesser, Cory M. Simon, and Katherine A. Mirica "Conductive covalent organic frameworks as chemiresistive sensor arrays for the detction and differentiation of gasotransmitters"*.

Motivation & Background
======
Chemical sensing plays a crucial role for living beings, an important capability to perceive the world and for bodily function. For example, employing the smell test with my favorite chemical sensor, the nose. Perhaps you've smelled a bit of food to check if it's still safe to eat (or extra flavorful, for the kimchi and sauerkraut lovers out there). Or maybe you left something to cook for a little too long and a smoke detector started beeping. Most people have experienced some form of chemical sensing. However, a particularly important kind of chemical sensing happens at a scale too small for our noses and household devices. Gasotransmitters, small signaling gas molecules, act as messengers in the human body and play essential roles in the function of physiological functions like the nervous, cardiovascular, and immune systems. In [1] an approach to qualitatively differentiate the gasotransmitters CO, H$_2$S, NO, and NH$_3$ via covalent organic framework (COF) arrays was investigated. As a non-expert in chemistry, I will refer those interested in COFs and gasotransmitters to the literature. The basic idea of the approach, however, is that different materials (Fe, Co, Cu, Ni-based COFs) can sense different gasotransmitters (CO, NO, H$_2$S, NH$_3$) well but have trouble differentiating between certain gases on their own. Hence, one would reasonably ask if a collection of these materials can effectively sense and differentiate gasotransmitters.  

[1]: *Georganna Benedetto, Robert M. Stolz, Zheng Meng, Elissa Shehayeb, Colin T. Morrell, Yu Man Chan, Gbenga Fabusola, Nikolaus Elsaesser, Cory M. Simon, and Katherine A. Mirica "Conductive covalent organic frameworks as chemiresistive sensor arrays for the detction and differentiation of gasotransmitters"*
