---
layout: base
title: Spanning Sets, Bases and Higher Dimentional Spaces &#124; Vectors and Matrices
---

# Higher Dimentional Spaces
{: .page-title}

## Bases and Components

### Linear Dependency

In $\mathbb{R}^3$ (similar argument for $\mathbb{R}^2$, the vector

$$
\mathbf{d} = \lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}
$$

is described as a linear combination of $\mathbf{a},\mathbf{b}, \mathbf{c}$.

If for vectors $\mathbf{a},\mathbf{b}, \mathbf{c}$,

$$
\lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}= \mathbf{0} \iff \lambda = \mu = \nu = 0
$$

then $\mathbf{a},\mathbf{b}, \mathbf{c}$ are linear independent. The reason for that is if let say $\lambda \not = 0$,
we can write $\mathbf{a} = -{\mu \over \lambda}\mathbf{b} - {\nu \over \lambda}\mathbf{c}$,
which is a linear combination of other vectors and therefore they are linearly dependent.

### Spanning Set and Basis

A set of vectors $\\{\mathbf{a}, \mathbf{b}\\}$ is a spanning set which spans $\mathbb{R}^2$ if for all vectors $\mathbf{r} \in \mathbb{R}^2$, there exists some $\lambda, \mu \in \mathbb{R}$ such that

$$
\mathbf{r} = \lambda\mathbf{a} + \mu\mathbf{b}
$$

$\\{\mathbf{a}, \mathbf{b}\\}$ spans $\mathbb{R}^2$ if $\mathbf{a} \times \mathbf{b} = \mathbf{0}$ (non-parallel).

For any vector $\mathbf{r} \in \mathbb{R}^2$, the components $(\lambda, \mu)$ are _unique_.

We said $\\{\mathbf{a}, \mathbf{b}\\}$ is a basis of the set of vectors in $\mathbb{R}^2$ if it is a spanning set and linear independent.

In $\mathbb{R}^2$, to find $\lambda$ and $\mu$ for $\vec{OP}$ geometrically, we can draw a line through $P$ which is parallel to $OA$ and intersects with $OB$ (or its extension) at $N$.
We have $\vec{OP} = \vec{ON} + \vec{NP} = \mu\mathbf{b} + \lambda\mathbf{a}$.

The same concept can be extended to $\mathbb{R}^3$,
a set of vectors $\\{\mathbf{a}, \mathbf{b}\\}, \mathbf{c}\\}$ is a spanning set which spans $\mathbb{R}^3$ if for all vectors $\mathbf{r} \in \mathbb{R}^3$, there exists some $\lambda, \mu, \nu \in \mathbb{R}$ such that

$$
\mathbf{r} = \lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}
$$

$\\{\mathbf{a}, \mathbf{b}, \mathbf{c}\\}$ spans $\mathbb{R}^3$ if $\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = 0$ (non-coplanar) and is a basis of $\mathbb{R}^3$.

The components $(\lambda, \mu, \nu)$ are _unique_.
For any $\mathbf{r} = \lambda \mathbf{a} + \mu \mathbf{b} + \nu \mathbf{c}$, we have

$$
\mathbf{r} \cdot (\mathbf{b} \times \mathbf{c}) = \lambda \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) + \mu \mathbf{b} \cdot (\mathbf{b} \times \mathbf{c}) + \nu \mathbf{c} \cdot (\mathbf{b} \times \mathbf{c}) = \lambda \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c})
$$

Therefore, $\lambda = [\mathbf{r}, \mathbf{b}, \mathbf{c}]/[\mathbf{a}, \mathbf{b}, \mathbf{c}]$ which is unique and similarily for $\mu, \nu$.

## Cartesian/Standard Basis

Although any three vectors can be as basis in $mathbb{R}^3$ as long as $\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = 0$,
things can be simplified if the basis vectors are orthogonal, have unit magnitude.
For a Cartesian basis, we have the basis vectors being the unit vectors along the $x, y, z$ axes, and denoted by $\mathbf{i}, \mathbf{j}, \mathbf{k}$.

With that, we have

$$
\begin{gather}
\mathbf{i} \cdot \mathbf{i} = \mathbf{j} \cdot \mathbf{j} = \mathbf{k} \cdot \mathbf{k} = 1 \\
\mathbf{i} \cdot \mathbf{j} = \mathbf{j} \cdot \mathbf{k} = \mathbf{k} \cdot \mathbf{i} = 0 \\
\mathbf{i} \times \mathbf{j} = \mathbf{k} \quad \mathbf{j} \times \mathbf{k} = \mathbf{i} \quad \mathbf{k} \times \mathbf{i} = \mathbf{j} \\
[\mathbf{i}, \mathbf{j}, \mathbf{k}] = 1
\end{gather}
$$

For any point $P$ with coordinates $(x, y, z)$, we can see that $\vec{OP} = \mathbf{v} = x\mathbf{i} + y\mathbf{j} + z\mathbf{k}$,
hence we can have the notation $\mathbf{v} = (x, y, z)$ and it is called the Cartesian components of $\mathbf{v}$.

Also, by "dotting" $\mathbf{v}$ by $\mathbf{i}, \mathbf{j}, \mathbf{k}$ respectively, we can conclude

$$
\mathbf{v} = (\mathbf{v} \cdot \mathbf{i}, \mathbf{v} \cdot \mathbf{j},\mathbf{v} \cdot \mathbf{k})
$$

For unit vector $\mathbf{\hat{v}}$, we can write

$$
\mathbf{\hat{v}} = (\cos \alpha, \cos \beta, \cos \gamma)
$$

which is called the direction cosines of $\mathbf{\hat{v}}$.

### Vector Component Identities

With the use of standard basis, some of the numeric operations of vectors can be simplified.
Given

$$
\begin{align*}
\mathbf{a} &= a_x\mathbf{i} + a_y\mathbf{j} + a_z\mathbf{k} \\
\mathbf{b} &= b_x\mathbf{i} + b_y\mathbf{j} + b_z\mathbf{k} \\
\mathbf{c} &= c_x\mathbf{i} + c_y\mathbf{j} + c_z\mathbf{k}
\end{align*}
$$

For addition,

$$
\lambda\mathbf{a} + \mu\mathbf{b} = (\lambda a_x + \mu b_x)\mathbf{i} + (\lambda a_y + \mu b_y)\mathbf{j} + (\lambda c_x + \mu c_x)\mathbf{k}
$$

For scalar product,

$$
\mathbf{a} \cdot \mathbf{b} = a_x b_x + a_y b_y + a_z b_z
$$

For vector product,

$$
\mathbf{a} \times \mathbf{b} = (a_y b_z - a_z b_y)\mathbf{i} + (a_z b_x - a_x b_z)\mathbf{j} + (a_x b_y - a_y b_x)\mathbf{k}
$$

or

$$
\mathbf{a} \times \mathbf{b} = \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
a_x & a_y & a_z \\
b_x & b_y & b_z \\
\end{vmatrix}
$$

For scalar triple product,

$$
[\mathbf{a}, \mathbf{b}, \mathbf{c}] = a_x b_y c_z + a_y b_z c_x + a_z b_x c_y - a_x b_z c_y - a_y b_x c_z - a_z b_y c_x
$$

or

$$
[\mathbf{a}, \mathbf{b}, \mathbf{c}] = \begin{vmatrix}
a_x & a_y & a_z \\
b_x & b_y & b_z \\
c_x & c_y & c_z \\
\end{vmatrix}
$$

For vector product, consider the $x$-component of the product

$$
\begin{align*}
\left(\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \right)_x = \left( \mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \right) \cdot \mathbf{i} &= a_y(\mathbf{b} \times \mathbf{c})_z - a_z(\mathbf{b} \times \mathbf{c})_y \\
&= a_y(b_x c_y - b_y c_x) - a_z(b_z c_x - b_x c_z) \\
&= (a_y c_y + a_z c_z)b_x - (a_z b_z + a_y c_y)c_x + a_x b_x c_x - a_x b_x c_x \\
&= (\mathbf{a} \cdot \mathbf{c})b_x - (\mathbf{a} \cdot \mathbf{b})c_x \\
&= \left( (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c} \right) \cdot \mathbf{i} \\
&= \left( (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c} \right)_x \\
\end{align*}
$$

Similar results will be arrived for $y$-component and $z$-component, hence

$$
\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) = (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c}
$$

We can see that the resulting vector has no component in direction $\mathbf{a}$ (outside the parentheses) because the resulting vector after the last vector multiplication by $\mathbf{a}$ is orthogonal to $\mathbf{a}$.

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
