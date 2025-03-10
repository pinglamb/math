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
> A **singular point** of a differential equation is a point that is not ordinary, i.e.
> $P(x_0) = 0$ and at least one of $Q$ and $R$ is not zero at $x_0$.

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

## Cauchy-Euler Equations

> *Definition.*{: .def}
> The **Cauchy-Euler equations** or **equidimensional equations** are the differential equations of the form
>
> $$
  L[y] = x^2 y'' + ax y' + by = 0
  $$
>
> where $a, b$ are real constants.

> *Proposition.*{: .prop}
> Assume a solution is of the form $y(x) = x^r$ for $x > 0$. Then
>
> $$
  L[x^r] = x^r[r(r-1) + ar + b] = 0
  $$
>
> Cancelling the $x^r$ factor and we obtain the **indicial equation**
>
> $$
  F(r) = ar(r-1) + br + c = 0
  $$
>
> and the roots are
>
> $$
  r_1, r_2 = {-(a - 1) \pm \sqrt{(a - 1)^2 - 4b} \over 2}
  $$

> *Proposition.*{: .prop}
> If the indicial equation has two real roots $r_1$ and $r_2$, then the general solution is
>
> $$
  y(x) = Ax^{r_1} + Bx^{r_2}
  $$

> *Proposition.*{: .prop}
> If the indicial equation has one repeated root $r$, then the general solution is
>
> $$
  y(x) = Ax^{r} + Bx^{r}\ln x = (A + B\ln x)x^r
  $$
>
> *Proof.*{: .prf}
>
> The other solution can be derived by reduction of order.
>
> Alternatively, note that $F(r) = (r - r_1)^2$ which implies $F'(r_1) = 0$ as well.
>
> By differentiating the differential equation with respect to $r$, we have
>
> $$
  {\partial \over \partial r} L[x^r] = {\partial \over \partial r} x^r F(r)
  $$
>
> and therefore
>
> $$
  L[x^r \ln x] = (r - r_1)^2 x^r \ln x + 2(r - r_1) x^r
  $$
>
> in which the R.H.S. is zero for $r = r_1$.
> Hence, $x^{r_1} \ln x$ is the second solution.

> *Proposition.*{: .prop}
> If the indicial equation has one complex roots $k = \rho \pm \omega i$, then the general solution is
>
> $$
  y(x) = x^{\rho}[A\cos(\omega\ln x) + B\sin(\omega\ln x)]
  $$
>
> *Proof.*{: .prf}
>
> Similar to having real roots, the general solution is
>
> $$
  y(x) = Cx^{\rho + \omega i} + Dx^{\rho - \omega i}
  $$
>
> Since
>
> $$
  x^{\rho \pm \omega i} = x^{\rho} e^{\pm \omega i \ln x} = x^\rho [\cos(\omega \ln x) \pm \sin(\omega \ln x)]
  $$
>
> As we want to make our solution real, we need to have $D = C^\ast$, i.e.
>
> $$
  \begin{align*}
  y(x) &= 2\text{Re}[Cx^{\rho + \omega i}] \\
  &= 2\text{Re}[(\alpha + \beta i)x^\rho [\cos(\omega \ln x) + \sin(\omega \ln x)]] \\
  &= 2x^\rho[\alpha \cos(\omega \ln x) - \beta \sin(\omega \ln x)]
  \end{align*}
  $$
>
> By rewriting the constants, we have $y(x) = x^{\rho}[A\cos(\omega\ln x) + B\sin(\omega\ln x)]$.

![Euler Equations](../images/ode-euler-equation-behaviour.png){: .size-2x}

> *Proposition.*{: .prop}
> For the case that $x < 0$, let $x = -\xi$ and $y = u(\xi)$, then
>
> $$
  {\mathrm{d}y \over \mathrm{d}x} = {\mathrm{d}u \over \mathrm{d}\xi} {\mathrm{d}\xi \over \mathrm{d}x} = - {\mathrm{d}u \over \mathrm{d}\xi}
  \quad \text{and} \quad
  {\mathrm{d}^2 y \over \mathrm{d}x^2} = {\mathrm{d} \over \mathrm{d}\xi} \left(-{\mathrm{d}u \over \mathrm{d}\xi}\right) {\mathrm{d} \xi \over \mathrm{d}x} = {\mathrm{d}^2u \over \mathrm{d}\xi^2}
  $$
>
> Thus, the Euler equation becomes
>
> $$
  \xi^2 u'' + a\xi u' + bu = 0
  $$
>
> which is exactly the same except for the variable names.
> Therefore,
>
> $$
  u(\xi) = \begin{cases}
  A\xi^{r_1} + B\xi^{r_2} \\
  (A + B \ln \xi) \xi^{r} \\
  \xi^\lambda (A \cos (\mu \ln \xi) + B \sin (\mu \ln \xi))
  \end{cases}
  $$
>
> To obtain the solutions in $x$, we just need to Substitude $\xi = -x$.
> Hence, combining the solutions for $x > 0$ and $x < 0$, we have
>
> $$
  y(x) = \begin{cases}
  A|x|^{r_1} + B|x|^{r_2} \\
  (A + B \ln |x|) |x|^{r} \\
  |x|^\lambda (A \cos (\mu \ln |x|) + B \sin (\mu \ln |x|))
  \end{cases}
  $$

## Singular Points

Although the singular points of a differential equation are usually few in number,
most of the time they determine the principal features of the solution to a much larger extent which we have to study more carefully.

> *Definition.*{: .def}
> A **regular singular point** of a differential equation is a point $x_0$ such that
>
> $$
  \lim_{x \to x_0} (x - x_0) {Q(x) \over P(x)}
  \quad \text{and} \quad
  \lim_{x \to x_0} (x - x_0)^2 {R(x) \over P(x)}
  $$
>
> are finite, or in other words, if both
>
> $$
  (x - x_0) {Q(x) \over P(x)}
  \quad \text{and} \quad
  (x - x_0)^2 {R(x) \over P(x)}
  $$
>
> are analytic at $x = x_0$.

## References

* William E. Boyce _Elementary Differential Equations and Boundary Value Problems_, 2009 - Chapter 5
