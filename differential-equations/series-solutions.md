---
layout: base
title: Series Solutions &#124; Differential Equations
---

# Series Solutions
{: .page-title}

Even though we can solve differential equations by methods mentioned previously, it is still useful to find solution in terms of power series for computational purpose.

> *Definition.*{: .def}
> A function $f$ is **analytic** at a point $x = x_0$ if it has a Taylor series expansion about $x = x_0$, i.e.
>
> $$
  f(x) = \sum_{n=0}^\infty {f^{(n)}(x_0) \over n!} (x - x_0)^n
  $$
>
> with a raidus of convergence $\rho > 0$.

> *Definition.*{: .def}
> An **orderinary point** $x_0$ of a differential equation
>
> $$
  P(x) y'' + Q(x) y' + R(x) y = 0
  $$
>
> is a point such that $p = Q/P$ and $q = R/P$ are analytic at $x_0$.

> *Definition.*{: .def}
> A **singular point** of a differential equation is a point that is not ordinary.

## Ordinary Points

> *Theorem.*{: .thm}
> If $x_0$ is an ordinary point of the differential equation
>
> $$
  P(x) y'' + Q(x) y' + R(x) y = 0
  $$
>
> then the general solution is of the form
>
> $$
  y = \sum_{n=0}^\infty a_n (x - x_0)^n = a_0 y_1(x) + a_1 y_2(x)
  $$
>
> where $a_0$ and $a_1$ are arbitrary and
>
> + $y_1$ and $y_2$ are two power series solutions that are analytic at $x_0$,
>
> + $y_1$ and $y_2$ form a fundamental set of solutions,
>
> + the radius of convergence for each of the series solutions is at least as large as
>   the minimum of the radii of convergence of the series for $p = Q/P$ and $q = R/P$.

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

Base on the above theorem, as $P(x) = 1, Q(x) = 0, R(x) = 1$ and $x_0 = 0$ is an ordinary point, we can conclude that

+ the solutions converge for all $x$,

+ the two solutions are linearly independent and form a fundamental set of solutions.

We can confirm their convergence by ratio test and found that they really converge for all $x$.
On the other hand, let

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

For ratio test to work, we have to find an explicit formula for the coefficients, and sometimes it will be hard or even not feasible.
The theorem provides a good way to find a lower bound of radius of convergence without even solving the equation.

> *Example.*{: .eg}
> For the Legendre equation
>
> $$
  (1 - x^2)y'' - 2xy' + \alpha(\alpha + 1)y = 0
  $$
>
> As $P(x) = 1 - x^2$, $Q(x) = -2x$ and $R(x) = \alpha(\alpha + 1)$ are polynomials,
> the distance of $x = 0$ from zeros of $P(x)$ is the radius of convergence,
> i.e. $P(x) = 0 \implies x = \pm 1$ so $\rho = 1$ or $\vert x \vert < 1$ for series solutions about $x = 0$.

## Near Singular Point

## References

* William E. Boyce _Elementary Differential Equations and Boundary Value Problems_, 2009 - Chapter 5
