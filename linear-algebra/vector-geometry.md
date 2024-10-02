---
layout: base
title: Vector Geometry &#124; Linear Algebra
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
\mathbf{x} = (1 - \lambda)\mathbf{a} + \lambda\mathbf{b}
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

### Intersection between Lines

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 4.7
