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

## Composition of Maps

Let $\mathcal{S}: U \to V$ and $\mathcal{T}: V \to W$ be linear maps,

$$
u \mapsto v = \mathcal{S}(u) \qquad v \mapsto w = \mathcal{T}(v)
$$

The _composite_ or _product_ map $\mathcal{TS}$ is the map $\mathcal{TS}: U \to W$ such that

$$
u \mapsto w = \mathcal{T}(\mathcal{S}(u))
$$

For the map to be well defined, the domain of $\mathcal{T}$ must include the image of $\mathcal{S}$.

## Bases of Maps

Let $\Set{e_j \mid j = 1, ..., n}, \Set{f_i \mid i = 1, ..., m}$ be the bases of vector spaces $V$ and $W$ respectively.

Consider a linear map $\mathcal{A}: V \to W$, i.e. $x \mapsto x' = \mathcal{A}(x)$, we have

$$
x' = \mathcal{A}\left( \sum_{j=1}^n x_j e_j \right) = \sum_{j=1}^n x_j \mathcal{A}(e_j) = \sum_{j=1}^n x_j e_j'
$$

As $e_j' \in W$,

$$
e_j' = \sum_{i=1}^m A_{ij} f_i
$$

Hence, combining the above,

$$
x' = \sum_{j=1}^n x_j \left( \sum_{i=1}^m A_{ij} f_i \right) = \sum_{i=1}^m \left( \sum_{j=1}^n A_{ij} x_j \right) f_i
$$

So, the $i$-th component of the image $x'$ under $\mathcal{A}$ is

$$
(x')_i = \sum_{j=1}^n A_{ij} x_j
$$

Alternatively, in expanded form, we have

$$
\begin{gather}
x_1' = A_{11}x_1 + A_{12}x_2 + \dots + A_{1n}x_n \\
x_2' = A_{21}x_1 + A_{22}x_2 + \dots + A_{2n}x_n \\
\vdots \\
x_m' = A_{m1}x_1 + A_{m2}x_2 + \dots + A_{mn}x_n
\end{gather}
$$

## Matrix Representation

Let $\mathsf{x}$ and $\mathsf{x}'$ be column matrices,

$$
\mathsf{x} = (x_1, x_2, ..., x_n) \qquad \mathsf{x}' = (x_1', x_2', ..., x_n')
$$

The linear map $\mathcal{A}: V \to W$ can be represented by the matrix

$$
\mathsf{A} = \begin{pmatrix}
A_{11} & A_{12} & \dots & A_{1n} \\
A_{21} & A_{22} & \dots & A_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
A_{m1} & A_{m2} & \dots & A_{mn} \\
\end{pmatrix}
$$

and we have

$$
\mathsf{x}' = \mathsf{A}\mathsf{x}
$$

We can also write

$$
\mathsf{A} = \begin{pmatrix} e_1' & e_2' & ... & e_n'\end{pmatrix}
$$

where $e_j' = \mathcal{A}(e_j)$ is the column matrix of $e_j$ with respect to $\Set{f_i}$ after the transformation.

Recall that for a vector, the component form represents an actual coordinates only after we have specifed the basis.
If we change the components, we get a different vector.
If we change the basis, we get a different representation of the same vector.

The matrix $\mathsf{A}$ above is of the same nature, i.e. the component of the linear map $\mathcal{A}: V \to W$.
It represents an actual "coordinates" of the map only if we have specified the bases, i.e. the bases of $V$ and $W$.
If we change the components, we get a different map.
If we change the bases, we get a different representation of the same map.

In other words, a linear map can have many matrix representations, but once the bases are chosen, we can find a unique matrix $\mathsf{A}$ as the components.

## Examples

The following are some example maps $\mathbb{R}^3 \to \mathbb{R}^3$ with respect to typical orthonormal basis $\Set{\mathbf{e_j} \mid j = 1, 2, 3}$.
To avoid ambiguity, we will use $\Set{\mathbf{f_i}} = \Set{\mathbf{e_j}}$ as the basis of the codomain.

### Rotation

Consider a rotation by an angle $\theta$ about the $x_3$ axis.

$$
\begin{align*}
\mathbf{e_1} \mapsto \mathbf{e_1}' &= \mathbf{f_1} \cos\theta + \mathbf{f_2} \sin\theta \\
\mathbf{e_2} \mapsto \mathbf{e_2}' &= -\mathbf{f_1} \sin\theta + \mathbf{f_2} \cos\theta \\
\mathbf{e_3} \mapsto \mathbf{e_3}' &= \mathbf{f_3}
\end{align*}
$$

Hence, the rotation matrix

$$
\mathsf{R}(\theta) = \begin{pmatrix}
\cos\theta & -\sin\theta & 0 \\
\sin\theta & \cos\theta & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$

### Reflection

Consider reflection $\mathcal{H}_\Pi$ in the plane $\Pi = \Set{\mathbf{x} \in \mathbb{R}^3 \mid \mathbf{x} \cdot \mathbf{n} = 0, \|\mathbf{n}\| = 1}$

For a point $P$, let $N$ be the foot of the perpendicular from $P$ to the plane, then $\vec{NP} = (\mathbf{x} \cdot \mathbf{n}) \mathbf{n}$.

Hence,

$$
\mathbf{x}' = \mathcal{H}_\Pi(\mathbf{x}) = \mathbf{x} - 2 (\mathbf{x} \cdot \mathbf{n}) \mathbf{n}
$$

Using suffix notation, we have

$$
\begin{align*}
x_i' &= x_i - 2 x_j n_j n_i \\
&= \delta_{ij}x_j - 2 n_i n_j x_j \\
&= (\delta_{ij} - 2 n_i n_j)x_j \\
&= H_{ij}x_j
\end{align*}
$$

Hence,

$$
(\mathsf{H})_{ij} = \delta_{ij} - 2 n_i n_j \qquad \mathsf{H} = \begin{pmatrix}
1 - 2n_1^2 & -2n_1n_2 & -2n_1n_3 \\
-2n_2n_1 & 1-2n_2^2 & -2n_2n_3 \\
-2n_3n_1 & -2n_3n_2 & 1-2n_3^2 \\
\end{pmatrix}
$$

### Dilatation

Dilatation is the effect of stretching or contracting a unit cube to a cuboid by different factors along different axes.

Consider the dilatation $\mathcal{D}$ such that

$$
\begin{align*}
\mathbf{e_1} \mapsto \mathbf{e_1}' &= \lambda\mathbf{f_1} \\
\mathbf{e_2} \mapsto \mathbf{e_2}' &= \mu\mathbf{f_2} \\
\mathbf{e_3} \mapsto \mathbf{e_3}' &= \nu\mathbf{f_3} \\
\end{align*}
$$

Hence,

$$
\mathsf{D} = \begin{pmatrix}
\lambda & 0 & 0 \\
0 & \mu & 0 \\
0 & 0 & \nu
\end{pmatrix}
$$

If $\lambda = \mu = \nu$, the transformation is called a _pure dilatation_.

### Shear

A simple shear is a transformation in the plane that displaces points in one direction, e.g. $x_1$ direction, by an amount proportional to the distance in that plane from, say, the $x_1$-axis.
For example, $\mathcal{S}_\lambda$ is the transformation such that

$$
\begin{align*}
\mathbf{e_1} \mapsto \mathbf{e_1}' &= \mathbf{f_1} \\
\mathbf{e_2} \mapsto \mathbf{e_2}' &= \mathbf{f_2} + \lambda\mathbf{f_1} \\
\mathbf{e_3} \mapsto \mathbf{e_3}' &= \mathbf{f_3} \\
\end{align*}
$$

which displaces points in $x_1$ direction by $\lambda$ times distance from $x_1$-axis.

Hence, for the above shear transformation,

$$
\mathsf{S}_\lambda = \begin{pmatrix}
1 & \lambda & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 3](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
