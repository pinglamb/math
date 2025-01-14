---
layout: base
title: Determinants &#124; Vectors and Matrices
---

# Determinants

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
