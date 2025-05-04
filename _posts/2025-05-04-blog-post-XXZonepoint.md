---
title: 'Towards an exact expression for the XXZ's one-point function'
date: 2025-05-04
permalink: /posts/2025/01/blog-post-XXZ/
tags:
  - XXZ
  - Bethe Ansatz
  - Integrable Probability
  - KPZ
---

Some observables from the XXZ spin-1/2 chain have shown KPZ behavior, but it is not entirely clear if the model lies within the KPZ universality class. Of particular interest for us is the one-point function, for which we aim to get an exact expression that is amenable to asymptotic analysis. This content is based on joint work with Axel Saenz Rodriguez. 

XXZ on the ring
-------

In previous posts ([1](https://elsaessern.github.io/posts/2025/01/blog-post-XXZ6V/),[2](https://elsaessern.github.io/posts/2025/01/blog-post-XXZ6Vpt2/)) I introduced the XXZ spin-1/2 chain (aka the Heisenberg-Ising spin chain). The Hamiltonian for this model reads as follows 

$$\begin{equation}
\mathcal{H} = \sum_{i=1}^N S_i^x S_{i+1}^x + S_i^y S_{i+1}^y + \Delta(S_i^z S_{i+1}^z - 1/2) 
\end{equation}$$

where the $$S_i^\alpha$$ are the quantum spin operators 

$$\begin{equation}
S_i^\alpha = Id \otimes Id \otimes \cdots \otimes \sigma^\alpha \otimes Id \cdots \otimes Id
\end{equation}$$

and $$\sigma^\alpha$$ are the 2x2 Pauli matrices. We are working with the XXZ chain on the ring (periodic 1D lattice) of length $$L$$, so we identify the $$L+1$$'th site with the first site, $$S_{L+1}^\alpha = S_1^\alpha$$. The dynamics of the model are governed by the Schrodinger equation

$$\begin{equation}
\frac{d}{dt} |\Psi(t)\rangle = \mathcal{H} |\Psi(t)\rangle 
\end{equation}$$

where $$|\Psi(t)\rangle $$ is an element of the Hilbert space $$\mathbb{H}$$ containing the spin configurations with a fixed number of down-spins & up-spins. That is, $$\mathbb{H}\subset \mathbb{V}_L = \mathbb{V}^{\otimes L}$$ with \mathbb{V}=\mathrm{Span}\{|\uparrow\rangle, |\downarrow\rangle\}$$. Our aim is have a complete spectral decomposition of the Hamiltonian $$\mathcal{H}$$. That is, we want eigenfunctions $$|\Psi(t)\rangle$$ such that 
  
$$\begin{equation}
\frac{d}{dt} |\Psi(t)\rangle = \mathcal{H} |\Psi(t)\rangle  = E |\Psi(t)\rangle
\end{equation}$$

with $$E$$ the respective eigenvalues. 
