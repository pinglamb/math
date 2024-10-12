---
layout: base
title: Matrices &#124; Vectors and Matrices
---

# Matrices

As described in [Linear Maps](linear-maps.md), matrices can be used to represent linear transformations.
Just like [vectors](vectors.md), we can do all sorts of algebraic operations on matrices.

## Addition

Let $\mathcal{A}: V \to W$ and $\mathcal{B}: V \to W$ be linear maps.
The linear map $(\mathcal{A} + \mathcal{B}): V \to W$ is defined by

$$
(\mathcal{A} + \mathcal{B})(\mathbf{x}) = \mathcal{A}(\mathbf{x}) + \mathcal{B}(\mathbf{x})
$$

For matrices $\mathsf{A}, \mathsf{B}, \mathsf{A} + \mathsf{B}$ associated with the maps, we have

$$
(\mathsf{A} + \mathsf{B})_{ij} x_j = (\mathsf{A} + \mathsf{B})(\mathbf{x})_i = \mathsf{A}(\mathbf{x})_i + \mathsf{B}(\mathbf{x})_i = (\mathsf{A}_{ij} + \mathsf{B}_{ij}) x_j
$$

Hence,

$$
\mathsf{A} + \mathsf{B} = \Set{\mathsf{A}_{ij} + \mathsf{B}_{ij}}
$$

## Multiplication by Scalar

Let $\mathcal{A}: V \to W$ be a linear map.
For a given $\lambda \in \mathbb{F}$, the linear map $\lambda\mathcal{A}$ is defined by

$$
(\lambda\mathcal{A})(\mathbf{x}) = \lambda(\mathcal{A}(\mathbf{x}))
$$

We have

$$
(\lambda\mathsf{A})_{ij} x_j = (\lambda\mathsf{A})(\mathbf{x})_i = \lambda(\mathsf{A}(\mathbf{x})_i) = \lambda(\mathsf{A}_{ij} x_j) = (\lambda\mathsf{A}_{ij}) x_j

$$

Hence,

$$
\lambda\mathsf{A} = \Set{\lambda\mathsf{A}_{ij}}
$$

We can see that with the above definitions, after some checks, matrix forms a vector space.

### Matrix Multiplication
