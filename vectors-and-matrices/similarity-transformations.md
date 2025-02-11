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

> *Definition.*{: .def}
> A **similarity transformation** is a map from $\mathsf{A} \mapsto \mathsf{P^{-1}AP}$.

> *Proposition.*{: .prop}
> Similarity is an _equivalence_ relation.

> *Proposition.*{: .prop}
> The identity matrix (or a multiple of it) is similar only with itself (or a multiple of it).

> *Property.*{: .prop}
> Similar matrices have the same determinant.
>
> $$
  \begin{align*}
  \det(\mathsf{P^{-1}AP}) &= \det \mathsf{P}^{-1} \det \mathsf{A} \det \mathsf{P} \\
  &= \det \mathsf{A} \det(\mathsf{P^{-1}P}) \\
  &= \det \mathsf{A}
  \end{align*}
  $$

> *Property.*{: .prop}
> Similar matrices have the same trace.
>
> $$
  \begin{align*}
  Tr(\mathsf{P^{-1}AP}) &= \mathsf{P}^{-1}_{ij}\mathsf{A}_{jk}\mathsf{P}_{ki} \\
  &= \mathsf{A}_{jk}\mathsf{P}_{ki}\mathsf{P}^{-1}_{ij} \\
  &= \mathsf{A}_{jk} \delta_{kj} \\
  &= Tr(\mathsf{A})
  \end{align*}
  $$

From the above, the determinants and traces of matrices representing a map $\mathcal{A}$ with respect to different bases are the same.
Therefore, the determinant and trace of a map is well-defined.

> *Property.*{: .prop}
> Similar matrices have the same characteristic polynomial and hence the same eigenvalues.
>
> $$
  \begin{align*}
  p_{\mathsf{B}}(\lambda) &= \det(\mathsf{B} - \lambda \mathsf{I}) \\
  &= \det(\mathsf{P^{-1}AP} - \lambda \mathsf{P^{-1}IP}) \\
  &= \det(\mathsf{P}^{-1}) \det(\mathsf{A} - \lambda \mathsf{I}) \det(\mathsf{P}) \\
  &= \det(\mathsf{A} - \lambda \mathsf{I}) \det(\mathsf{P}^{-1}P) \\
  &= p_{\mathsf{A}}(\lambda)
  \end{align*}
  $$

Therefore, the characteristic polynomial of linear map is well-defined.

> *Definition.*{: .def}
> The **characteristic polynomial** of a linear map $\mathcal{A}$ is the polynomial
>
> $$
  p_{\mathcal{A}}(\lambda) = \det(\mathsf{A} - \lambda\mathsf{I})
  $$
>
> where $\mathsf{A}$ is any matrix representation of $\mathcal{A}$.

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Gilbert Strang _Linear Algebra and Its Applications_, 2006 - Chapter 5
