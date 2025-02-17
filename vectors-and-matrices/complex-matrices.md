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
> For a Hermitian matrix $\mathsf{A}$ and for all complex vectors $\mathbf{x}$, the number $\mathsf{x}^\dagger \mathsf{A} \mathsf{x}$ is real.
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
> Every eigenvalue of a Hermitian matrix $\mathsf{A}$  is real.
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
> The eigenvectors of a Hermitian matrix $\mathsf{A}$ corresponding to different eigenvalues are orthogonal.
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

> *Property.*{: .prop}
> Lengths (inner products) are preserved by unitary matrix $\mathsf{U}$.
>
> *Proof.*{: .prf}
>
> $$
  (\mathsf{Ux})^\dagger (\mathsf{Uy}) = \mathsf{x^\dagger U^\dagger U y} = \mathsf{x^\dagger y}
  $$
>
> Hence, $\Vert \mathsf{U}\mathbf{x} \Vert^2 = \mathsf{(Ux)^\dagger (Ux)} = \mathsf{x^\dagger x} = \Vert \mathbf{x} \Vert^2$.

> *Property.*{: .prop}
> Every eigenvalue of a unitary matrix $\mathsf{U}$ has unit modulus.
>
> *Proof.*{: .prf}
>
> Suppose $\mathsf{U}\mathbf{x} = \lambda \mathbf{x}$, we have $\Vert \mathsf{U}\mathbf{x} \Vert = \Vert \mathbf{x} \Vert = \Vert \lambda \mathbf{x} \Vert$, hence $\vert \lambda \vert = 1$.

> *Property.*{: .prop}
> The eigenvectors of an unitary matrix $\mathsf{U}$ corresponding to different eigenvalues are orthogonal.
>
> *Proof.*{: .prf}
>
> Suppose $\mathsf{U}\mathsf{x}\_1 = \lambda\_1\mathsf{x}\_1$ and $\mathsf{U}\mathsf{x}\_2 = \lambda\_2\mathsf{x}\_2$. We have
>
> $$
  \mathsf{x}_1^\dagger \mathsf{x}_2 = (\mathsf{U} \mathsf{x}_1)^\dagger (\mathsf{U} \mathsf{x}_2) = \lambda_1^\ast \lambda_2 \mathsf{x}_1^\dagger \mathsf{x}_2
  $$
>
> As $\vert \lambda\_1 \vert^2 = \lambda\_1^\ast \lambda\_1 = 1$, $\lambda\_1^\ast \lambda\_2 \not= 1$ otherwise $\lambda\_1 = \lambda\_2$.
> Hence, we can only have $\mathsf{x}\_1^\dagger \mathsf{x}\_2 = 0$.

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

## Cayley-Hamilton Theorem

> *Theorem.*{: .thm}
> **[Cayley-Hamilton Theorem]**
> Every complex square matrix satisfies its own characteristic equation, i.e.
>
> $$
  p_{\mathsf{A}}(\mathsf{A}) = 0
  $$

## Forms

> *Definition.*{: .def}
> A map $\mathcal{F}: \mathbb{F}^n \to \mathbb{F}$, where
>
> $$
  \mathcal{F}(\mathbf{x}) = \mathsf{x}^\dagger\mathsf{A}\mathsf{x} = \sum_{i=1}^n \sum_{j=1}^n x_i^\ast A_{ij} x_j
  $$
>
> is called a sesquilinear **form** and $\mathsf{A}$ is called its coefficient matrix.

> *Definition.*{: .def}
> If $\mathsf{A}$ is an Hermitian matrix, the map $\mathcal{F}: \mathbb{C}^n \to \mathbb{C}$ is referred to as an **Hermitian form** on $\mathbb{C}^n$.

> *Definition.*{: .def}
> If $\mathsf{A}$ is a real symmetric matrix, the map $\mathcal{F}: \mathbb{R}^n \to \mathbb{R}$ is referred to as a **quadratic form** on $\mathbb{R}^n$.

> *Proposition.*{: .prop}
> As the coefficient matrix $\mathsf{H}$ of a Hermitian form can be factorized as
>
> $$
  \mathsf{H} = \mathsf{U \Lambda U^\dagger}
  $$
>
> Let $\mathsf{x}' = \mathsf{U^\dagger x}$, we have
>
> $$
  \mathcal{F}(\mathbf{x}) = \mathsf{x^\dagger U \Lambda U^\dagger x} = \mathsf{x'^\dagger \Lambda x'} = \sum_{i=1}^n \lambda_i \vert x_i' \vert^2
  $$
>
> By transforming to a basis of orthonormal eigenvectors, the form is simplified and the orthonormal basis vectors are called **principal axes**.

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 3, 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Gilbert Strang _Linear Algebra and Its Applications_, 2006 - Chapter 5
