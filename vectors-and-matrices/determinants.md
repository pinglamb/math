---
layout: base
title: Determinants &#124; Vectors and Matrices
---

# Determinants

## $3 \times 3$

Consider the effect of a linear map $\mathcal{A}: \mathbb{R}^3 \to \mathbb{R}^3$ on the volume of the unit cube defined by orthonormal basis vectors $\Set{\mathbf{e}_i}$.
Let $\mathsf{A} = \Set{A_{ij}}$ be the matrix associated with $\mathcal{A}$, then the volume of the mapped cube is given by

$$
\begin{align*}
\mathbf{e}_1' \cdot (\mathbf{e}_2' \times \mathbf{e}_3') &= \varepsilon_{ijk} (\mathbf{e}_1')_i (\mathbf{e}_2')_j (\mathbf{e}_3')_k \\
&= \varepsilon_{ijk} (A_{il} (\mathbf{e}_1)_l) (A_{jm} (\mathbf{e}_2)_m) (A_{kn} (\mathbf{e}_3)_n) \\
&= \varepsilon_{ijk} (A_{il} \delta_{1l}) (A_{jm} \delta_{2m}) (A_{kn} \delta_{3n}) \\
&= \varepsilon_{ijk} A_{i1} A_{j2} A_{k3} \\
\end{align*}
$$

> *Definition.*{: .def}
> The **determinant** of a $3 \times 3$ matrix $\mathsf{A}$ is given by
>
> $$
  \det \mathsf{A}
  \equiv \vert \mathsf{A} \vert
  \equiv \begin{vmatrix}
  A_{11} & A_{12} & A_{13} \\
  A_{21} & A_{22} & A_{23} \\
  A_{31} & A_{32} & A_{33} \\
  \end{vmatrix}
  = \begin{vmatrix} \mathbf{e}_1' & \mathbf{e}_2' & \mathbf{e}_3' \end{vmatrix}
  = \epsilon_{ijk} \mathsf{A}_{i1} \mathsf{A}_{j2} \mathsf{A}_{k3}
  = \epsilon_{ijk} \mathsf{A}_{1i} \mathsf{A}_{2j} \mathsf{A}_{3k}
  $$
>
> which represents the volume of the transformed unit cube with respect to orthonormal basis.

> *Definition.*{: .def}
> A linear map is _volume preserving_ iff $\det \mathsf{A} = \pm 1$, where $\mathsf{A}$ is a matrix with respect to an orthonormal basis.

> *Property.*{: .prop}
> If $\Set{\mathbf{e}_i}$ is right-handed orthonormal basis,
> then the set $\Set{\mathbf{e}_i'}$ is right-handed if $\det \mathsf{A} > 0$, and left-handed if $\det \mathsf{A} < 0$.

## $2 \times 2$

By setting $A_{13} = A_{31} = A_{23} = A{32} = 0$ and $A_{33} = 1$, we have the determinant for a $2 \times 2$ matrix

$$
\det \mathsf{A} = \begin{vmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22} \\
\end{vmatrix} = A_{11}A_{22} - A_{12}A_{21}
$$

Similarily, $\mathsf{A}$ is _area preseving_ iff $\det \mathsf{A} = \pm 1$.

Note that the determinant of $3 \times 3$ can be rewritten as

$$
\begin{align*}
\det \mathsf{A}
&= A_{11} \begin{vmatrix}
         A_{22} & A_{23} \\
         A_{32} & A_{33}
         \end{vmatrix}
- A_{21} \begin{vmatrix}
         A_{12} & A_{13} \\
         A_{32} & A_{33}
         \end{vmatrix}
+ A_{31} \begin{vmatrix}
         A_{12} & A_{13} \\
         A_{22} & A_{23}
         \end{vmatrix} \\
&= A_{11} \begin{vmatrix}
         A_{22} & A_{23} \\
         A_{32} & A_{33}
         \end{vmatrix}
- A_{12} \begin{vmatrix}
         A_{21} & A_{23} \\
         A_{31} & A_{33}
         \end{vmatrix}
+ A_{13} \begin{vmatrix}
         A_{21} & A_{22} \\
         A_{31} & A_{32}
         \end{vmatrix} \\
\end{align*}
$$

## $n \times n$

The [Levi-Civita symbol](suffix-notation.md#levi-civita-symbol) can be generalized to higher dimensions base on the [sign of permutation](../groups/permutations.md#sign-of-permutation).

> *Definition.*{: .def}
> The **Levi-Civita symbol** is defined to be
>
> $$
  \varepsilon_{j_1j_2...j_n} = \begin{cases}
  +1 & \text{if } (j_1, j_2, ..., j_n) \text{ is an even permutation} \\
  -1 & \text{if } (j_1, j_2, ..., j_n) \text{ is an odd permutation} \\
  0 & \text{if any two labels are the same} \\
  \end{cases}
  $$

> *Definition.*{: .def}
> The determinant of a $n \times n$ matrix $\mathsf{A}$ is defined by
>
> $$
  \det \mathsf{A} = \sum_{i_1i_2...i_n} \varepsilon_{i_1 i_2 ... i_n} A_{i_1 1} A_{i_2 2} ... A_{i_n n}
  $$
>
> or alternatively
>
> $$
  \det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma) A_{\sigma(1) 1} A_{\sigma(2) 2} ... A_{\sigma(n) n}
  $$

## Properties

> *Lemma.*{: .lem}
> Let $\mathsf{A}$ be a square matrix and $\rho$ be a permutation.
> For any term in the sum of $\det \mathsf{A}$ over $S_n$,
>
> $$
  A_{\sigma(1) 1} A_{\sigma(2) 2} ... A_{\sigma(n) n}
  = A_{\sigma(\rho(1)) \rho(1)} A_{\sigma(\rho(2)) \rho(2)} ... A_{\sigma(\rho(n)) \rho(n)}
  $$
>
> *Proof.*{: .prf}
>
> The product on the L.H.S. is identical to that on the R.H.S. up to order.

> *Property.*{: .prop}
> For any square matrix $\mathsf{A}$
>
> $$
  \det \mathsf{A} = \det \mathsf{A}^\intercal
  $$
>
> Hence, we have
>
> $$
  \sum_{i_1i_2...i_n} \varepsilon_{i_1 i_2 ... i_n} A_{i_1 1} A_{i_2 2} ... A_{i_n n}
  = \sum_{j_1j_2...j_n} \varepsilon_{j_1 j_2 ... j_n} A_{1 j_1} A_{2 j_2} ... A_{n j_n}
  $$
>
> *Proof.*{: .prf}
>
> From the above lemma, by choosing $\rho = \sigma^{-1}$ and use the fact that $\epsilon(\sigma) = \epsilon(\sigma^{-1})$,
>
> $$
  \det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma^{-1}) A_{1 \sigma^{-1}(1)} A_{2 \sigma^{-1}(2)} ... A_{n \sigma^{-1}(n)}
  $$
>
> As every permutation has an unique inverse, we can just relabel $\sigma^{-1}$ to $\sigma$, i.e.
>
> $$
  \det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma) A_{1 \sigma(1)} A_{2 \sigma(2)} ... A_{n \sigma(n)} = \det \mathsf{A}^\intercal
  $$

> *Property.*{: .prop}
> If a matrix $\mathsf{B}$ is obtained from $\mathsf{A}$ by multiplying any _single_ row or column of $\mathsf{A}$ by $\lambda$ then
>
> $$
  \det \mathsf{B} = \lambda \det \mathsf{A}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \det \mathsf{B} &= \varepsilon_{j_1...j_r...j_n} B_{1j_1}...B_{rj_r}...B_{nj_n} \\
  &= \varepsilon_{j_1...j_r...j_n} A_{1j_1}...(\lambda A_{rj_r})...A_{nj_n} \\
  &= \lambda \varepsilon_{j_1...j_r...j_n} A_{1j_1}...A_{rj_r}...A_{nj_n} \\
  &= \lambda \det \mathsf{A}
  \end{align*}
  $$

> *Property.*{: .prop}
> Let $\mathsf{A}$ be a $n \times n$ matrix, then
>
> $$
  \det \lambda \mathsf{A} = \lambda^n \det \mathsf{A}
  $$

> *Property.*{: .prop}
> If $\mathsf{B}$ is obtained from $\mathsf{A}$ by interchanging two rows or two columns, then
>
> $$
  \det \mathsf{B} = -\det \mathsf{A}
  $$
>
> *Proof.*{: .prf}
>
> The sign of permutation chanags when any of the two elements are interchanged.

> *Property.*{: .prop}
> If two rows or two columns of $\mathsf{A}$ are identical, $\det \mathsf{A} = 0$.
>
> *Proof.*{: .prf}
>
> Interchange the two identical rows will yield the same matrix $\mathsf{A}$ and hence
>
> $$
  \det \mathsf{A} = -\det \mathsf{A} = 0
  $$

> *Property.*{: .prop}
> If $\mathsf{B}$ is obtained from $\mathsf{A}$ by adding to a given row/column a multiple of another row/column, then
>
> $$
  \det \mathsf{B} = \det \mathsf{A}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \det \mathsf{B}
  &= \varepsilon_{j_1...j_r...j_n} B_{1j_1}...B_{rj_r}...B_{nj_n} \\
  &= \varepsilon_{j_1...j_r...j_n} A_{1j_1}...(A_{rj_r} + \lambda A_{sj_r})...A_{nj_n} \\
  &= \varepsilon_{j_1...j_r...j_n} A_{1j_1}...A_{rj_r}...A_{nj_n} + \lambda \varepsilon_{j_1...j_r...j_n} A_{1j_1}...A_{sj_r}...A_{sj_s}...A_{nj_n} \\
  &= \varepsilon_{j_1...j_r...j_n} A_{1j_1}...A_{rj_r}...A_{nj_n} + \lambda 0 \\
  &= \det \mathsf{A}
  \end{align*}
  $$
>
> because the determinant is zero if two rows are equal.

> *Property.*{: .prop}
> If the rows or columns of $\mathsf{A}$ are linearly dependent, then
>
> $$
  \det \mathsf{A} = 0
  $$
>
> *Proof.*{: .prf}
>
> Assume the $r$-th rows are linearly dependent on the other rows,
> we can subtract the linear combination from it to get a row of zeros.
> Hence, $\det \mathsf{A} = 0$.

> *Property.*{: .prop}
> Contrapositively, the rows and columns of $\mathsf{A}$ are linearly independent if
>
> $$
  \det \mathsf{A} \not = 0
  $$

> *Property.*{: .prop}
> Conversely, if $\det \mathsf{A} = 0$, then rows/columns are linearly dependent.

## Matrix Product

> *Lemma.*{: .lem}
> Let $\rho$ be a permutation, then
>
> $$
  \epsilon(\rho) \det \mathsf{A} = \sum_{\sigma \in S_n} \epsilon(\sigma) A_{\sigma(1)\rho(1)}A_{\sigma(2)\rho(2)}...A_{\sigma(n)\rho(n)}
  $$
>
> or equivalently
>
> $$
  \varepsilon_{p_1p_2...p_n} \det A = \sum_{i_1i_2...i_n} \varepsilon_{i_1i_2...i_n} A_{i_1p_1}A_{i_2p_2}...A_{i_np_n}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \epsilon(\rho) \det \mathsf{A}
  &= \epsilon(\rho) \sum_{\tau \in S_n} \epsilon(\tau) A_{\tau(1)1}A_{\tau(2)2}...A_{\tau(n)n} \\
  &= \epsilon(\rho) \sum_{\tau \in S_n} \epsilon(\tau) A_{\tau(\rho(1))\rho(1)}A_{\tau(\rho(2))\rho(2)}...A_{\tau(\rho(n))\rho(n)} \\
  &= \sum_{\tau \in S_n} \epsilon(\tau\rho) A_{\tau(\rho(1))\rho(1)}A_{\tau(\rho(2))\rho(2)}...A_{\tau(\rho(n))\rho(n)} \\
  &= \sum_{\sigma \in S_n} \epsilon(\sigma) A_{\sigma(1))\rho(1)}A_{\sigma(2))\rho(2)}...A_{\sigma(n))\rho(n)} \\
  \end{align*}
  $$
>
> since summing over $\sigma = \tau\rho$ is equivalent to summing over $\tau$.

> *Theorem.*{: .thm}
> If $\mathsf{A}$ and $\mathsf{B}$ are both square matrices, then
>
> $$
  \det \mathsf{AB} = \det \mathsf{A} \det \mathsf{B}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \det \mathsf{AB}
  &= \varepsilon_{i_1i_2...i_n} (\mathsf{AB})_{i_1 1}(\mathsf{AB})_{i_2 2}...(\mathsf{AB})_{i_n n} \\
  &= \varepsilon_{i_1i_2...i_n} A_{i_1 k_1}B_{k_1 1}A_{i_2 k_2}B_{k_2 2}...A_{i_n k_n}B_{k_n n} \\
  &= \varepsilon_{i_1i_2...i_n} A_{i_1 k_1}A_{i_2 k_2}...A_{i_n k_n}B_{k_1 1}B_{k_2 2}...B_{k_n n} \\
  &= (\det \mathsf{A})(\varepsilon_{k_1k_2...k_n} B_{k_1 1}B_{k_2 2}...B_{k_n n}) \\
  &= \det \mathsf{A} \det \mathsf{B}
  \end{align*}
  $$

> *Corollary.*{: .cor}
> If $\mathsf{A}$ is orthogonal, then
>
> $$
  \det \mathsf{A} = \pm 1
  $$
>
> *Proof.*{: .prf}
>
> $$
  (\det \mathsf{A})^2 = \det \mathsf{A} \det \mathsf{A}^\intercal = \det \mathsf{A}\mathsf{A}^\intercal = \det \mathsf{I} = 1
  $$


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
