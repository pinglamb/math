---
layout: base
title: Vectors &#124; Linear Algebra
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

### Cauchy-Schwarz Inequality

For all $\mathbf{a}, \mathbf{b} \in \mathbb{R}^2$/,

$$
| \mathbf{a} \cdot \mathbf{b} | \le | \mathbf{a}| | \mathbf{b}|
$$

By definition,

$$
|\mathbf{a} \cdot \mathbf{b}| = |\mathbf{a}||\mathbf{b}||\cos \theta| \le |\mathbf{a}||\mathbf{b}|
$$

with equality holds when $\mathbf{a} = \mathbf{0}$ or $\mathbf{b} = \mathbf{0}$ or $\mathbf{a} = \lambda\mathbf{b}$.

## Vector Product

The vector/cross product $\mathbf{a} \times \mathbf{b}$ of an ordered pair $\mathbf{a}, \mathbf{b}$ is a vector such that

1. The magnitude of $$\mathbf{a} \times \mathbf{b}$$ is

$$|\mathbf{a} \times \mathbf{b}| = |\mathbf{a}||\mathbf{b}|\sin \theta$$

with $0 \le \theta \le \pi$ with definition similar to dot product (non-reflex angle after "tail-to-tail" or "head-to-head" placement of the two vectors).

2. $\mathbf{a} \times \mathbf{b}$ is orthongonal to both $\mathbf{a}$ and $\mathbf{b}$ (if $\mathbf{a} \times \mathbf{b} \not = \mathbf{0}$)

3. $\mathbf{a} \times \mathbf{b}$ has the direction defined by "right-hand rule" ($\mathbf{a}$ - index finger, $\mathbf{b}$ - second finger, $\mathbf{a} \times \mathbf{b}$ - thumb)

<p align="center"><img src="https://github.com/user-attachments/assets/72e22713-a95f-4669-a054-fd55797a74be" alt=""></p>

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

<p align="center"><img src="https://github.com/user-attachments/assets/5eac629b-5ea6-4bb8-85b8-8fb42ef0d2e4" alt=""></p>

We can see that $\|\mathbf{b}''\| = \|\mathbf{b'}\| = \|\mathbf{b}\| \sin \theta$.
By construction, $\mathbf{b''} = \mathbf{\hat{a}} \times \mathbf{b}$.
Hence,

$$
\mathbf{a} \times (\lambda\mathbf{b} + \mu\mathbf{c}) = \lambda\mathbf{a} \times \mathbf{b} + \mu\mathbf{a} \times \mathbf{c}
$$

with a similar argument as the proof in dot product.

## Triple Products

### Scalar Triple Product

The scalar triple product is defined by

$$
[\mathbf{a}, \mathbf{b}, \mathbf{c}] = \mathbf{a} \cdot(\mathbf{b} \times \mathbf{c})
$$

Assume $\mathbf{a}, \mathbf{b}, \mathbf{c}$ have the sense of the right-hand rule,
the volume of a parallelepiped is given by $[\mathbf{a}, \mathbf{b}, \mathbf{c}]$.

<p align="center"><img src="https://github.com/user-attachments/assets/6e5060f2-f1a6-4ec5-8527-3026620d1f61" alt=""></p>

Since the order of $\mathbf{a}, \mathbf{b}, \mathbf{c}$ doesn't affect the volume, we have

$$
[\mathbf{a}, \mathbf{b}, \mathbf{c}] = [\mathbf{b}, \mathbf{c}, \mathbf{a}] = [\mathbf{c}, \mathbf{a}, \mathbf{b}] = -[\mathbf{b}, \mathbf{a}, \mathbf{c}] = - [\mathbf{a}, \mathbf{c}, \mathbf{b}] = - [\mathbf{c}, \mathbf{b}, \mathbf{a}]
$$

As $\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = \mathbf{c} \cdot (\mathbf{a} \times \mathbf{b})$ and dot product is commutative, we have

$$
\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = (\mathbf{a} \times \mathbf{b}) \cdot \mathbf{c}
$$

### Vector Triple Product

The vector triple product is defined by

$$
(\mathbf{a} \times \mathbf{b}) \times \mathbf{c} = - \mathbf{c} \times (\mathbf{a} \times \mathbf{b}) = - (\mathbf{b} \times \mathbf{a}) \times \mathbf{c} = \mathbf{c} \times (\mathbf{b} \times \mathbf{a})
$$

We will later see that

$$
\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) = (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c}
$$

## Bases and Components

### Linear Dependency

In $\mathbb{R}^3$ (similar argument for $\mathbb{R}^2$, the vector

$$
\mathbf{d} = \lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}
$$

is described as a linear combination of $\mathbf{a},\mathbf{b}, \mathbf{c}$.

If for vectors $\mathbf{a},\mathbf{b}, \mathbf{c}$,

$$
\lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}= \mathbf{0} \iff \lambda = \mu = \nu = 0
$$

then $\mathbf{a},\mathbf{b}, \mathbf{c}$ are linear independent. The reason for that is if let say $\lambda \not = 0$,
we can write $\mathbf{a} = -{\mu \over \lambda}\mathbf{b} - {\nu \over \lambda}\mathbf{c}$,
which is a linear combination of other vectors and therefore they are linearly dependent.

### Spanning Set and Basis

A set of vectors $\\{\mathbf{a}, \mathbf{b}\\}$ is a spanning set which spans $\mathbb{R}^2$ if for all vectors $\mathbf{r} \in \mathbb{R}^2$, there exists some $\lambda, \mu \in \mathbb{R}$ such that

$$
\mathbf{r} = \lambda\mathbf{a} + \mu\mathbf{b}
$$

$\\{\mathbf{a}, \mathbf{b}\\}$ spans $\mathbb{R}^2$ if $\mathbf{a} \times \mathbf{b} = \mathbf{0}$ (non-parallel).

For any vector $\mathbf{r} \in \mathbb{R}^2$, the components $(\lambda, \mu)$ are _unique_.

We said $\\{\mathbf{a}, \mathbf{b}\\}$ is a basis of the set of vectors in $\mathbb{R}^2$ if it is a spanning set and linear independent.

In $\mathbb{R}^2$, to find $\lambda$ and $\mu$ for $\vec{OP}$ geometrically, we can draw a line through $P$ which is parallel to $OA$ and intersects with $OB$ (or its extension) at $N$.
We have $\vec{OP} = \vec{ON} + \vec{NP} = \mu\mathbf{b} + \lambda\mathbf{a}$.

The same concept can be extended to $\mathbb{R}^3$,
a set of vectors $\\{\mathbf{a}, \mathbf{b}\\}, \mathbf{c}\\}$ is a spanning set which spans $\mathbb{R}^3$ if for all vectors $\mathbf{r} \in \mathbb{R}^3$, there exists some $\lambda, \mu, \nu \in \mathbb{R}$ such that

$$
\mathbf{r} = \lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}
$$

$\\{\mathbf{a}, \mathbf{b}, \mathbf{c}\\}$ spans $\mathbb{R}^3$ if $\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = 0$ (non-coplanar) and is a basis of $\mathbb{R}^3$.

The components $(\lambda, \mu, \nu)$ are _unique_.
For any $\mathbf{r} = \lambda \mathbf{a} + \mu \mathbf{b} + \nu \mathbf{c}$, we have

$$
\mathbf{r} \cdot (\mathbf{b} \times \mathbf{c}) = \lambda \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) + \mu \mathbf{b} \cdot (\mathbf{b} \times \mathbf{c}) + \nu \mathbf{c} \cdot (\mathbf{b} \times \mathbf{c}) = \lambda \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c})
$$

Therefore, $\lambda = [\mathbf{r}, \mathbf{b}, \mathbf{c}]/[\mathbf{a}, \mathbf{b}, \mathbf{c}]$ which is unique and similarily for $\mu, \nu$.

## Cartesian/Standard Basis

Although any three vectors can be as basis in $mathbb{R}^3$ as long as $\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = 0$,
things can be simplified if the basis vectors are orthogonal, have unit magnitude.
For a Cartesian basis, we have the basis vectors being the unit vectors along the $x, y, z$ axes, and denoted by $\mathbf{i}, \mathbf{j}, \mathbf{k}$.

With that, we have

$$
\begin{gather}
\mathbf{i} \cdot \mathbf{i} = \mathbf{j} \cdot \mathbf{j} = \mathbf{k} \cdot \mathbf{k} = 1 \\
\mathbf{i} \cdot \mathbf{j} = \mathbf{j} \cdot \mathbf{k} = \mathbf{k} \cdot \mathbf{i} = 0 \\
\mathbf{i} \times \mathbf{j} = \mathbf{k} \quad \mathbf{j} \times \mathbf{k} = \mathbf{i} \quad \mathbf{k} \times \mathbf{i} = \mathbf{j} \\
[\mathbf{i}, \mathbf{j}, \mathbf{k}] = 1
\end{gather}
$$

For any point $P$ with coordinates $(x, y, z)$, we can see that $\vec{OP} = \mathbf{v} = x\mathbf{i} + y\mathbf{j} + z\mathbf{k}$,
hence we can have the notation $\mathbf{v} = (x, y, z)$ and it is called the Cartesian components of $\mathbf{v}$.

Also, by "dotting" $\mathbf{v}$ by $\mathbf{i}, \mathbf{j}, \mathbf{k}$ respectively, we can conclude

$$
\mathbf{v} = (\mathbf{v} \cdot \mathbf{i}, \mathbf{v} \cdot \mathbf{j},\mathbf{v} \cdot \mathbf{k})
$$

For unit vector $\mathbf{\hat{v}}$, we can write

$$
\mathbf{\hat{v}} = (\cos \alpha, \cos \beta, \cos \gamma)
$$

which is called the direction cosines of $\mathbf{\hat{v}}$.

### Vector Component Identities

With the use of standard basis, some of the numeric operations of vectors can be simplified.
Given

$$
\begin{align*}
\mathbf{a} &= a_x\mathbf{i} + a_y\mathbf{j} + a_z\mathbf{k} \\
\mathbf{b} &= b_x\mathbf{i} + b_y\mathbf{j} + b_z\mathbf{k} \\
\mathbf{c} &= c_x\mathbf{i} + c_y\mathbf{j} + c_z\mathbf{k}
\end{align*}
$$

For addition,

$$
\lambda\mathbf{a} + \mu\mathbf{b} = (\lambda a_x + \mu b_x)\mathbf{i} + (\lambda a_y + \mu b_y)\mathbf{j} + (\lambda c_x + \mu c_x)\mathbf{k}
$$

For scalar product,

$$
\mathbf{a} \cdot \mathbf{b} = a_x b_x + a_y b_y + a_z b_z
$$

For vector product,

$$
\mathbf{a} \times \mathbf{b} = (a_y b_z - a_z b_y)\mathbf{i} + (a_z b_x - a_x b_z)\mathbf{j} + (a_x b_y - a_y b_x)\mathbf{k}
$$

or

$$
\mathbf{a} \times \mathbf{b} = \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
a_x & a_y & a_z \\
b_x & b_y & b_z \\
\end{vmatrix}
$$

For scalar triple product,

$$
[\mathbf{a}, \mathbf{b}, \mathbf{c}] = a_x b_y c_z + a_y b_z c_x + a_z b_x c_y - a_x b_z c_y - a_y b_x c_z - a_z b_y c_x
$$

or

$$
[\mathbf{a}, \mathbf{b}, \mathbf{c}] = \begin{vmatrix}
a_x & a_y & a_z \\
b_x & b_y & b_z \\
c_x & c_y & c_z \\
\end{vmatrix}
$$

For vector product, consider the $x$-component of the product

$$
\begin{align*}
\left(\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \right)_x = \left( \mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \right) \cdot \mathbf{i} &= a_y(\mathbf{b} \times \mathbf{c})_z - a_z(\mathbf{b} \times \mathbf{c})_y \\
&= a_y(b_x c_y - b_y c_x) - a_z(b_z c_x - b_x c_z) \\
&= (a_y c_y + a_z c_z)b_x - (a_z b_z + a_y c_y)c_x + a_x b_x c_x - a_x b_x c_x \\
&= (\mathbf{a} \cdot \mathbf{c})b_x - (\mathbf{a} \cdot \mathbf{b})c_x \\
&= \left( (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c} \right) \cdot \mathbf{i} \\
&= \left( (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c} \right)_x \\
\end{align*}
$$

Similar results will be arrived for $y$-component and $z$-component, hence

$$
\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) = (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c}
$$

We can see that the resulting vector has no component in direction $\mathbf{a}$ (outside the parentheses) because the resulting vector after the last vector multiplication by $\mathbf{a}$ is orthogonal to $\mathbf{a}$.

## Vector Equations

We use vector manipulation on the equation so to simplify the terms, normally by dotting or crossing the equation with some vectors.

For example,

$$
\mathbf{x} - (\mathbf{x} \times \mathbf{a}) \times \mathbf{b} = \mathbf{c}
$$

After dotting with $\mathbf{b}$ and some substitutions, we will have

$$
\mathbf{x} = {\mathbf{c} + (\mathbf{c} \cdot \mathbf{b})a \over 1 + \mathbf{a} \cdot \mathbf{b}}
$$

This is another technique [here](https://math.stackexchange.com/questions/3879932/how-to-solve-the-vector-equation-mathbfr-mathbfr-times-mathbfd-m).

## Lines, Planes and Spheres

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* [https://math.stackexchange.com/questions/1109142/proving-that-the-dot-product-is-distributive](https://math.stackexchange.com/questions/1109142/proving-that-the-dot-product-is-distributive)
