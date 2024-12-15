---
layout: base
title: Matrix Groups &#124; Groups
---

# Matrix Groups
{: .page-title}

Consider $M_{n \times n}(F)$, the set of $n \times n$ matrices over $F = \mathbb{R}, \mathbb{C}$.
Matrix multiplication is associative as they are some sort of linear transformation, but generally not commutative.
If $I$ is the identity, the matrices have inverses iff they have non-zero determinants.
Hence, we have the following definition of a group containing these matrices:

## General Linear Group

> *Definition.*{: .def}
> The **general linear group** is defined by
>
> $$
  \text{GL}_n(F) = \set{A \in M_{n \times n}(F) : \det(A) \not = 0}
  $$

## Special Linear Group

> *Lemma.*{: .lem}
> $\det: \text{GL}_n(F) \to F^\ast$ is a surjective homomorphism.
>
> *Proof.*{: .prf}
>
> As $\det AB = \det A \det B$, $\det$ is a group homomorphism.
> For any $x \in F^\ast$,
>
> $$
  \det \begin{pmatrix}
  x \\
   & 1 & 0 \\
   & 0 & \ddots \\
   &  &  & 1 \\
  \end{pmatrix} = x
  $$
>
> so $\det$ is surjective.

> *Definition.*{: .def}
> The **special linear group** is the kernel of $\det$, i.e.
>
> $$
  \text{SL}_n(F) = \set{A \in \text{GL}_n(F) : \det(A) = 1}
  $$

> *Lemma.*{: .lem}
> The special linear group is a normal subgroup of general linear group, i.e. $\text{SL}_n(F) \trianglelefteq \text{GL}_n(F)$.
>
> *Proof.*{: .prf}
>
> Algebrically, kernel is always a normal subgroup.

## Orthogonal Group

Recall the properties of transpose $A^\intercal$ of $A$,

+ $(AB)^\intercal = B^\intercal A^\intercal$

+ $(A^{-1})^\intercal = (A^\intercal)^{-1}$

+ $A^\intercal A = I \iff A A^\intercal = I \iff A^\intercal = A^{-1}$

+ $\det A^\intercal = \det A$

> *Definition.*{: .def}
> The **orthogonal group** is defined by
>
> $$
  \text{O}_n = \set{A \in \text{GL}_n(\mathbb{R}) : A^\intercal A = I}
  $$
