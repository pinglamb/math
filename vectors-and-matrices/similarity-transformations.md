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

## Change of Basis

Every linear transformation is represented by a matrix depending on the choice of basis.
Similar matrices actually represent the same transformation with respect to different bases.

> *Definition.*{: .def}
> Let $\Set{\mathbf{e}\_i}$ and $\Set{\mathbf{e}\_j'}$ be two sets of basis vectors of $\mathbb{F}^n$.
> Since $\Set{\mathbf{e}\_i}$ is a basis, we can represent individual $\mathbf{e}\_j'$ as
>
> $$
  \mathbf{e}_j' = \sum_{i=1}^n P_{ij} \mathbf{e}_i
  $$
>
> for some numbers $P\_{ij}$.
>
> The **transformation matrix** $\mathsf{P}$ is a square $n \times n$ matrix containing the numbers $P\_{ij}$, i.e.
>
> $$
  \mathsf{P} = \begin{pmatrix}
  P_{11} & P_{12} & \cdots & P_{1n} \\
  P_{21} & P_{22} & \cdots & P_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  P_{n1} & P_{n2} & \cdots & P_{nn} \\
  \end{pmatrix}
  = \begin{pmatrix}
  \mathbf{e}_1' & \mathbf{e}_2' & \cdots & \mathbf{e}_n'
  \end{pmatrix}
  $$
>
> Similarily, we can also represent individual $\mathbf{e}\_i$ as
>
> $$
  \mathbf{e}_i = \sum_{k=1}^n Q_{ki} \mathbf{e}_k'
  $$
>
> and hence the transformation matrix $\mathsf{Q}$ is
>
> $$
  \mathsf{Q} = \begin{pmatrix}
  Q_{11} & Q_{12} & \cdots & Q_{1n} \\
  Q_{21} & Q_{22} & \cdots & Q_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  Q_{n1} & Q_{n2} & \cdots & Q_{nn} \\
  \end{pmatrix}
  = \begin{pmatrix}
  \mathbf{e}_1 & \mathbf{e}_2 & \cdots & \mathbf{e}_n
  \end{pmatrix}
  $$

> *Property.*{: .prop}
> The transformation matrices are inverses of each other, i.e.
>
> $$
  \mathsf{PQ} = \mathsf{QP} = \mathsf{I}
  $$
>
> *Proof.*{: .prf}
>
> By substitution, we have
>
> $$
  \mathbf{e}_j'
  = \sum_{i=1}^n P_{ij} \left( \sum_{k=1}^n Q_{ki} \mathbf{e}_k' \right)
  = \sum_{k=1}^n \mathbf{e}_k' \left( \sum_{i=1}^n Q_{ki} P_{ij} \right)
  $$
>
> As the set $\Set{\mathbf{e}\_j'}$ is a basis and so linearly independent, we have
>
> $$
  \mathbf{e}_j' = \sum_{k=1}^n \mathbf{e}_j' \delta_{kj}
  $$
>
> Hence,
>
> $$
  \sum_{i=1}^n Q_{ki} P_{ij} = \delta_{kj}
  $$
>
> and $\mathsf{QP} = \mathsf{I}$. Similarily, we can derive $\mathsf{PQ} = \mathbf{I}$ by a similar substitution.

> *Proposition.*{: .prop}
> Consider a vector $\mathbf{u}$, we can represent it in component form respect to bases $\Set{\mathbf{e}\_i}$ and $\Set{\mathbf{e}\_j'}$, i.e.
>
> $$
  \mathbf{u} = \sum_{i=1}^n u_i \mathbf{e}_i = \sum_{j=1}^n u_j' \mathbf{e}_j'
  = \sum_{j=1}^n u_j' \sum_{i=1} P_{ij} \mathbf{e}_i
  = \sum_{i=1}^n \mathbf{e}_i \sum_{j=1}^n P_{ij} u_j'
  $$
>
> Therefore, we have
>
> $$
  \mathsf{u} = \mathsf{Pu'} \quad \text{or} \quad \mathsf{u'} = \mathsf{P^{-1}u}
  $$

From the above, we can see that if $\mathsf{B} = \mathsf{P^{-1}AP}$, the transformation $\mathsf{B}\mathbf{v} = \mathsf{P^{-1}AP}\mathbf{v}$ consists of
changing the basis by $\mathsf{P}$, applying the same transformation $\mathsf{A}$, and then changing it back by $\mathsf{P}^{-1}$.
Therefore, $\mathsf{A}$ and $\mathsf{B}$ are the same transformation with respect to different bases.

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 5](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Gilbert Strang _Linear Algebra and Its Applications_, 2006 - Chapter 5
