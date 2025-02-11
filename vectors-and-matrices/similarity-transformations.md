---
layout: base
title: Similarity Transformations &#124; Vectors and Matrices
---

# Similarity Transformations
{: .page-title}

> *Definition.*{: .def}
> The $n \times n$ matrices $\mathsf{A}$ and $\mathsf{B}$ are **similar/conjugate** if for some invertible matrix $\mathsf{P}$
>
> $$
  \mathsf{B} = \mathsf{P^{-1}AP}
  $$

> *Proposition.*{: .prop}
> Similarity is an _equivalence_ relation.

> *Definition.*{: .def}
> A **similarity transformation** is a map from $\mathsf{A} \mapsto \mathsf{P^{-1}AP}$.

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

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Gilbert Strang _Linear Algebra and Its Applications_, 2006 - Chapter 5
