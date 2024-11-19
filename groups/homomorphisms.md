---
layout: base
title: Homomorphisms &#124; Groups
---

# Homomorphisms

When considering sets, functions are allowed to do anything, as we can map any element in domain to any element in codomain.
However, as groups have some additional structure on top of sets, we are more interested in functions that respect/preserve the group structure, and they are called _homomorphisms_.

Before studying the relations between groups, we first revise the definition of functions and some of its properties.

## Functions

### Definition

Given $X, Y$ be two sets, a function $f: X \to Y$ maps $x \in X$ to **exactly one** $y \in Y$.
$X$ is the **domain** and $Y$ is the **codomain** of $f$.

### Composition

We can compose two functions by applying one after another, e.g. let $f: X \to Y$ and $g: Y \to Z$ be two functions, then $g \circ f: X \to Z$ is a function with $(g \circ f)(x) = g(f(x))$.

Function composition is _associative_, i.e.

$$
(h \circ (g \circ f))(x) = h(g(f(x))) = (h \circ g)(f(x)) = ((h \circ g) \circ f)(x)
$$

It is NOT commutative, e.g. $f(x) = x + 1$, $g(x) = 2x$, $(g \circ f)(x) = 2x + 2$ but $(f \circ g)(x) = 2x + 1$.

### Injection, Surjection and Bijection

A function $f$ is _injective_ if it maps everything in $Y$ at most once, i.e. $\forall x, y \in X$

$$
f(x) = f(y) \implies x = y
$$

A function $f$ is surjective if it maps everything in $Y$ at least once, i.e.

$$
(\forall y \in Y, \exists x \in X) \, f(x) = y
$$

A function $f$ is bijective if it is both injective and surjective, i.e. it hits everything exactly once.

A function has inverse $f^{-1}$ iff $f$ is bijective, i.e. $(f \circ f^{-1}) = 1_Y$ and $(f^{-1} \circ f) = 1_X$.

The composition of bijections is bijection.

## Definition of Homomorphisms

Let $(G, \ast)$ and $(H, \times)$ be two groups. A function $f$ is a homomorphism iff

$$
(\forall a, b \in G) \, f(a \ast b) = f(a) \times f(b)
$$

## Properties

### Preservation of identity

Homomorphism has identity preserved, meaning

$$
f(e_G) = e_H
$$

where $e_G$ and $e_H$ are the identity of $G$ and $H$ repsectively.

_[Proof]_ As

$$
\begin{gather}
f(e_G) = f(e_G \ast e_G) = f(e_G) \times f(e_G) \\
f(e_G)^{-1} \times f(e_G) = (f(e_G)^{-1} \times f(e_G)) \times f(e_G) \\
e_H = f(e_G)
\end{gather}
$$

### Preservation of inverse

Also, the inverse is also preserved, meaning

$$
f(a^{-1}) = f(a)^{-1}
$$

_[Proof]_ As

$$
\begin{gather}
f(e_G) = f(a \ast a^{-1}) = f(a) \times f(a^{-1}) = e_H \\
f(e_G) = f(a^{-1} \ast a) = f(a^{-1}) \times f(a) = e_H
\end{gather}
$$

$f(a^{-1})$ is the inverse of $f(a)$ in $H$, i.e. $f(a^{-1}) = f(a)^{-1}$.

### Composition is homomorphism

Let $f: G_1 \to G_2$ and $g: G_2 \to G_3$ be homomorphisms, then for $a, b \in G_1$,

$$
\begin{align*}
(g \circ f)(a \ast_1 b) = g(f(a \ast_1 b)) &= g(f(a) \ast_2 f(b)) \\
&= g(f(a)) \ast_3 g(f(b)) \\
&= (g \circ f)(a) \ast_3 (g \circ f)(b)
\end{align*}
$$

## Image and Kernel

Let $f: G \to H$ be a homomorphism, then the _image_ of $f$ is defined by

$$
\text{im}\, f = f(G) = \set{f(g) \in H : g \in G}
$$

which is same as the _codomain_ of a function.

The _kernel_ of $f$ is defined by

$$
\ker f = f^{-1}(\set{e_H}) = \set{g \in G : f(g) = e_H}
$$

which is the set of elements in $G$ that are mapped to identity of $H$.

Image and Kernel are subgroups of $H$ and $G$ respectively, i.e. $\text{im}\, f \le H$ and $\ker f \le G$

_[Proof]_ For $\text{im}\, f$, as $f(e_G) = e_H$, $e_H \in \text{im}\, f$.
Also, for all $h_1, h_2 \in \text{im}\, f$, there exists $g_1, g_2 \in G$ with $h_i = f(g_i)$. Hence,

$$
f(g_1 \ast g_2^{-1}) = f(g_1) \times f(g_2^{-1}) = h_1 \times h_2^{-1} \in \text{im}\, f
$$

For $\ker f$, $e_G \in \ker f$ by the preservation of identity. For all $g_1, g_2 \in \ker f$, i.e. $f(g_1) = f(g_2) = e_H$, we have

$$
f(g_1 \ast g_2^{-1}) = f(g_1) \times f(g_2^{-1}) = e_H \times e_H = e_H
$$

Hence, $g_1 \ast g_2^{-1} \in \ker f$.

### Normal subgroup

Also, for any $a \in G$, for all $k \in \ker f$, we have

$$
f(aka^{-1}) = f(a)f(k)f(a^{-1}) = e_H
$$

Hence, $aka^{-1} \in \ker f$ and $\ker f$ is a _normal subgroup_ of $G$.

### Injection via Kernel

A homomorphism $f: G \to H$ is

* injective iff $\ker f = \set{e_G}$

* surjective iff $\text{im}\, f = H$

_[Proof]_ If $\ker f = \set{e_G}$, given $a, b \in G$ such that $f(a) = f(b)$,

$$
f(e_G) = f(a \ast a^{-1}) = f(a) \times f(a^{-1}) = f(b) \times f(a^{-1}) = f(b \ast a^{-1}) = e_H
$$

Hence, $b \ast a^{-1} = e$ and $b = a$.

Conversely, if $f$ is injective, for $k \in \ker f$, $f(k) = e_H = f(e_G) \implies k = e_G$.

## Isomorphisms

Isomorphisms are bijective homomorphisms. Two groups $G$ and $H$ are isomorphic if there exists an isomorphism between them, denoted as $G \cong H$.

Also, the inverse of isomorphism $f^{-1}: H \to G$ is also an isomorphism.

_[Proof]_ As $f$ is bijective, $f^{-1}: H \to G$ exists and is bijective, and

$$
f^{-1}(h_1 \times h_2) = f^{-1}(f(g_1 \ast g_2)) = g_1 \ast g_2 = f^{-1}(h_1) \ast f^{-1}(h_2)
$$

$f^{-1}$ is a bijective homomorphism and therefore an isomorphism.

Isomorphic groups are considered to be "the same", except the elements and operations are being relabeled.

## Endomorphisms and Automorphisms

Endomorphisms are homomorphisms that has the same domain as codomain, meaning it is a mapping to itself.
Automorphisms are isomorphisms that are also endomorphic.

Automorphism can be thought as a symmetry of the group as it is a bijection to itself preserving the structure.
Hence, a set of automorphisms is also a group as it is symmetries of something.

## Examples

### Exponential Map

In Power Series form:

$$
\exp(x) = 1 + x + {x^2 \over 2!} + {x^3 \over 3!} + ...
$$

which has the property

$$
\exp(a + b) = \exp(a)\exp(b)
$$

It is a homomorphism from $(\mathbb{R}, +)$ to $(\mathbb{R}^{\ast}, \times)$, but not an isomorphism as it is not surjective.
However, it is an isomorphism between $(\mathbb{R}, +)$ and $(\mathbb{R}\_{> 0}, \times)$, and the inverse is the logarithmic map $\log(x)$.
$\text{im} \exp = \mathbb{R}_{> 0}$ and $\ker \exp = \set{0}$.

### Determinants

In linear algebra, using 2-by-2 matrices as example, we have

$$
\det(A) = ad - bc
$$

which has the property

$$
\det(AB) = \det(A) \det(B)
$$

It is a homomorphism from $(\text{GL}\_n(\mathbb{R}), \times)$ to $(\mathbb{R}^{\ast}, \times)$. $\ker \det = \text{SL}_n(\mathbb{R})$.

### Integers modulo m

In number theory, using $(\mathbb{Z}/5\mathbb{Z})^\times$ as example, it possesses a primitive root of unity $g$ where

$$
(\mathbb{Z}/5\mathbb{Z})^\times = \set{ g^n : n \in \mathbb{Z}/4\mathbb{Z} }
$$

meaning every elements can be represented by some powers of $g$. We also have

$$
g^{a + b} = (g^a)(g^b)
$$

Therefore, it is a homomorphism from $(\mathbb{Z}/4\mathbb{Z}, +)$ to $((\mathbb{Z}/5\mathbb{Z})^\times, \times)$.

On the other hand, let $f(a) = 2a$, then $f$ is an automorphism of $(\mathbb{Z}/5\mathbb{Z}, +)$ with inverse $f^{-1}(a) = 3a$.

## References

* [Dexter Chua _Part IA - Groups_, 2014 - Chapter 1.2](https://dec41.user.srcf.net/notes/IA\_M/groups.pdf)
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 1](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
