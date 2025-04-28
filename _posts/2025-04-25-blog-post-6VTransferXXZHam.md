---
title: 'The Six-Vertex Model & XXZ Quantum Spin Chain part 2'
date: 2025-04-20
permalink: /posts/2025/01/blog-post-XXZ6Vpt2/
tags:
  - XXZ
  - Bethe Ansatz
  - Six Vertex
  - Integrable Probability
---

Here we introduce the *transfer matrix* of the six-vertex model and show a mathematical relationship it has with the *hamiltonian* of the XXZ quantum spin chain (aka Heisenberg-Ising hamiltonian).
This is a follow up to my previous blog post which you can find [here](https://elsaessern.github.io/posts/2025/01/blog-post-XXZ6V/). The work that follows is essentially that of section 10.14 in R.J. Baxter's book "Exactly Solved Models in Statistical Mechanics" adapted to the more specific case of the six-vertex model and XXZ spin chain (compared to the more general XYZ spin chain and eight-vertex model). 

The Transfer Matrix
-----

We first recall the arrow representation of the six possible vertex configurations. Moving forward these are the local configurations we will be referring to.

<img src='/images/6VArrows.png' style="width:500px;height:200px;">

For a finite subset of our square lattice (let's say M rows x N columns), we impose the 'ice-rule' which means each vertex must have exactly two of its adjacent edges pointing up or to the right and the other two pointing down or to the left (equivalently, two of the adjacent arrows must point towards the vertex and two must point away from the vertex)[^1]. 
This is what restricts us to the six local configurations. We will also impose toroidal boundary conditions which means the bottom & top edges and left & right edges are identified with each other respectively. Below is an example of a 4x5 configuration satisfying the ice-rule. 

<img src='/images/6VArrows.png' style="width:500px;height:400px;">

Now consider a horizontal row of the lattice and the adjacent horizontal and vertical edges. For each edge $$i$$, associate a 'spin' (different from the quantum spin we consider in the XXZ spin chain) 
such that $$\mu_i=+1$$ if the arrow is pointing up $$(\uparrow)$$ or to the right $$(\rightarrow)$$ and $$\mu_i=-1$$ if the arrow is pointing down $$(\downarrow)$$ or to the left $$(\downarrow)$$. 
Let $$\alpha_1,\ldots,\alpha_N$$ be the spins on the lower row of vertical edges, $$\beta_1,\ldots,\beta_N$$ be the spins on the upper row of vertical edges, and $$\mu_1,\ldots,\mu_N$$ be the spins on the horizontal edges. Note that the boundary conditions imply that $$\alpha_{N+1}=\alpha_1$$ and similarly for $$\beta$$ and $$\mu$$.









[^1]: A generalized version of this rule admits only an even number of adjacent arrows pointing in or out of a vertex. This allows for two additional local vertices, which is why the generalized model is called the eight-vertex model. 
