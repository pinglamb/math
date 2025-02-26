---
layout: base
title: Möbius Groups &#124; Groups
---

# Möbius Groups
{: .page-title}

The definition and properties of [Möbius Transformations](../vectors-and-matrices/mobius-transformations.md) are discussed elsewhere and we will focus our study from group perspectives.

> *Proposition.*{: .prop}
> The Möbius maps form a group $M$ under composition.
>
> *Proof.*{: .prf}
>
> 0\. Möbius maps are [closed under composition](../vectors-and-matrices/mobius-transformations.md#composition).
>
> 1\. The identity is
>
> $$
  1_{\mathbb{C}_\infty}(z) = {1z + 0 \over 0z + 1}
  $$
>
> 2\. The [inverse](../vectors-and-matrices/mobius-transformations.md#inverse) of $f(z)$ is
>
> $$
  f^{-1}(z) = {dz - b \over -cz + a}
  $$
>
> 3\. Composition of functions is always associative.

## Matrix Representation

> *Proposition.*{: .prop}
> The map $\theta: \text{GL}\_2(\mathbb{C}) \to M$ where
>
> $$
  A = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \mapsto f_{A} \quad \text{where} \quad f_{A}(z) = {az + b \over cz + d}
  $$
>
> is a surjective group homomorphism.
>
> *Proof.*{: .prf}
>
> $\theta$ lands in $M$ as $A \in \text{GL}\_2(\mathbb{C})$ gives $ad - bc \not= 0$, which also shows surjectivity.
>
> From the composition formula and matrix multiplication,
>
> $$
  \theta(A_2)\theta(A_1)(z) = \theta(A_2A_1)(z)
  $$
>
> and hence $\theta$ is a surjective group homomorphism.

> *Proposition.*{: .prop}
> The kernel of $\theta$ is
>
> $$
  \ker \theta = \Set{A : z = {az + b \over cz + d}} = \Set{\lambda I : \lambda \in \mathbb{C},  \lambda \not= 0} = Z
  $$

> *Definition.*{: .def}
> The **projective general linear group** is defined by
>
> $$
  \text{PGL}_2(\mathbb{C}) = \text{GL}_2(\mathbb{C}) / Z
  $$
>
> By Isomorphism Theorem, $M \cong \text{PGL}_2(\mathbb{C})$.

> *Proposition.*{: .prop}
> As $f\_A = f\_B$ iff $B = \lambda A$, we also have $\theta: \text{SL}\_2(\mathbb{C}) \to M$ an surjective group homomorphism,
> with kernel $\Set{\pm I}$ and hence $M$ is isomorphic to the quotient group $\text{SL}\_2/\Set{\pm I}$.

> *Definition.*{: .def}
> The **projective special linear group** is defined by
>
> $$
  \text{PSL}_2(\mathbb{C}) = \text{SL}_2(\mathbb{C}) / \Set{\pm I}
  $$
>
> By Isomorphism Theorem, $M \cong \text{PSL}_2(\mathbb{C})$.

## Conjugacy

> *Proposition.*{: .prop}
> Any Möbius map is conjugate to $f(z) = vz$ for some $v \not= 0$, or to $f(z) = z + 1$.
>
> *Proof.*{: .prf}
>
> From the above, $\theta: \text{GL}\_2(\mathbb{C}) \to M$ is a surjective homomorphism.
>
> The conjugacy classes in $\text{GL}\_2(\mathbb{C})$ are
>
> $$
  \begin{align*}
  \begin{pmatrix} \lambda & 0 \\ 0 & \mu \end{pmatrix} \quad &\longmapsto \quad g(z) = {\lambda z + 0 \over 0z + \mu} = {\lambda \over \mu}z \\
  \\
  \begin{pmatrix} \lambda & 0 \\ 0 & \lambda \end{pmatrix} \quad &\longmapsto \quad g(z) = {\lambda z + 0 \over 0z + \lambda} = z \\
  \\
  \begin{pmatrix} \lambda & 1 \\ 0 & \lambda \end{pmatrix} \quad &\longmapsto \quad g(z) = {\lambda z + 1 \over 0z + \lambda} = z + {1 \over \lambda} \\
  \end{align*}
  $$
>
> In fact, $\begin{pmatrix} 1 & {1 \over \lambda} \\\\ 0 & 1 \end{pmatrix}$ is conjugate to $\begin{pmatrix} 1 & 1 \\\\ 0 & 1 \end{pmatrix}$:
>
> $$
  \begin{pmatrix} \lambda & 0 \\ 0 & 1 \end{pmatrix}
  \begin{pmatrix} 1 & {1 \over \lambda} \\ 0 & 1 \end{pmatrix}
  \begin{pmatrix} {1 \over \lambda} & 0 \\ 0 & 1 \end{pmatrix}
  = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \quad \longmapsto \quad g(z) = z + 1
  $$

The property that can be transferred to conjugates is the number of fixed point.
From the above, we can see that $g(z) = vz$ fixes $0$ and $\infty$ and $g(z) = z + 1$ fixes $\infty$ only.
Therefore,

> *Proposition.*{: .prop}
> Every non-identity Möbius map has exactly one or two fixed points.
>
> *Proof.*{: .prf}
>
> For any $g \in M, g \not= 1\_M$, there is $h \in M$ such that $hgh^{-1}(z) = vz$ or $z + 1$.
>
> Suppose $g$ fixes $w$, we have
>
> $$
  g(w) = w \iff hgh^{-1}(h(w)) = h(w)
  $$
>
> so $g$ and $hgh^{-1}$ has the same number of fixed points.
> Hence, $g$ has either exactly $2$ (for $hgh^{-1}(z) = vz$) or exactly $1$ (for $hgh^{-1}(z) = z + 1$) fixed points.

Finally, [any Möbius map with at least three fixed points is the identity](../vectors-and-matrices/mobius-transformations.md#identity-three-fixed-points).

> *Proposition.*{: .prop}
> Let $f$ be a Möbius map fixes $w$, then for any Möbius map $h$, the conjugate $hfh^{-1}$ fixes $h(w)$.
> If otherwise $hfh^{-1}$ fixes $w$, then $f$ fixes $h^{-1}(w)$.
>
> *Proof.*{: .prf}
>
> If $f(w) = w$, $hfh^{-1}(h(w)) = hf(w) = h(w)$.
>
> If $hfh^{-1}(w) = w$, $f(h^{-1}(w)) = h^{-1}(w)$.

## Acting on $C\_\infty$

> *Definition.*{: .def}
> An action of $G$ on $X$ is called **three-transitive** if there is always a $g \in G$ such that for any two triples $x\_1, x\_2, x\_3$ and $y\_1, y\_2, y\_3$ of distinct elements of $X$, $g(x\_i) = y\_i$.
> If this $g$ is unique, the action is called **sharply three-transitive**.

> *Proposition.*{: .prop}
> The Möbius group $M$ acts sharply three-transitively on $C\_\infty$.

## References

* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 4, 5, 7](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
* Alan F. Beardon Algebra and Geometry, 2005 - Chapter 13
