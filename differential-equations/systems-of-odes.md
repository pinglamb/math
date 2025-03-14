---
layout: base
title: Systems of First Order Differential Equations &#124; Differential Equations
---

# Systems of First Order Differential Equations
{: .page-title}

The reason to focus on first order differential equations is that
any arbitrary $n$th order equation $y^{(n)} = F(t, y, y', ..., y^{(n-1)})$ can be transformed into a system of $n$ first order equations.
Let $x_1 = y$, $x_2 = y'$, ..., $x_n = y^{(n-1)}$ then we have

$$
\begin{align*}
x_1' &= x_2 \\
x_2' &= x_3 \\
&\quad \vdots \\
x_n' &= F(t, x_1, x_2, ..., x_{n-1})
\end{align*}
$$

which is a system of $n$ first order differential equations.

> *Definition.*{: .def}
> A general system of first order linear equation is of the form
>
> $$
  \begin{align*}
  x_1' &= p_{11}(t)x_1 + \cdots + p_{1n}(t)x_n + g_1(t) \\
  &\quad \vdots \\
  x_n' &= p_{n1}(t)x_1 + \cdots + p_{nn}(t)x_n + g_n(t)
  \end{align*}
  $$
>
> If $g_1(t), ..., g_n(t)$ are zero then the system is **homogeneous**.

It is more precise to write the systems in matrix notation, i.e.

$$
\mathbf{x}' = \mathbf{P}(t) \mathbf{x} + \mathbf{g}(t)
$$

> *Theorem.*{: .thm}
> For the homogeneous equation
>
> $$
  \mathbf{x}' = \mathbf{P}(t) \mathbf{x}
  $$
>
> The set of vector functions $\mathbf{x_1}(t), ..., \mathbf{x_n}(t)$ which are linearly independent solutions is called a **fundamental set of solutions** of the system.
> The general solution is the linear combination
>
> $$
  \boldsymbol{\phi}(t) = c_1\mathbf{x_1}(t) + \cdots + c_n\mathbf{x_n}(t)
  $$
>
> *Proof.*{: .prf}
>
> Let $\boldsymbol{\xi} = \boldsymbol{\phi}(t_0)$ for some $t_0$ in the interval of the solutions.
> If there exists unique solution $c_1, ..., c_n$ for the system of algebraic equation
>
> $$
  c_1\mathbf{x_1}(t_0) + \cdots + c_n\mathbf{x_n}(t_0) = \boldsymbol{\xi}
  $$
>
> then every solution can be expressed as a linear combination.
>
> Let $\mathbf{X}(t) = \begin{pmatrix} \mathbf{x_1}(t) & \cdots & \mathbf{x_n}(t) \end{pmatrix}$.
> The system is equivalent to
>
> $$
  \mathbf{X}(t_0) \mathbf{c} = \boldsymbol{\xi}
  $$
>
> where $\vert \mathbf{X}(t_0) \vert = W\[\mathbf{x_1}, ..., \mathbf{x_n}\](t_0) \not= 0$ as the vector functions are linearly independent.
>
> Hence, there is a unique solution $\mathbf{c} = \mathbf{X}^{-1}(t_0) \boldsymbol{\xi}$.

> *Proposition.*{: .prop}
> The Wronskian $W\[\mathbf{x_1}, ..., \mathbf{x_n}\]$ of the solutions either is identically zero or else never vanishes.
>
> *Proof.*{: .prf}
>
> The Wronskian satisfies the differential equation
>
> $$
  {\mathrm{d} W \over \mathrm{d}t} = (p_{11} + ... + p_{nn}) W
  $$
>
> Hence,
>
> $$
  W(t) = c \exp \left\{ \int [p_{11}(t) + ... + p_{nn}(t)] \mathrm{d}t \right\}
  $$
>
> which is known as **Abel's formula** and $W(t) \equiv 0$ or $W(t) \not = 0$ for all $t$ in the interval of solutions.

The above is an extension of the theories we estabished for ordinary differential equations.
There is also a similar existence and uniqueness theorem which is omitted here.

## Linear + Homogeneous + Constant Coefficients

> *Proposition.*{: .prop}
> Consider a system of first order differential equations
>
> $$
  \mathbf{x}' = \mathbf{A} \mathbf{x}
  $$
>
> where $\mathbf{A}$ is a constant $n \times n$ matrix.
> Assume the solutions is of the form
>
> $$
  \mathbf{x} = \mathbf{v} e^{\lambda t} \quad \text{and} \quad \mathbf{x}' = \lambda\mathbf{v} e^{\lambda t}
  $$
>
> Then substituting them back we have $\lambda \mathbf{v} e^{\lambda t} = \mathbf{A} \mathbf{v} e^{\lambda t}$, and
>
> $$
  (\mathbf{A} - \lambda \mathbf{I})\mathbf{v} = \mathbf{0}
  $$
>
> Therefore, $\lambda$ and $\mathbf{v}$ are the eigenvalues and eigenvectors of $\mathbf{A}$.
>
> Hence, if we have the $n$ eigenvalues (counted with multiplicity) and $n$ linearly independent eigenvectors,
> then the general solution is
>
> $$
  \mathbf{x}(t) = c_1 \mathbf{v}_1 e^{\lambda_1t} + ... + c_n \mathbf{v}_n e^{\lambda_n t}
  $$

## Fundamental Matrices

## Linear + Inhomogeneous + Constant Coefficients

## Qualitative Analysis

## References

* William E. Boyce _Elementary Differential Equations and Boundary Value Problems_, 2009 - Chapter 7
