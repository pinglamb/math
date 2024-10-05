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

## Basis and Dimensions

### Linear Independence

A set of $m$ vectors $\Set{v_1, v_2, ..., v_m}$ of vector space $V$ is _linearly independent_ if for all scalars $\lambda \in \mathbb{F}$,

$$
\sum_i \lambda_i v_i = 0_V \quad \implies \quad \lambda_i = 0_{\mathbb{F}}
$$

Otherwise, we can see that we can express a vector in the set by other vectors in the same set.

### Spanning Set

A set of $m$ vectors $\Set{v_1, v_2, ..., v_m}$ of vector space $V$ is a _spanning set_ for V if for every vector $v \in V$,
there exists scalars $\lambda_i \in \mathbb{F}$ such that

$$
v = \lambda_1 v_1 + \lambda_2 v_2 + ... + \lambda_m v_m
$$

We state that $m \ge n$ so the set can span $V$.

### Basis

We then define a linearly independent subset of vectors that spans $V$ is a _basis_ of V.

If $S = \Set{v_1, v_2, ..., v_n}$ is a basis of $\mathbb{R}^n$, then there exists unique scalars $\lambda_i \in \mathbb{R}$,
which we called them _components_, such that

$$
v = \lambda_1 v_1 + \lambda_2 v_2 + ... + \lambda_n v_n
$$

### Dimension

The _dimension_ of a space is defined by the number of vectors in a basis of the space.

Hence, $\dim \mathbb{R}^2 = 2$, $\dim \mathbb{R}^3 = 3$ and $\dim \mathbb{R}^n = n$.

## n-dimensional Real Space

### Definition

We define $\mathbb{R}^n$ to be the set of all n-tuples

$$
\Set{\mathbf{x} = (x_1, x_2, ..., x_n) \mid x_i \in \mathbb{R} \text{ with } i = 1, 2, ..., n}
$$

For $\mathbf{x}, \mathbf{y} \in \mathbb{R}^n$ and $\lambda \in \mathbb{R}$, we define

$$
\begin{gather}
\mathbf{x} + \mathbf{y} = (x_1 + y_1, x_2 + y_2, ..., x_n + y_n) \\
\lambda \mathbf{x} = (\lambda x_1, \lambda x_2, ..., \lambda x_n) \\
\mathbf{0} = (0, 0, ..., 0) \\
\mathbf{-x} = (-x_1, -x_2, ..., -x_3)
\end{gather}
$$

We can see that $\mathbb{R}^n$ over $\mathbf{R}$ satifies the above axioms and hence is a vector space over $\mathbb{R}$.

### Scalar Product

We define the scalar product on $\mathbb{R}^n$ for $\mathbf{x}, \mathbf{y} \in \mathbb{R}^n$ as

$$
\mathbf{x} \cdot \mathbf{y} = \sum_{i=1}^n x_i y_i = x_1 y_1 + x_2 y_2 + ... + x_n y_n
$$

which satisfies the axioms of scalar/inner product of vector space.

This definition is consistent with that of $\mathbb{R}^3$ only when we are dealing with standard basis.

### Norm

For $\mathbf{x} \in \mathbb{R}^n$,

$$
\|x\| = (\mathbf{x} \cdot \mathbf{x})^{1 \over 2} = \left( \sum_{i=1}^n x_i^2 \right)^{1 \over 2}
$$

while the interior angle $\theta$ between vectors $\mathbf{x}$ and $\mathbf{y}$ is defined to be

$$
\theta = \arccos \left( {\mathbf{x} \cdot \mathbf{y} \over \|x\|\|y\| } \right)
$$

and we state $\mathbf{x}, \mathbf{y}$ is orthogonal if $\mathbf{x} \cdot \mathbf{y} = 0$

## n-dimensional Complex Space

### Definition

We define $\mathbb{C}^n$ to be the set of all n-tuples

$$
\Set{\mathbf{x} = (z_1, z_2, ..., z_n) \mid z_i \in \mathbb{C} \text{ with } i = 1, 2, ..., n}
$$

For $\mathbf{x}, \mathbf{y} \in \mathbb{C}^n$ and $\lambda \in \mathbb{C}$, we define

$$
\begin{gather}
\mathbf{x} + \mathbf{y} = (x_1 + y_1, x_2 + y_2, ..., x_n + y_n) \\
\lambda \mathbf{x} = (\lambda x_1, \lambda x_2, ..., \lambda x_n) \\
\mathbf{0} = (0, 0, ..., 0) \\
\mathbf{-x} = (-x_1, -x_2, ..., -x_3)
\end{gather}
$$

We can see that $\mathbb{C}^n$ over $\mathbf{C}$ satifies the axioms as well and hence is a vector space over $\mathbb{C}$.

The standard basis of $\mathbb{R}^n$ can serve as standard basis of $\mathbb{C}^n$, hence $\dim \mathbb{C}^n = n$.

### Scalar Product

We define the scalar product on $\mathbb{C}^n$ for $\mathbf{x}, \mathbf{y} \in \mathbb{C}^n$ as

$$
\mathbf{x} \cdot \mathbf{y} = \sum_{i=1}^n x_i^{\ast} y_i = x_1^{\ast} y_1 + x_2^{\ast} y_2 + ... + x_n^{\ast} y_n
$$

The set axioms are different than that of $\mathbb{R}^n$, which is as follow

$$
\begin{gather}
\mathbf{x} \cdot \mathbf{y} = (\mathbf{y} \cdot \mathbf{x})^{\ast} \\
\mathbf{x} \cdot (\lambda \mathbf{y} + \mu \mathbf{z}) = \lambda (\mathbf{x} \cdot \mathbf{y}) + \mu (\mathbf{x} \cdot \mathbf{z}) \\
\mathbf{x} \cdot \mathbf{x} \ge 0
\end{gather}
$$

The axioms are reqally similar except that scalar product on $\mathbb{C}^n$ is not symmetric,
hence we can't derive the linearity of the first argument, i.e.

$$
(\lambda\mathbf{x} + \mu\mathbf{y}) \cdot \mathbf{z} \not = \lambda\mathbf{x} \cdot \mathbf{y} + \mu \mathbf{x} \cdot \mathbf{z}
$$

## Subspaces

## Reference

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 7
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
