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

With the above we can start the study of tensors of different ranks.

> *Definition.*{: .def}
> A rank $0$ Cartesian tensor is the set of quantities that is invariant under rotations, i.e. a scalar.

> *Definition.*{: .def}
> A rank $1$ Cartesian tensor is the set of quantities with components that change under rotations following the condition
>
> $$
  v_i' = R_{ij} v_j \qquad \text{and} \qquad v_i = R_{ji} v_j'
  $$
>
> i.e. a vector.

> *Proposition.*{: .prop}
> The scalar product of two rank $1$ tensors is a rank $0$ tensor.
>
> *Proof.*{: .prf}
>
> $$
  \mathbf{u} \cdot \mathbf{v} = u_i' v_i' = R_{ij} u_j R_{ik} v_k = \delta_{jk} u_j v_k = u_j v_j
  $$

> *Proposition.*{: .prop}
> The gradient of a rank $0$ tensor is a rank $1$ tensor.
>
> *Proof.*{: .prf}
>
> $$
  F_i' = (\nabla \phi)_i' = { \partial \phi' \over \partial x_i'} = { \partial x_j \over \partial x_i' } {\partial \phi \over \partial x_j} = R_{ij} F_j
  $$

> *Proposition.*{: .prop}
> The divergence of a rank $1$ tensor is a rank $0$ tensor.
>
> *Proof.*{: .prf}
>
> $$
  \left( {\partial v_i \over \partial x_i} \right)' = {\partial v_i' \over \partial x_i'} = {\partial x_j \over \partial x_i'} {\partial R_{ik} v_k \over \partial x_j}
  = R_{ij} R_{ik} {\partial v_k \over \partial x_j} = \delta_{jk} {\partial v_k \over \partial x_j} = {\partial v_j \over \partial x_j}
  $$

Following on from rank $0$ tensor with no subscripts and rank $1$ tensor with one subscript, we can extend this idea to quantities that require two or more subscripts to identify a particular element.

> *Definition.*{: .def}
> A rank $2$ Cartesian tensor is the set of quantities with components that change under rotations following the condition
>
> $$
  T_{ij}' = R_{ik} R_{jl} T_{kl} \qquad \text{and} \qquad T_{ij} = R_{ki} R_{lj} T_{kl}'
  $$

> *Definition.*{: .def}
> A rank $p$ Cartesian tensor is the set of quantities with components that change under rotations following the condition
>
> $$
  T_{i_1 i_2 ... i_p}' = R_{i_1 j_1} R_{i_2 j_2} ... R_{i_p j_p} T_{j_1 j_2 ... j_p}
  \qquad \text{and} \qquad
  T_{i_1 i_2 ... i_p}  = R_{j_1 i_1} R_{j_2 i_2} ... R_{j_p i_p} T_{j_1 j_2 ... j_p}'
  $$

A rank $2$ tensor is geometrically like linear map that transform one vector into another without reference to any coordinate system, and behaves in the same way under orthogonal transformations $\mathsf{T}' = \mathsf{RTR'}$.
However, not all linear maps are rank $2$ tensors. The critical idea behind tensors is that all the subscripts must refer to the same coordinate system.
For example, a rank $2$ tensor in $\mathbb{R}^3$ has 9 components because the underlying coordinate system has $3$ axes, and therefore $3 \times 3$ combinations among them.
In order to identify a quantity, we will need a value for each of them, i.e. $xx, xy, xz, yx, yy, yz, zx, zy, zz$ and requires two subscripts.

In the discussion of [differential operators](differential-operators.md), we only define the gradient of scalar field.
With tensors, we can define the gradient of vector field (and generalized to any order).

> *Proposition.*{: .prop}
> The gradient of a rank $1$ tensor is a rank $2$ tensor.
>
> *Proof.*{: .prf}
>
> $$
  T_{ij}' = { \partial v_i' \over \partial x_j'} = R_{ik} { \partial x_l \over \partial x_j'} { \partial v_k \over \partial x_l } = R_{ik} R_{jl} T_{kl}
  $$

## Algebra of Tensors

> *Proposition.*{: .prop}
> The sum and difference of two tensors of the same rank is also a tensor.
> Multiplying a tensor by a constant is also a tensor.
>
> *Proof.*{: .prf}
>
> It follows immediately from the linearity of a rotation of coordinates.

> *Proposition.*{: .prop}
> If $T_{i_1 i_2 ... i_p}$ are the components of a tensor, then so as the set of quantities formed by interchanging the order of indices, e.g. $T_{i_2 i_1 ... i_p}$.

> *Definition.*{: .def}
> Suppose $S$ is a tensor of rank $p$ and $T$ is a tensor of ranks $q$.
> The **outer/tensor product** of them, denoted by $S \otimes T$, is defined by
>
> $$
  (S \otimes T)_{i_1 i_2 ... i_p j_1 j_2 ... j_q} = S_{i_1 i_2 ... i_p} T_{j_1 j_2 ... j_q}
  $$

> *Proposition.*{: .prop}
> The outer product of two tensors of rank $p$ and $q$ respectively is also a tensor of rank $p + q$.
>
> *Proof.*{: .prf}
>
> Using outer product of two first-rank tensors $\mathbf{u}$ and $\mathbf{v}$ as example, we have
>
> $$
  T_{ij}' = u_i' v_j' = R_{ik} R_{jl} u_k v_l = R_{ik} R_{jl} T_{kl}
  $$

> *Proposition.*{: .prop}
> Suppose $S$ is a tensor $S$ of rank $p$.
> Then **contraction** on two indices using $\delta_{ij}$ results with a tensor $T$ of rank $p - 2$, i.e.
>
> $$
  T_{k_1 ... k_{p-2}} = \delta_{ij} S_{ij k_1 ... k_{p-2}}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  T_{i i k_1 .. k_{p-2}}' &= R_{im} R_{in} R_{k_1 l_1} ... R_{k_{p-2} l_{p-2}} T_{m n l_1 ... l_{p-2}} \\
  &= \delta_{mn} R_{k_1 l_1} ... R_{k_{p-2} l_{p-2}} T_{m n l_1 ... l_{p-2}} \\
  &= R_{k_1 l_1} ... R_{k_{p-2} l_{p-2}} T_{m m l_1 ... l_{p-2}}
  \end{align*}
  $$

For example, a second-rank tensor can be contracted to a scalar, which we call the _trace_, i.e. $\text{Tr}\, T = T_{ii}$.
Another example is the scalar product of two vectors, which we first have the outer product of two vectors and contracting it to produce a scalar (rank $1 + 1 - 2$).

## Quotient Law

> *Proposition.*{: .prop}
> **[Quotient Law]**
> Suppose that $T$ and $U$ are tensors.
> If
>
> $$
  S_{i_1 ... k ... i_p} T_{j_1 ... k ... j_q} = U_{i_1 ... i_p j_1 ... j_q}
  $$
>
> holds for all rotations then $S$ is a tensor.
>
> *Proof.*{: .prf}
>
> We use $p = q = 2$ as example to demonstrate the principle.
> Given that $S_{ik} T_{jk} = U_{ij}$, then
>
> $$
  \begin{align*}
  S_{ik}' T_{jk}' = U_{ij}' &= R_{il} R_{jm} U_{lm}  \\
  &= R_{il} R_{jm} S_{ln} T_{mn} \\
  &= R_{il} R_{jm} S_{ln} R_{om} R_{kn} T_{ok}' \\
  &= R_{il} R_{kn} S_{ln} T_{jk}'
  \end{align*}
  $$
>
> Therefore, we have
>
> $$
  (S_{ik}' - R_{il} R_{kn} S_{ln}) T_{jk}' = 0 \quad \implies \quad S_{ik}' = R_{il} R_{kn} S_{ln}
  $$
>
> Similar arguments can be applied for the case $S_{ik} T_{kj} = U_{ij}$.

Quotient law provides a convenient way to test wheater a given quantity is a tensor.
For example, if we want to check if $T_{i_1 i_2 ... i_{p+q}}$ is a tensor, we can contract it with a rank $q$ tensor and check if the result is a rank $p$ tensor.

## Symmetry and Anti-Symmetry

> *Definition.*{: .def}
> A tensor is **symmetric** with respect to its first two subscripts if $T_{i_2 i_1 ... i_p} = T_{i_1 i_2 ... i_p}$.

> *Definition.*{: .def}
> A tensor is **antisymmetric** with respect to its first two subscripts if $T_{i_2 i_1 ... i_p} = -T_{i_1 i_2 ... i_p}$

> *Definition.*{: .def}
> A tensor is **totally antisymmetric** if it is antisymmetric in all pairs of indices.

> *Proposition.*{: .prop}
> Any tensor can always be written as the sum of a symmetric tensor $S_{i_1 i_2 ... i_p}$ and an antisymmetric tensor $A_{i_1 i_2 ... i_p}$, i.e.
>
> $$
  T_{i_1 i_2 ... i_p} = {1 \over 2} (T_{i_1 i_2 ... i_p} + T_{i_2 i_1 ... i_p}) + {1 \over 2} (T_{i_1 i_2 ... i_p} - T_{i_2 i_1 ... i_p}) = S_{i_1 i_2 ... i_p} + A_{i_1 i_2 ... i_p}
  $$

## Invariant Tensors

There are two important invariant tensors in $\mathbb{R}^n$.

> *Definition.*{: .def}
> A tensor is **invariant** under a given rotation $R$ if
>
> $$
  T_{i_1 ... i_p}' = R_{i_1 j_1} ... R_{i_p j_p} T_{j_1 ... j_p} = T_{i_1 ... i_p}
  $$

> *Definition.*{: .def}
> A tensor is **isotropic** if it is invariant under all rotations $R$.

Obviously, all tensors of rank $0$ are isotropic.

> *Proposition.*{: .prop}
> The **Kronecker delta** $\delta_{ij}$ is a rank $2$ isotropic tensor.
>
> *Proof.*{: .prf}
>
> $$
  \delta_{ij}' = R_{ik} R_{jl} \delta_{kl} = R_{ik} R_{jk} = \delta_{ij}
  $$

> *Proposition.*{: .prop}
> The **Levi-Civita Symbol** $\varepsilon_{i_i i_2 ... i_p}$ is a rank $p$ totally anti-symmetric tensor.
> It is invariant when $R \in SO(p)$ but not $R \in O(p)$.
>
> *Proof.*{: .prf}
>
> For a $p \times p$ matrix, we have
>
> $$
  (\det A) \varepsilon_{i_1 i_2 ... i_p} = A_{i_1 j_1} A_{i_2 j_2} ... A_{i_p j_p} \varepsilon_{j_1 j_2 ... j_n}
  $$
>
> It can be verified this with the use of Laplace expansion,
>
> + when any two of the indices take the same value, the R.H.S. is the determinant of a matrix with a repeated row, so both side is $0$;
>
> + when the indices are of even permutation, the R.H.S. is the determinant of the matrix in Laplace expansion form;
>
> + when the indices are of odd permutation, the R.H.S. is the determinant of the same matrix will two rows interchanged, and both side is $- \det A$.
>
> Hence,
>
> $$
  \varepsilon_{i_1 i_2 ... i_p}' = R_{i_1 j_1} R_{i_2 j_2} ... R_{i_n j_n} \varepsilon_{j_1 j_2 ... j_n} = \det R \, \varepsilon_{i_1 i_2 ... i_p}
  $$
>
> and whether $\varepsilon_{i_1 i_2 ... i_p}$ is invariant depends on $\det R = \pm 1$.

> *Proposition.*{: .prop}
> In $\mathbb{R}^3$, $T_{ij} = \alpha \delta_{ij}$ is the only rank $2$ non-zero isotropic tensor,
> $T_{ijk} = \beta \varepsilon_{ijk}$ is the only rank $3$ isotropic tensor
> and there are no isotropic tensors of rank $1$.

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 6
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 26
