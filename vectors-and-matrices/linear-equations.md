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
