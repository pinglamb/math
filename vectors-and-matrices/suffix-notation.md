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

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2.11](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* [https://en.wikipedia.org/wiki/Levi-Civita_symbol](https://en.wikipedia.org/wiki/Levi-Civita_symbol)
