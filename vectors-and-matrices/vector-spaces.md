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

We generalize properties of vectors in $\mathbb{R}^2$/$\mathbb{R}^3$ and prove them algebraically.

As vector addition of vector spaces is abelian group, we have

* additive identity $0 \in V$ is unique
* additive inverse $-a \in V$ is unique
* subtraction is defined by addition of additive inverse, i.e.

$$
a - b = a + (-b)
$$

Also, scalar multiplication by $0 \in \mathbb{F}$ yields the additive identity

$$
\begin{align*}
0_{\mathbb{F}} a &= 0_{\mathbb{F}} a + 0_{V} \\
&= 0_{\mathbb{F}} a + a + (-a) \\
&= (0_{\mathbb{F}} + 1) a + (-a) \\
&= a + (-a) \\
&= 0_{V}
\end{align*}
$$

and scalar multiplication by $-1$ yields the additive inverse.

$$
\begin{align*}
(-1)a &= (-1)a + 0_{V} \\
&= (-1)a + a + (-a) \\
&= (-1 + 1) a + (-a) \\
&= 0_{\mathbb{F}}a + (-a) \\
&= 0_{V} + (-a) \\
&= -a
\end{align*}
$$

Furthermore, scalar multiplifcation with zero vector $0\_V$ yields $0\_V$, i.e. $\lambda 0_V = 0_V$ as

$$
\lambda 0_V + \lambda a = \lambda (0_V + a) = \lambda a
$$

If $\lambda a = 0$, either $\lambda = 0\_{\mathbb{F}}$ or $a = 0\_V$.
Assume $\lambda \not = 0_{\mathbb{F}}$, there exists $\lambda^{-1}$ such that

$$
a = (\lambda^{-1}\lambda)a = \lambda^{-1}0_V = 0_V
$$

Assume $a \not = 0\_V$, then $\lambda a = 0\_V$ for all other $a \in V$ only when $\lambda = 0_\mathbb{F}$.

## Scalar Product

The scalar/inner product of vectors $a, b \in V$, denoted by $a \cdot b$ or $\langle a \mid b \rangle$,
is a map $V \times V \to \mathbb{R}$ that satisfies the following properties:

* _Symmetric_, i.e.

$$
a \cdot b = b \cdot a
$$

* Linearilty in the second argument

$$
a \cdot (\lambda b + \mu c) = \lambda (a \cdot b) + \mu (a \cdot c)
$$

* Non-negativity, with equality holds iff $a = 0_V$, i.e.

$$
a \cdot a \ge 0_\mathbb{R}
$$

This definition is only for real vector spaces. For complex vector spaces, we have a different set of axioms.

### Norm

The _norm_ of a vector, denoted by $\|a\|$ or $\\\|a\\\|$ is defined as

$$
|a| = \|a\| = \sqrt{a \cdot a}
$$

### Cauchy-Schwarz inequality

The Cauchy-Schwarz inequality

$$
\|a \cdot b\| \le \|a\|\|b\|
$$

can be generalized by proving that algebraically.

Consider the expression $\\\|a + \lambda b\\\|^2$, from the above axioms about scalar product, we have

$$
\begin{align*}
\|a + \lambda b\|^2 &\ge 0 \\
(a + \lambda b) \cdot (a + \lambda b) &\ge 0 \\
\|b\|^2 \lambda^2 + 2 (a \cdot b) \lambda + \|a\|^2 &\ge 0
\end{align*}
$$

Viewing this as a quadratic equation in $\lambda$, as it is always non-negative, it has at most one root. Hence,

$$
\Delta = (2 a \cdot b)^2 - 4\|a\|^2\|b\|^2 \le 0
$$

$$
\|a \cdot b\| \le \|a\|\|b\|
$$

## Dimension

## $R^n$

## $C^n$

## Subspaces

## Reference

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 7
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
