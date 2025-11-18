---
layout: base
title: Determinants &#124; Linear Algebra
---

# Determinants of Matrices
{: .page-title}

We now focus on actual computation of determinants of matrices. First of all, we recall the definition.

> *Definition.*{: .def}
> If $A \in \text{Mat}_n(\mathbb{F})$ then the **determinant** of $A$ is defined by
>
> $$
  \det A = \sum_{\sigma \in S_n} \epsilon(\sigma) \left( \prod_{i=1}^n A_{i \sigma(i)} \right)
  $$

> *Proposition.*{: .prop}
> Let $D$ be a volume form on $\mathbb{F}^n$ and $A = \begin{pmatrix} A^{(1)} & \cdots & A^{(n)} \end{pmatrix}$. Then
>
> $$
  D(A^{(1)}, ..., A^{(n)}) = \det A \cdot D(e_1, ..., e_n)
  $$
>
> or alternatively $D(Ae_1, ..., Ae_n) = \det A \cdot D(e_1, ..., e_n)$.
>
> *Proof.*{: .prf}
>
> We compute
>
> $$
  \begin{align*}
  D(A^{(1)}, ..., A^{(n)}) &= D \left( \sum_{i_1} A_{i_1 1} e_{i_1}, A^{(2)}, ..., A^{(n)} \right) \\
  &= \sum_{i_1} A_{i_1 1} D \left( e_{i_1}, A^{(2)}, ..., A^{(n)} \right) \\
  &= \sum_{i_1} \sum_{i_2} A_{i_1 1} A_{i_2 2} D \left( e_{i_1}, e_{i_2}, ..., A^{(n)} \right) \\
  &= \sum_{i_1, ..., i_n} \left( \prod_{j=1}^n A_{i_j j} \right) D(e_{i_1}, ..., e_{i_n})
  \end{align*}
  $$
>
> $D(e_{i_1}, ..., e_{i_n}) = 0$ unless all $i_j$ are distinct, which means there is $\sigma \in S_n$ such that $i_j = \sigma(j)$.
> Hence,
>
> $$
  D(A^{(1)}, ..., A^{(n)}) = \sum_{\sigma \in S_n} \left( \prod_{j=1}^n A_{\sigma(j) j} \right) D(e_{\sigma(1)}, ..., e_{\sigma(n)})
  $$
>
> and $D(e_{\sigma(1)}, ..., e_{\sigma(n)}) = \epsilon(\sigma) D(e_1, ..., e_n)$.

We follow with an important result about determinants.

> *Proposition.*{: .prop}
> Let $A, B \in \text{Mat}_n(\mathbb{F})$. Then
>
> $$
  \det AB = \det A \det B
  $$
>
> *Proof.*{: .prf}
>
> Let $D$ be a non-zero volume form on $\mathbb{F}^n$ and $D_A: \mathbb{F}^n \times \cdots \times \mathbb{F}^n \to \mathbb{F}$ be given by
>
> $$
  D_A(v_1, ..., v_n) = D(Av_1, ..., Av_n)
  $$
>
> Then $D_A$ is also a volume form. Thus,
>
> $$
  D_A(Bv_1, ..., Bv_n) = (\det B) D_A(e_1, ..., e_n) = (\det B) D(Ae_1, ..., Ae_n) = (\det B)(\det A) D(e_1, ..., e_n)
  $$
>
> and on the other hand
>
> $$
  D_A(Bv_1, ..., Bv_n) = D(ABe_1, ..., ABe_n) = (\det AB) D(e_1, ..., e_n)
  $$
>
> and hence $\det AB = \det A \det B$.

## Elementary Row/Column Operations

> *Proposition.*{: .prop}
> Let $A \in \text{Mat}_n(\mathbb{F})$. Then
>
> + Let $A'$ be a matrix obtained by interchanging $A^{(i)}$ and $A^{(j)}$ for $j \not= i$. Then
>
>   $$
    D(A') = - D(A)
    $$
>
> + Let $A'$ be a matrix obtained by replacing $A^{(i)}$ by $\lambda A^{(i)}$. Then
>
>   $$
    D(A') = \lambda D(A)
    $$
>
> + Let $A'$ be a matrix obtained by replacing $A^{(i)}$ by $A^{(i)} + \lambda A^{(j)}$ for $j \not= i$. Then
>
>   $$
    D(A') = D(A)
    $$
>
> *Proof.*{: .prf}
>
> Follows immediately from axioms and properties.

With that, we can compute the determinants by applying the elementary row/column operations until we get the upper/lower triangular form in which $\det A = \text{tr}\, A'$.

## Row/Column Expansions

> *Definition.*{: .def}
> $\widehat{A_{ij}}$ denotes the submatrix of $A$ obtained by deleting the $i$th row and $j$th column.

> *Proposition.*{: .prop}
> **[Row/Column Expansions]**
> Let $A \in \text{Mat}_n(\mathbb{F})$. Then
>
> $$
  \det A = \sum_{j=1}^n (-1)^{i+j} A_{ij} \det \widehat{A_{ij}} = \sum_{i=1}^n (-1)^{i+j} A_{ij} \det \widehat{A_{ij}}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \det A &= \det(A^{(1)}, ..., \sum_i A_{ij} e_i, ..., A^{(n)}) \\
  &= \sum_i A_{ij} \det(A^{(1)}, ..., e_i, ..., A^{(n)}) \\
  &= \sum_i A_{ij} (-1)^{i+j} \det A'
  \end{align*}
  $$
>
> where
>
> $$
  A' = \begin{pmatrix}
  1 & \ast \\
  0 & \widehat{A_{ij}}
  \end{pmatrix}
  $$
>
> which is obtained by interchanging $i-1$ times with the rows above and $j-1$ times with the columns on the left, and introduces the $(-1)^{i+j-2} = (-1)^{i+j}$ term.
>
> For $\sigma \in S_n$, $\prod A_{i \sigma(i)}' = 0$ unless $\sigma(1) = 1$ so $\det B = \det \widehat{A_{ij}}$ as required.

## Singularity and Inverses

## Block Triangular Matrices

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 5
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 5
