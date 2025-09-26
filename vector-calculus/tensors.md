---
layout: base
title: Tensors &#124; Vector Calculus
---

# Tensors
{: .page-title}

Roughly speaking, tensors are generalisations of objects like vectors and matrices which have any number of indices, i.e. $T_{ij...k}$.
The underlying object described by a tensor has to be independent of the choice of basis, meaning the components of a tensor should transform in the right way under rotations.

Consider a rotation $R$ from a basis $\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3$ to a new one $\mathbf{e}_1', \mathbf{e}_2', \mathbf{e}_3'$, we have

$$
R_{ij} = \mathbf{e}'_i \cdot \mathbf{e}_j
$$

and the components of a position vector $\mathbf{x}$ are related by

$$
x_i' = R_{ij} x_j
$$

Since we are considering rigid rotations of the coordinate axes, the transformation matrix will be orthogonal such that $R^{-1} = R^\intercal$, we have

$$
x_i = R_{ji} x_j' \qquad \text{and} \qquad {\partial x_i \over \partial x_j'} = R_{ji}  \qquad \text{and} \qquad R_{ik} R_{jk} = R_{ki} R_{kj} = \delta_{ij}
$$

With the above we can start the study of tensors of different orders.

> *Definition.*{: .def}
> A zero-order Cartesian tensor is a scalar, i.e. quantity that are invariant under rotations.

> *Definition.*{: .def}
> A first-order Cartesian tensor is a vector, i.e. the components change under rotations in a way such that
>
> $$
  \mathbf{v} = v_i \mathbf{e}_i = v_i' \mathbf{e}_i' = R_{ij} v_j \mathbf{e}_i'
  $$

> *Proposition.*{: .prop}
> The scalar product of two first-order tensors is a zero-order tensor.
>
> *Proof.*{: .prf}
>
> $$
  \mathbf{u} \cdot \mathbf{v} = u_i' v_i' = R_{ij} u_j R_{ik} v_k = \delta_{jk} u_j v_k = u_j v_j
  $$

> *Proposition.*{: .prop}
> The gradient of a zero-order tensor is a first-order tensor.
>
> *Proof.*{: .prf}
>
> $$
  F_i' = (\nabla \phi)_i' = { \partial \phi' \over \partial x_i'} = { \partial x_j \over \partial x_i' } {\partial \phi \over \partial x_j} = R_{ij} F_j
  $$

> *Proposition.*{: .prop}
> The divergence of a first-order tensor is a zero-order tensor.
>
> *Proof.*{: .prf}
>
> $$
  \left( {\partial v_i \over \partial x_i} \right)' = {\partial v_i' \over \partial x_i'} = {\partial x_j \over \partial x_i'} {\partial R_{ik} v_k \over \partial x_j}
  = R_{ij} R_{ik} {\partial v_k \over \partial x_j} = \delta_{jk} {\partial v_k \over \partial x_j} = {\partial v_j \over \partial x_j}
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 6
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 26
