---
layout: base
title: Eigenvalues and Eigenvectors &#124; Vectors and Matrices
---

# Eigenvalues and Eigenvectors
{: .page-title}

Eigenvalues and eigenvectors provide a different way of factorizing matrices, such that we can raise it to some powers, and are really useful for studying certain kind of problems.

> *Definition.*{: .def}
> Let $\mathsf{A}$ be the $n \times n$ matrix. If
>
> $$
  \mathsf{A}\mathbf{x} = \lambda \mathbf{x}
  $$
>
> for some non-zero vector $\mathbf{x} \in \mathbb{F}^n$ and $\lambda \in \mathbf{F}$,
> then $\mathbf{x}$ is an **eigenvector** of $\mathsf{A}$ with **eigenvalue** $\lambda$.
>
> The equation can be rewritten as
>
> $$
  (\mathsf{A} - \lambda \mathsf{I}) \mathbf{x} = \mathbf{0}
  $$
>
> which has non-zero solution $\mathbf{x}$ iff
>
> $$
  \det(\mathsf{A} - \lambda \mathsf{I}) = 0
  $$

It means that the eigenvalues are chosen such that the matrix $\mathsf{A} - \lambda\mathsf{I}$ is singular,
then the corresponding eigenvector is in the nullspace and can be found by elimination.

> *Definition.*{: .def}
> The **characteristic polynomial** of the matrix $\mathsf{A}$ is the polynomial
>
> $$
  p_{\mathsf{A}}(\lambda) = \det(\mathsf{A} - \lambda\mathsf{I})
  $$
>
> which is an $n$-th order polynomial in $\lambda$.
> The roots of the characteristic polynomial are the eigenvalues of $\mathsf{A}$.

> *Definition.*{: .def}
> The **characteristic equation** of the matrix $\mathsf{A}$ is the equation
>
> $$
  p_{\mathsf{A}}(\lambda) = \det(\mathsf{A} - \lambda\mathsf{I}) = 0
  $$

> *Property.*{: .prop}
> By Fundamental Theorem of Algebra, there are $n$ eigenvalues (each counted with multiplicity).

> *Property.*{: .prop}
> Suppose
>
> $$
  p_{\mathsf{A}}(\lambda) = c_0 + c_1 \lambda + ... + c_n \lambda^n
  $$
>
> and the $n$ eigenvalues are $\lambda_1, \lambda_2, ..., \lambda_n$. Then
>
> + $c_0 = \det(\mathsf{A}) = \lambda_1 \lambda_2 ... \lambda_n$,
>
> + $c_n = (-1)^n$.
>
> + $c_{n-1} = (-1)^{n-1} Tr(\mathsf{A}) = (-1)^{n-1}(\lambda_1 + \lambda_2 + ... + \lambda_n)$,
>
> *Proof.*{: .prf}
>
> $$
  p_{\mathsf{A}}(\lambda) = \det(\mathsf{A} - \lambda \mathsf{I}) = \sum_{i_1i_2...i_n} \varepsilon_{i_1i_2...i_n} (A_{i_1 1} - \lambda \delta_{i_1 1})\ldots(A_{i_n n} - \lambda \delta_{i_n n})
  $$
>
> + By having $\lambda = 0$,
>
    $$
    p_{\mathsf{A}}(0) = c_0 = \det(\mathsf{A})
    $$
>
> + From the summation, the coeffient of $\lambda^{n}$ comes from only the diagonal, so $c\_n = (-1)^n$. Hence,
>
>   $$
    p_{\mathsf{A}}(\lambda) = (\lambda_1 - \lambda)(\lambda_2 - \lambda)...(\lambda_n - \lambda)
    $$
>
> + From the summation, the coeffient of $\lambda^{n-1}$ comes from only the diagonal, and compare that with the factorized $p\_{\mathsf{A}}(\lambda)$ above, we have
>
>  $$
   \begin{align*}
   c_{n-1} &= (-1)^{n-1}(A_{11} + A_{22} + ... + A_{nn}) \\
           &= (-1)^{n-1}Tr(\mathsf{A}) \\
           &= (-1)^{n-1}(\lambda_1 + \lambda_2 + ... + \lambda_n)
   \end{align*}
   $$

This is useful for checking if the eigenvalues we found are correct.

> *Property.*{: .prop}
> The eigenvalues of $\mathsf{A}^\intercal$ are the same as $\mathsf{A}$.
>
> *Proof.*{: .prf}
>
> $$
  \det(\mathsf{A}^\intercal - \lambda \mathsf{I}) = \det((\mathsf{A} - \lambda \mathsf{I})^\intercal) = \det(\mathsf{A} - \lambda \mathsf{I})
  $$

## Eigenspaces

The eigenvalues and eigenvectors are useful if we are able to have a full set of $n$ linearly independent eigenvectors for a $n \times n$ matrix.
Later on, we will see that if we have $n$ distinct eigenvalues, their corresponding eigenvectors have to be linearly independent.
However, if we have repeated roots for the characteristic polynomial, we need to further analyze if there are other linearly independent eigenvectors that repeated eigenvalue.

> *Definition.*{: .def}
> The **eigenspace** of $\lambda$, denoted by $E\_{\lambda}$, is the subspace containing the set of all eigenvectors corresponding to $\lambda$, together with $\mathbf{0}$.
> It is a subspace because it is the kernel/nullspace of $(\mathsf{A} - \lambda\mathsf{I})\mathbf{x} = \mathbf{0}$.

> *Definition.*{: .def}
> The **algebraic multiplicity** of an eigenvalue $\lambda$ is the multiplicity of that as a root of the characteristic polynomial.
> An eigenvalue with an algebraic multiplicity greater than one is said to be **degenerate**.

> *Definition.*{: .def}
> The **geometric multiplicity** of an eigenvalue $\lambda$ is the maximum number of linearly independent eigenvectors corresponding to $\lambda$.
> It is the dimension of the eigenspace of $\lambda$.

> *Definition.*{: .def}
> The **defect** of an eigenvalue $\lambda$ is the difference between its algebraic and geometric multiplicity.

> *Theorem.*{: .thm}
> Suppose that the matrix $\mathsf{A}$ has distinct eigenvalues $\lambda\_1, ... \lambda\_r$ and eigenvectors $\mathbf{x}\_1, ..., \mathsf{x}\_r$,
> then $\mathbf{x}\_1, ... \mathbf{x}\_r$ are linearly independent.
>
> *Proof.*{: .prf}
>
> Suppose they are linearly dependent. Let
>
> $$
  c_1 \mathbf{y}_1 + c_2 \mathbf{y}_2 + ... + c_m \mathbf{y}_m = \mathbf{0}
  $$
>
> be the smallest set of eigenvectors such that they have a non-trival linear combination, i.e. $c\_1 \not= 0$.
>
> Multiplying the equation by $\mathsf{A}$ and subtract the $\lambda\_1$ multiple of the above equation, we have
>
> $$
  c_2 (\lambda_2 - \lambda_1) \mathbf{y}_2 + ... + c_m (\lambda_m - \lambda_1) \mathbf{y}_m = \mathbf{0}
  $$
>
> As all the eigenvalues are distinct, we found a shorter non-trival linear combination which contradicts with the above.

> *Corollary.*{: .cor}
> A matrix with $n$ disinct eigenvalues must have $n$ linearly independent eigenvectors.
> These $n$ eigenvectors form a basis for $\mathbb{F}^n$.

It is important to note that even though there aren't $n$ distinct eigenvalues,
we might still be able to find $n$ linearly independent eigenvectors.

## Diagonalization

> *Definition.*{: .def}
> A $n \times n$ matrix $\mathsf{D} = \Set{D\_{ij}}$ is a diagonal matrix if $D\_{ij} = 0$ whenver $i \not= j$, i.e.
>
> $$
  \mathsf{D} = \begin{pmatrix}
  D_{11} \\
  & D_{22} \\
  & & \ddots \\
  & & & D_{nn}
  \end{pmatrix}
  $$

> *Property.*{: .prop}
> The computation to raise $\mathsf{D}$ to the powers of $m$ is trivial, i.e.
>
> $$
  \mathsf{D}^m = \begin{pmatrix}
  D_{11}^m \\
  & D_{22}^m \\
  & & \ddots \\
  & & & D_{nn}^m
  \end{pmatrix}
  $$

> *Theorem.*{: .thm}
> Suppose a $n \times n$ matrix has $n$ linearly independent eigenvectors.
> Let $\mathsf{S}$ be a matrix with these eigenvectors as columns,
> then $\mathsf{\Lambda} = \mathsf{S^{-1}AS}$ is a diagonal matrix with the eigenvalues of $\mathsf{A}$ are on the diagonal, i.e.
>
> $$
  \mathsf{\Lambda} = \mathsf{S^{-1}AS} = \begin{pmatrix}
  \lambda_1 \\
  & \lambda_2 \\
  & & \ddots \\
  & & & \lambda_n \\
  \end{pmatrix}
  $$
>
> $\mathsf{S}$ is called the eigenvector matrix and $\mathsf{\Lambda}$ is called the eigenvalue matrix.
>
> *Proof.*{: .prf}
>
> Let $\mathbf{x}\_i$ be the linearly independent eigenvectors of $\mathsf{A}$, we have
>
> $$
  \begin{align*}
  \mathsf{AS} &= \mathsf{A}\begin{pmatrix}
  \mathbf{x}_1 & \mathbf{x}_2 & \cdots & \mathbf{x}_n
  \end{pmatrix} \\
  &= \begin{pmatrix}
  \mathsf{A}\mathbf{x}_1 & \mathsf{A}\mathbf{x}_2 & \cdots & \mathsf{A}\mathbf{x}_n
  \end{pmatrix} \\
  &= \begin{pmatrix}
  \lambda_1\mathbf{x}_1 & \lambda_2\mathbf{x}_2 & \cdots & \lambda_n\mathbf{x}_n
  \end{pmatrix} \\
  &= \begin{pmatrix}
  \mathbf{x}_1 & \mathbf{x}_2 & \cdots & \mathbf{x}_n
  \end{pmatrix} \begin{pmatrix}
  \lambda_1 \\
  & \lambda_2 \\
  & & \ddots \\
  & & & \lambda_n \\
  \end{pmatrix} \\
  &= \mathsf{S\Lambda}
  \end{align*}
  $$
>
> As the columns of $\mathsf{S}$ is linearly independent, it is invertible. Hence,
>
> $$
  \mathsf{\Lambda} = \mathsf{S^{-1}AS}
  $$

## Matrix Powers

> *Proposition.*{: .prop}
> The eigenvalues of $\mathsf{A}^k$ are $\lambda\_1^k, ... \lambda\_n^k$ and each eigenvector of $\mathsf{A}$ is still an eigenvector of $\mathsf{A}^k$.
>
> *Proof.*{: .prf}
>
> Given $\mathsf{A}\mathbf{x} = \lambda \mathbf{x}$, multiplying both side by $\mathsf{A}$ again we have
>
> $$
  \mathsf{A}^2\mathbf{x} = \mathsf{A}(\lambda\mathbf{x}) = \lambda (\mathsf{A} \mathbf{x}) = \lambda^2 \mathbf{x}
  $$
>
> Therefore, $\lambda^2$ is the eigenvalue of $\mathsf{A}^2$ and the eigenvectors are unchanged and the same process can be repeated to the $k$-th power.

If we are able to factorize $\mathsf{A}$ as $\mathsf{S \Lambda S^{-1}}$, we can find the powers of $\mathsf{A}$ by

$$
\mathsf{A}^k = (\mathsf{S \Lambda S^{-1}})(\mathsf{S \Lambda S^{-1}})...(\mathsf{S \Lambda S^{-1}}) = \mathsf{S \Lambda^k S^{-1}}
$$

> *Proposition.*{: .prop}
> If $\mathsf{A}$ is invertible, the eigenvalues of $\mathsf{A}^{-1}$ are $1/\lambda\_i$.
>
> *Proof.*{: .prf}
>
> Given $\mathsf{A}\mathbf{x} = \lambda \mathbf{x}$, we have
>
> $$
  {1 \over \lambda} \mathbf{x} = \mathsf{A}^{-1} \mathbf{x}
  $$

## Reference

* Gilbert Strang _Linear Algebra and Its Applications_, 2006 - Chapter 5
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
