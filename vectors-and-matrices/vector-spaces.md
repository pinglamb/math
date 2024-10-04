---
layout: base
title: Vector Spaces &#124; Vectors and Matrices
---

# Vector Spaces

The essential features of vectors is that we can have a linear combination of vectors which again is a vector.
This idea can be generalized to different kinds of quantities, not just about magnitude and direction.
An algebraic approach to study that helps us to generalize the results in $\mathbb{R}^2$ and $\mathbb{R}^3$ to other vector spaces such as $\mathbb{R}^n$ and $\mathbb{C}^n$.

## Definition

A vector space $V$ over the field $\mathbb{F}$ is a set of $V$ of vectors, a field $\mathbb{F}$ of scalars,
an addition $a + b$ of vectors $a$ and $b$, and a scalar multiplication $\lambda v$ of a scalar $\lambda$ and a vector $v$,
which together satify the following properties/axioms:

* $V$ is _closed_ under addition, i.e.

$$
\forall a, b \in V \implies a + b \in V
$$

* addition is _commutative_, i.e. for all $a, b \in V$

$$
a + b = b + a
$$

* addition is _associative_, i.e. for all $a, b, c \in V$

$$
a + (b + c) = (a + b) + c
$$

* addition has an _identity_ element, i.e. there exists an element $0 \in V$ such that

$$
a + 0 = a
$$

* for all $a \in V$, there exists an _additive inverse_ $a' \in V$ such that

$$
a + a' = 0
$$

* $V$ is _closed_ under scalar multiplication, i.e.

$$
\forall \lambda \in F, \forall a \in V \implies \lambda a \in V
$$

* scalar multiplication is _distributive over scalar addition_, i.e. for all $\lambda, \mu \in \mathbb{F}$ and $a \in V$

$$
(\lambda + \mu)a = \lambda a + \mu a
$$

* scalar multiplication is _distributive over vector addition_, i.e. for all $\lambda \in \mathbb{F}$ and $a, b \in V$

$$
\lambda (a + b)= \lambda a + \lambda b
$$

* scalar multiplication is "associative", i.e. for all $\lambda, \mu \in \mathbb{F}$ and $a \in V$

$$
\lambda (\mu a) = (\lambda \mu) a
$$

* scalar multiplication has an _identity_ element, i.e. there exists an element $1 \in \mathbb{F}$ such that

$$
1 a = a
$$

Base on our study of [vectors](vectors.md) in $\mathbb{R}^2$/$\mathbb{R}^3$, we can see that they form a vector space over $\mathbb{R}$.

## Properties

## Dimension

## R^n

## C^n

## Subspaces

## Reference

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 7
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
