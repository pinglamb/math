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

> *Proposition.*{: .prop}
> For a constant $2 \times 2$ matrix with two distinct real eigenvalues $\lambda_1$ and $\lambda_2$ and corresponding eigenvectors $\mathbf{v}_1$ and $\mathbf{v}_2$,
> the general solution is
>
> $$
  \mathbf{x}(t) = A \mathbf{v}_1 e^{\lambda_1t} + B \mathbf{v}_2 e^{\lambda_2t}
  $$

> *Proposition.*{: .prop}
> For a constant real $2 \times 2$ matrix with two complex eigenvalues $\lambda = \rho \pm i\omega$ and corresponding eigenvectors $\mathbf{v} = \mathbf{u_1} \pm i \mathbf{u_2}$,
> the general solution is
>
> $$
  \begin{align*}
  \mathbf{x}(t)
  &= e^{\rho t} [(A \cos \omega t + B \sin \omega t) \mathbf{u_1} + (B \cos \omega t - A \sin \omega t) \mathbf{u_2}] \\
  &= A e^{\rho t} (\mathbf{u_1}\cos \omega t - \mathbf{u_2} \sin \omega t) + B e^{\rho t} (\mathbf{u_1} \sin \omega t + \mathbf{u_2} \cos \omega t)
  \end{align*}
  $$
>
> *Proof.*{: .prf}
>
> For a real matrix, the complex eigenvalues are always conjugate to each other, so as the corresponding eigenvectors because
> if $\lambda = \rho + i \omega$ and $\mathbf{v}$ are the eigenvalue and eigenvector of $\mathbf{A}$, then
>
> $$
  [(\mathbf{A} - \lambda \mathbf{I})\mathbf{v}]^\ast = (\mathbf{A} - \lambda^\ast \mathbf{I})\mathbf{v}^\ast = 0
  $$
>
> so $\lambda^\ast$ and $\mathbf{v}^\ast$ are also eigenvalue and eigenvector of $\mathbf{A}$.
>
> Substitude them into the general solution gives us
>
> $$
  \mathbf{x}(t) = c_1 \mathbf{v} e^{(\rho + i\omega)t} + c_2 \mathbf{v}^\ast e^{(\rho - i\omega)t}
  = e^{\rho t} (c_1 \mathbf{v} e^{i\omega t} + c_2 \mathbf{v}^\ast e^{-i\omega t})
  $$
>
> We can ensure real solutions by having $c_1 = a + ib$ and $c_2 = c_1^\ast = a - ib$ and it becomes
>
> $$
  \begin{align*}
  \mathbf{x}(t) &= 2e^{\rho t} \text{Re}\left[(a + ib)(\mathbf{u_1} + i\mathbf{u_2})(\cos \omega t + i\sin\omega t) \right] \\
  &= 2e^{\rho t} \left[ (a \cos \omega t - b \sin \omega t)\mathbf{u_1} - (b \cos \omega t + a \sin \omega t)\mathbf{u_2} \right]
  \end{align*}
  $$
>
> Hence, let $A = 2a$ and $B = -2b$, by rearranging the terms, we have
>
> $$
  \mathbf{x}(t) = A e^{\rho t} (\mathbf{u_1}\cos \omega t - \mathbf{u_2} \sin \omega t) + B e^{\rho t} (\mathbf{u_1} \sin \omega t + \mathbf{u_2} \cos \omega t)
  $$

## Linear + Inhomogeneous + Constant Coefficients

## Fundamental Matrices

## Qualitative Analysis

## References

* William E. Boyce _Elementary Differential Equations and Boundary Value Problems_, 2009 - Chapter 7
