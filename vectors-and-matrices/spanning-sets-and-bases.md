---
layout: base
title: Spanning Sets, Bases and Higher Dimentional Spaces &#124; Vectors and Matrices
---

# Higher Dimentional Spaces
{: .page-title}

The discussion of vectors in $\mathbb{R}^2$ and $\mathbb{R}^3$ is base on geometric intuition.
In order to generalize the results to higher dimensional vector spaces such as $\mathbb{R}^n$ and $\mathbb{C}^n$,
we need to take an algebraic approach to build the tools for redefining vectors.

## Spanning Sets and Bases

> *Definition.*{: .def}
> A set of $m$ vectors $\Set{v_1, v_2, ..., v_m}$ of vector space $V$ is **linearly independent** if for all scalars $\lambda \in \mathbb{F}$,
>
> $$
  \sum_i \lambda_i v_i = 0_V \quad \implies \quad \lambda_i = 0_{\mathbb{F}}
  $$
>
> Otherwise, the vectors are said to be **linearly dependent** since there exist scalars such that
>
> $$
  \sum_i \lambda_i v_i = 0_V
  $$
>
> By arranging the terms, we can express a vector in the set by other vectors in the same set.

> *Definition.*{: .def}
> A **spanning set** for a vector space $V$ is a set of $m$ vectors $\Set{v_1, v_2, ..., v_m}$ such that for every vector $v \in V$,
> there exists scalars $\lambda_i \in \mathbb{F}$ in which
>
> $$
  v = \lambda_1 v_1 + \lambda_2 v_2 + ... + \lambda_m v_m
  $$

We state that $m \ge n$ and for a given $v$ the $\lambda_i$ are not necessarily unique if $m > n$.

> *Definition.*{: .def}
> A **basis** of $V$ is a linearly independent subset of vectors that spans $V$.

> *Theorem.*{: .thm}
> If $S = \Set{v_1, v_2, ..., v_n}$ is a basis of $V$, then for all $v \in V$, there exists unique scalars $\lambda_i \in \mathbb{F}$ such that
>
> $$
  v = \lambda_1 v_1 + \lambda_2 v_2 + ... + \lambda_n v_n
  $$

> *Definition.*{: .def}
> The **components** of $v \in V$ respect to a ordered basis $S$ are the scalars such that
>
> $$
  v = \lambda_1 v_1 + \lambda_2 v_2 + ... + \lambda_n v_n
  $$

> *Definition.*{: .def}
> The **dimension** of a vector space $V$, denoted by $\dim V$, is defined by the number of vectors in a basis of the space.

Hence, $\dim \mathbb{R}^2 = 2$, $\dim \mathbb{R}^3 = 3$ and $\dim \mathbb{R}^n = n$.

## $\mathbb{R}^3$

> *Theorem.*{: .thm}
> Let $\mathbf{a}, \mathbf{b}, \mathbf{c} \in \mathbb{R}^3$ such that $[\mathbf{a}, \mathbf{b}, \mathbf{c}] = 0$,
> then the set $\Set{\mathbf{a}, \mathbf{b}, \mathbf{c}}$ spans $\mathbb{R}^3$, i.e.
> for any vector $\mathbf{r} \in \mathbb{R}^3$,
>
> $$
  \mathbf{r} = \lambda\mathbf{a} + \mu\mathbf{b} + \nu\mathbf{c}
  $$
>
> for suitable and unique real scalars $\lambda, \mu, \nu \in \mathbb{R}$.
>
> *Proof.*{: .prf}
>
> _Geometric construction_.
> Consider a 3D space, an origin $O$, and three non-zero and non-coplanar vectors $\mathbf{a}, \mathbf{b}, \mathbf{c}$.
> Let $r$ be the position vector of a point $P$ in the space.
>
> Let $\Pi_{\mathbf{ab}}$ be the plane containing $\mathbf{a}$ and $\mathbf{b}$.
> Draw a line through $P$ parallel to $\vec{OC} = \mathbf{c}$.
> This line cannot be parallel to $\Pi_{\mathbf{ab}}$ because $\mathbf{a}, \mathbf{b}, \mathbf{c}$ are not coplanar.
> Hence, they intersect at a point $N$ such that $\vec{NP} = \nu \mathbf{c}$.
> As $N$ is on $\Pi_{\mathbf{ab}}$, there exists $\lambda, \mu \in \mathbb{R}$ such that $\vec{ON} = \lambda \mathbf{a} + \mu \mathbf{b}$.
> It follows that
>
> $$
  \mathbf{r} = \vec{OP} = \vec{ON} + \vec{NP} = \lambda \mathbf{a} + \mu \mathbf{b} + \nu \mathbf{c}
  $$
>
> Consider
>
> $$
  \begin{align*}
  \mathbf{r} \cdot (\mathbf{b} \times \mathbf{c})
  &= (\lambda \mathbf{a} + \mu \mathbf{b} + \nu \mathbf{c}) \cdot (\mathbf{b} \times \mathbf{c}) \\
  &= \lambda \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) + \mu \mathbf{b} \cdot (\mathbf{b} \times \mathbf{c}) + \nu \mathbf{c} \cdot (\mathbf{b} \times \mathbf{c}) \\
  &= \lambda \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c})
  \end{align*}
  $$
>
> Hence, $\lambda, \mu, \nu$ are unique by construction and we have
>
> $$
  \lambda = {[\mathbf{r}, \mathbf{b}, \mathbf{c}] \over [\mathbf{a}, \mathbf{b}, \mathbf{c}]},
  \quad
  \mu = {[\mathbf{r}, \mathbf{c}, \mathbf{a}] \over [\mathbf{a}, \mathbf{b}, \mathbf{c}]},
  \quad
  \nu = {[\mathbf{r}, \mathbf{a}, \mathbf{b}] \over [\mathbf{a}, \mathbf{b}, \mathbf{c}]}
  $$

If the set $\Set{\mathbf{a}, \mathbf{b}, \mathbf{c}}$ spans $\mathbf{R}^3$ and is linearly independent, then it is a basis of $\mathbb{R}^3$.

### Cartesian/Standard Basis

From the above, three vectors do not have to be mutually orthogonal to be a basis.
However, things can be simplified if the basis vectors are mutually orthogonal and have unit magnitude.

> *Definition.*{: .def}
> A **orthonormal basis** is a basis in which the spanning sets are mutually orthogonal and have unit magnitude.
> It is also conventional to order them so that they are right-handed.

> *Definition.*{: .def}
> Let $OX, OY, OZ$ be a right-handed set of Cartesian axes,
> then the set of corresponding unit vectors $\Set{\mathbf{i}, \mathbf{j}, \mathbf{k}}$ forms a basis for $\mathbb{R}^3$ satisfying
>
> $$
  \begin{gather}
  \mathbf{i} \cdot \mathbf{i} = \mathbf{j} \cdot \mathbf{j} = \mathbf{k} \cdot \mathbf{k} = 1 \\
  \mathbf{i} \cdot \mathbf{j} = \mathbf{j} \cdot \mathbf{k} = \mathbf{k} \cdot \mathbf{i} = 0 \\
  \mathbf{i} \times \mathbf{j} = \mathbf{k} \quad \mathbf{j} \times \mathbf{k} = \mathbf{i} \quad \mathbf{k} \times \mathbf{i} = \mathbf{j} \\
  [\mathbf{i}, \mathbf{j}, \mathbf{k}] = 1
  \end{gather}
  $$
>
> and is called the **Cartesian/standard basis**.

> *Definition.*{: .def}
> Given a vector $\mathbf{v}$ and a Cartesian basis $\Set{\mathbf{i}, \mathbf{j}, \mathbf{k}}$ such that
>
> $$
  \mathbf{v} = v_x\mathbf{i} + v_y\mathbf{j} + v_z\mathbf{k}
  $$
>
> Then the **Cartesian components** of $\mathbf{v}$ is the tuple $(x, y, z)$.

> *Theorem.*{: .thm}
> Let $\mathbf{v}$ be a vector, then
>
> $$
  (v_x, v_y, v_z) = (\mathbf{v} \cdot \mathbf{i}, \mathbf{v} \cdot \mathbf{j}, \mathbf{v} \cdot \mathbf{k})
  $$
>
> *Proof.*{: .prf}
>
> Base on the properties about the dot products of the basis vectors above.

> *Corollary.*{: .cor}
> For an unit vector $\mathbf{\hat{t}} = (t_x, t_y, t_z)$ with respect to the standard basis,
> the **direction cosines** are defined by
>
> $$
  \mathbf{\hat{t}} = (\cos \alpha, \cos \beta, \cos \gamma)
  $$
>
> where $\alpha, \beta, \gamma$ are the angles between $\mathbf{t}$ and $\mathbf{i}, \mathbf{j}, \mathbf{k}$ respectively.

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

> *Proposition.*{: .prop}
> _Addition_
>
> $$
  \lambda\mathbf{a} + \mu\mathbf{b} = (\lambda a_x + \mu b_x)\mathbf{i} + (\lambda a_y + \mu b_y)\mathbf{j} + (\lambda c_x + \mu c_x)\mathbf{k}
  $$

> *Proposition.*{: .prop}
> _Scalar product_
>
> $$
  \mathbf{a} \cdot \mathbf{b} = a_x b_x + a_y b_y + a_z b_z
  $$

> *Proposition.*{: .prop}
> _Vector product_
>
> $$
  \mathbf{a} \times \mathbf{b} = (a_y b_z - a_z b_y)\mathbf{i} + (a_z b_x - a_x b_z)\mathbf{j} + (a_x b_y - a_y b_x)\mathbf{k}
  $$
>
> or
>
> $$
  \mathbf{a} \times \mathbf{b} = \begin{vmatrix}
  \mathbf{i} & \mathbf{j} & \mathbf{k} \\
  a_x & a_y & a_z \\
  b_x & b_y & b_z \\
  \end{vmatrix}
  $$

> *Proposition.*{: .prop}
> _Scalar triple product_
>
> $$
  [\mathbf{a}, \mathbf{b}, \mathbf{c}] = a_x b_y c_z + a_y b_z c_x + a_z b_x c_y - a_x b_z c_y - a_y b_x c_z - a_z b_y c_x
  $$
>
> or
>
> $$
  [\mathbf{a}, \mathbf{b}, \mathbf{c}] = \begin{vmatrix}
  a_x & a_y & a_z \\
  b_x & b_y & b_z \\
  c_x & c_y & c_z \\
  \end{vmatrix}
  $$

> *Proposition.*{: .prop}
> _Vector triple product_,
> consider the $x$-component of the product
>
> $$
  \begin{align*}
  \left(\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \right)_x = \left( \mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \right) \cdot \mathbf{i} &= a_y(\mathbf{b} \times \mathbf{c})_z - a_z(\mathbf{b} \times \mathbf{c})_y \\
  &= a_y(b_x c_y - b_y c_x) - a_z(b_z c_x - b_x c_z) \\
  &= (a_y c_y + a_z c_z)b_x - (a_z b_z + a_y c_y)c_x + a_x b_x c_x - a_x b_x c_x \\
  &= (\mathbf{a} \cdot \mathbf{c})b_x - (\mathbf{a} \cdot \mathbf{b})c_x \\
  &= \left( (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c} \right) \cdot \mathbf{i} \\
  &= \left( (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c} \right)_x \\
  \end{align*}
  $$
>
> Similar results will be arrived for $y$-component and $z$-component, hence
>
> $$
  \mathbf{a} \times (\mathbf{b} \times \mathbf{c}) = (\mathbf{a} \cdot \mathbf{c}) \mathbf{b} - (\mathbf{a} \cdot \mathbf{b}) \mathbf{c}
  $$
{: #vector-triple-product}

## $\mathbb{R}^n$

We can now bootstrap to higher dimensional spaces base on the standard basis of $\mathbb{R}^3$.

> *Definition.*{: .def}
> We define $\mathbb{R}^n$ to be the set of all $n$-tuples
>
> $$
  \Set{\mathbf{x} = (x_1, x_2, ..., x_n) : x_i \in \mathbb{R} \text{ with } i = 1, 2, ..., n}
  $$
>
> with respect to the _standard basis_
>
> $$
  \mathbf{e_1} = (1, 0, ..., 0), ..., \mathbf{e_n} = (0, 0, ..., 1)
  $$
>
> For $\mathbf{x}, \mathbf{y} \in \mathbb{R}^n$ and $\lambda \in \mathbb{R}$, we also define
>
> $$
  \begin{align*}
  \mathbf{x} + \mathbf{y} &= (x_1 + y_1, x_2 + y_2, ..., x_n + y_n) \\
  \lambda \mathbf{x} &= (\lambda x_1, \lambda x_2, ..., \lambda x_n) \\
  \mathbf{0} &= (0, 0, ..., 0) \\
  \mathbf{-x} &= (-x_1, -x_2, ..., -x_3)
  \end{align*}
  $$

> *Proposition.*{: .prop}
> $\mathbb{R}^n$ is a vector space over $\mathbb{R}$.

### Scalar Product

> *Definition.*{: .def}
> The **scalar product** on $\mathbb{R}^n$ for $\mathbf{x}, \mathbf{y} \in \mathbb{R}^n$ is defined by
>
> $$
  \mathbf{x} \cdot \mathbf{y} = \sum_{i=1}^n x_i y_i = x_1 y_1 + x_2 y_2 + ... + x_n y_n
  $$

> *Proposition.*{: .prop}
> The definition above satisfies the axioms of scalar/inner product of vector space.

> *Definition.*{: .def}
> The **length** or **Euclidean norm** of a vector $\mathbf{x} \in \mathbb{R}^n$ is defined to be
>
> $$
  \vert x \vert \equiv (\mathbf{x} \cdot \mathbf{x})^{1 \over 2} = \left( \sum_{i=1}^n x_i^2 \right)^{1 \over 2}
  $$

> *Definition.*{: .def}
> The **interior angle** $\theta$ between vectors $\mathbf{x}$ and $\mathbf{y}$ is defined to be
>
> $$
  \theta = \arccos \left( {\mathbf{x} \cdot \mathbf{y} \over \vert x \vert \vert y \vert } \right)
  $$

> *Definition.*{: .def}
> Non-zero vectors $\mathbf{x}, \mathbf{y}$ is defined to be **orthogonal** if $\mathbf{x} \cdot \mathbf{y} = 0$.

> *Proposition.*{: .prop}
> The Cauthy-Schwarz inequality holds.

The definition is consistent with that of $\mathbb{R}^3$ only when the $x_i$ and $y_i$ are components with respect to an orthonormal basis.

## $\mathbf{C}^n$

> *Definition.*{: .def}
> We define $\mathbb{C}^n$ to be the set of all $n$-tuples
>
> $$
  \Set{\mathbf{z} = (z_1, z_2, ..., z_n) : z_i \in \mathbb{C} \text{ with } i = 1, 2, ..., n}
  $$
>
> with respect to the _standard basis_
>
> $$
  \mathbf{e_1} = (1, 0, ..., 0), ..., \mathbf{e_n} = (0, 0, ..., 1)
  $$
>
> For $\mathbf{u}, \mathbf{v} \in \mathbb{C}^n$ and $\lambda \in \mathbb{C}$, we define
>
> $$
  \begin{align*}
  \mathbf{u} + \mathbf{v} &= (u_1 + v_1, u_2 + v_2, ..., u_n + v_n) \\
  \lambda \mathbf{u} &= (\lambda u_1, \lambda u_2, ..., \lambda u_n) \\
  \mathbf{0} &= (0, 0, ..., 0) \\
  \mathbf{-u} &= (-u_1, -u_2, ..., -u_n)
  \end{align*}
  $$

> *Proposition.*{: .prop}
> $\mathbb{C}^n$ is a vector space over $\mathbb{C}$.

The standard basis of $\mathbb{R}^n$ can serve as standard basis of $\mathbb{C}^n$, hence $\dim \mathbb{C}^n = n$.

### Scalar Product

> *Definition.*{: .def}
> The **scalar product** on $\mathbb{C}^n$ for $\mathbf{u}, \mathbf{v} \in \mathbb{C}^n$ is defined by
>
> $$
  \mathbf{u} \cdot \mathbf{v} = \sum_{i=1}^n u_i^{\ast} v_i = u_1^{\ast} v_1 + u_2^{\ast} v_2 + ... + u_n^{\ast} v_n
  $$

> *Proposition.*{: .prop}
> The scalar product on $\mathbb{C}^n$ satisfies the following axioms (slightly different from that of $\mathbb{R}^n$)
>
> + _Symmetric up to conjugate_, i.e.
>
>   $$
    \mathbf{u} \cdot \mathbf{v} = (\mathbf{v} \cdot \mathbf{u})^{\ast}
    $$
>
> + _Linearilty_ in the second argument, i.e.
>
>   $$
    \mathbf{u} \cdot (\lambda \mathbf{v} + \mu \mathbf{w}) = \lambda (\mathbf{u} \cdot \mathbf{v}) + \mu (\mathbf{u} \cdot \mathbf{w})
    $$
>
> + Non-negativity, with equality holds iff $a = 0_V$, i.e.
>
>   $$
    \vert \mathbf{u} \vert^2 \equiv \mathbf{u} \cdot \mathbf{u} \ge 0
    $$
>
> + _Non-degeneracy_, i.e. the only vector of zero _norm_ should be the zero vector, i.e.
>
>   $$
    \vert \mathbf{u} \vert = 0 \implies \mathbf{u} = \mathbf{0}
    $$
{: #complex-space-scalar-product-axioms}

The axioms are really similar to that of scalar product on $\mathbb{R}^n$ except for being symmetric,
hence we can't derive the linearity of the first argument.

> *Definition.*{: .def}
> Non-zero vectors $\mathbf{x}, \mathbf{y}$ is defined to be **orthogonal** if $\mathbf{x} \cdot \mathbf{y} = 0$.

> *Proposition.*{: .prop}
> The Cauthy-Schwarz inequality holds.

## Reference

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
