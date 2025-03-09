---
layout: base
title: Series Solutions &#124; Differential Equations
---

# Series Solutions
{: .page-title}

> *Definition.*{: .def}
> For a differential equation
>
> $$
  P(x) {\mathrm{d}^2 y \over \mathrm{d}x^2} + Q(x) {\mathrm{d} y \over \mathrm{d} x} + R(x) y = 0
  $$
>
> An **orderinary point** is a point $x_0$ such that $P(x_0) \not= 0$.
> Since $P$ is continuous, it follows that there is an interval about $x_0$ in which $P(x)$ is never zero.
>
> On the other hand, $x_0$ is a **singular point** if $P(x_0) = 0$.
> At least one of the $Q(x_0)$ and $R(x_0)$ is not zero and hence one of the $Q/P$ or $R/P$ becomes unbounded as $x \to x_0$.

## Near Ordinary Point

> *Example.*{: .eg}
> For the differential equation
>
> $$
  y'' + y = 0
  $$
>
> Consider a power series about $x_0 = 0$ that converges in some interval $\vert x \vert < \rho$, we have
>
> $$
  y = \sum_{n=0}^\infty a_n x^n
  \quad \text{and} \quad
  y' = \sum_{n=1}^\infty n a_n x^{n-1}
  \quad \text{and} \quad
  y'' = \sum_{n=2}^\infty n(n-1) a_n x^{n-2}
  $$
>
> Then
>
> $$
  \begin{align*}
  \sum_{n=2}^\infty n(n-1) a_n x^{n-2} + \sum_{n=0}^\infty a_n x^n &= 0 \\
  \sum_{n=0}^\infty (n+2)(n+1) a_{n+2} x^n + \sum_{n=0}^\infty a_n x^n &= 0 \\
  \end{align*}
  $$
>
> For this equation to be satisfied for all $x$, we need to have
>
> $$
  (n+2)(n+1) a_{n+2} + a_n = 0
  $$
>
> For the even-numbered coefficients
>
> $$
  a_2 = - {a_0 \over 2!}
  \quad \text{and} \quad
  a_4 = - {a_2 \over 3 \cdot 4} = {a_0 \over 4!}
  \quad \text{and} \quad
  a_{2k} = {(-1)^k \over (2k)!} a_0
  $$
>
> For the odd-numbered coefficients
>
> $$
  a_3 = - {a_1 \over 3!}
  \quad \text{and} \quad
  a_5 = - {a_3 \over 4 \cdot 5} = {a_1 \over 5!}
  \quad \text{and} \quad
  a_{2k+1} = {(-1)^k \over (2k + 1)!} a_1
  $$
>
> Hence,
>
> $$
  y = a_0 \sum_{n=0}^\infty {(-1)^n \over (2n)!} x^{2n} + a_1 \sum_{n=0}^\infty {(-1)^n \over (2n + 1)!} x^{2n + 1}
  $$
>
> Be noted that the series solutions provide only a local approximation about $x = 0$ if they are truncated.

With the series solutions, we can already do some analysis.
We can check their convergence by ratio test and found that they both converge for all $x$.
We can also compute their Wronskian to check if they form a fundamental set of solutions.
Let

$$
C(x) = \sum_{n=0}^\infty {(-1)^n \over (2n)!} x^{2n}
\quad \text{and} \quad
S(x) = \sum_{n=0}^\infty {(-1)^n \over (2n + 1)!} x^{2n + 1}
$$

We found that

$$
C'(x) = -S(x) \quad \text{and} \quad S'(x) = C(x)
$$

Their Wronskian at $x = 0$ is

$$
W[C, S](0) = \begin{vmatrix} C(0) & S(0) \\ -S(0) & C(0) \end{vmatrix} = \begin{vmatrix} 1 & 0 \\ 0 & 1 \end{vmatrix} = 1
$$

and therefore the two solutions are indeed linearly independent.

According to the list of [Power Series](power-series.md#important-series),
the two series solutions are indeed $\sin x$ and $\cos x$, which matches the solutions we found by other techniques.
The function $\sin x$ can in fact be defined as the unique solution of the IVP $y'' + y = 0, y(0) = 0, y'(0) = 1$.
Similarily, the function $\cos x$ can be defined as the unique solution of the IVP $y'' + y = 0, y(0) = 1, y'(0) = 0$

## Near Singular Point

## References

* William E. Boyce _Elementary Differential Equations and Boundary Value Problems_, 2009 - Chapter 5
