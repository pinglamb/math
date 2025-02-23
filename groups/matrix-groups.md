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

> *Proposition.*{: .prop}
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

> *Proposition.*{: .prop}
> The special linear group is a normal subgroup of general linear group, i.e. $\text{SL}_n(F) \trianglelefteq \text{GL}_n(F)$.
>
> *Proof.*{: .prf}
>
> Algebraically, kernel is always a normal subgroup.

> *Proposition.*{: .prop}
> $\text{GL}\_n(\mathbb{R}) / \text{SL}\_n(\mathbb{R}) \cong \mathbb{R}^\ast$.
>
> *Proof.*{: .prf}
>
> By Isomorphism Theorem, $\text{GL}\_n(\mathbb{R}) / \text{SL}\_n(\mathbb{R})$ is isomorphic to $\text{im}(\det) = \mathbb{R}^\ast$.

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

> *Proposition.*{: .prop}
> Orthogonal group is a group with respect to matrix multiplication.
>
> *Proof.*{: .prf}
>
> For any $A, B \in \text{O}_n$, $(AB)^\intercal(AB) = B^\intercal A^\intercal A B = I$, so $AB \in \text{O}_n$ and it is closed under matrix multiplication.
> $I$ is the identity element.
> For $A \in \text{O}_n$, $(A^\intercal)^\intercal A^\intercal = A A^\intercal = I$, so $A^\intercal \in \text{O}_n$ and $A^{-1} = A^\intercal$ is the inverse.
> Matrix multiplication is associative.

> *Proposition.*{: .prop}
> $\det: \text{O}_n \to \set{\pm 1}$ is a surjective homomorphism.
>
> *Proof.*{: .prf}
>
> For any $A \in \text{O}_n$, $\det A \det A^\intercal = (\det A)^2 = \det I = 1$, so $\det A = \pm 1$ and it is a homomorphism.
>
> Similarily,
>
> $$
  \det \begin{pmatrix}
  -1 \\
  & 1 & 0 \\
  & 0 & \ddots \\
  &  &  & 1 \\
  \end{pmatrix} = -1
  $$
>
> so it is surjective.

> *Definition.*{: .def}
> The **special orthogonal group** is the kernel of $\det: \text{O}_n \to \set{\pm 1}$, i.e.
>
> $$
  \text{SO}_n = \set{A \in \text{O}_n : \det(A) = 1}
  $$

The geometric property of orthogonal matrices is the following:

> *Proposition.*{: .prop}
> Orthogonal matrices are isometries, i.e.
>
> 1. $A$ preserves dot product, $(Ax)^\intercal (Ay) = x^\intercal y$.
>
> 2. $A$ preserves length, $\vert Ax \vert = \vert x \vert$.
>
> *Proof.*{: .prf}
>
> $$
  (Ax)^\intercal (Ay) = x^\intercal A^\intercal A y = x^\intercal I y = x^\intercal y
  $$
>
> $$
  \vert Ax \vert^2 = (Ax)^\intercal (Ax) = x^\intercal x = \vert x \vert
  $$

## Unitary Group

Unitary group is the variation of orthogonal group over complex numbers, base on the Hermitian conjugate $(A^\dagger)\_{ij} = (A^\ast)\_{ji}$.
We still have

+ $(AB)^\dagger = B^\dagger A^\dagger$

+ $(A^{-1})^\dagger = (A^\dagger)^{-1}$

+ $A^\dagger A = I \iff A A^\dagger = I \iff A^\dagger = A^{-1}$

+ $\det A^\dagger = (\det A)^\ast$

> *Definition.*{: .def}
> The **unitary group** is defined by
>
> $$
  \text{U}_n = \set{A \in \text{GL}_n(\mathbb{C}) : A^\dagger A = I}
  $$

With similar proof as orthogonal group, $\text{U}_n$ is a group.

Let $S^1 = \set{z \in \mathbb{C} : \vert z \vert = 1}$, which is the unit circle in complex plane and forms a group under complex multiplication.
We have

> *Lemma.*{: .lem}
> $\det: \text{U}_n \to S^1$ is a surjective homomorphism.
>
> *Proof.*{: .prf}
>
> For any $A \in \text{O}_n$, $\det A \det A^\dagger = \vert \det A \vert^2 = 1$, so $\det A \in S^1 $ and it is a homomorphism.
>
> Similarily, given $z \in S^1$,
>
> $$
  \det \begin{pmatrix}
  z \\
  & 1 & 0 \\
  & 0 & \ddots \\
  &  &  & 1 \\
  \end{pmatrix} = z
  $$
>
> so it is surjective.

> *Definition.*{: .def}
> The **special unitary group** is the kernel of $\det: \text{U}_n \to S^1$, i.e.
>
> $$
  \text{SU}_n = \set{A \in \text{U}_n : \det(A) = 1}
  $$

Equivalently, unitary matrices preserve the complex dot product $x^\dagger y = x_1^\ast y_1 + x_2^\ast y_2 + ... + x_n^\ast y_n$.

## References

* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 4](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
