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

## Hyperbolic Functions

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 6
