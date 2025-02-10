---
layout: base
title: Complex Matrices &#124; Vectors and Matrices
---

# Complex Matrices
{: .page-title}

Complex matrices share lots of the same definitions as real matrices.
However, due to the fact that the [scalar product aximons](spanning-sets-and-bases.md#complex-space-scalar-product-axioms) are different,
in order to preserve that in complex matrices, we have to change some of the definitions.

## Conjugate Transpose

> *Definition.*{: .def}
> Let $\mathsf{A} = \Set{A_{ij}}$ be a matrix, with $A_{ij} \in \mathbb{C}$.
> The **Hermitian conjugate** or **conjugate transpose** or **adjoint** is defined to be
>
> $$
  \mathsf{A}^\dagger = (\mathsf{A}^\intercal)^\ast = (\mathsf{A}^\ast)^\intercal
  $$

> *Property.*{: .prop}
> Similar to transpose of real matrices, we have
>
> $$
  \mathsf{A}^{\dagger\dagger} = \mathsf{A}
  $$

> *Property.*{: .prop}
> Let $\mathsf{A} = \Set{A_{ij}}$ and $\mathsf{B} = \Set{B_{ij}}$ be matrices such that $\mathsf{AB}$ exists, then
>
> $$
  (\mathsf{A}\mathsf{B})^\dagger = \mathsf{B}^\dagger \mathsf{A}^\dagger
  $$

## Hermitian Matrices

Hermitian matrices are to complex matrices what symmetric matrices are to real matrices.

> *Definition.*{: .def}
> A square $n \times n$ complex matrix $\mathsf{A} = \Set{A_{ij}}$ is **Hermitian** if
>
> $$
  \mathsf{A} = \mathsf{A}^\dagger \iff A_{ij} = A_{ji}^\ast
  $$

> *Definition.*{: .def}
> A square $n \times n$ complex matrix $\mathsf{A} = \Set{A_{ij}}$ is **skew-Hermitian** if
>
> $$
  \mathsf{A} = -\mathsf{A}^\dagger \iff A_{ij} = -A_{ji}^\ast
  $$

> *Property.*{: .prop}
> For Hermitian and skew-Hermitian matrices, the diagonal elements are real and pure imaginary respectively.

## Unitary Matrices

Unitary matrices are to complex matrices what orthonormal matrices are to real matrices.

> *Definition.*{: .def}
> A complex square matrix $\mathsf{U}$ is said to be **unitary** if its Hermitian conjugate is equal to its inverse, i.e.
>
> $$
  \mathsf{U}^\dagger = \mathsf{U}^{-1}
  $$

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 3](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
