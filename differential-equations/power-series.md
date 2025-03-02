---
layout: base
title: Power Series &#124; Differential Equations
---

# Power Series
{: .page-title}

> *Definition.*{: .def}
> A **power series** in $(x - a)$ (or centered at $a$ or about $a$) is a series of the form
>
> $$
  \sum_{n=0}^{\infty} c_n (x - a)^n = c_0 + c_1 (x - a) + c_2 (x - a)^2 + ...
  $$

As it is an infinite sum, the domain of it is the interval of $x$ where the series converges.

For a given power series about $a$, there are only three possibilities:

1. The series converges only when $x = a$

2. The series converges for all $x$

3. There is a postiive number $R$ such that the series converges for $\|x - a\| < R$ and diverges for $\|x - a\| > R$

> *Definition.*{: .def}
> The **radius of convergence** is the positive number $R$ such that the series converges for $\|x - a\| < R$ and diverges for $\|x - a\| > R$.

For the edge case when $x - a = \pm R$, the convergence check has to be done separately.

## Power Series Representation

Power series can be used to represent functions, for example

$$
{1 \over 1 - x} = 1 + x + x^2 + ... = \sum_{n=0}^{\infty} x^n
$$

with domain $\|x\| < 1$.

Base on that, we can derive the power series for other functions, such as

$$
{1 \over x+2} = {1 \over 2\left[1 - \left(-{x \over 2}\right) \right]} = {1 \over 2} \sum_{n=0}^{\infty} \left(-{x \over 2}\right)^n = \sum_{n=0}^{\infty} {(-1)^n \over 2^{n+1}}x^n
$$

which converges if $\|-x/2\| < 1$, meaning $\|x\| < 2$.

We can also differentiate and integrate a power series term-by-term to obtain another power series, which has the same radii of convergence as the original power series.

With this, we can derive the power series for some functions, for example, as

$$
\begin{align*}
{1 \over (1-x)^2} &= {\mathrm{d} \over \mathrm{d}x} {1 \over 1-x} \\
&= 1 + 2x + 3x^2 + ... \\
&= \sum_{n=0}^{\infty} (n+1)x^n
\end{align*}
$$

and it has the same radius of convergence $R = 1$.

On the other hand, we have

$$
\begin{align*}
\ln(1+x) &= \int {1 \over 1+x} \mathrm{d}x = \int (1 - x + x^2 - x^3 + ...) \mathrm{d}x \\
&= x - {x^2 \over 2} + {x^3 \over 3} - {x^4 \over 4} + ... + C \\
&= \sum_{n=1}^{\infty} {(-1)^{n - 1} \over n} x^n + C
\end{align*}
$$

Substitude $x = 0$, we have $C = \ln 1 = 0$ and the radius of convergence is $R = 1$.

## Taylor Series

> *Theorem.*{: .thm}
> If $f$ has a power series representation (expansion) at $a$, that is, if
>
> $$
  f(x) = \sum_{n=0}^\infty c_n (x-a)^n \quad |x - a| < R
  $$
>
> then
>
> $$
  c_n = {f^{(n)}(a) \over n!}
  $$
>
> *Proof.*{: .prf}
>
> By differentiating both side of the expansion repeatedly.

> *Definition.*{: .def}
> The **Taylor series** of the function $f$ at $a$ is defined by
>
> $$
  f(x) = f(a) + {f'(a) \over 1!}(x - a) + {f''(a) \over 2!}(x - a)^2 + \cdots
  $$

> *Definition.*{: .def}
> The **Maclaurin series** is the Taylor series with $a = 0$, i.e.
>
> $$
  f(x) = \sum_{n=0}^\infty {f^{(n)}(0) \over n!} x^n = f(0) + {f'(0) \over 1!}x + {f''(0) \over 2!}x^2 + \cdots
  $$

The question now is at what circumstances is a function $f$ equal to the sum of its Taylor series, provided $f$ has derivatives of all orders.

> *Definition.*{: .def}
> The $n$-th order **Taylor polynomial** $T_n$ for $f$ about $a$ is defined by
>
> $$
  T_n(x) = \sum_{j=0}^{n} {f^{(j)}(a) \over j!} (x - a)^j
  $$

> *Definition.*{: .def}
> The $n$th order **Taylor remainder** $R_n$ is the difference
>
> $$
  R_n(x) = f(x) - T_n(x)
  $$

> *Theorem.*{: .thm}
> Suppose $f(x) = T_n(x) + R_n(x)$, where $T_n$ is the $n$-th degree Taylor polynomial of $f$ at $a$.
> If
>
> $$
  \lim_{n \to \infty} R_n(x) = 0
  $$
>
> for $\|x - a\| < R$, then $f$ is equal to the sum of its Taylor series on the interval $\|x - a\| < R$.
>
> *Proof.*{: .prf}
>
> Base on the definition,
>
> $$
  \lim_{n \to \infty} T_n(x) = \lim_{n \to \infty} [f(x) - R_n(x)] = f(x) - \lim_{n \to \infty} R_n(x) = f(x)
  $$

> *Theorem.*{: .thm}
> **[Taylor's Inequality]**
> If
>
> $$
  |f^{(n+1)}(x)| \le M \quad \text{for} \quad |x - a| \le d
  $$
>
> then the remainder $R_n(x)$ of the Taylor series satisfies the inequality
>
> $$
  |R_n(x)| \le {M \over (n+1)!}|x - a|^{n+1} \quad \text{for} \quad |x - a| \le d
  $$

It means if we can find a bound of $(n+1)$-th derivative, we can use that to bound $R_n(x)$ and potentially prove its limit is $0$ by Squeeze Theorem.

## Integral Remainer

Taylor's Theorem can be thought as a higher-order version of the tangent line approximation discussed in [differentiability](differentiability.md).
It states that a function $f$ of class $C^n$ on an interval $I$ containing the point $x = a$ is the sum of a certain polynomial of degree $n$
and a remainder term that vanishes more rapidly than $\|x-a\|^n$ as $x \to a$ (i.e. $o(h^n)$).

Suppose that $f$ is of class $C^{n+1}$ on an interval $I \subset \mathbb{R}$ and $a \in I$,
i.e. $f^{j}$ exists and is continuous on $I$ for $0 \le j \le n + 1$.
Then the remainder $R_n$ is given by

$$
R_n(h) = {h^{n+1} \over n!} \int_0^1 (1 - t)^n f^{n+1}(a + th) \mathrm{d}t
$$

From this, we can see that $R_n(h) = o(h^{n+1})$ if $f^{n+1}$ exists.

## Binomial Series

> *Proposition.*{: .prop}
> **[Binomial Series]**
> If $k$ is any real number and $\vert x \vert < 1$, then
>
> $$
  (1 + x)^k = \sum_{r=0}^\infty {k \choose r} x^k = 1 + kx + {k(k-1) \over 2!}x^2 + \cdots
  $$
>
> *Proof.*{: .prf}
>
> For $f(x) = (1 + x)^k$ where $k$ can be any real number, we have
>
> $$
  \begin{align*}
  f(0) &= 1 \\
  f'(0) &= k \\
  f''(0) &= k(k-1) \\
  &\vdots \\
  f^{(r)}0) &= k(k-1)\cdots(k-r+1) \\
  \end{align*}
  $$
>
> Therefore, the Maclaurin series of $f(x)$ is
>
> $$
  (1 + x)^k = \sum_{r=0}^\infty {k \choose r} x^r
  $$
>
> When $k$ is non-negative integer, the series is finite as the terms with $n > k$ is $0$ and it is the same as the typical binonial expansion.
> Otherwise, the series is infinite and by Ratio test,
>
> $$
  \lim_{n \to \infty} \left| {a_{n+1} \over a_n}\right| = \lim_{n \to \infty} {|k - n| \over n + 1}|x| = |x|
  $$
>
> so the series converge if $\|x\| < 1$.

It is possible to prove that the remainder term $R_n(x)$ approaches $0$, but it turns out to be difficult.

> *Proposition.*{: .prop}
> The binonimal series is equal to $(1 + x)^k$.
>
> *Proof.*{: .prf}
>
> Let $g(x)$ be the binomial series, we have
>
> $$
  g'(x) = {k g(x) \over 1 + x}
  $$
>
> Let $h(x) = (1 + x)^{-k}g(x)$, $h(0) = 1$, and we have
>
> $$
  h'(x) = -(1+x)^{-k}{k g(x) \over 1+x} + (1+x)^{-k}g'(x) = 0
  $$
>
> Hence, $h(x)$ is a constant function, i.e. $h(x) = 1$, and $(1 + x)^k = \sum_{n=0}^{\infty} {k \choose n} x^n$.

This method of proving the function equals to its Taylor expansion can be used for other series as well.

## List of Important Series

$$
\begin{align*}
{1 \over 1-x} &= \sum_{n=0}^\infty x^n && = 1 + x + x^2 + x^3 + \cdots & (R = 1) \\
e^x &= \sum_{n=0}^\infty {x^n \over n!} && = 1 + {x \over 1!} + {x^2 \over 2!} + {x^3 \over 3!} + \cdots & (R = \infty) \\
\sin x &= \sum_{n=1}^\infty (-1)^n {x^{2n+1} \over (2n+1)!} && = x - {x^3 \over 3!} + {x^5 \over 5!} - {x^7 \over 7!} + \cdots & (R = \infty) \\
\cos x &= \sum_{n=0}^\infty (-1)^n {x^{2n} \over (2n)!} && = 1 - {x^2 \over 2!} + {x^4 \over 4!} - {x^6 \over 6!} + \cdots & (R = \infty) \\
\tan^{-1} x &= \sum_{n=0}^\infty (-1)^n {x^{2n+1} \over 2n+1} && = x - {x^3 \over 3} + {x^5 \over 5} - {x^7 \over 7} + \cdots & (R = 1) \\
\ln (1+x) &= \sum_{n=1}^\infty (-1)^{n-1}{x^n \over n} && = x - {x^2 \over 2} + {x^3 \over 3} - {x^4 \over 4} + \cdots & (R = 1) \\
(1+x)^k &= \sum_{n=0}^\infty {k \choose n} x^n && = 1 + kx + {k(k-1) \over 2!}x^2 + {k(k-1)(k-2) \over 3!}x^3 + \cdots & (R = 1) \\
\end{align*}
$$

The above series can be multiplied and divided to form new series,
i.e. if $f(x) = \sum a_n x^n$ and $g(x) = \sum b_n x^n$ converges for $\|x\| < R$ then their product also converges for $\|x\| < R$ and represents $f(x)g(x)$.

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 11.10
* [Gerald B. Folland _Advanced Calculus_, 2022 - Chapter 2.7](http://www.math.washington.edu/~folland/Homepage/AdvCalc24.pdf)
