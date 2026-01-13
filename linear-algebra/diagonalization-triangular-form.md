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
Also, we give a special name to these kernels.

> *Definition.*{: .def}
> The $\lambda$-**eigenspace** of $\alpha$, denoted by $E_\alpha(\lambda)$ or simply $E(\lambda)$, is the subspace of $\lambda$-eigenvectors of $\alpha$, i.e.
>
> $$
  E(\lambda) = \ker (\alpha - \lambda \iota)
  $$

In the proof of the theorem we can see that $V = E(\lambda_1) \oplus \cdots \oplus E(\lambda_r)$.
Also note that the $E(0)$ is equivalent to the nullspace of the linear map so $\dim E(0) = n(\alpha)$.

We can translate the above theorem into a similar one for matrices.

> *Corollary.*{: .cor}
> A matrix $A \in \text{Mat}_n(\mathbf{F})$ is similar to a diagonal matrix $D$ iff the minimal polynomial of $A$ has the form
>
> $$
  m(x) = (x - \lambda_1) \cdots (x - \lambda_r)
  $$
>
> with distinct $\lambda_i \in \mathbf{F}$, i.e. $D = P^{-1}AP$.
> $D$ has diagonal entries $\Set{\lambda_i, ..., \lambda_n}$ given by the eigenvalues of $A$, repeated if necessary; and $P$ is the invertible matrix whose columns are the corresponding eigenvectors.

> *Theorem.*{: .thm}
> Let $\alpha_1, ..., \alpha_k \in \text{End}(V)$ be diagonalizable.
> Then there exists a basis of $V$ such that the basis vectors are eigenvectors simultaneously for the endomorphisms iff $\alpha_i \alpha_j = \alpha_j \alpha_i$ for $1 \le i, j \le k$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $\alpha_1, ..., \alpha_k$ are diagonalizable, then for sure they commute.
>
> ($\Leftarrow$) For $\dim V = 1$, it is obviously true since any vectors are eigenvectors and any matrix representations are diagonal.
> Assume the statement is true for sets of linear maps acting on lower dimensional vector spaces.
> Suppose that $\alpha_i$ are ordered in a way that $\alpha_1$ has the most number of eigenvalues.
> If all the linear maps $\alpha_i$ have only one eigenvalue, then $\alpha_i = \lambda_i \iota$ so any basis will consist of eigenvectors for $\Set{\alpha_i}$.
>
> Let $\lambda_1, ..., \lambda_r$ be the distinct eigenvalues of $\alpha_1$ with $r > 1$ and $E_i = E\_{\alpha_1}(\lambda_i)$ for $1 \le i \le r$.
> Since $\alpha_1$ is diagonalizable, we have
>
> $$
  V = E_1 \oplus \cdots \oplus E_r
  $$
>
> For any $v \in E_i$, we have
>
> $$
  \alpha_1(\alpha_j v) = \alpha_j \alpha_1 v = \alpha_j(\lambda_i v) = \lambda_i (\alpha_j(v))
  $$
>
> so $\alpha_j(v) \in E_i$ and $\alpha_j\|_{E_i} \in \text{End}(E_i)$.
>
> Let $m_j\|\_{E_i}(x)$ be the minimal polynomial of $\alpha_j\|\_{E_i}$, we have $m_j\|\_{E_i}(\alpha_j) = 0$ so $m_j\|\_{E_i} \mid m_j\|\_V$.
> Since $\alpha_j$ is diagonalizable, $m_j\|\_V$ consists of distinct linear factors and so as $m_j\|\_{E_i}$ and therefore $\alpha_j\|\_{E_i}$ is diagonalizable.
> By induction hypothesis, each of the subspace $E_i$ has a basis such that the basis vectors are eigenvectors simultaneously for the endomorphisms and their union is the required basis for $V$.

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 6
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 23, 24
