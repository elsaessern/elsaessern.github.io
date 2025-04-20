---
title: 'An unexpected relationship: the mathematical ties of a model for a square sheet of ice and one-dimensional magnetism'
date: 2025-01-10
permalink: /posts/2025/01/blog-post-XXZ6V/
tags:
  - XXZ
  - Bethe Ansatz
  - Six Vertex
  - Integrable Probability
---


XXZ Quantum Spin Chain & The Six Vertex Model
==========

What does a model for the possible orientations of hydrogen and oxygen atoms on a sheet of ice have to do with a toy model for magnetism on a chain? Although the original aim for both of these models were describing different things, molecular structure of ice and magnetism, they are intimately related via their mathematical construction. In particular, the operators that govern the dynamics of each model commute, and thus share the same eigenvectors. 

XXZ Spin-1/2 Chain on the Ring
----------

Originally a toy model for magnetism, the XXZ Spin-1/2 chain describes a finite number of quantum spins on a 1D lattice (in this case periodic). The quantum spin at lattice site \\( j \\) in a chain of length \\( L \\) is described by the operators 
\\[ \begin{equation*}
      \begin{split}
      S_j^\alpha = \frac{1}{\sqrt{2}}\left(\mathrm{Id} \otimes\cdots \otimes \mathrm{Id} \otimes \sigma^{\alpha} \otimes \mathrm{Id} \otimes\cdots \otimes \mathrm{Id} \\
      \sigma^x = \begin{pmatrix}
         0 & 1 \\
         1 & 0
    \end{pmatrix},\quad \sigma^y = \begin{pmatrix}
         0 & -i \\
         i & 0
    \end{pmatrix},\quad \sigma^z = \begin{pmatrix}
         1 & 0 \\
         0 & -1
    \end{pmatrix}
      \end{split}
    \end{equation*} \\]
which act on the L-fold tensor product, \\(\mathbb{V}_L = \mathbb{V}^{\otimes L} \\), of a 2D complex vector space with a basis given by spin up and down labels \\(\mathbb{V}=\mathrm{Span}\{ \mid \uparrow \rangle, \mid \downarrow \rangle \} \\). For example, the basis of $\mathbb{V}_2$ is given by 
$$\begin{equation*}
    \mid \uparrow \rangle \otimes \mid \uparrow \rangle = \mid \uparrow \uparrow \rangle,\, \mid \uparrow \rangle \otimes \mid \downarrow \rangle = \mid \uparrow \downarrow \rangle,\, \mid \downarrow \rangle \otimes \mid \uparrow \rangle = \mid \downarrow \uparrow \rangle,\, \mid \downarrow \rangle \otimes \mid \downarrow \rangle = \mid \downarrow \downarrow \rangle.
\end{equation*}$$
The \\( \sigma^{\alpha} \\) in \\(S_j^\alpha \\) is in the \\( j \\)'th position of the tensor product.
