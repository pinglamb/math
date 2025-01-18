---
layout: base
title: Linear Equations &#124; Vectors and Matrices
---

# Linear Equations
{: .page-title}

> *Definition.*{: .def}
> Given a system of equations
>
> $$
  \mathsf{A}\mathbf{x} = \mathbf{d}
  $$
>
> where $\mathsf{A}$ is a $m \times n$ matrix, $\mathbf{x}$ is a $n \times 1$ column vector of unknowns and $\mathbf{d}$ is a $m \times 1$ column vector.
>
> If $\mathbf{d} = \mathbf{0}$, it is called a system of **homogenerous** equations, otherwise it is called a system of **inhomogeneous** equations.

> *Proposition.*{: .prop}
> If $\mathsf{A}$ is a square matrix ($m = n$) and $\det \mathsf{A} \not= 0$, then the system of equations has a _unique_ solution, namely
>
> $$
  \mathbf{x} = \mathsf{A}^{-1}\mathbf{d}
  $$

It is computation heavy to find the inverse base on the method described in [matrix inverses](determinants.md#matrix-inverses),
which leads to the following important methodology.

## Gaussian Elimination

> *Proposition.*{: .prop}
> The solutions to the system of equations remain the same after the following elementary row operations:
>
> + interchange of two rows,
>
> + addition of a constant multiple of one row to another,
>
> + multiplication of a row by a non-zero constant.
>
> We can do the same to the columns with an appropriate relabelling of the unknowns.

> *Proposition.*{: .prop}
> **[Gaussian Elimination]**
> By applying the elementary row operations to a system of equations, we can reduce it to the form
>
> $$
  \begin{align*}
  A_{11}x_1 + A_{12}x_2 + ... + A_{1r}x_r + ... + A_{1n}x_n &= d_1 \\
  A_{22}^{(2)}x_2 + ... + A_{2r}^{(2)}x_r + ... + A_{2n}^{(2)}x_n &= d_2^{(2)} \\
  \ddots \quad + \quad \vdots \quad + \quad ... \quad + \quad\vdots\quad &= \,\vdots \\
  A_{rr}^{(r)}x_r + ... + A_{rn}^{(r)}x_n &= d_r^{(r)} \\
  0 &= d_{r+1}^{(r)} \\
  \vdots &= \,\vdots \\
  0 &= d_m^{(r)} \\
  \end{align*}
  $$
>
> in which every next row we have one less unknown.
>
> + If $r < m$ and at least one of the numbers $d_{r+1}^{(r)}, ..., d_{m}^{(r)}$ is non-zero,
>   then the equations are inconsistent and there is no solutions and the system is **overdetermined**.
>
> + If $r = n \le m$ (and $d_{i}^{(r)} = 0$ for $r + 1 \le i \le m$),
>   then there is a unique solution and the system is **determined**.
>
> + If $r < n$ (and $d_{i}^{(r)} = 0$ for $r + 1 \le i \le m$),
>   then there are infinitely many solutions and the system is **underdetermined**.

The same method can be used for find the determinant of $\mathsf{A}$, with the elementary operations being

+ interchange of two rows,

+ addition of a constant multiple of one row to another,

+ interchange of two columns.

If there are $k$ row and column swaps, then

$$
\det \mathsf{A} = (-)^k \begin{vmatrix}
A_{11} & A_{12} & ... & A_{1r} & A_{1\,r+1} & ... & A_{1n} \\
0 & A_{22}^{(2)} & ... & A_{2r}^{(2)} & A_{2\,r+1}^{(2)} & ... & A_{2n}^{(2)} \\
\vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & ... & A_{rr}^{(r)} & A_{r\,r+1}^{(r)} & ... & A_{rn}^{(r)} \\
0 & 0 & ... & 0 & 0 & ... & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & ... & 0 & 0 & ... & 0 \\
\end{vmatrix}
$$

If $r < n$, then $\det \mathsf{A} = 0$.
If $r = n$, then $\det \mathsf{A} = (-)^kA_{11}A_{22}^{(2)}...A_{nn}^{(n)}$.

## Rank of Matrix

Consider a linear map $\mathcal{A}: \mathbb{R}^n \to \mathbb{R}^m$, the [rank](linear-maps.md#definition-rank) of $\mathcal{A}$ is defined to be the dimension of the image, i.e.

$$
r(\mathcal{A}) = \dim \mathcal{A}(\mathbb{R}^n)
$$

Let $\Set{\mathbf{e}_j}$ be a standard basis of $\mathbb{R}^n$, then $\Set{\mathcal{A}(\mathbf{e}_j)}$ must span the image.
As the number of linearly independent vectors in $\Set{\mathcal{A}(\mathbf{e}_j)}$ is equal to $r(\mathcal{A})$ and $\mathcal{A}(\mathbf{e}_j)$ are the column vectors of matrix $\mathsf{A}$,
the number of linearly independent columns of $\mathsf{A}$ is equal to $r(\mathcal{A})$.
We then have the following definition.

> *Definition.*{: .def}
> The **column/row rank** of a matrix $\mathsf{A}$ is defined to be the maximum number of linearly independent columns/rows of $\mathsf{A}$.

> *Theorem.*{: .thm}
> The row rank of a matrix is equal to its column rank, and hence the rank of matrix is well-defined.
>
> *Proof.*{: .prf}
>
> Let $r$ be the row rank of the matrix $\mathsf{A}$, so $\mathsf{A}$ has a linearly independent set of $r$ row vectors
>
> $$
  \mathbf{v}_k^\intercal = \begin{pmatrix} v_{k1} & v_{k2} & \cdots & v_{kn} \end{pmatrix} \quad \text{for } k = 1, 2, ..., r
  $$
>
> For the $i$-th row of $\mathsf{A}$, i.e.
>
> $$
  \mathbf{r}_i^\intercal = \begin{pmatrix} A_{i1} & A_{i2} & \cdots & A_{in} \end{pmatrix}
  $$
>
> it can be written as a linear combination of $\Set{\mathbf{v}_k^\intercal}$ so we have
>
> $$
  \mathbf{r}_i^\intercal = \sum_{k=1}^{r} u_{ik} \mathbf{v}_k^\intercal
  $$
>
> for some coefficients $u_{ik}$. In terms of matrix coefficients,
>
> $$
  A_{ij} = \sum_{k=1}^{r} u_{ik} v_{kj}
  $$
>
> Alternatively, this expression can be written as
>
> $$
  \begin{pmatrix}
  A_{1j} \\
  A_{2j} \\
  \vdots \\
  A_{mj} \\
  \end{pmatrix} =
  \sum_{k=1}^{r} v_{kj} \begin{pmatrix}
  u_{1k} \\
  u_{2k} \\
  \vdots \\
  u_{mk} \\
  \end{pmatrix}
  $$
>
> So any column $\mathbf{c}_j$ of $\mathsf{A}$ can be expressed as a linear combination of the $r$ column vectors $\mathbf{u}_k$ (not necessary linearly independent), i.e.
>
> $$
  \mathbf{c}_j = \sum_{k=1}^{r} v_{kj} \mathbf{u}_k
  $$
>
> and hence the column rank must be less than of equal to row rank.
> By applying the same argument to $\mathsf{A}^\intercal$, we conclude row rank and column rank are equal to each other.

> *Corollary.*{: .cor}
> If $\det \mathsf{A} = 0$, the rows/columns are linearly dependent.
>
> *Proof.*{: .prf}
>
> As the rank of a matrix doesn't change under elementary row operations,
> we can use Gaussian elimination to calculate the rank.
> Hence, if $\det \mathsf{A} = 0$, there are some rows/columns of zeros after applying Gaussian elimination and therefore the rows/columns of $\mathsf{A}$ are linearly dependent.
{: #linear-dependent-proof}

## References

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 4](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
