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

## Rank, Kernel and Nullity

### Definition

Let $\mathcal{T}: V \to W$, as discussed above, $\mathcal{T}(V)$ is the image of $V$ under $T$ and is a subspace of $W$.

The _rank_ of $\mathcal{T}$ is the dimension of the image, i.e.

$$
r(\mathcal{T}) = \dim \mathcal{T}(V)
$$

<hr />

The _kernel_ or _null space_ of $\mathcal{T}$ is the subset of $V$ that maps to the zero element in $W$.

$$
\ker \mathcal{T} = \Set{x \in V \mid \mathcal{T}(x) = 0_W}
$$

As stated above, $\mathcal{T}(0_V) = 0_W$ so $0_V \in \ker \mathcal{T}$.

Suppose $a, b \in \ker \mathcal{T}$, as

$$
\mathcal{T}(\lambda a + \mu b) = \lambda \mathcal{T}(a) + \mu \mathcal{T}(b) = 0_W
$$

$\lambda a + \mu b \in \ker \mathcal{T}$.

Hence $\ker \mathcal{T}$ is a subspace of $V$.

<hr />

The _nullity_ of $\mathcal{T}$ is the dimension of the kernel, i.e.

$$
n(\mathcal{T}) = \dim \ker \mathcal{T}
$$

### Rank-Nullity Theorem

Let $\mathcal{T}: V \to W$ be a linear map, then

$$
r(\mathcal{T}) + n(\mathcal{T}) = \dim V
$$
