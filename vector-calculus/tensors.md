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
> A zero-order Cartesian tensor is quantity that is invariant under rotations, i.e. a scalar.

> *Definition.*{: .def}
> A first-order Cartesian tensor is quantity with components that change under rotations following the condition
>
> $$
  v_i' = R_{ij} v_j \qquad \text{and} \qquad v_i = R_{ji} v_j'
  $$
>
> i.e. a vector.

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

Following on from zero-order tensor with no subscripts and first-order tensor with one subscript, we can extend this idea to quantities that require two or more subscripts to identify a particular element.

> *Definition.*{: .def}
> A second-order Cartesian tensor is quantity with components that change under rotations following the condition
>
> $$
  T_{ij}' = R_{ik} R_{jl} T_{kl} \qquad \text{and} \qquad T_{ij} = R_{ki} R_{lj} T_{kl}'
  $$

> *Definition.*{: .def}
> A $p$-order Cartesian tensor is quantity with components that change under rotations following the condition
>
> $$
  T_{i_1 i_2 ... i_p}' = R_{i_1 j_1} R_{i_2 j_2} ... R_{i_p j_p} T_{j_1 j_2 ... j_p}
  \qquad \text{and} \qquad
  T_{i_1 i_2 ... i_p}  = R_{j_1 i_1} R_{j_2 i_2} ... R_{j_p i_p} T_{j_1 j_2 ... j_p}'
  $$

A second-order tensor is geometrically like linear map that transform one vector into another without reference to any coordinate system, and behaves in the same way under orthogonal transformations $\mathsf{T}' = \mathsf{RTR'}$.
However, not all linear maps are second-order tensors. The critical idea behind tensors is that all the subscripts must refer to the same coordinate system.
For example, a second-order tensor in 3D has 9 components because the underlying coordinate system has $3$ axes, and therefore $3 \times 3$ combinations among them.
In order to identify a quantity, we will need a value for each of them, i.e. $xx, xy, xz, yx, yy, yz, zx, zy, zz$ and requires two subscripts.

In the discussion of [differential operators](differential-operators.md), we only define the gradient of scalar field.
With tensors, we can define the gradient of vector field (or generalized to any order).

> *Proposition.*{: .prop}
> The gradient of a first-order tensor is a second-order tensor.
>
> *Proof.*{: .prf}
>
> $$
  T_{ij}' = { \partial v_i' \over \partial x_j'} = R_{ik} { \partial x_l \over \partial x_j'} { \partial v_k \over \partial x_l } = R_{ik} R_{jl} T_{kl}
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 6
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 26
