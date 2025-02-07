---
layout: base
title: Eigenvalues and Eigenvectors &#124; Vectors and Matrices
---

# Eigenvalues and Eigenvectors
{: .page-title}

> *Definition.*{: .def}
> Let $\mathcal{A}: \mathbb{F}^n \to \mathbb{F}^n$ be a linear map.
> If
>
> $$
  \mathcal{A}(\mathbf{x}) = \lambda \mathbf{x}
  $$
>
> for some non-zero vector $\mathbf{x} \in \mathbb{F}^n$ and $\lambda \in \mathbf{F}$,
> then $\mathbf{x}$ is an **eigenvector** of $\mathcal{A}$ with **eigenvalue** $\lambda$.

> *Definition.*{: .def}
> Let $\mathsf{A}$ be the $n \times n$ matrix associated with the map $\mathcal{A}$ for a given basis.
> Consistent with the definition for maps, if
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
> By Fundamental Theorem of Algebra, for maps from $\mathbb{C}^n$ to $\mathbb{C}^n$ has $n$ eigenvalues (each counted with multiplicity).

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

## Eigenspaces

> *Definition.*{: .def}
> The **eigenspace** of $\lambda$, denoted by $E\_{\lambda}$, is the subspace containing the set of all eigenvectors corresponding to $\lambda$, together with $\mathbf{0}$.
> It is a subspace because it is the kernel/nullspace of $(\mathsf{A} - \lambda\mathsf{I})\mathbf{x} = \mathbf{0}$.


## Reference

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
