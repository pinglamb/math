---
layout: base
title: Suffix Notation &#124; Vectors and Matrices
---

# Suffix Notation

Suffix notation is a concise way for expressing vectors (and tensors).
Some manipulations can be easier with the notation.
Here are some identities that can be useful.

## Kronecker Delta

$$
\delta_{ij} v_j = v_i
$$

$$
\delta_{ij} \delta_{jk} = \delta_{ik}
$$

$$
\delta_{ij} A_{jk} = A_{ik}
$$

$$
\delta_{ij} \varepsilon_{jkl} = \varepsilon_{ikl}
$$

$$
\delta_{ij} \sigma_{jklmno...} = \sigma_{iklmno...}
$$

$$
\delta_{ij} \delta_{ji} = \delta_{ii} = 3 (= n)
$$

## Levi-Civita Symbol

$$
\varepsilon_{ijk} \delta_{jk} = 0
$$

$$
\varepsilon_{ijk} = \varepsilon_{jki} = \varepsilon_{kij} = -\varepsilon_{ikj} = -\varepsilon_{jik} = -\varepsilon_{kji}
$$

$$
\varepsilon_{ijk} \varepsilon_{lmn} = \begin{vmatrix}
\delta_{il} & \delta_{im} & \delta_{in} \\
\delta_{jl} & \delta_{jm} & \delta_{jn} \\
\delta_{kl} & \delta_{km} & \delta_{kn} \\
\end{vmatrix}
$$

For 3 repeated indices, as for any distinct values of $i, j, k$, the product is $1$, and there are $3!$ combinations. Hence,

$$
\varepsilon_{ijk} \varepsilon_{ijk} = 6 (= n!)
$$

For 2 repeated indices, when $k \not = l$, both side vanishs. When $k = l$, there are two ways left to choose $i, j$. Hence,

$$
\varepsilon_{ijk} \varepsilon_{ijl} = 2 \delta_{kl}
$$

For 1 repeated index,

$$
\varepsilon_{ijk} \varepsilon_{imn} = \delta_{jm} \delta_{kn} - \delta_{jn} \delta_{km}
$$

## Some Vector Algebra

### Dot Product

$$
\begin{align*}
\delta_{ij} a_i b_j &= a_j b_j \\
&= a_1 b_1 + a_2 b_2 + a_3 b_3 \\
&= \mathbf{a} \cdot \mathbf{b}
\end{align*}
$$

### Vector Product

$$
\begin{align*}
\varepsilon_{ijk} a_j b_k &= (\mathbf{a} \times \mathbf{b})_i
\end{align*}
$$

## Scalar Triple Product

$$
\begin{align*}
\varepsilon_{ijk} a_i b_j c_k &= a_i (\mathbf{b} \times \mathbf{c})_i \\
&= \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c})
\end{align*}
$$

We can also see that

$$
[\mathbf{b}, \mathbf{c}, \mathbf{a}] = \varepsilon_{ijk} b_i c_j a_k = \varepsilon_{kij} a_k b_i c_j = [\mathbf{a}, \mathbf{b}, \mathbf{c}]
$$

and

$$
[\mathbf{b}, \mathbf{a}, \mathbf{c}] = \varepsilon_{ijk} b_i a_j c_k = -\varepsilon_{jik} a_j b_i c_k = -[\mathbf{a}, \mathbf{b}, \mathbf{c}]
$$

## Triple Vector Product

$$
\begin{align*}
(\mathbf{a} \times (\mathbf{b} \times \mathbf{c}))_i &= \varepsilon_{ijk} a_j (\mathbf{b} \times \mathbf{c})_k \\
&= \varepsilon_{ijk} a_j \varepsilon_{klm} b_l c_m \\
&= (\delta_{il} \delta_{jm} - \delta_{im} \delta_{jl}) a_j b_l c_m \\
&= a_m c_m b_i - a_l b_l c_i \\
&= ((\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c})_i
\end{align*}
$$

## Basis Vectors

$$
e_i \cdot e_j = \delta_{ij}
$$

$$
(e_j)_i = (e_i)_j = \delta_{ij}
$$

$$
\begin{align*}
(e_j \times e_k)_i &= \varepsilon_{ilm} (e_j)_l (e_k)_m \\
&= \varepsilon_{ilm} \delta_{jl} \delta_{km} \\
&= \varepsilon_{ijk}
\end{align*}
$$

## Matrix

$$
(\mathsf{x}')_i = x_i' = A_{ij} x_j
$$

## Suffix Noatation and Tensors

Some examples of suffix notation:

$$
(\mathbf{a} \cdot \mathbf{b}) \mathbf{c} = \mathbf{d} \quad \equiv \quad a_i b_i c_j = d_j
$$

$$
\begin{align*}
((\mathbf{a} \cdot \mathbf{c})\mathbf{b} - (\mathbf{a} \cdot \mathbf{b})\mathbf{c}) &\equiv a_i c_i b_j - a_k b_k c_j \\
&\equiv a_i c_i b_j - a_i b_i c_j \\
&\equiv a_i (c_i b_j - b_i c_j)
\end{align*}
$$

### Kronecker Delta

The Kronecker delta $\delta_{ij}$ is a tensor, defined by in matrix form

$$
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

which is an identity matrix. Hence, $\delta_{ij}$ is _symmetric_, i.e.

$$
\delta_{ij} = \delta_{ji}
$$

Also,

$$
\begin{gather}
a_i \delta_{ij} = \sum_i a_i \delta_{ij} = a_j \\
\delta_{ij} a_j = \sum_j \delta_{ij} a_j = a_i
\end{gather}
$$

$$
\delta_{ij}\delta_{jk} = \sum_{j} \delta_{ij}\delta_{jk} = \delta_{ik}
$$

$$
\delta_{ii} = \sum_{i} \delta_{ii} = 3
$$

$$
a_i \delta_{ij} b_j = a_i b_i = a_j b_j = \mathbf{a} \cdot \mathbf{b}
$$

## Basis Vectors

In general, we can write $\mathbf{e_1} = \mathbf{i}$, $\mathbf{e_2} = \mathbf{j}$ and $\mathbf{e_3} = \mathbf{k}$ as the basis vectors of $\mathbb{R}^3$.

Hence,

$$
\mathbf{e_i} \cdot \mathbf{e_j} = \delta_{ij}
$$

$$
\mathbf{a} \cdot \mathbf{e_i} = a_i
$$

$$
(\mathbf{e_i})_j = (\mathbf{e_j})_i = \delta_{ij}
$$

### Levi-Civita Symbol / Alternating Tensor

Define

$$
\epsilon_{ijk} = \begin{cases}
+1 &\quad ijk \text{ is even permutation} \\
-1 &\quad ijk \text{ is odd permutation} \\
0  &\quad \text{otherwise (i.e. repeated suffices)}
\end{cases}
$$

Therefore,

$$
\begin{align*}
\epsilon_{123} = \epsilon_{231} = \epsilon_{312} &= +1 \\
\epsilon_{213} = \epsilon_{132} = \epsilon_{321} &= -1 \\
\epsilon_{111} = \epsilon_{112} = \,... &= 0 \\
\end{align*}
$$

Hence,

$$
\epsilon_{123} = \epsilon_{231} = \epsilon_{312} = -\epsilon_{213} = -\epsilon_{132} = -\epsilon_{321}
$$

For a symmetric tensor $s_{ij}$,

$$
\epsilon_{ijk} s_{ij} = \epsilon_{jik} s_{ji} = - \epsilon_{ijk} s_{ij}
$$

Hence,

$$
\epsilon_{ijk} s_{ij} = 0
$$

By expansion of the formula, we have

$$
(\mathbf{a} \times \mathbf{b})_i = \epsilon_{ijk} a_j b_k
$$

The following is an useful identity

$$
\epsilon_{ijk}\epsilon_{ipq} = \delta_{jp}\delta_{kq} - \delta_{jq}\delta_{kp}
$$

With the above, ths scalar triple product is given by

$$
\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = \epsilon_{ijk} a_i b_j c_k
$$

and vector triple product

$$
\begin{align*}
\mathbf{a} \times (\mathbf{b} \times \mathbf{c})_i &= \epsilon_{ijk} a_j (\mathbf{b} \times \mathbf{c})_k \\
&= \epsilon_{ijk} a_j \epsilon_{klm} b_l c_m \\
&= -\epsilon_{kji} \epsilon_{klm} a_j b_l c_m \\
&= -(\delta_{jl}\delta_{im} - \delta_{jm}\delta_{il}) a_j b_l c_m \\
&= a_j b_i c_j - a_j b_j c_i \\
&= ((\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c})_i
\end{align*}
$$

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2.11](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* [https://en.wikipedia.org/wiki/Levi-Civita_symbol](https://en.wikipedia.org/wiki/Levi-Civita_symbol)
