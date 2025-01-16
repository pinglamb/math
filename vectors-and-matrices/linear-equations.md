---
layout: base
title: Linear Equations &#124; Vectors and Matrices
---

# Linear Equations
{: .page-title}

## Matrix Inverses

> *Lemma.*{: .lem}
> Given $n \times n$ matrix $\mathsf{A} = \Set{A_{ij}}$, then
>
> $$
  \begin{align*}
  \sum_{k=1}^n A_{ik} \Delta_{Ik} &= 0 \quad \text{for any } i \not= I \\
  \sum_{k=1}^n A_{kj} \Delta_{kJ} &= 0 \quad \text{for any } j \not= J
  \end{align*}
  $$
>
> Therefore, under summation convention, we have
>
> $$
  \begin{align*}
  A_{ik}\Delta_{jk} &= \delta_{ij} \det \mathsf{A} \\
  A_{ki}\Delta_{kj} &= \delta_{ij} \det \mathsf{A}
  \end{align*}
  $$
>
> *Proof.*{: .prf}
>
> In terms of the Laplace expansion formulae, we have
>
> $$
  \det \mathsf{A} = \sum_{k=1}^n A_{Ik} \Delta_{Ik} = \sum_{k=1}^n A_{kJ} \Delta_{kJ}
  $$
>
> for any $1 \le I \le n$ or $1 \le J \le n$.
>
> Let $\mathsf{B}$ be the matrix obtained by replacing the $I$-th row of $\mathsf{A}$ with one of the other row, say the $i$-th.
> Since $\mathsf{B}$ has two identical rows, $\det \mathsf{B} = 0$.
> However, the cofactors $\Delta_{Ik}$ for $I$-th row of $\mathsf{B}$ is the same as that of the $I$-th row of $\mathsf{A}$, therefore
>
> $$
  \begin{align*}
  0 = \det \mathsf{B} &= \sum_{k=1}^n B_{Ik} \Delta_{Ik} \\
                      &= \sum_{k=1}^n A_{ik} \Delta_{Ik} \quad \text{for any } i \not= I
  \end{align*}
  $$
>
> Hence, we have
>
> $$
  \begin{align*}
  A_{ik} \Delta_{jk} &= \begin{cases}
                       \det \mathsf{A} & \text{if } i = j \\
                       0 & \text{if } i \not= j
                       \end{cases} \\
  &= \delta_{ij} \det \mathsf{A}
  \end{align*}
  $$
>
> and we can obtain the same result for the other case by replacing the $J$-th column.

> *Theorem.*{: .thm}
> Given $n \times n$ matrix $\mathsf{A}$ with $\det \mathsf{A} \not= 0$, then the matrix $B = \Set{B_{ij}}$ such that
>
> $$
  B_{ij} = {1 \over \det \mathsf{A}} \Delta_{ji}
  $$
>
> is the inverse of $\mathsf{A}$, i.e. $\mathsf{AB} = \mathsf{BA} = \mathsf{I}$.
>
> *Proof.*{: .prf}
>
> With the above lemma, we have
>
> $$
  \begin{align*}
  (\mathsf{AB})_{ij} &= A_{ik}B_{kj} \\
  &= { A_{ik} \Delta_{jk} \over \det \mathsf{A} } \\
  &= { \delta_{ij} \det \mathsf{A} \over \det \mathsf{A} } \\
  &= \delta_{ij}
  \end{align*}
  $$
>
> Therefore, $\mathsf{AB} = \mathsf{I}$.
> Similarily, $\mathsf{BA} = \mathsf{I}$ and hence $B = \mathsf{A}^{-1}$ and $\mathsf{A}$ is invertible.

The formula for finding the inverse is base on the Laplace explansion formula.
From the formula and the above lemma, we can see that multiplying and summing the cofactors with the "right" row/column we can get the determinant,
but doing that with the "wrong" row/column we will get zero. Hence, the product of the matrix with the tranpose of its cofactors matrix is
(using $3 \times 3$ matrix as example)

$$
\begin{pmatrix}
A_{11} & A_{12} & A_{13} \\
A_{21} & A_{22} & A_{23} \\
A_{31} & A_{32} & A_{33} \\
\end{pmatrix}
\begin{pmatrix}
\Delta_{11} & \Delta_{21} & \Delta_{31} \\
\Delta_{12} & \Delta_{22} & \Delta_{32} \\
\Delta_{13} & \Delta_{23} & \Delta_{33} \\
\end{pmatrix} =
\begin{pmatrix}
\det \mathsf{A} & 0 & 0 \\
0 & \det \mathsf{A} & 0 \\
0 & 0 & \det \mathsf{A} \\
\end{pmatrix}
$$

and hence we can find the inverse by dividing that by $\det \mathsf{A}$.
