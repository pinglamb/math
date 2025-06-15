---
layout: base
title: Special Functions of Analysis &#124; Analysis
---

# Special Functions of Analysis
{: .page-title}

Some of the functions play an important role in different fields of sciences which we shall develop their principal properties.
Among them are exponential, logarithmic and trigonometric functions.
Instead of like the brief [discussions](../vectors-and-matrices/exponential-cosine-sine-functions.md) before,
we shall define them as the sums of infinite series and prove their well known properties in a rigorous manner.

## Exponential Function

> *Definition.*{: .def}
> The exponential function is defined by the series
>
> $$
  \exp x = 1 + x + {x^2 \over 2!} + \cdots + {x^n \over n!} + \cdots
  $$

> *Proposition.*{: .prop}
> $\exp x$ converges absolutely for all values of $x$, real or complex.
>
> *Proof.*{: .prf}
>
> $$
  \lim_{n \to \infty} \left| {x^{n+1} \over (n+1)!} \cdot {n! \over x^n} \right| = \lim_{n \to \infty} {|x| \over n+1} = 0
  $$
>
> By d'Alembert's ratio test, the series converges absolutely for all values of $x$.

We then have the following defining property about "powers".

> *Proposition.*{: .prop}
> $\exp x \times \exp y = \exp(x + y)$.
>
> *Proof.*{: .prf}
>
> As $\exp$ converges absolutely, the product of two series also converges absolutely.
>
> The terms of degree $n$ in $x$ and $y$ are
>
> $$
  {x^n \over n!} + \cdots + {x^r \over r!}{y^{n-r} \over (n-r)!} + \cdots + {y^n \over n!} = {(x + y)^n \over n!}
  $$

> *Proposition.*{: .prop}
> The following facts are immediate.
>
> + $\exp 0 = 1$;
>
> + $\exp(-x) = 1/\exp(x)$;
>
> + $\exp x$ never vanishes.

> *Definition.*{: .def}
> The **Euler's number**, denoted as $e$, is defined by $e = \exp 1$, i.e.
>
> $$
  e = 1 + {1 \over 1!} + {1 \over 2!} + \cdots + {1 \over n!} + \cdots
  $$

> *Proposition.*{: .prop}
> $e$ is irrational.

> *Proposition.*{: .prop}
> Suppose $r \in \mathbb{Q}$. Then $\exp r = e^r$.
>
> *Proof.*{: .prf}
>
> For positive integer $r = n$, $\exp n = (\exp 1)^n = e^n$.
>
> For negative integer $r = -n$, $\exp(-n) = {1 \over (\exp 1)^n} = e^{-n}$.
>
> For $r = p/q$, $(\exp(p/q))^q = \exp p = e^p$ therefore $\exp(p/q) = e^{p/q}$.

We can then extend our definition for irrational powers.

> *Definition.*{: .def}
> If $x$ is irrational, $e^x$ is defined to mean $\exp x$.

$\exp x$ is of its own order of magnitude.

> *Proposition.*{: .prop}
> For any fixed $k$ (however large)
>
> $$
  {\exp x \over x^k} \to \infty \quad \text{as} \quad x \to \infty
  $$
>
> *Proof.*{: .prf}
>
> $x^k$ is just one term of the series defining $\exp x$.

Next, we find the derivative of $\exp x$, but we cannot apply the sum rule as it works only for finite terms.
For series, we may need to give different arguments in each particular case.

> *Proposition.*{: .prop}
> The derivative of $\exp x$ is $\exp x$, i.e.
>
> $$
  {\mathrm{d} \over \mathrm{d}x} \exp x = \exp x
  $$
>
> *Proof.*{: .prf}
>
> We have
>
> $$
  {\exp(x + h) - \exp x \over h} = \exp x {\exp h - 1 \over h}
  $$
>
> and
>
> $$
  {\exp h - 1 \over h} = 1 + {h \over 2!} + {h^2 \over 3!} + \cdots
  $$
>
> Let $\phi(h) = h/2! + h^2/3! + \cdots$. Since $n! > 2^n$, we have
>
> $$
  \begin{align*}
  |\phi(h)| &\le {|h| \over 2} + {|h|^2 \over 2^2} + \cdots + {|h|^n \over 2^n} + \cdots \\
  &= {|h/2| \over 1 - |h/2|} \to 0 \quad \text{as} \quad h \to 0
  \end{align*}
  $$

> *Proposition.*{: .prop}
> $\exp x$ is a continuous function.
>
> *Proof.*{: .prf}
>
> Since $\exp x$ is differentiable by all $x$, $\exp x$ is continuous.

> *Proposition.*{: .prop}
> $\exp x$ is strictly increasing function and takes every value greater than $0$ for one value of $x$.
>
> *Proof.*{: .prf}
>
> If $x \ge 0$, from the series, $\exp x \ge 1$.
> If $x < 0$, $\exp x = 1 / \exp(-x) > 0$.
> $\exp x$ has a derivative which is positive for all $x$ and therefore $\exp x$ is strictly increasing.
>
> As $x \to \infty$, $\exp x \to \infty$. As $x \to -\infty$, $\exp x \to 0^+$.

This allows us to define the inverse of exponential function.

## Logarithmic Function

> *Definition.*{: .def}
> If $x > 0$, write $y = \log x$ if $x = \exp y$.

> *Proposition.*{: .prop}
> Base on the properties of inverse function, the following results are immediate.
>
> + The derivative of $\log x$ is
>
>   $$
    { \mathrm{d} \over \mathrm{d}x } \log x = {1 \over x}
    $$
>
> + $\log ab = \log a + \log b$;
>
> + $\log x \to \infty$ as $x \to \infty$;
>
> + $\log x \to -\infty$ as $x \to 0^+$.

$\log x$ grows more slowly than $x$ raised to any positive power.

> *Proposition.*{: .prop}
> If $k > 0$ (however small),
>
> $$
  {\log x \over x^k} \to 0 \quad \text{as} \quad x \to \infty
  $$

There is a simple representation of $\log(1+x)$ as a power series.

> *Proposition.*{: .prop}
> If $-1 < x < 1$,
>
> $$
  \log(1 + x) = x - {x^2 \over 2} + {x^3 \over 3} + \cdots + (-1)^{n-1} {x^n \over n} + \cdots
  $$

> *Definition.*{: .def}
> If $a > 0$ and $x$ is irrational, $a^x = e^{x \log a}$.

## Trigonometric Functions

Here we develop the results of analytical trigonometry by relating them with the exponential function.

> *Definition.*{: .def}
> The functions $\cos$ and $\sin$ are defined by the following power series
>
> $$
  \begin{align*}
  \cos x &= 1 - {x^2 \over 2!} + {x^4 \over 4!} - \cdots + (-1)^{n} {x^{2n} \over (2n)!} + \cdots \\
  \sin x &= x - {x^3 \over 3!} + {x^5 \over 5!} - \cdots + (-1)^{n} {x^{2n+1} \over (2n+1)!} + \cdots
  \end{align*}
  $$

> *Proposition.*{: .prop}
> Base on the power series definition, we have
>
> $$
  \begin{align*}
  \cos z &= {\exp(iz) + \exp(-iz) \over 2} \\
  \sin z &= {\exp(iz) - \exp(-iz) \over 2i}
  \end{align*}
  $$

> *Proposition.*{: .prop}
> Since exponential function converges absolutely, both of the series converge absolutely.

> *Proposition.*{: .prop}
> The following facts are immediate.
>
> + $\cos(-z) = \cos(z)$;
>
> + $\sin(-z) = -\sin(z)$;
>
> + $\cos 0 = 1$;
>
> + $\sin 0 = 0$.

> *Proposition.*{: .prop}
> The following results can be derived from the above relation.
>
> + $\sin(x + y) = \sin x \cos y + \cos x \sin y$;
>
> + $\cos(x + y) = \cos x \cos y - \sin x \sin y$;
>
> + $\sin^2 z + \cos^2 z = 1$.
>
> *Proof.*{: .prf}
>
> For example,
>
> $$
  \begin{align*}
  \sin(x + y) &= {1 \over 2i} (\exp(i(x+y)) - \exp(-i(x+y))) \\
  &= {1 \over 2i} (\exp(ix)\exp(iy) - \exp(-ix)\exp(-iy)) \\
  &= {\exp(ix) - \exp(-ix) \over 2i}{\exp(iy) + \exp(-iy) \over 2} + {\exp(ix) + \exp(-ix) \over 2}{\exp(iy) - \exp(-iy) \over 2i} \\
  &= \sin x \cos y + \cos x \sin y
  \end{align*}
  $$
>
> Also,
>
> $$
  \sin^2 z + \cos^2 z = { \exp(2iz) - 2 + \exp(-2iz) \over -4} + { \exp(2iz) + 2 + \exp(-2iz) \over 4} = 1
  $$

> *Proposition.*{: .prop}
> For $x \in \mathbb{R}$,
>
> $$
  -1 \le \cos x \le 1 \quad \text{and} \quad -1 \le \sin x \le 1
  $$
>
> *Proof.*{: .prf}
>
> Since $\sin^2 x + \cos^2 x = 1$.

> *Proposition.*{: .prop}
> The derivatives of $\sin z$ and $\cos z$ are
>
> $$
  {\mathrm{d} \over \mathrm{d} z} \sin z = \cos z \quad \text{and} \quad {\mathrm{d} \over \mathrm{d} x} \cos z = -\sin z
  $$
>
> *Proof.*{: .prf}
>
> We can prove it using similar argument as that of $\exp x$. Alternatively, we use complex differentiation,
>
> $$
  \begin{align*}
  {\mathrm{d} \over \mathrm{d} z} \sin z &= {i\exp(iz) + i\exp(-iz) \over 2i} = \cos z \\
  {\mathrm{d} \over \mathrm{d} z} \cos z &= {i\exp(iz) - i\exp(-iz) \over 2} = -\sin z
  \end{align*}
  $$

It is well-known that the two functions have period of $2\pi$.
The result is not obvious from the series, but we can still prove them analytically.

> *Proposition.*{: .prop}
> There is a smallest positive constant $\pi/2$, where $\sqrt{2} < \pi/2 < \sqrt{3}$, such that $\cos(\pi/2) = 0$.
>
> *Proof.*{: .prf}
>
> For $0 < x < 2$,
>
> $$
  \sin x = \left( x - {x^3 \over 3!} \right) + \left( {x^5 \over 5!} - {x^7 \over 7!} \right) + \cdots > 0
  $$
>
> Therefore, $\cos x$ is a decreasing function for $0 < x < 2$.
>
> Since
>
> $$
  \begin{align*}
  \cos \sqrt{2} &= \left( 1 - {\sqrt{2}^2 \over 2!} \right) + \left( {\sqrt{2}^4 \over 4!} - {\sqrt{2}^6 \over 6!} \right) + \cdots > 0 \\
  \cos \sqrt{3} &= \left( 1 - {\sqrt{3}^2 \over 2!} + {\sqrt{3}^4 \over 4!} \right) - \left( {\sqrt{3}^6 \over 6!} - {\sqrt{3}^8 \over 8!} \right) + \cdots < 0
  \end{align*}
  $$
>
> by intermediate value theorem, there exists a value $\sqrt{2} < \pi/2 < \sqrt{3}$ such that $\cos(\pi/2) = 0$.

> *Proposition.*{: .prop}
> $\sin(\pi/2) = 1$.
>
> *Proof.*{: .prf}
>
> $\sin^2(\pi/2) + \cos^2(\pi/2) = 1$ and $\sin(\pi/2)$ is positive.

> *Proposition.*{: .prop}
> By the addition formulae,
>
> + $\sin(x + \pi/2) = \cos x$, $\cos(x + \pi/2) = -\sin x$;
>
> + $\sin(x + \pi) = -\sin x$, $\cos(x + \pi) = -\cos x$;
>
> + $\sin(x + 2\pi) = \sin x$, $\cos(x + 2\pi) = \cos x$.

> *Proposition.*{: .prop}
> $\exp z$ has a period of $2\pi i$.

The series don't provide a practical way of obtaining accurate approximations to $\pi$.

## Inverse Trigonometric Functions

> *Proposition.*{: .prop}
> The equation $x = \sin y$ defines an inverse function
>
> $$
  y = \arcsin x
  $$
>
> such that $y$ increases from $-\pi/2$ to $\pi/2$ as $x$ increases from $-1$ to $1$.
>
> Also,
>
> $$
  {\mathrm{d} \over \mathrm{d}x } \arcsin x = {1 \over \sqrt{1 - x^2}}
  $$
>
> *Proof.*{: .prf}
>
> Since $\mathrm{d}x/\mathrm{d}y = \cos y > 0$ for $-\pi/2 < y < \pi/2$.
> $\sin y$ is strictly increasing from $-1$ to $1$, therefore the inverse exists.
>
> Also,
>
> $$
  {\mathrm{d}y \over \mathrm{d}x} = {1 \over \mathrm{d}x/\mathrm{d}y} = {1 \over \cos y} = {1 \over \sqrt{1 - x^2}}
  $$
>
> since $\cos y$ is positive in that range.

## Hyperbolic Functions

> *Definition.*{: .def}
> The hyperbolic cosine and sine are defined by
>
> $$
  \begin{align*}
  \cosh z &= 1 + {z^2 \over 2!} + {z^4 \over 4!} + \cdots + {z^{2n} \over (2n)!} + \cdots \\
  \sinh z &= z + {z^3 \over 3!} + {z^5 \over 5!} + \cdots + {z^{2n+1} \over (2n+1)!} + \cdots
  \end{align*}
  $$

> *Proposition.*{: .prop}
> Base on the power series definition, we have
>
> $$
  \begin{align*}
  \cosh z &= {\exp z + \exp(-z) \over 2} \\
  \sinh z &= {\exp z - \exp(-z) \over 2} \\
  \end{align*}
  $$

> *Proposition.*{: .prop}
> $\cosh z = \cos iz$ and $i\sinh z = \sin iz$.

> *Proposition.*{: .prop}
> Hyperbolic functions share some similar properties to circular functions.
>
> + Derivatives:
>
>   $$
    {\mathrm{d} \over \mathrm{d} z} \cosh z  = \sinh z \quad \text{and} \quad {\mathrm{d} \over \mathrm{d}z} \sinh z = \cosh z
    $$
>
> + $\cosh^2 z - \sinh^2 z = 1$;
>
> + $\cosh 2z = \cosh^2 z + \sinh^2 z$;
>
> + $\sinh 2z = 2\sinh z \cosh z$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 6
