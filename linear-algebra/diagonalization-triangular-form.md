---
layout: base
title: Diagonalization and Triangular Form &#124; Linear Algebra
---

# Diagonalization and Triangular Form
{: .page-title}

It can be equally useful to study polynomials which send individual vectors to zero, which leads to the discussion of eigenvalues and eigenvectors.

## Eigenvalues and Eigenvectors

> *Definition.*{: .def}
> Let $\alpha \in \text{End}(V)$. An element $\lambda \in \mathbf{F}$ is called a **eigenvalue** (or **characteristic root**) of $\alpha$ if there exists a vector $v \not= 0$ in $V$ such that $\alpha(v) = \lambda v$.
> That nonzero vector $v$ is called a **eigenvector** (or **characteristic vector**) belonging to $\lambda$.

> *Definition.*{: .def}
> The $\lambda$-**eigenspace** of $\alpha$, denoted by $E_\alpha(\lambda)$ or simply $E(\lambda)$, is the subspace of $\lambda$-eigenvectors of $\alpha$, i.e.
>
> $$
  E(\lambda) = \ker (\alpha - \lambda \iota)
  $$

An eigenspace is a one-dimensional $\alpha$-invariant subspace resulting from the polynomial $f(x) = x - \lambda$.
Also, a small note that the eigenspace $E(0)$ is equivalent to the nullspace of the linear map so $\dim E(0) = n(\alpha)$.

We can define the same for matrices, i.e. $Av = \lambda v$ and the correspondence between linear maps and matrices show that $\lambda$ is a eigenvalue of $\alpha$ iff $\lambda$ is a eigenvalue of the matrix of $\alpha$ with respect to any basis.

> *Proposition.*{: .prop}
> Let $v_1, ..., v_r$ be eigenvectors belonging to distinct eigenvalues $\lambda_1, ..., \lambda_r$ of $\alpha \in \text{End}(V)$. Then $\Set{v_1, ..., v_r}$ are linearly independent.
>
> *Proof.*{: .prf}
>
> It is obviously true for $r = 1$. Assume it is true for any set fewer than $r$ vectors. Suppose that
>
> $$
  \mu_1 v_1 + \mu_2 v_2 + ... + \mu_r v_r = 0
  $$
>
> If any of the $\Set{\mu_i}$ are zero, all of them must be zero due to the induction hypothesis and $\Set{v_i}$ are linearly independent.
> Suppose all $\mu_i \not= 0$, we have
>
> $$
  \alpha(\mu_1 v_1 + \mu_2 v_2 + ... + \mu_r v_r) = \mu_1 \lambda_1 v_1 + \mu_2 \lambda_2 v_2 + ... + \mu_r \lambda_r v_r = 0
  $$
>
> and
>
> $$
  \lambda_1(\mu_1 v_1 + \mu_2 v_2 + ... + \mu_r v_r) = \mu_1 \lambda_1 v_1 + \mu_2 \lambda_1 v_2 + ... + \mu_r \lambda_1 v_r = 0
  $$
>
> so by subtracting one from the other, we have
>
> $$
  \mu_2 (\lambda_2 - \lambda_1) v_2 + \mu_3 (\lambda_3 - \lambda_1) v_3 + ... + \mu_r (\lambda_r - \lambda_1) v_r = 0
  $$
>
> Since the $\Set{\lambda_i}$ are distinct, by induction hypothesis, the above is only possible if $\mu_2 = ... = \mu_r = 0$ which implies $\mu_1 = 0$ and $\Set{v_i}$ are linaerly independent.

> *Proposition.*{: .prop}
> $\lambda$ is an eigenvalue of $\alpha$ iff the determinant $\det(\alpha - \lambda \iota) = 0$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $\lambda$ is an eigenvalue of $\alpha$, there exists $v \not= 0$ such that $(\alpha - \lambda \iota) v = 0$ which implies $\det(\alpha - \lambda \iota) = 0$.
>
> ($\Leftarrow$) If $\det(\alpha - \lambda \iota) = 0$, then $\alpha - \lambda \iota$ is not one to one and there exists distinct vectors $v_1, v_2$ such that
>
> $$
  (\alpha - \lambda_i \iota) v_1 = (\alpha - \lambda_i \iota) v_2
  $$
>
> and $v = v_1 - v_2 \not= 0$ satisfies $\alpha v = \lambda v$.

> *Definition.*{: .def}
> The **characteristic polynomial** of $\alpha$ is defined by
>
> $$
  \chi_\alpha(\lambda) = \det(\lambda \iota - \alpha)
  $$

Similar to minimal polynomial, the characteristic polynomial is independent of the choice of basis, i.e. the characteristic polynomial of $\alpha$ is well-defined.

> *Proposition.*{: .prop}
> The characteristic polynomial of $\alpha$ is independent of the choice of the matrix of $\alpha$.
>
> *Proof.*{: .prf}
>
> Let $A$ and $B$ be similar, i.e. $B = P^{-1}AP$. Then
>
> $$
  \det(\lambda I - B) = \det(\lambda I - P^{-1}AP) = \det P^{-1} (\lambda I - A) P = \det P^{-1} \det (\lambda I - A) \det P = \det(\lambda I - A)
  $$

## Diagonalization

The minimal polynomial determines if we can find a basis such that the matrix representation of the endomorphism is as simple as possible.

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
In the proof of the theorem we can see that $V = E(\lambda_1) \oplus \cdots \oplus E(\lambda_r)$.

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

## Triangular Form

When a linear map fails to diagonalize, we would still want a way to come as close to that.

> *Definition.*{: .def}
> An endomorphism $\alpha \in \text{End}(V)$ is **triangulable** if there exists a basis for $V$ such that the corresponding matrix is upper triangular.

> *Theorem.*{: .thm}
> **[Triangular Form Theorem]**
> An endomorphism $\alpha \in \text{End}(V)$ is triangulable iff the minimal polynomial $m(x)$ of $\alpha$ is a product of linear factors.
> Let $m(x) = (x - \lambda_1)^{e_1} \cdots (x - \lambda_r)^{e_r}$ where $\Set{e_i}$ are positive integers and $\Set{\lambda_i}$ are distinct.
> Then there exists a basis of $V$ such that the matrix $A$ of $\alpha$ with respect to this basis has the form
>
> $$
  A = \begin{pmatrix}
  A_1 & & & 0 \\
  & A_2 \\
  & & \ddots \\
  0 & & & A_r
  \end{pmatrix}
  $$
>
> where the matrices $\Set{A_i}$ is $d_i$-by-$d_i$ for $d_i \ge e_i$ and upper triangular and therefore $A$ is also upper triangular.
>
> *Proof.*{: .prf}
>

## Cayley-Hamilton Theorem

It can be hard to determine the minimal polynomial of a given linear map, but there is an important theorem to estabish its relationship with the characteristic polynomial.

> *Theorem.*{: .thm}
> **[Cayley-Hamilton Theorem]**
> Suppose that $V$ is a finite dimensional vector space over $\mathbf{F}$ and $\alpha \in \text{End}(V)$. Then $\chi_\alpha(\alpha) = 0$.
>
> *Proof.*{: .prf}
>

The result has many imporatnt implications regarding eigenvalues, minimal polynomials and characteristic polynomials.

> *Corollary.*{: .cor}
> Suppose that $V$ is a finite dimensional vector space over $\mathbf{F}$ and $\alpha \in \text{End}(V)$. Then
>
> $$
  m_\alpha(x) \mid \chi_\alpha(x)
  $$
>
> and so $\deg m_\alpha \le \dim V$.

> *Proposition.*{: .cor}
> Let $\alpha \in \text{End}(V)$ and $\lambda \in \mathbf{F}$. Then the following are equivalent:
>
> + $\lambda$ is an eigenvalue of $\alpha$;
>
> + $\lambda$ is a root of $\chi_\alpha(x)$;
>
> + $\lambda$ is a root of $m_\alpha(x)$.
>
> *Proof.*{: .prf}
>
> (1) and (2) are equivalent as proved before. If $\alpha v = \lambda v$ for $v \not= 0$, then for any polynomial $p(x) \in \mathbf{F}[x]$, $p(\alpha) v = p(\lambda) v$. Thus,
>
> $$
  m_\alpha(\lambda) v = m_\alpha(\alpha) v = 0
  $$
>
> so $m(\lambda) = 0$ and (1) implies (3). $m_\alpha(x) \mid \chi_\alpha(x)$ so (3) implies (2).
>
> Alternatively, if $m_\alpha(\lambda) = 0$, then $m_\alpha(x) = (x - \lambda)q(x)$ where $q(\alpha) \not= 0$.
> Therefore, there exists $v \in V$ such that $q(\alpha)(v) \not= 0$ and $(\alpha - \lambda \iota)(q(\alpha)(v)) = m_\alpha(\alpha)(v) = 0$ so $q(\alpha)(v)$ is an $\lambda$-eigenvector and (3) implies (1).

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 6
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 23, 24
