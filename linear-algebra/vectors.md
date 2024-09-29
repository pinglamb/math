---
layout: base
title: Vectors
---

# Vectors

The discussion here focuses on vectors in 2D and 3D spaces, i.e. $\mathbb{R}^2$ and $\mathbb{R}^3$.
It begins from defining vectors and various operations among them geometrically.
It then can be extended to algebraic definitions and generalized to the concept of [vector spaces](linear-algebra/vector-spaces.md).

## Definition

In $\mathbb{R}^2$ and $\mathbb{R}^3$, a vector is a quantity that is specified by a \[positive] _magnitude_ and a _direction_ in space.
A vector $\mathbf{v}$ is represented geometrically as a line segment $\vec{AB}$ with magnitude $\|\mathbf{v}\|$ and with direction from $A$ to $B$.
With a chosen origin $O$, every point $P$ in 2D/3D space has a position vector $\mathbf{x} = \vec{OP}$.

When $\|\mathbf{v}\| = 0$, we have the zero/null vector, denoted by $\mathbf{0}$.

When $\|\mathbf{v}\| \not= 0$, a unit vector is a vector in the same direction as $\mathbf{v}$ with magnitude equals to $1$, denoted by $\mathbf{\hat{v}}$.
Hence,

$$
\mathbf{\hat{v}} = {\mathbf{v} \over |\mathbf{v}|}
$$

## Vector Addition

Vectors add according to the Parallelogram Law of Addition,

$$
\mathbf{a} + \mathbf{b} = \mathbf{c} \iff \vec{OA} + \vec{OB} = \vec{OC}
$$

where $OACB$ is a parallelogram.

### Properties

As $\vec{OA} = \vec{BC}$ and $\vec{OB} = \vec{AC}$ (opposite sides of the parallelogram),

$$
\vec{OC} = \vec{OA} + \vec{AC} = \vec{OB} + \vec{BC}
$$

Hence, vector addition is _commutative_, i.e.

$$
\mathbf{a} + \mathbf{b} = \mathbf{b} + \mathbf{a}
$$

Geometrically we can deduce that vector addition is _associative_, i.e.

$$
\mathbf{a} + (\mathbf{b} + \mathbf{c}) = (\mathbf{a} + \mathbf{b}) + c
$$

The _null/zero vector_ $\mathbf{0}$ is the _additive identity_, i.e.

$$
\mathbf{a} + \mathbf{0} = \mathbf{0} + \mathbf{a} = \mathbf{a}
$$

The _inverse_ of $\mathbf{a}$, namely $-\mathbf{a}$, is a vector parallel to $\mathbf{a}$ with same magitude,
i.e. $\|-\mathbf{a}\| = \|\mathbf{a}\|$, but opposite direction, and we have

$$
\mathbf{a} + (-\mathbf{a}) = (-\mathbf{a}) + \mathbf{a} = \mathbf{0}
$$

We can therefore define subtraction by

$$
\mathbf{b} - \mathbf{a} = \mathbf{b} + (-\mathbf{a})
$$

According to the above, the set of $\mathbb{R}^2$ / $\mathbb{R}^3$ vectors form a abelian group under addition.

## Multiplication by Scalars

Let $\mathbf{a}$ be an vector and $\lambda \in \mathbb{R}$, $\lambda\mathbf{a}$ is defined as a vector parallel to $\mathbf{a}$,
with magnitude $\|\lambda\| \|\mathbf{a}\|$ and same direction as $\mathbf{a}$ when $\lambda > 0$ and opposite direction to $\mathbf{a}$ when $\lambda < 0$.

### Properties

Geometrically, we can see that multiplication by scalars is _distributive_ over vector addition

$$
\begin{align*}
(\lambda + \mu)\mathbf{a} &= \lambda\mathbf{a} + \mu\mathbf{a} \\
\lambda (\mathbf{a} + \mathbf{b}) &= \lambda\mathbf{a} + \lambda\mathbf{b}
\end{align*}
$$

and _associative_

$$
\lambda(\mu\mathbf{a}) = (\lambda\mu)\mathbf{a}
$$

and has _multiplicative identity_ $1$

$$
1\mathbf{a} = \mathbf{a}
$$

When $\lambda = 0$, since $0\|\mathbf{a}\| = 0$, we have

$$
0\mathbf{a} = \mathbf{0}
$$

When $\lambda = -1$, since $\|(-1)\mathbf{a}\| = \|-1\| \|\mathbf{a}\| = \|a\|$ and is of oppositie direction as $\mathbf{a}$, by definition,

$$
(-1)\mathbf{a} = -\mathbf{a}
$$

## Scalar Product

Let $A, B, C$ be the vertices and $\alpha = \angle BAC$ of a triangle in 2D, according to Cosine Law we have

$$
|CB|^2 = |AB|^2 + |AC|^2 - 2|AB||AC|\cos\alpha
$$

By putting them in vector terms, let $\mathbf{a} = \vec{AB}$ and $\mathbf{b} = \vec{AC}$, we have $\vec{CB} = \mathbf{a} - \mathbf{b}$.
Hence,

$$
|\mathbf{a} - \mathbf{b}|^2 = |\mathbf{a}|^2 + |\mathbf{b}|^2 - 2|\mathbf{a}||\mathbf{b}|\cos\alpha
$$

The scalar/dot product of two vectors $\mathbf{a}$ and $\mathbf{b}$ is defined to be the scalar number

$$
\mathbf{a} \cdot \mathbf{b} = |\mathbf{a}| |\mathbf{b}|\cos\theta
$$

where $0 \le \theta \le \pi$ is the non-reflex angle between $\mathbf{a}$ and $\mathbf{b}$ once they are placed "tail to tail" or "head to head".

Later on we can see that with such definition, we have (which is consistent with binomial expansion)

$$
(\mathbf{a} - \mathbf{b})^2 = (\mathbf{a} - \mathbf{b}) \cdot (\mathbf{a} - \mathbf{b}) = \mathbf{a} \cdot \mathbf{a} + \mathbf{b} \cdot \mathbf{b} - 2(\mathbf{a} \cdot \mathbf{b})
$$

In geometry, the projection of $\mathbf{b}$ onto $\mathbf{a}$ is the part of $\mathbf{b}$ that is parallel to $\mathbf{a}$,
denoted by $\mathbf{b}^{\perp}$. When $0 \le \theta \le \pi/2$, $\|\mathbf{b}^{\perp}\| = \|\mathbf{b}\| \cos \theta$ and $\mathbf{b}^{\perp}$ is in same direction as $\mathbf{a}$,
Therefore,

$$
\mathbf{b}^{\perp} = (|\mathbf{b}|\cos\theta)\,\mathbf{\hat{a}}
$$

When $\pi / 2 < \theta \le \pi$, $\|\mathbf{b}^{\perp}\| = \|\mathbf{b}\| \cos (\pi - \theta)$ and $\mathbf{b}^{\perp}$ is in opposite direction as $\mathbf{a}$.
Therefore,

$$
\mathbf{b}^{\perp} = \left(-|\mathbf{b}|\cos(\pi -\theta)\right)\,\mathbf{\hat{a}} = (|\mathbf{b}|\cos\theta)\,\mathbf{\hat{a}}
$$

Hence,

$$
\mathbf{b}^{\perp} = |\mathbf{b}|{\mathbf{b} \cdot \mathbf{a} \over |\mathbf{b}||\mathbf{a}|}\mathbf{\hat{a}} = {\mathbf{b} \cdot \mathbf{a} \over |\mathbf{a}|^2}\mathbf{a} = (\mathbf{b} \cdot \mathbf{\hat{a}})\,\mathbf{\hat{a}}
$$

### Properties

Base on the definiton, we can see that scalar multiplication is _commutative_, i.e.

$$
\mathbf{a} \cdot \mathbf{b} = \mathbf{b} \cdot \mathbf{a}
$$

A scalar product of a vector with itself is always $\ge 0$

$$
\mathbf{a} \cdot \mathbf{a} = |\mathbf{a}|^2 \ge 0
$$

with equality holds if and only if $\mathbf{a} = \mathbf{0}$.

If $\mathbf{a} \cdot \mathbf{b} = 0$ and $\mathbf{a} \not = \mathbf{0}$ and $\mathbf{b} \not = \mathbf{0}$, then $\mathbf{a} \perp \mathbf{b}$ and $\theta = \pi/2$.

### Linearity in the Arguments

From the definition, we can see that for $\lambda \in \mathbb{R}$,

$$
\mathbf{a} \cdot (\lambda\mathbf{b}) = (\lambda \mathbf{a}) \cdot \mathbf{b} = \lambda(\mathbf{a} \cdot \mathbf{b})
$$

According to the following graph,

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/Dot_product_distributive_law.svg/320px-Dot_product_distributive_law.svg.png" alt=""></p>

We can see that $\mathbf{b}^{\perp} + \mathbf{c}^{\perp} = (\mathbf{b} + \mathbf{c})^{\perp}$.
Hence,

$$
\begin{align*}
{\mathbf{a} \cdot \mathbf{b} \over |\mathbf{a}|^2}\mathbf{a} + {\mathbf{a} \cdot \mathbf{c} \over |\mathbf{a}|^2}\mathbf{a} &= {\mathbf{a} \cdot (\mathbf{b} + \mathbf{c}) \over |\mathbf{a}|^2}\mathbf{a} \\
(\mathbf{a} \cdot \mathbf{b} + \mathbf{a} \cdot \mathbf{c})(\mathbf{a} \cdot \mathbf{a}) &= [\mathbf{a} \cdot (\mathbf{b} + \mathbf{c})](\mathbf{a} \cdot \mathbf{a}) \\
\mathbf{a} \cdot \mathbf{b} + \mathbf{a} \cdot \mathbf{c} &= \mathbf{a} \cdot (\mathbf{b} + \mathbf{c})
\end{align*}
$$

Combining the above, we have what we called _linearity in the second argument_,

$$
\mathbf{a} \cdot (\lambda \mathbf{b} + \mu \mathbf{c}) = \lambda \mathbf{a} \cdot \mathbf{b} + \mu \mathbf{a} \cdot \mathbf{c}
$$

In fact, as scalar multiplication of vectors in real vector spaces is commutative, we also have linearity in the first argument (which might not be true in other vector spcaes).

## Vector Product

The vector/cross product $\mathbf{a} \times \mathbf{b}$ of an ordered pair $\mathbf{a}, \mathbf{b}$ is a vector such that

1. The magnitude of $$\mathbf{a} \times \mathbf{b}$$ is

$$|\mathbf{a} \times \mathbf{b}| = |\mathbf{a}||\mathbf{b}|\sin \theta$$

with $0 \le \theta \le \pi$ with definition similar to dot product (non-reflex angle after "tail-to-tail" or "head-to-head" placement of the two vectors).

2. $\mathbf{a} \times \mathbf{b}$ is orthongonal to both $\mathbf{a}$ and $\mathbf{b}$ (if $\mathbf{a} \times \mathbf{b} \not = \mathbf{0}$)

3. $\mathbf{a} \times \mathbf{b}$ has the direction defined by "right-hand rule" ($\mathbf{a}$ - index finger, $\mathbf{b}$ - second finger, $\mathbf{a} \times \mathbf{b}$ - thumb)

<p align="center"><img src="../.gitbook/assets/vector-product.png" alt=""></p>

Consider a triangle with vertices $O, A, B$, we have area of $OAB$ equals to ${1 \over 2}\|\mathbf{a}\|\|\mathbf{b}\| \sin \theta = {1 \over 2}\|\mathbf{a} \times \mathbf{b}\|$,
and area of parallelogram $OACB$ equals to $\|\mathbf{a} \times \mathbf{b}\|$, with the direction of $\mathbf{a} \times \mathbf{b}$ orthogonal to the triangle/parallelogram.

The vector product is only defined for $\mathbb{R}^3$ space but not all vector spaces in general.

### Properties

Vector product is _anti-commutative_

$$
\mathbf{a} \times \mathbf{b} = - \mathbf{b} \times \mathbf{a}
$$

Vector product of a vector with itself is a zero vector

$$
\mathbf{a} \times \mathbf{a} = \mathbf{0}
$$

Given $\mathbf{a} \not = \mathbf{0}$ and $\mathbf{b} \not = \mathbf{0}$

$$
\mathbf{a} \times \mathbf{b} = \mathbf{0} \implies \mathbf{a} = \lambda \mathbf{b}
$$

i.e. $\mathbf{a}$ and $\mathbf{b}$ are parallel and $\theta = 0$ or $\theta = \pi$.

From definition

$$
\mathbf{a} \times (\lambda\mathbf{b}) = \lambda ( \mathbf{a} \times \mathbf{b})
$$

### Linearity in the Second Arguments

The vector product $\mathbf{\hat{a}} \times \mathbf{b}$ can be constructed by two steps.
First project $\mathbf{b}$ onto a plane orthogonal to $\mathbf{\hat{a}}$ and then rotate the projection $\mathbf{b'}$ by $\pi/2$ in "anti-clockwise" direction
(when looking in the opposite direction of $\mathbf{\hat{a}}$) to form $\mathbf{b''}$.

<p align="center"><img src="../.gitbook/assets/Screenshot 2024-09-27 at 5.08.53 PM.png" alt=""></p>

We can see that $\|\mathbf{b}''\| = \|\mathbf{b'}\| = \|\mathbf{b}\| \sin \theta$.
By construction, $\mathbf{b''} = \mathbf{\hat{a}} \times \mathbf{b}$.
Hence,

$$
\mathbf{a} \times (\lambda\mathbf{b} + \mu\mathbf{c}) = \lambda\mathbf{a} \times \mathbf{b} + \mu\mathbf{a} \times \mathbf{c}
$$

with a similar argument as the proof in dot product.

## Triple Products

## Bases and Components

## Vector Equations

## Lines, Planes and Spheres

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* [https://math.stackexchange.com/questions/1109142/proving-that-the-dot-product-is-distributive](https://math.stackexchange.com/questions/1109142/proving-that-the-dot-product-is-distributive)
