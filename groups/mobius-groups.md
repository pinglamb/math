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

The kernel of $\theta$ is

$$
\ker \theta = \Set{A : z = {az + b \over cz + d}} = \Set{\lambda I : \lambda \in \mathbb{C},  \lambda \not= 0}
$$

> *Proposition.*{: .prop}
> As $f\_A = f\_B$ iff $B = \lambda A$, we also have $\theta: \text{SL}\_2(\mathbb{C}) \to M$ an surjective group homomorphism,
> with kernel $\Set{\pm I}$ and hence $M$ is isomorphic to the quotient group $\text{SL}\_2/\Set{\pm I}$.

## Conjugacy

## Acting on $C\_\infty$

## References

* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 4](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
* Alan F. Beardon Algebra and Geometry, 2005 - Chapter 13
