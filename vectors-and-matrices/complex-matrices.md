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

There are three basic properties of Hermitian matrices regarding eigenvalues and eigenvectors, which apply equally well to real symmetric matrices.

> *Property.*{: .prop}
> If $\mathsf{A} = \mathsf{A}^\dagger$, then for all complex vectors $\mathbf{x}$, the number $\mathsf{x}^\dagger \mathsf{A} \mathsf{x}$ is real.
>
> *Proof.*{: .prf}
>
> Consider
>
> $$
  (\mathsf{x}^\dagger \mathsf{A} \mathsf{x})^\dagger = \mathsf{x}^{\dagger} \mathsf{A}^{\dagger} \mathsf{x}^{\dagger\dagger} = \mathsf{x}^\dagger \mathsf{A} \mathsf{x}
  $$
>
> The conjugate transpose of the $1 \times 1$ matrix $\mathsf{x}^\dagger \mathsf{A} \mathsf{x}$ is equal to itself and therefore the number must be real.

> *Property.*{: .prop}
> If $\mathsf{A} = \mathsf{A}^\dagger$, every eigenvalue is real.
>
> *Proof.*{: .prf}
>
> Suppose $\mathsf{A}\mathsf{x} = \lambda \mathsf{x}$. By multiplying both side by $\mathsf{x}^\dagger$, we have
>
> $$
  \mathsf{x}^\dagger \mathsf{A} \mathsf{x} = \lambda \mathsf{x}^\dagger \mathsf{x}
  $$
>
> As $\mathsf{x}^\dagger \mathsf{A} \mathsf{x}$ is real and $\mathsf{x}^\dagger \mathsf{x} = \vert \mathsf{x} \vert^2$ is also real and positive,
>
> $$
  \lambda = { \mathsf{x}^\dagger \mathsf{A} \mathsf{x} \over \mathsf{x}^\dagger \mathsf{x} }
  $$
>
> is real.

> *Property.*{: .prop}
> If $\mathsf{A} = \mathsf{A}^\dagger$, the eigenvectors of $\mathsf{A}$ coming from different eigenvalues are orthogonal to one another.
>
> *Proof.*{: .prf}
>
> Suppose $\mathsf{A}\mathsf{x}\_1 = \lambda\_1\mathsf{x}\_1$ and $\mathsf{A}\mathsf{x}\_2 = \lambda\_2\mathsf{x}\_2$. We have
>
> $$
  \lambda_1 \mathsf{x}_1^\dagger \mathsf{x}_2 = (\lambda_1 \mathsf{x}_1)^\dagger \mathsf{x}_2 = (\mathsf{A}\mathsf{x}_1)^\dagger \mathsf{x}_2 = \mathsf{x}_1^\dagger \mathsf{A}^\dagger \mathsf{x}_2 = \mathsf{x}_1^\dagger (\mathsf{A} \mathsf{x}_2) = \lambda_2 \mathsf{x}_1^\dagger \mathsf{x}_2
  $$
>
> As $\lambda\_1 \not= \lambda\_2$, we have $\mathsf{x}\_1^\dagger \mathsf{x}\_2 = 0$, hence the two eigenvectors are orthogonal.

In fact, the above property is also true for eigenvectors from same eigenvalues, meaning we can always find $n$ orthogonal vectors for a $n \times n$ Hermitian matrix, which are also linearly independent.

## Unitary Matrices

Unitary matrices are to complex matrices what orthonormal matrices are to real matrices.

> *Definition.*{: .def}
> A complex square matrix $\mathsf{U}$ is said to be **unitary** if its Hermitian conjugate is equal to its inverse, i.e.
>
> $$
  \mathsf{U}^\dagger = \mathsf{U}^{-1}
  $$

## Diagonalization of Hermitian Matrices

From the above, for any Hermitian matrix, we can choose $\mathbf{x} / \vert \mathbf{x} \vert$ as the eigenvectors to form the diagonalizing matrix $\mathsf{S}$, which is an unitary matrix.

> *Proposition.*{: .prop}
> For a $n \times n$ Hermitian matrix $\mathsf{H}$, there are always $n$ orthogonal, and therefore linearly independent, eigenvectors that form a orthonormal basis for $\mathbb{C}^n$.
> Hence, it is always diagonalizable by a unitary matrix $\mathsf{U}$, i.e.
>
> $$
  \mathsf{H} = \mathsf{U \Lambda U^\dagger}
  $$
>
> Real symmetric matrices are a special case, where the eigenvalues and eigenvectors being real, and the diagonalizing matrix $\mathsf{Q}$ is orthonormal, i.e.
>
> $$
  \mathsf{A} = \mathsf{Q \Lambda Q^\intercal}
  $$

## Normal Matrices

> *Definition.*{: .def}
> A square matrix $\mathsf{A}$ is **normal** if
>
> $$
  \mathsf{A A^\dagger} = \mathsf{A^\dagger A}
  $$

> *Proposition.*{: .prop}
> Normal matrices have $n$ linearly independent eigenvectors and hence always diagonalizable.
> It means skew-Hermitian matrices and unitary matrices can always be diagonalized as well.

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 3, 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Gilbert Strang _Linear Algebra and Its Applications_, 2006 - Chapter 5
