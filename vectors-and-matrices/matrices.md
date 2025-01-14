---
layout: base
title: Matrices &#124; Vectors and Matrices
---

# Matrices
{: .page-title}

As described in [Linear Maps](linear-maps.md), matrices can be used to represent linear transformations.
Just like [vectors](vectors.md), we can do all sorts of algebraic operations on matrices in a way that matches the properties of linear maps.

## Addition

> *Definition.*{: .def}
> Let $\mathcal{A}: V \to W$ and $\mathcal{B}: V \to W$ be linear maps.
> The linear map $(\mathcal{A} + \mathcal{B}): V \to W$ is defined by
>
> $$
  (\mathcal{A} + \mathcal{B})(\mathbf{x}) = \mathcal{A}(\mathbf{x}) + \mathcal{B}(\mathbf{x})
  $$

> *Proposition.*{: .prop}
> Suppose that $\mathsf{A} = \Set{A_{ij}}, \mathsf{B} = \Set{B_{ij}}$ and $(\mathsf{A} + \mathsf{B}) = \Set{(A + B)_{ij}}$
> are the $m \times n$ matrices associated with the maps, then
>
> $$
  \begin{align*}
  (\mathsf{A} + \mathsf{B})_{ij} x_j
  &= ((\mathcal{A} + \mathcal{B})(\mathbf{x}))_i \\
  &= (\mathcal{A}(\mathbf{x}))_i + (\mathcal{B}(\mathbf{x}))_i \\
  &= (\mathsf{A}_{ij} + \mathsf{B}_{ij}) x_j
  \end{align*}
  $$
>
> Hence, for consistency, matrix addition must be defined by
>
> $$
  \mathsf{A} + \mathsf{B} = \Set{\mathsf{A}_{ij} + \mathsf{B}_{ij}}
  $$

## Multiplication by Scalar

> *Definition.*{: .def}
> Let $\mathcal{A}: V \to W$ be a linear map.
> For a given $\lambda \in \mathbb{F}$, the linear map $(\lambda\mathcal{A}): V \to W$ is defined by
>
> $$
  (\lambda\mathcal{A})(\mathbf{x}) = \lambda(\mathcal{A}(\mathbf{x}))
  $$

> *Proposition.*{: .prop}
> Suppose $\mathcal{A} = \Set{A_{ij}}$ be the matrix of $\mathcal{A}$, then
>
> $$
  \begin{align*}
  ((\lambda\mathcal{A})(\mathbf{x}))_i
  &= (\lambda\mathsf{A}(\mathbf{x}))_i \\
  &= \lambda(A_{ij} x_j) \\
  &= (\lambda A_{ij}) x_j
  \end{align*}
  $$
>
> Hence, for consistency the matrix of $\lambda\mathcal{A}$ must be
>
> $$
  \lambda\mathsf{A} = \Set{\lambda A_{ij}}
  $$

We can see that with the above definitions, after some checks, matrix forms a vector space.

## Matrix Multiplication

> *Proposition.*{: .prop}
> Let $\mathcal{S}: U \to V$ and $\mathcal{T}: V \to W$ be linear maps,
> in which $\mathsf{S} = \Set{S_{ij}}$ and $\mathsf{T} = \Set{T_{ij}}$ be the associated matrices.
>
> Consider the composite map $\mathcal{W} = \mathcal{T}\mathcal{S}: U \to W$ with associated matrix $\mathsf{W} = \Set{W_{ij}}$.
> If
>
> $$
  \mathbf{x}' = \mathcal{S}(\mathbf{x}) \quad \text{and} \quad \mathbf{x}'' = \mathcal{T}(\mathbf{x}')
  $$
>
> then
>
> $$
  x_i'' = T_{ij}(S_{jk}x_k) = (T_{ij}S_{jk}) x_k \quad \text{and} \quad x_i'' = W_{ik} x_k
  $$
>
> Hence, for consistency,
>
> $$
  W_{ik} = T_{ij}S_{jk}
  $$

> *Property.*{: .prop}
> Matrix multiplication is _associative_, i.e.
>
> $$
  \mathsf{A}(\mathsf{B}\mathsf{C}) = (\mathsf{A}\mathsf{B})\mathsf{C}
  $$
>
> *Proof.*{: .prf}
>
> In terms of suffix notation,
>
> $$
  \begin{align*}
  (\mathsf{A}(\mathsf{B}\mathsf{C}))_{ij} &= A_{ik}(\mathsf{B}\mathsf{C})_{kj} = A_{ik}B_{kl}C_{lj} \\
  ((\mathsf{A}\mathsf{B})\mathsf{C})_{ij} &= (\mathsf{A}\mathsf{B})_{il}C_{lj} = A_{ik}B_{kl}C_{lj}
  \end{align*}
  $$

> *Property.*{: .prop}
> Matrix multiplication in general is _not commutative_.

## Transpose

> *Definition.*{: .def}
> Let $\mathsf{A} = \Set{A_{ij}}$ be a $m \times n$ matrix.
> The **transpose** $\mathsf{A}^\intercal$ of $\mathsf{A}$ is defined to be a $n \times m$ matrix with
>
> $$
  (\mathsf{A}^\intercal)_{ij} = (\mathsf{A})_{ji} = A_{ji}
  $$

> *Property.*{: .prop}
> By definition,
>
> $$
  (\mathsf{A}^\intercal)^\intercal = \mathsf{A}
  $$

> *Property.*{: .prop}
> Let $\mathsf{A} = \Set{A_{ij}}$ and $\mathsf{B} = \Set{B_{ij}}$ be matrices such that $\mathsf{AB}$ exists, then
>
> $$
  (\mathsf{A}\mathsf{B})^\intercal = \mathsf{B}^\intercal \mathsf{A}^\intercal
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  ((\mathsf{A}\mathsf{B})^\intercal)_{ik} &= (\mathsf{A}\mathsf{B})_{ki} \\
  &= A_{kj} B_{ji} \\
  &= (\mathsf{B}^\intercal)_{ij} (\mathsf{A}^\intercal)_{jk} \\
  &= (\mathsf{B}^\intercal \mathsf{A}^\intercal)_{ik}
  \end{align*}
  $$

## Hermitian Conjugate

> *Definition.*{: .def}
> Let $\mathsf{A} = \Set{A_{ij}}$ be a matrix, with $A_{ij} \in \mathbb{C}$.
> The **Hermitian conjugate** or **conjugate transpose** or **adjoint** is defined to be
>
> $$
  \mathsf{A}^\dagger = (\mathsf{A}^\intercal)^\ast = (\mathsf{A}^\ast)^\intercal
  $$

> *Property.*{: .prop}
> Similarly to transposes,
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

## Symmetric Matrices

> *Definition.*{: .def}
> A square $n \times n$ matrix $\mathsf{A} = \Set{A_{ij}}$ is **symmetric** if
>
> $$
  \mathsf{A} = \mathsf{A}^\intercal \iff A_{ij} = A_{ji}
  $$

> *Definition.*{: .def}
> A square $n \times n$ matrix $\mathsf{A} = \Set{A_{ij}}$ is **antisymmetric** if
>
> $$
  \mathsf{A} = -\mathsf{A}^\intercal \iff A_{ij} = -A_{ji}
  $$

> *Property.*{: .prop}
> For an antisymmetric matrix, as $A_{11} = -A_{11}, A_{22} = -A_{22}, ...$, the diagonal elements have to be zero, i.e.
>
> $$
  A_{11} = A_{22} = ... = A_{nn} = 0
  $$

## Hermitian Matrices

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

## Trace

> *Definition.*{: .def}
> The **trace** of a square $n \times n$ matrix $\mathsf{A} = \Set{A_{ij}}$ is equal to the sum of the diagonal elements, i.e.
>
> $$
  Tr(\mathsf{A}) = A_{ii}
  $$

> *Proposition.*{: .prop}
> Let $\mathsf{B} = \Set{B_{ij}}$ be $m \times n$ matrix and $\mathsf{C} = \Set{C_{ij}}$ be $n \times m$ matrix,
> though $\mathsf{BC}$ and $\mathsf{CB}$ are not necessary equal (or even of different sizes), however
>
> $$
  Tr(\mathsf{BC}) = (\mathsf{BC})_{ii} = B_{ij}C_{ji} = C_{ji}B_{ij} = (\mathsf{CB})_{jj} = Tr(\mathsf{CB})
  $$

## Identity Matrix

> *Definition.*{: .def}
> The **unit matrix** or **identity matrix** is defined to be
>
> $$
  \mathsf{I} = \begin{pmatrix}
  1 & 0 & \dots & 0 \\
  0 & 1 & \dots & 0 \\
  \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \dots & 1 \\
  \end{pmatrix} = \Set{\delta_{ij}}
  $$

> *Property.*{: .prop}
> Let $\mathsf{A} = \Set{A_{ij}}$ be a $n \times n$ matrix, then
>
> $$
  \begin{align*}
  (\mathsf{IA})_{ij} &= \delta_{ik}A_{kj} = A_{ij} \\
  (\mathsf{AI})_{ij} &= A_{ik}\delta_{kj} = A_{ij}
  \end{align*}
  $$
>
> i.e.
>
> $$
  \mathsf{IA} = \mathsf{AI} = \mathsf{A}
  $$

## Decomposition of Square Matrix

> *Definition.*{: .def}
> An **isotropic matrix** is a scalar multiple of the identity matrix.

> *Proposition.*{: .prop}
> A $n \times n$ square matrix $\mathsf{B}$ can be decomposed into _isotropic_, _symmetric trace-free_ and _antisymmetric_ parts.
>
> *Proof.*{: .prf}
>
> We construct the matrices $\mathsf{A}$ and $\mathsf{S}$ from $\mathsf{B}$ as
>
> $$
  \mathsf{A} = {1 \over 2} \left( \mathsf{B} - \mathsf{B}^\intercal \right)
  \quad \text{and} \quad
  \mathsf{S} = {1 \over 2} \left( \mathsf{B} + \mathsf{B}^\intercal \right)
  $$
>
> We have
>
> $$
  \begin{align*}
  \mathsf{A}^\intercal &= {1 \over 2} \left( \mathsf{B}^\intercal - \mathsf{B} \right) = -\mathsf{A} \\
  \mathsf{S}^\intercal &= {1 \over 2} \left( \mathsf{B}^\intercal + \mathsf{B} \right) = \mathsf{S} \\
  \mathsf{A} + \mathsf{S} &= {1 \over 2} \left( \mathsf{B} - \mathsf{B}^\intercal + \mathsf{B} + \mathsf{B}^\intercal \right) = \mathsf{B} \\
  \end{align*}
  $$
>
> Therefore, $\mathsf{S}$ is symmetric and $\mathsf{A}$ is antisymmetric.
>
> Let $n\sigma = Tr(\mathsf{S})$, so $\sigma = {1 \over n}S_{ii}$, and write
>
> $$
  \mathsf{E} = \mathsf{S} - \sigma\mathsf{I}
  $$
>
> Then $\mathsf{E}$ is a trace-free symmetric tensor.
>
> Hence,
>
> $$
  \mathsf{B} = \sigma\mathsf{I} + \mathsf{E} + \mathsf{A}
  $$
>
> represents the decomposition of a square matrix into isotropic, symmetric trace-free and antisymmetric parts.

## Inverse

> *Definition.*{: .def}
> Let $\mathsf{A}$ be a $m \times n$ matrix.
> A $n \times m$ matrix $\mathsf{B}$ is a **left inverse** of $\mathsf{A}$ if $\mathsf{BA} = \mathsf{I}$ ($n \times n$).
> A $n \times m$ matrix $\mathsf{C}$ is a **right inverse** of $\mathsf{A}$ if $\mathsf{AC} = \mathsf{I}$ ($m \times m$).

> *Property.*{: .prop}
> If both the left inverse $\mathsf{B}$ and right inverse $\mathsf{C}$ exist, then
>
> $$
  \mathsf{B} = \mathsf{BI} = \mathsf{BAC} = \mathsf{IC} = \mathsf{C}
  $$

> *Definition.*{: .def}
> Let $\mathsf{A}$ be a $n \times n$ matrix. $\mathsf{A}$ is **invertible** if there exists an unique matrix $\mathsf{A}^{-1}$ such that
>
> $$
  \mathsf{A}^{-1}\mathsf{A} = \mathsf{A}\mathsf{A}^{-1} = \mathsf{I}
  $$

> *Property.*{: .prop}
> From the above, the inverse of $\mathsf{A}^{-1}$ is $\mathsf{A}$, i.e.
>
> $$
  (\mathsf{A}^{-1})^{-1} = \mathsf{A}
  $$

> *Property.*{: .prop}
> Let $\mathsf{A}$ and $\mathsf{B}$ be matrices, we have
>
> $$
  \mathsf{AB}^{-1} = \mathsf{B}^{-1}\mathsf{A}^{-1}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \mathsf{B}^{-1}\mathsf{A}^{-1}(\mathsf{A}\mathsf{B}) = \mathsf{B}^{-1}(\mathsf{A}^{-1}(\mathsf{A})\mathsf{B} = \mathsf{B}^{-1}\mathsf{B} = \mathsf{I} \\
  (\mathsf{A}\mathsf{B})\mathsf{B}^{-1}\mathsf{A}^{-1} = \mathsf{A}(\mathsf{B}\mathsf{B}^{-1})\mathsf{A}^{-1} = \mathsf{A}\mathsf{A}^{-1} = \mathsf{I}
  \end{align*}
  $$

## Orthogonal Matrices

> *Definition.*{: .def}
> A $n \times n$ real square matrix $\mathsf{A} = \Set{A_{ij}}$ is **orthogonal** if
>
> $$
  \mathsf{A}\mathsf{A}^\intercal = \mathsf{I} = \mathsf{A}^\intercal\mathsf{A}
  $$
>
> i.e. if $\mathsf{A}$ is invertible and $\mathsf{A}^{-1} = \mathsf{A}^\intercal$.

> *Property.*{: .prop}
> The rows of orthogonal matrix form an orthonormal set, so as the columns.
>
> *Proof.*{: .prf}
>
> Consider
>
> $$
  (\mathsf{A}\mathsf{A}^\intercal)_{ij} = \mathsf{A}_{ik}(\mathsf{A}^\intercal)_{kj} = A_{ik}A_{jk} = \delta_{ij}
  $$
>
> The dot products of the $i$-th row with other rows are $0$ and the dot product with itself is $1$.
> Therefore, the rows of $\mathsf{A}$ form an orthonormal set.
>
> Similarly, since $\mathsf{A}^\intercal \mathsf{A} = \mathsf{I}$, the columns also form an orthonormal set.

> *Property.*{: .prop}
> Suppose the map $\mathcal{A}$ has a matrix $\mathsf{A}$ with repsect to an orthonormal basis $\Set{\mathbf{e}_i}$.
> If $\mathsf{A}$ is orthogonal, then the image of $\Set{\mathbf{e}_i}$ is also an orthonormal set
> (which may be right-handed or left handed depending on the sign of $\det \mathsf{A}$).

> *Property.*{: .prop}
> Suppose the map is represented by an orthogonal matrix with respect to an orthonormal basis, a real scalar product is preserved, i.e.
>
> $$
  \mathbf{x}' \cdot \mathbf{y}' = \mathbf{x} \cdot \mathbf{y}
  $$
>
> *Proof.*{: .prf}
>
> With an orthonormal basis,
>
> $$
  \mathbf{x} \cdot \mathbf{y} = \mathsf{x}^\intercal \mathsf{y}
  $$
>
> Hence,
>
> $$
  \begin{align*}
  \mathbf{x}' \cdot \mathbf{y}' &= (\mathsf{x}')^\intercal \mathsf{y}' \\
  &= (\mathsf{x}^\intercal \mathsf{A}^\intercal) (\mathsf{A} \mathsf{y}) \\
  &= \mathsf{x}^\intercal \mathsf{I} \mathsf{y} \\
  &= \mathsf{x}^\intercal \mathsf{y} \\
  &= \mathbf{x} \cdot \mathbf{y} \\
  \end{align*}
  $$

> *Property.*{: .prop}
> Suppose the map is represented by an orthogonal matrix with respect to an orthonormal basis, then the map is an _isometry_, i.e.
> distances are preserved by the mapping.
>
> *Proof.*{: .prf}
>
> As the real scalar product is preserved, we have
>
> $$
  \begin{align*}
  \vert \mathbf{x}' - \mathbf{y}' \vert^2 &= (\mathbf{x}' - \mathbf{y}') \cdot (\mathbf{x}' - \mathbf{y}') \\
  &= (\mathbf{x} - \mathbf{y}) \cdot (\mathbf{x} - \mathbf{y}) \\
  &= \vert \mathbf{x} - \mathbf{y} \vert^2
  \end{align*}
  $$

## Unitary Matrices

> *Definition.*{: .def}
> A complex square matrix $\mathsf{U}$ is said to be **unitary** if its Hermitian conjugate is equal to its inverse, i.e.
>
> $$
  \mathsf{U}^\dagger = \mathsf{U}^{-1}
  $$

Unitary matrices are to complex matrices what orthonormal matrices are to real matrices.

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 3](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
