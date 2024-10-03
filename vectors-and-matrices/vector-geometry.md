---
layout: base
title: Vector Geometry &#124; Vectors and Matrices
---

# Vector Geometry

Vectors provide a convenient way for describing geometry in $\mathbf{R}^3$.

## Lines

### Vector Equations

Let $A$ be a point with $\vec{OA} = \mathbf{a}$, $\mathbf{t}$ be a non-zero vector,
and $L$ be a line through $A$ and parallel to $\mathbf{t}$.

A point $X$ with $\vec{OX} = \mathbf{x}$ is on $L$ if and only if $\mathbf{x} - \mathbf{a}$ is parallel to $\mathbf{t}$, i.e.

$$
(\mathbf{x} - \mathbf{a}) = \lambda \mathbf{t}
$$

for some $\lambda \in \mathbb{R}$.

It implies

$$
(\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}
$$

If we have two position vectors $\mathbf{a}$ and $\mathbf{b}$ instead,
we can take $\mathbf{t} = \mathbf{b} - \mathbf{a}$ and therefore

$$
(\mathbf{x} - \mathbf{a}) \times (\mathbf{b} - \mathbf{a}) = \mathbf{0}
$$

or alternatively

$$
\begin{align*}
\mathbf{x} &= \mathbf{a} + \lambda(\mathbf{b} - \mathbf{a}) \\
           &= (1 - \lambda)\mathbf{a} + \lambda\mathbf{b}
\end{align*}
$$

### Distance between Point and Line

Let $Y$ be a point with $\vec{OY} = \mathbf{y}$, a line $L$ through $A$ and parallel to $\mathbf{t}$ and $d$ be the distance between them.
Consider the plane containing $Y$ and $L$, we have

$$
d = |(\mathbf{y} - \mathbf{a})|\sin\theta
$$

where $\theta$ is the non-reflex angle between $\vec{OA}$ and $\mathbf{t}$.

As

$$
|(\mathbf{y} - \mathbf{a}) \times \mathbf{t}| = |(\mathbf{y} - \mathbf{a})||\mathbf{t}|\sin\theta
$$

we can conclude

$$
d = {|(\mathbf{y} - \mathbf{a}) \times \mathbf{t}| \over |\mathbf{t}|}
$$

### Distance between Parallel Lines

Let $L_1: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ and $L_2: (\mathbf{x} - \mathbf{b}) \times \mathbf{t} = \mathbf{0}$ be two parallel lines.

As $\mathbf{b}$ is a point on $L_2$, from the above, we can see that the distance $d$ between $L_1$ and $L_2$ is

$$
d = {|(\mathbf{b} - \mathbf{a}) \times \mathbf{t}| \over |\mathbf{t}|}
$$

### Distance between Skew Lines

### Intersection between Lines

Let $L_1: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ and $L_2: (\mathbf{x} - \mathbf{b}) \times \mathbf{u} = \mathbf{0}$ be two lines.

For them to intersect at a single point, the two lines can't be parallel, hence

$$
\mathbf{t} \times \mathbf{u} \not = 0
$$

Consider a line $L_2'$ through $\mathbf{a}$ and parallel to $L_2$,
$L_1$ and $L_2\'$ forms a plane $\Pi$ with normal vector $\mathbf{t} \times \mathbf{u}$.
Therefore, the vector equation for $\Pi$ is

$$
(\mathbf{x} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u}) = 0
$$

As $L_2$ is parallel to $L_1$, either $L_2$ intersects $\Pi$ nowhere (in which $L_1$ and $L_2$ has no intersection)
or $L_2$ is on the plane $\Pi$.
Therefore, the condition for $L_1$ and $L_2$ to intersect is

$$
(\mathbf{b} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u}) = 0
$$

Conversely, if the above is true, the plane $\Pi$ passes through the origin as the distance of the plane from origin is $0$,
hence, we can express $\mathbf{b} - \mathbf{a}$ as

$$
\mathbf{b} - \mathbf{a} = \mathbf{0} + \lambda \mathbf{t} + \mu \mathbf{u}
$$

for some $\lambda, \mu \in \mathbb{R}$.

Let $\mathbf{x}$ be a point such that

$$
\mathbf{x} = \mathbf{a} + \lambda\mathbf{t} = \mathbf{b} - \mu\mathbf{u}
$$

We can see that $\mathbf{x}$ is a point on both $L_1$ and $L_2$ and therefore it is the intersection of $L_1$ and $L_2$.

To solve for $\mathbf{x}$, we have

$$
\begin{gather}
\mathbf{a} + \lambda\mathbf{t} = \mathbf{b} - \mu\mathbf{u} \\
\lambda(\mathbf{t} \times \mathbf{u}) = (\mathbf{b} - \mathbf{a}) \times \mathbf{u} \\
\lambda |\mathbf{t} \times \mathbf{u}|^2 = [\mathbf{t} \times \mathbf{u}, \mathbf{b} - \mathbf{a}, \mathbf{u}] \\
\end{gather}
$$

Hence,

$$
\mathbf{x} = \mathbf{a} + {[\mathbf{t} \times \mathbf{u}, \mathbf{b} - \mathbf{a}, \mathbf{u}] \over |\mathbf{t} \times \mathbf{u}|^2}\mathbf{t}
$$

## Planes

Let $A$ be a point with $\vec{OA} = \mathbf{a}$ and $\mathbf{n}$ be a non-zero vector.
The vector equation of the plane $\Pi$ which contains $\mathbf{a}$ and has normal in the direction of $mathbf{n}$ is

A point $X$ with $\vec{OX} = \mathbf{x}$ is on $\Pi$ if and only if $(\mathbf{x} - \mathbf{a}) \perp \mathbf{n}$, i.e.

$$
(\mathbf{x} - \mathbf{a}) \cdot \mathbf{n} = 0
$$

Given three points $\mathbf{a}, \mathbf{b}, \mathbf{c}$, the equation for the plane $\Pi$ which contains all three points is

$$
(\mathbf{x} - \mathbf{a}) \cdot [(\mathbf{b} - \mathbf{a}) \times (\mathbf{c} - \mathbf{a})] = [\mathbf{x} - \mathbf{a}, \mathbf{b} - \mathbf{a}, \mathbf{c} - \mathbf{a}] = 0
$$

or alternatively

$$
[\mathbf{x}, \mathbf{b}, \mathbf{c}] + [\mathbf{a}, \mathbf{x}, \mathbf{c}] + [\mathbf{a}, \mathbf{b}, \mathbf{x}] = [\mathbf{a}, \mathbf{b}, \mathbf{c}]
$$

As $\mathbf{b} - \mathbf{a}$ and $\mathbf{c} - \mathbf{a}$ are non-parallel, we can represent any point on the plane as

$$
\begin{align*}
\mathbf{x} &= \mathbf{a} + \lambda(\mathbf{b} - \mathbf{a}) + \mu(\mathbf{c} - \mathbf{a}) \\
           &= (1 - \lambda - \mu)\mathbf{a} + \lambda\mathbf{b} + \mu\mathbf{c}
\end{align*}
$$

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 4.7
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Section 2.13](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
