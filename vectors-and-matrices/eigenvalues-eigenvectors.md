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

> *Definition.*{: .def}
> The **characteristic polynomial** of the matrix $\mathsf{A}$ is the polynomial
>
> $$
  p_{\mathsf{A}}(\lambda) = \det(\mathsf{A} - \lambda\mathsf{I})
  $$
>
> which is an $n$-th order polynomial in $\lambda$.

> *Definition.*{: .def}
> The **characteristic equation** of the matrix $\mathsf{A}$ is the equation
>
> $$
  p_{\mathsf{A}}(\lambda) = \det(\mathsf{A} - \lambda\mathsf{I}) = 0
  $$

## Reference

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
