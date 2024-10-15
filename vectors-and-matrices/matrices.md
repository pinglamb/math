---
layout: base
title: Matrices &#124; Vectors and Matrices
---

# Matrices

As described in [Linear Maps](linear-maps.md), matrices can be used to represent linear transformations.
Just like [vectors](vectors.md), we can do all sorts of algebraic operations on matrices.

## Addition

Let $\mathcal{A}: V \to W$ and $\mathcal{B}: V \to W$ be linear maps.
The linear map $(\mathcal{A} + \mathcal{B}): V \to W$ is defined by

$$
(\mathcal{A} + \mathcal{B})(\mathbf{x}) = \mathcal{A}(\mathbf{x}) + \mathcal{B}(\mathbf{x})
$$

For matrices $\mathsf{A}, \mathsf{B}, \mathsf{A} + \mathsf{B}$ associated with the maps, we have

$$
(\mathsf{A} + \mathsf{B})_{ij} x_j = (\mathsf{A} + \mathsf{B})(\mathbf{x})_i = \mathsf{A}(\mathbf{x})_i + \mathsf{B}(\mathbf{x})_i = (\mathsf{A}_{ij} + \mathsf{B}_{ij}) x_j
$$

Hence,

$$
\mathsf{A} + \mathsf{B} = \Set{\mathsf{A}_{ij} + \mathsf{B}_{ij}}
$$

## Multiplication by Scalar

Let $\mathcal{A}: V \to W$ be a linear map.
For a given $\lambda \in \mathbb{F}$, the linear map $\lambda\mathcal{A}$ is defined by

$$
(\lambda\mathcal{A})(\mathbf{x}) = \lambda(\mathcal{A}(\mathbf{x}))
$$

We have

$$
(\lambda\mathsf{A})_{ij} x_j = (\lambda\mathsf{A})(\mathbf{x})_i = \lambda(\mathsf{A}(\mathbf{x})_i) = \lambda(\mathsf{A}_{ij} x_j) = (\lambda\mathsf{A}_{ij}) x_j

$$

Hence,

$$
\lambda\mathsf{A} = \Set{\lambda\mathsf{A}_{ij}}
$$

We can see that with the above definitions, after some checks, matrix forms a vector space.

### Matrix Multiplication

Let $\mathcal{S}: U \to V$ and $\mathcal{T}: V \to W$ be linear maps.
Consider the composite map $\mathcal{T}\mathcal{S}: U \to W$, we have

$$
(\mathsf{T}\mathsf{S})_{ik} x_k = (\mathcal{T}\mathcal{S})(\mathbf{x})_i = \mathcal{T}(\mathcal{S}(\mathbf{x}))_i = \mathsf{T}_{ij}(\mathsf{S}_{jk} x_k) = (\mathsf{T}_{ij}\mathsf{S}_{jk}) x_k
$$

Hence,

$$
(\mathsf{T}\mathsf{S})_{ik} = \mathsf{T}_{ij}\mathsf{S}_{jk}
$$

Matrix multiplication is _associative_ but _not commutative_.

## Transpose

### Definition

Let $\mathsf{A} = \Set{A_{ij}}$ be a $m \times n$ matrix.
The _transpose_ $\mathsf{A}^\intercal$ of $\mathsf{A}$ is defined to be a $n \times m$ matrix with

$$
(\mathsf{A}^\intercal)_{ij} = (\mathsf{A})_{ji} = A_{ji}
$$

From definition, we can see that

$$
(\mathsf{A}^\intercal)^\intercal = \mathsf{A}
$$

Also,

$$
\begin{align*}
((\mathsf{A}\mathsf{B})^\intercal)_{ik} &= (\mathsf{A}\mathsf{B})_{ki} \\
&= \mathsf{A}_{kj} \mathsf{B}_{ji} \\
&= (\mathsf{B}^\intercal)_{ij} (\mathsf{A}^\intercal)_{jk} \\
&= (\mathsf{B}^\intercal \mathsf{A}^\intercal)_{ik}
\end{align*}
$$

Hence,

$$
(\mathsf{A}\mathsf{B})^\intercal = \mathsf{B}^\intercal \mathsf{A}^\intercal
$$

### Hermitian Conjugate

Let $\mathsf{A} = \Set{A_{ij}}$ be a matrix, with $A_{ij} \in \mathbb{C}$.
The _Hermitian conjugate_ or _conjugate transpose_ or _adjoint_ is defined to be

$$
\mathsf{A}^\dagger = (\mathsf{A}^\intercal)^\ast = (\mathsf{A}^\ast)^\intercal
$$

We also have

$$
\mathsf{A}^{\dagger\dagger} = \mathsf{A}
$$

and

$$
(\mathsf{A}\mathsf{B})^\dagger = \mathsf{B}^\dagger \mathsf{A}^\dagger
$$

### Symmetric Matrices

A square matrix is _symmetric_ if

$$
\mathsf{A} = \mathsf{A}^\intercal \iff A_{ij} = A_{ji}
$$

and is _antisymmetric_ if

$$
\mathsf{A} = -\mathsf{A}^\intercal \iff A_{ij} = -A_{ji}
$$

For an antisymmetric matrix, as $A_{11} = -A_{11}, A_{22} = -A_{22}, ...$, the diagonal elements have to be zero.

### Hermitian Matrices

A square complex matrix is _Hermitian_ if

$$
\mathsf{A} = \mathsf{A}^\dagger \iff A_{ij} = A_{ji}^\ast
$$

and is _skew-Hermitian_ if

$$
\mathsf{A} = -\mathsf{A}^\dagger \iff A_{ij} = -A_{ji}^\ast
$$

For Hermitian and skew-Hermitian matrices, the diagonal elements are real and pure imaginary respectively.

## Trace

The _trace_ of a square matrix is equal to the sum of the diagonal elements, i.e.

$$
Tr(\mathsf{A}) = A_{ii}
$$

Let $\mathsf{B}$ be $m \times n$ matrix and $\mathsf{C}$ be $n \times m$ matrix,
though $\mathsf{BC}$ and $\mathsf{CB}$ are not necessary equal (or even of different sizes),

$$
Tr(\mathsf{BC}) = (\mathsf{BC})_{ii} = B_{ij}C_{ji} = C_{ij}B_{ji} = (\mathsf{CB})_{ii} = Tr(\mathsf{CB})
$$

## Identity Matrix

The _unit_ or _identity_ matrix is defined to be

$$
\mathsf{I} = \begin{pmatrix}
1 & 0 & \dots & 0 \\
0 & 1 & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & 1 \\
\end{pmatrix} = \Set{\delta_{ij}}
$$

We have

$$
\begin{align*}
(\mathsf{IA})_{ij} &= \delta_{ik}A_{kj} = A_{ij} \\
(\mathsf{AI})_{ij} &= A_{ik}\delta_{kj} = A_{ij}
\end{align*}
$$

Hence,

$$
\mathsf{IA} = \mathsf{AI} = \mathsf{A}
$$

## Decomposition of Square Matrix

For a square matrix $\mathsf{B}$, we construct

$$
\begin{align*}
\mathsf{A} &= {1 \over 2} \left( \mathsf{B} - \mathsf{B}^\intercal \right) \\
\mathsf{S} &= {1 \over 2} \left( \mathsf{B} + \mathsf{B}^\intercal \right)
\end{align*}
$$

As

$$
\begin{align*}
\mathsf{A}^\intercal &= {1 \over 2} \left( \mathsf{B}^\intercal - \mathsf{B} \right) = -\mathsf{A} \\
\mathsf{S}^\intercal &= {1 \over 2} \left( \mathsf{B}^\intercal + \mathsf{B} \right) = \mathsf{S} \\
\mathsf{A} + \mathsf{S} &= \mathsf{B} \\
\end{align*}
$$

Let $n\sigma = Tr(\mathsf{S})$, so $\sigma = {1 \over n}S_{ii}$, and write

$$
\mathsf{E} = \mathsf{S} - \sigma\mathsf{I}
$$

$\mathsf{E}$ is a trace-free symmetric tensor, and

$$
\mathsf{B} = \sigma\mathsf{I} + \mathsf{E} + \mathsf{A}
$$

which represents the decomposition of a square matrix into _isotropic_, _symmetric trace-free_ and _antisymmetric_ parts.

## Inverse

Let $\mathsf{A}$ be a $m \times n$ matrix.
A $n \times m$ matrix $\mathsf{B}$ is a left inverse of $\mathsf{A}$ if $\mathsf{BA} = \mathsf{I}$ ($n \times n$).
A $n \times m$ matrix $\mathsf{C}$ is a right inverse of $\mathsf{A}$ if $\mathsf{AC} = \mathsf{I}$ ($m \times m$).

If both the left inverse $\mathsf{B}$ and right inverse $\mathsf{C}$ exist, then

$$
\mathsf{B} = \mathsf{BI} = \mathsf{BAC} = \mathsf{IC} = \mathsf{C}
$$

Let $\mathsf{A}$ be a square matrix. $\mathsf{A}$ is _invertible_ if there exists a matrix $\mathsf{A}^{-1}$, which is unique, such that

$$
\mathsf{A}^{-1}\mathsf{A} = \mathsf{A}\mathsf{A}^{-1} = \mathsf{I}
$$

We have

$$
(\mathsf{A}^{-1})^{-1} = \mathsf{A}
$$

and

$$
\mathsf{AB}^{-1} = \mathsf{B}^{-1}\mathsf{A}^{-1}
$$

## Orthogonal Matrix

A real square matrix is _orthogonal_ if

$$
\mathsf{A}\mathsf{A}^\intercal = \mathsf{I} = \mathsf{A}^\intercal\mathsf{A}
$$

i.e. if $\mathsf{A}$ is invertible and $\mathsf{A}^{-1} = \mathsf{A}^\intercal$

As

$$
(\mathsf{A}\mathsf{A}^\intercal)_{ij} = \mathsf{A}_{ik}(\mathsf{A}^\intercal)_{kj} = \mathsf{A}_{ik}\mathsf{A}_{jk} = \delta_{ij}
$$

it means the product of the $i$-th row with other rows is $0$ and product with itself is $1$.
It implies that the rows (and columns) of $\mathsf{A}$ form an orthonormal set.

A map $\mathcal{A}$ with orthogonal matrix $\mathsf{A}$ with repsect to an orthonormal basis transforms $\Set{\mathbf{e}_i}$ to an orthonormal set
(which may be right-handed or left handed depending on the sign of $\det \mathsf{A}$.

Rotation and reflection matrices are examples of orthogonal matrix.

The scalar product is preserved after the mapping represented by an orthogonal matrix with respect to an orthonormal basis as ($\mathbf{x} \cdot \mathbf{y} = \mathsf{x}^\intercal \mathsf{y}$ if the basis is orthonormal)

$$
\begin{align*}
\mathbf{x}' \cdot \mathbf{y}' &= (\mathsf{x}')^\intercal \mathsf{y}' \\
&= (\mathsf{x}^\intercal \mathsf{A}^\intercal) (\mathsf{A} \mathsf{y}) \\
&= \mathsf{x}^\intercal \mathsf{I} \mathsf{y} \\
&= \mathsf{x}^\intercal \mathsf{y} \\
&= \mathbf{x} \cdot \mathbf{y} \\
\end{align*}
$$

Hence, the map is an _isometry_, i.e. distances are preserved.

For a complex square matrix to be _unitary_ if its Hermitian conjugate is equal to its inverse, i.e.

$$
\mathsf{A}^\dagger = \mathsf{A}^{-1}
$$

which has similar properties as orthogonal real matrix.

## Determinants

### 3-by-3

Let $\mathcal{A}: \mathbb{R}^3 \to \mathbb{R}^3$ with matrix representation $\mathsf{A}$ be a linear map with standard orthonormal basis $\Set{\mathbf{e}_i}$.
Consider the effect of the linear map to the volume of the unit cube, which is

$$
\begin{align*}
\mathbf{e}_1' \cdot (\mathbf{e}_2' \times \mathbf{e}_3') &= \varepsilon_{ijk} (\mathbf{e}_1')_i (\mathbf{e}_2')_j (\mathbf{e}_3')_k \\
&= \varepsilon_{ijk} (\mathsf{A}_{il} (\mathbf{e}_1)_l) (\mathsf{A}_{jm} (\mathbf{e}_2)_m) (\mathsf{A}_{kn} (\mathbf{e}_3)_n) \\
&= \varepsilon_{ijk} (\mathsf{A}_{il} \delta_{1l}) (\mathsf{A}_{jm} \delta_{2m}) (\mathsf{A}_{kn} \delta_{3n}) \\
&= \varepsilon_{ijk} \mathsf{A}_{i1} \mathsf{A}_{j2} \mathsf{A}_{k3} \\
\end{align*}

$$

The determinant $\det \mathsf{A}$ of $\mathsf{A}$ is given by

$$
\det \mathsf{A} \equiv |\mathsf{A}| \equiv \begin{vmatrix}
A_{11} & A_{12} & A_{13} \\
A_{21} & A_{22} & A_{23} \\
A_{31} & A_{32} & A_{33} \\
\end{vmatrix} = \epsilon_{ijk} \mathsf{A}_{i1} \mathsf{A}_{j2} \mathsf{A}_{k3} = \epsilon_{ijk} \mathsf{A}_{1i} \mathsf{A}_{2j} \mathsf{A}_{3k}
$$

which represents the volume of the transformed unit cube.
A linear map is _volume preserving_ if and only if $\det \mathsf{A} = \pm 1$ (with respect to orthonormal basis).

If $\Set{\mathbf{e}_i}$ is right-handed basis, then the transformed basis is right-handed if $\det \mathsf{A} > 0$, and left-handed if $\det \mathsf{A} < 0$.

### 2-by-2

By setting $A_{13} = A_{31} = A_{23} = A{32} = 0$ and $A_{33} = 1$, we have the determinant for a $2 \times 2$ matrix

$$
\det \mathsf{A} = \begin{vmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22} \\
\end{vmatrix} = A_{11}A_{22} - A_{12}A_{21}
$$

Similarily, $\mathsf{A}$ is _area preseving_ if and only if $\det \mathsf{A} = \pm 1$.

### n-by-n

The determinant of a $n \times n$ matrix $\mathsf{A}$ is defined by

$$
\det \mathsf{A} = \epsilon_{i_1 i_2 ... i_n} A_{i_1 1} A_{i_2 2} ... A_{i_n n}
$$

Let $S_n$ be the set of permutations of $\Set{1, 2, ..., n}$ and $\epsilon(\sigma)$ be the sign of permutation $\sigma \in S_n$, then

$$
\det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma) A_{\sigma(1) 1} A_{\sigma(2) 2} ... A_{\sigma(n) n}
$$

## Properties of Determinants

### Transpose

Let $\rho$ be a permutation, we have

$$
A_{\sigma(1) 1} A_{\sigma(2) 2} ... A_{\sigma(n) n} = A_{\sigma(\rho(1)) \rho(1)} A_{\sigma(\rho(2)) \rho(2)} ... A_{\sigma(\rho(n)) \rho(n)}
$$

because the R.H.S. is just a reordering of L.H.S.

By choosing $\rho = \sigma^{-1}$,

$$
\det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma^{-1}) A_{1 \sigma^{-1}(1)} A_{2 \sigma^{-1}(2)} ... A_{n \sigma^{-1}(n)}
$$

As $\epsilon(\sigma^{-1}) = \epsilon(\sigma)$ and every permutation has an unique inverse,

$$
\det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma) A_{1 \sigma(1)} A_{2 \sigma(2)} ... A_{n \sigma(n)} = \det \mathsf{A}^\intercal
$$

Hence, we can also write

$$
\det \mathsf{A} = \det \mathsf{A}^\intercal = \epsilon_{j_1 j_2 ... j_n} A_{1 j_1} A_{2 j_2} ... A_{n j_n}
$$

### Scalar product

Let $\mathsf{A}$ be a $n \times n$ matrix,

$$
\mathsf{B} = \lambda \mathsf{A} \implies \det \mathsf{B} = \lambda^n \det \mathsf{A}
$$

### Interchanges

If $\mathsf{B}$ is obtained from interchanging two rows/columns of $\mathsf{A}$,
then $\det \mathsf{B} = - \det \mathsf{A}$.

Hence, if two rows/columns are identical, $\det \mathsf{A} = 0$.

### Row/Column Operations

If $\mathsf{B}$ is obtained from adding to a row/column of $\mathsf{A}$ by multiple of another row/column, then $\det \mathsf{B} = \det \mathsf{A}$.

### Linear Dependent Rows/Columns

If the rows or columns of $\mathsf{A}$ are linearly dependent, then $\det \mathsf{A} = 0$.

If $\det \mathsf{A} \not = 0$, then rows/columns $\mathsf{A}$ are linear independent (the contrapositive).

Conversely, if $\det \mathsf{A} = 0$, then rows/columns are linearly dependent, is also true.

### Matrix product

If $\mathsf{A}$ and $\mathsf{B}$ are square matrix, then

$$
\det \mathsf{AB} = \det \mathsf{A} \det \mathsf{B}
$$

From that, if $\mathsf{A}$ is orthogonal,

$$
(\det \mathsf{A})^2 = \det \mathsf{A} \det \mathsf{A}^\intercal = \det \mathsf{I} = 1
$$

Hence, $\det \mathsf{A} = \pm 1$.

## Minors and cofactors

### Definition

Let $\mathsf{A}$ be a $n \times n$ matrix, define $\mathsf{A}^{ij}$ be the matrix omitting the $i$-th row and $j$-th column of $\mathsf{A}$.

The _minor_ $M_{ij}$ of the $ij$-th element of $\mathsf{A}$ is defined by

$$
M_{ij} = \det \mathsf{A}^{ij}
$$

The _cofactor_ $\Delta_{ij}$ of the $ij$-th element of $\mathsf{A}$ is defined by

$$
\Delta_{ij} = (-)^{i - j} M_{ij} = (-)^{i - j} \det \mathsf{A}^{ij}
$$

### Laplace Expansion Formula

The _Laplace expansion formula_ is given by

$$
\det \mathsf{A} = \sum_{k = 1}^{n} A_{Ik} \Delta_{Ik} = \sum_{k = 1}^{n} A_{kI} \Delta_{kI}
$$

for a chosen $1 \le I \le n$.

It expresses $\det \mathsf{A}$ as a sum of $n$ determinants of one less row and column than the original.

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 3](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
