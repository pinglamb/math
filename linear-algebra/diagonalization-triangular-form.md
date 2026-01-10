---
layout: base
title: Diagonalization and Triangular Form &#124; Linear Algebra
---

# Diagonalization and Triangular Form
{: .page-title}

With the relationship between endomorphism and its minimal polynomial established, we are now ready to find a basis such that the matrix representation of the endomorphism is as simple as possible.

## Diagonalization

> *Definition.*{: .def}
> An endomorphism $\alpha \in \text{End}(V)$ is **diagonalizable** if there exists a basis for $V$ consisting of eigenvectors of $\alpha$.
> The matrix of $\alpha$ with respect to such basis is a diagonal matrix.

> *Theorem.*{: .thm}
> **[Diagonalizability Theorem]**
> An endomorphism $\alpha \in \text{End}(V)$ is diagonalizable iff the minimal polynomial $m(x)$ of $\alpha$ is a product of distinct linear factors.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose that $\alpha$ is diagonalizable. Let $\Set{v_1, ..., v_n}$ be a basis of $\alpha$ consisting of eigenvectors corresponding to eigenvalues $\Set{\lambda_1, ...., \lambda_n}$.
> Suppose that $\Set{v_i}$ are ordered in a way that the corresponding eigenvalues $\Set{\lambda_1, ..., \lambda_r}$ are distinct and $\Set{\lambda_{r+1}, ... \lambda_n}$ coincide with some value in $\Set{\lambda_1, ..., \lambda_r}$.
>
> Let
>
> $$
  m(x) = (x - \lambda_1) \cdots (x - \lambda_r)
  $$
>
> Since $(\alpha - \lambda_i \cdot \iota) v_i = 0$ for $1 \le i \le r$ and $(\alpha - \lambda_j \cdot \iota) v_i = 0$ for $r + 1 \le i \le n$ and $\lambda_j = \lambda_i$, we have
>
> $$
  m(\alpha)v_i = 0, \qquad 1 \le i \le n
  $$
>
> Therefore, $m(\alpha) = 0$ and the minimal polynomial of $\alpha$ is a factor of $m(x)$.
> However, deleting any factors of $m(x)$ to obtain a polynomial $m^\ast(x)$ will result with $m^\ast(\alpha) \not= 0$ since $\Set{\lambda_i}$ are distinct, so $m(x)$ is the minimal polynomial.
>
> ($\Leftarrow$) If the minimal polynomial has the form $m(x) = (x - \lambda_1) \cdots (x - \lambda_r)$ with $\Set{\lambda_r}$ distinct, then
>
> $$
  V = \ker (\alpha - \lambda_1 \cdot \iota) \oplus \cdots \oplus \ker (\alpha - \lambda_r \cdot \iota)
  $$
>
> Let $\Set{v\_{i1}, ..., v_{id_i}}$ be a basis for $\ker (\alpha - \lambda_i \cdot \iota)$, then their union is a basis for $V$ since it is a direct sum of the kernels.
> For any $v\_{ij} \in \ker (\alpha - \lambda_i \cdot \iota)$ with $v\_{ij} \not= 0$, $(\alpha - \lambda_i \cdot \iota) v\_{ij} = 0$ implies $\alpha v\_{ij} = \lambda_i v\_{ij}$ so $\Set{v\_{ij}}$ are indeed eigenvectors of the endomorphism $\alpha$.

Note that the theorem doesn't require the linear map has $n$ distinct eigenvalues to be diagonalizable.

> *Definition.*{: .def}
> The $\lambda$-**eigenspace** of $\alpha$, denoted by $E_\alpha(\lambda)$ or simply $E(\lambda)$, is the subspace of $\lambda$-eigenvectors of $\alpha$, i.e.
>
> $$
  E(\lambda) = \ker (\alpha - \lambda \iota)
  $$

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 6
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 23, 24
