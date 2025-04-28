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

<img src='/images/6Vex.png' style="width:500px;height:400px;">

Now consider a horizontal row of the lattice and the adjacent horizontal and vertical edges. For each edge $$i$$, associate a 'spin' (different from the quantum spin we consider in the XXZ spin chain) 
such that $$\mu_i=+1$$ if the arrow is pointing up $$(\uparrow)$$ or to the right $$(\rightarrow)$$ and $$\mu_i=-1$$ if the arrow is pointing down $$(\downarrow)$$ or to the left $$(\downarrow)$$. 
Let $$\mathbf{\alpha}=\{\alpha_1,\ldots,\alpha_N\}$$ be the spins on the lower row of vertical edges, $$\mathbf{\beta}=\{\beta_1,\ldots,\beta_N\}$$ be the spins on the upper row of vertical edges, and $$\mathbf{\mu}=\{\mu_1,\ldots,\mu_N\}$$ be the spins on the horizontal edges. Note that the boundary conditions imply that $$\alpha_{N+1}=\alpha_1$$ and similarly for $$\beta$$ and $$\mu$$. In terms of spins, we define the weights of local configurations in the following notation $$w(\mu, \alpha \mid \beta, \mu')$$ where $$\mu$$ is the horizontal arrow to the left of the vertex, $$\alpha$$ is the vertical arrow below the vertex, $$\beta$$ is the vertical arrow above the vertex, and $$\mu'$$ is the horizontal arrow to the right of the vertex. Denoting $$+1$$ spin value by $$+$$ and $$-1$$ spin value by $$-$$, we have the local weights

$$\begin{equation} 
\begin{split}
w(+,+ \mid +,+) &= a_1 \quad w(-,- \mid -,-)=a_2 \\
w(+,- \mid -,+) &= b_1 \quad w(-,+ \mid +,-)=b_2 \\
w(+,- \mid +,-) &= c_1 \quad w(-,+ \mid -,+)=c_2 \\
\end{split}
\end{equation}$$

where $$w=0$$ otherwise. We define the *transfer matrix* $$V$$ by is entries indexed by different spin configurations of vertical edge rows $$\mathbf{\alpha}$$ and $$\mathbf{\beta}$$ as follows 

$$\begin{equation}
V_{\mathbf{\alpha}\mathbf{\beta}}=\sum_{\mu_1}\cdots\sum_{\mu_N} w(\mu_1,\alpha_1\mid \beta_1,\mu_2)w(\mu_2,\alpha_2 \mid \beta_2,\mu_3)\cdots w(\mu_N,\alpha_N \mid \beta_N, \mu_1).
\end{equation}$$

Where the transfer matrix meets the hamiltonian
------
In this section we will derive a direct relationship between the transfer matrix $$V$$ and the XXZ hamiltonian $$\mathcal{H}$$. 
Fix $$a=a_1=a_2$$, $$b=b_1=b_2$$, and $$c=c_1=c_2$$. We can then rewrite the weight function $$w$$ as 

$$\begin{equation} 
w(\mu,\alpha \mid \beta,\nu) = \frac14[a'(1+ \alpha\beta\mu\nu) + b'(\alpha\beta+\mu\nu)+c'(\alpha\nu+\beta\mu)] 
\end{equation}$$

with $$a'=\frac12(a+b+c)$$, $$b'=\frac12(a+b-c)$$, and $$c'=\frac12(a-b+c)$$. Equivalently, 

$$\begin{equation}
w(\mu,\alpha \mid \beta,\nu) = \frac12\left( [(a+c)+(a-c)\mu\alpha]\delta(\mu,\beta)\delta(\alpha,\nu) + [(b+d)-(b-d)\mu\alpha]\delta(\mu,-\beta)\delta(\alpha,-\nu) \right)
\end{equation}$$

where $$\delta(\alpha,\beta)=1$$ if $$\alpha=\beta$$ and zero otherwise ($$\delta$$ here is the Kronicker delta). We will now compute a logarithmic derivative of $$V$$ by varying the weights. First consider the case when $$b=0$$ and $$a=c=c_0 > 0$$. Then,

$$\begin{equation}
w(\mu,\alpha \mid \beta, \nu) = c_0 \delta(\mu,\beta)\delta(\alpha,\nu)
\end{equation}$$

In this case we denote the transfer matrix as $$V_0$$ and 

$$\begin{equation}
\begin{split}
(V_0)_{\mathbf{\alpha}\mathbf{\beta}}&=\sum_{\mu_1}\cdots\sum_{\mu_N} w(\mu_1,\alpha_1\mid \beta_1,\mu_2)w(\mu_2,\alpha_2 \mid \beta_2,\mu_3)\cdots w(\mu_N,\alpha_N \mid \beta_N, \mu_1) \\
&= \sum_{\mu_1}\cdots\sum_{\mu_N} c_0^N \delta(\mu_1,\beta_1)\delta(\alpha_1,\mu_2)\delta(\mu_2,\beta_2)\delta(\alpha_2,\mu_3)\cdots\delta(\mu_N,\beta_N)\delta(\alpha_N,\mu_1) \\
&= c_0^N \delta(\alpha_1,\beta_2)\delta(\alpha_2,\beta_3)\cdots \delta(\alpha_{N-1},\beta_N)\delta(\alpha_N,\beta_1)
\end{split}
\end{equation}$$

which means that $$c_0^{-N} V_0$$ is the left-shift operator sending the spin configuration $$\{\alpha_1,\ldots\alpha_N\}$$ to $$\{\alpha_N,\alpha_1,\ldots,\alpha_{N-1}\}$$. We can perturb this case setting $$a = c_0 + \delta a$$, $$b=\delta b$$, and $$c = c_0 + \delta c$$ with $$\delta a$$, $$\delta b$$, $$\delta c$$ infinitesemal increments in $$a, b, c$$. Denote $$\delta w$$ and $$\delta V$$ as the increments induced in $$w$$ and $$V$$. Then 

$$\begin{equation}
\delta V_{\mathbf{\alpha}\mathbf{\beta}} = c_0^{N-1}\sum_{j=1}^N \cdots \delta(\alpha_{j-2},\beta_{j-1}) \delta w(\alpha_{j-1},\alpha_j\mid \beta_j,\beta_{j+1}) \delta(\alpha_{j+1},\beta_{j+2})
\end{equation}$$

and then composing $$\delta V$$ with $$V_0^{-1}$$ we have 
$$\begin{equation}
(V_0^{-1} \delta V)_{\mathbf{\alpha}\mathbf{\beta}}=c_0^{-1} \sum_{j=1}^N \cdots \delta(\alpha_{j-1},\beta_{j-1})\delta w(\alpha_j,\alpha_{j+1} \mid \beta_j,\beta_{j+1}) \delta(\alpha_{j+2},\beta_{j+2})\cdots.
\end{equation}$$

We can rewrite this as a sum of operators if we define 

$$\begin{equation} 
(U_i)_{\mathbf{\alpha}\mathbf{\beta}} = \delta(\alpha_1,\beta_1) \cdots \delta(\alpha_{i-1},\beta_{i-1}) w(\alpha_i,\alpha_{i+1}\mid \beta_i,\beta_{i+1})\delta(\alpha_{i+2},\beta_{i+2})\cdots \delta(\alpha_N,\beta_N)
\end{equation}$$

so then 

$$\begin{equation}
V_0^{-1}\delta V = c_0^{-1}(\delta U_1 + \cdots + \delta U_N).
\end{equation}$$

Up to this point one may have reasonably asked several times (if they kept reading that is) where the heck does the XXZ hamiltonian come into play? Fret not, this is where things begin to come together. Recall the hamiltonian $$\mathcal{H}$$

$$\begin{equation}
\mathcal{H} = \sum_{j=1}^N S_j^x S_{j+1}^x + S_{j}^y S_{j+1}^y + \Delta(S_j^z S_{j+1}^z - \frac12)
\end{equation}$$

and spin operators $$S_j^x, S_j^y, S_j^z$$. An alternative to the the tensor product definition of the spin operators, we can write 
$$\begin{equation}
S_j^x = \frac{1}{\sqrt{2}}c_j, \quad S_j^y = \frac{1}{\sqrt{2}}i c_j s_j, \quad S_j^z = \frac{1}{\sqrt{2}}s_j
\end{equation}$$

where

$$\begin{equation}
(s_j)_{\mathbf{\alpha}\mathbf{\beta}} = \alpha_j \delta(\alpha_1,\beta_1)\delta(\alpha_2,\beta_2)\cdots \delta(\alpha_N,\beta_N)
\end{equation}$$

and

$$\begin{equation}
(c_j)_{\mathbf{\alpha}\mathbf{\beta}} = \delta(\alpha_1,\beta_1)\cdots \delta(\alpha_{j-1},\beta_{j-1}) \delta(\alpha_j,-\beta_j)\delta(\alpha_{j+1},\beta_{j+1})\cdots\delta(\alpha_N,\beta_N).
\end{equation}$$

That is, $$s_j$$ is a diagonal matrix with entries $$\alpha_j$$ (the $$j$$'th spin value ($$+1$$ or $$-1$$) in the corresponding spin configuration $$\mathbf{\alpha}$$) and $$c_j$$ is the spin-flip operator that reverses the spin in position $$j$$. Now the relation between $$\mathcal{H}$$ and $$V$$ will appear via the operator $$U_j$$, $$s_j$$ and $$c_j$$. We can express $$U_j$$ in terms of $$s_j$$ and $$c_j$$ if write out the weight function $$w$$ in $$U_j$$ 

$$\begin{equation}
(U_j)_{\mathbf{\alpha}\mathbf{\beta}}=\delta(\alpha_1,\beta_1)\cdots \delta(\alpha_{j-1},\beta_{j-1})\frac12\left([(a+c)+(a-c)\alpha_j\alpha_{j+a}]\delta(\alpha_j,\beta_j)\delta(\alpha_{j+1},\beta_{j+1}) + [b - b\alpha_j\alpha_{j+1}]\delta(\alpha_j,-\beta_j)\delta(\alpha_{j+1},-\beta_{j+1}) \right) \delta(\alpha_{j+2},\beta_{j+2}\cdots \delta(\alpha_N,\beta_N)
\end{equation}$$

and we can see that 

$$\begin{equation}
\begin{split}
U_j &= \frac12\left[(a+c)Id + (a-c)s_j s_{j+1} + b c_j c_{j+1} - b s_j c_j s_{j+1}c_{j+1} \right] \\
 &= \frac{(a+c)}{2}Id + bS_j^x S_{j+1}^x + bS_j^y S_{j+1}^y + (a-c)S_j^z S_{j+1}^z.
\end{split}
\end{equation}$$

So then 

$$\begin{equation}
\delta U_j = \frac{(\delta a+ \delta c)}{2}Id + \delta b S_j^x S_{j+1}^x + \delta b S_j^y S_{j+1}^y + (\delta a- \delta c)S_j^z S_{j+1}^z
\end{equation}$$

and thus 

$$\begin{equation}\begin{split}
V_0^{-1}\delta V &= c_0^{-1}\sum_{j=1}^N \frac{(\delta a+ \delta c)}{2}Id + \delta b S_j^x S_{j+1}^x + \delta b S_j^y S_{j+1}^y + (\delta a- \delta c)S_j^z S_{j+1}^z \\
&= \delta b \sum_{j=1}^N S_j^x S_{j+1}^x + S_{j}^y S_{j+1}^y + \Delta(S_j^z S_{j+1}^z - \frac12)
\end{split}\end{equation}$$

when $$\delta a = 0$$ and $$\Delta = -\frac{\delta c}{2 \delta b}$$. And hence with these parameters 

$$\begin{equation}
\frac{V_0^{-1}\delta V}{\delta b} = \mathcal{H}.
\end{equation}$$



[^1]: A generalized version of this rule admits only an even number of adjacent arrows pointing in or out of a vertex. This allows for two additional local vertices, which is why the generalized model is called the eight-vertex model. 
