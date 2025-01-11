---
layout: base
title: Suffix Notation &#124; Vectors and Matrices
---

# Suffix Notation
{: .page-title}

Suffix notation is a concise way for expressing vectors (and tensors).
It is generally easier to manipulate vectors with that, together with _Einstein's summation convention_.

## Kronecker Delta

> *Definition.*{: .def}
> The **Kronecker delta** $\delta_{ij}$ is a tensor, defined by, in matrix form
>
> $$
  \begin{pmatrix}
  \delta_{11} & \delta_{12} & \delta_{13} \\
  \delta_{21} & \delta_{22} & \delta_{23} \\
  \delta_{31} & \delta_{32} & \delta_{33}
  \end{pmatrix}
  =
  \begin{pmatrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & 0 & 1
  \end{pmatrix}
  $$

> *Property.*{: .prop}
> $\delta_{ij}$ is _symmetric_, i.e.
>
> $$
  \delta_{ij} = \delta_{ji}
  $$

> *Property.*{: .prop}
> $\delta_{ii} = 3 (= n)$.

> *Property.*{: .prop}
> The delta function behaves like a suffix switching quantity, i.e.
>
> $$
  \begin{align*}
  \delta_{ij} a_j &= a_i \\
  \delta_{ij} \delta_{jk} &= \delta_{ik} \\
  \delta_{ij} A_{jk} &= A_{ik} \\
  \delta_{ij} \varepsilon_{jkl} &= \varepsilon_{ikl} \\
  \delta_{ij} \sigma_{jklmno...} &= \sigma_{iklmno...}
  \end{align*}
  $$
>
> Hence,
>
> $$
  \delta_{ij} \delta_{ji} = \delta_{ii} = 3 (= n)
  $$

## Levi-Civita Symbol / Alternating Tensor

> *Definition.*{: .def}
> The **Levi-Civita symbol** $\varepsilon_{ijk}$ or **alternating tensor** is the set of $27$ quantities such that
>
> $$
  \varepsilon_{ijk} = \begin{cases}
  +1 & \text{if } ijk \text{ is an even permutation} \\
  -1 & \text{if } ijk \text{ is an odd permutation} \\
  0  & \text{otherwise (i.e. repeated suffices)}
  \end{cases}
  $$
>
> Therefore, the non-zero components are
>
> $$
  \begin{align*}
  \varepsilon_{123} = \varepsilon_{231} = \varepsilon_{312} &= 1 \\
  \varepsilon_{213} = \varepsilon_{132} = \varepsilon_{321} &= -1 \\
  \end{align*}
  $$
>
> Further
>
> $$
  \varepsilon_{ijk} = \varepsilon_{jki} = \varepsilon_{kij} = -\varepsilon_{jik} = -\varepsilon_{ikj} = -\varepsilon_{jki}
  $$

> *Proposition.*{: .prop}
> For a symmetric tensor $s_{ij}$,
>
> $$
  \varepsilon_{ijk} s_{ij} = 0
  $$
>
> Hence,
>
> $$
  \varepsilon_{ijk} \delta_{ij} = 0
  $$
>
> *Proof.*{: .prf}
>
> By relabelling the dummy suffices, we have
>
> $$
  \varepsilon_{ijk} s_{ij} = \varepsilon_{jik} s_{ji}
  $$
>
> As $\varepsilon_{jik} = -\varepsilon_{ijk}$ and $s_{ji} = s_{ij}$, we have
>
> $$
  \varepsilon_{jik} s_{ji} = -\varepsilon_{ijk} s_{ij}
  $$
>
> As $\varepsilon_{ijk} s_{ij} = -\varepsilon_{ijk} s_{ij}$, we conclude
>
> $$
  \varepsilon_{ijk} s_{ij} = 0
  $$
>
> and so as
>
> $$
  \varepsilon_{ijk} \delta_{ij} = 0
  $$

> *Proposition.*{: .prop}
> For no repeated indices,
>
> $$
  \varepsilon_{ijk} \varepsilon_{pqr} = \begin{vmatrix}
  \delta_{ip} & \delta_{iq} & \delta_{ir} \\
  \delta_{jp} & \delta_{jq} & \delta_{jr} \\
  \delta_{kp} & \delta_{kq} & \delta_{kr} \\
  \end{vmatrix}
  $$

> *Proposition.*{: .prop}
> For one repeated index,
>
> $$
  \epsilon_{ijk}\epsilon_{ipq} = \delta_{jp}\delta_{kq} - \delta_{jq}\delta_{kp}
  $$

> *Proposition.*{: .prop}
> For two repeated indices,
>
> $$
  \varepsilon_{ijk} \varepsilon_{ijp} = 2 \delta_{kp}
  $$
>
> *Proof.*{: .prf}
>
> When $k \not = p$, both side vanishs.
> When $k = p$, there are two ways left to choose $i, j$.

> *Proposition.*{: .prop}
> For three repeated indices,
>
> $$
  \varepsilon_{ijk} \varepsilon_{ijk} = 6 (= n!)
  $$
>
> *Proof.*{: .prf}
>
> As for any distinct values of $i, j, k$, the "product" is $1$, and there are $3!$ choices.

## Basis Vectors

Let $\mathbf{e_1} = \mathbf{i}$, $\mathbf{e_2} = \mathbf{j}$ and $\mathbf{e_3} = \mathbf{k}$ be the standard basis vectors of $\mathbb{R}^3$.
Be noted that $\mathbf{e}_i$ means one of the basis vector for $i = 1, 2, 3$ instead of $\mathbf{i}$.

> *Proposition.*{: .prop}
> For any two of the basis vector,
>
> $$
  \mathbf{e}_i \cdot \mathbf{e}_j = \delta_{ij}
  $$
>
> *Proof.*{: .prf}
>
> $\mathbf{e}\_i \cdot \mathbf{e}\_j = 1$ iff $i = j$, matching the definition of $\delta_{ij}$.

> *Proposition.*{: .prop}
> In terms of suffix notation,
>
> $$
  \mathbf{a} \cdot \mathbf{e}_i = a_i
  $$

> *Proposition.*{: .prop}
> The suffix label of basis vector is interchangeable, i.e.
>
> $$
  (\mathbf{e}_j)_i = (\mathbf{e}_i)_j = \delta_{ij}
  $$
>
> *Proof.*{: .prf}
>
> The $i$-th component of $\mathbf{e}\_j$ is given by
>
> $$
  (\mathbf{e}_j)_i = \mathbf{e}_j \cdot \mathbf{e}_i = \delta_{ij}
  $$
>
> Similarily,
>
> $$
  (\mathbf{e}_i)_j = \mathbf{e}_i \cdot \mathbf{e}_j = \delta_{ij}
  $$

## Vector Algebra

> *Proposition.*{: .prop}
> The scalar/dot product is given by
>
> $$
  \mathbf{a} \cdot \mathbf{b} = \delta_{ij} a_i b_j = a_i b_i = a_j b_j
  $$

> *Proposition.*{: .prop}
> The vector/cross product is given by
>
> $$
  (\mathbf{a} \times \mathbf{b})_i = \varepsilon_{ijk} a_j b_k
  $$

> *Proposition.*{: .prop}
> The scalar triple product is given by
>
> $$
  \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = \varepsilon_{ijk} a_i b_j c_k
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c})
  &= a_i (\mathbf{b} \times \mathbf{c})_i \\
  &= \varepsilon_{ijk} a_i b_j c_k
  \end{align*}
  $$

> *Proposition.*{: .prop}
> The vector triple product is given by
>
> $$
  (\mathbf{a} \times (\mathbf{b} \times \mathbf{c}))_i = a_jb_ic_j - a_jb_jc_i
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \mathbf{a} \times (\mathbf{b} \times \mathbf{c})_i &= \epsilon_{ijk} a_j (\mathbf{b} \times \mathbf{c})_k \\
  &= \epsilon_{ijk} a_j \epsilon_{klm} b_l c_m \\
  &= -\epsilon_{kji} \epsilon_{klm} a_j b_l c_m \\
  &= -(\delta_{jl}\delta_{im} - \delta_{jm}\delta_{il}) a_j b_l c_m \\
  &= a_j b_i c_j - a_j b_j c_i \\
  &= ((\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c})_i
  \end{align*}
  $$
{: #vector-triple-product}

> *Proposition.*{: .prop}
> Cauthy-Schwarz inequality can be proved by suffix notation.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \vert \mathbf{x} \vert^2 \vert \mathbf{y} \vert^2 - \vert x \cdot y \vert^2
  &= x_ix_iy_jy_j - x_iy_ix_jy_j \\
  &= {1 \over 2}x_ix_iy_jy_j + {1 \over 2}x_jx_jy_iy_i - x_iy_ix_jy_j \\
  &= {1 \over 2}(x_iy_j - x_jy_i)(x_iy_j - x_jy_i) \\
  &\ge 0
  \end{align*}
  $$

## Matrix

> *Proposition.*{: .prop}
>
> $$
  (\mathsf{x}')_i = x_i' = A_{ij} x_j
  $$



## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2.11](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* [https://en.wikipedia.org/wiki/Levi-Civita_symbol](https://en.wikipedia.org/wiki/Levi-Civita_symbol)
