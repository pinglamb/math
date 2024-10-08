---
layout: base
title: Linear Maps &#124; Vectors and Matrices
---

# Linear Maps

The crucial property of vectors spaces is that the linear combination of vectors are again a vector.
The defining property of linear maps is that it preserves the linear combination in a natural way, i.e.
image of a linear combination is a linear combination of the images, or $\mathcal{T}(\lambda x + \mu y) = \lambda \mathcal{T}(x) + \mu \mathcal{T}(y)$.

## Definition

Let $V, W$ be vector spaces. The map $\mathcal{T}: V \to W$ is a _linear map_ or _linear transformation_ if for all $x, y \in V$ and $\lambda, \mu \in \mathbb{F}$,

$$
\begin{align*}
\mathcal{T}(a + b) &= \mathcal{T}(a) + \mathcal{T}(b) \\
\mathcal{T}(\lambda a) &= \lambda \mathcal{T}(a)
\end{align*}
$$

or equivalently

$$
\mathcal{T}(\lambda a + \mu b) = \lambda \mathcal{T}(a) + \mu \mathcal{T}(b)
$$

$\mathcal{T}(V)$ is a subspace of $W$ as for all $\mathcal{T}(a), \mathcal{T}(b) \in \mathcal{T}(V)$,

$$
\lambda \mathcal{T}(a) + \mu \mathcal{T}(b) = \mathcal{T}(\lambda a + \mu b) \in \mathcal{T}(V)
$$

It follows that $0_W \in \mathcal{T}(V)$. Furthermore, as

$$
\mathcal{T}(a) = \mathcal{T}(a + 0_V) = \mathcal{T}(a) + \mathcal{T}(0_V)
$$

Hence, $\mathcal{T}(0_V) = 0_W$.
