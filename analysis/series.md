---
layout: base
title: Series &#124; Analysis
---

# Series
{: .page-title}

The convergence of a sequence allows us to consider infinite sums, or series.

> *Definition.*{: .def}
> A **series** is the infinite sum of a sequence $(a_n)$.
> Let $s_n$ denote its $n$th **partial sum**, i.e.
>
> $$
  s_n = \sum_{k=1}^n a_n = a_1 + a_2 + \cdots + a_n
  $$
>
> If $s_n \to s$, then we say the series converges to $s$, otherwise the series diverges.

> *Proposition.*{: .prop}
> If a series $\sum a_n$ converges, then $a_n \to 0$.
>
> *Proof.*{: .prf}
>
> Let $\sum a_n = s$. Then $s_n \to s$ and $s_{n-1} \to s$, so $a_n = s_n - s_{n-1} \to 0$.

It provides an easy check for divergence when we know the explicit formula of $a_n$.

> *Proposition.*{: .prop}
> **[Divergence Test]**
> If the underlying sequence is not a null sequence, i.e. $a_n \not \to 0$, then the series is divergent.

The converse of the statement is not true though, for example the harmonic series has the terms approaching $0$ but the sum is divergent.

> *Proposition.*{: .prop}
> **[Harmonic Series]**
> The sequence $a_n = 1/n$ converges to $0$ but the series
>
> $$
  \sum_{n=1}^\infty {1 \over n} = 1 + {1 \over 2} + {1 \over 3} + \cdots = \infty
  $$
>
> *Proof.*{: .prf}
>
> Consider the terms $a_{2^n + 1}$ to $a_{2^{n+1}}$, their sum is
>
> $$
  {1 \over 2^n + 1} + {1 \over 2^n + 2} + \cdots + {1 \over 2^{n+1}} \ge {2^n \over 2^{n+1}} = {1 \over 2}
  $$
>
> Therefore, the sum is
>
> $$
  1 + {1 \over 2} + {1 \over 3} + {1 \over 4} + \cdots = 1 + {1 \over 2} + \left({1 \over 3} + {1 \over 4}\right) + \cdots \ge 1 + {1 \over 2} + {1 \over 2} + \cdots = \infty
  $$

Here are some examples of convergent series.

> *Proposition.*{: .prop}
> **[Geometric Series]**
> If $\vert r \vert < 1$, then
>
> $$
  \sum_{n=0}^\infty r^n = {1 \over 1 - r}
  $$
>
> *Proof.*{: .prf}
>
> $(1 - r)s_n = 1 - r^{n+1}$. As $n \to \infty$, $r^{n+1} \to 0$, hence $s_n \to 1 / (1 - r)$.

> *Proposition.*{: .prop}
> Let
>
> $$
  a_n = {1 \over n(n+1)} = {1 \over n} - {1 \over n+1}
  $$
>
> Then
>
> $$
  s_n = \left(1 - {1 \over 2}\right) + \left({1 \over 2} - {1 \over 3}\right) + \cdots = 1 - {1 \over {n+1}}
  $$
>
> So, $s_n \to 1$ as $n \to \infty$.

> *Property.*{: .prop}
> As convergence of series is equivalent to convergence of its partial sum sequence, we have
>
> + when the sum exists, it is unique;
>
> + $\sum (s_n + t_n) = s + t$;
>
> + $\sum cs_n = cs$;
>
> + if $s_n \le t_n$ for all $n$, then $s \le t$.

Complex series converge iff the sum of real parts and the sum of imaginary parts both converge.

> *Proposition.*{: .prop}
> Suppose that $z_n = x_n + i y_n$ and $s = \sigma + i\tau$.
> Then $\sum z_n$ converges to $s$ if $\sum x_n$ converges to $\sigma$ and $\sum y_n$ converges to $\tau$.

> *Proposition.*{: .prop}
> **[General Principle of Convergence]**
> Suppose that $(z_n)$ is a sequence of complex numbers.
> Then $\sum z_n$ converges iff
>
> $$
  (\forall \varepsilon > 0)(\exists N \in \mathbb{N})(\forall m, n : m > n \ge N)\;|s_m - s_n| = \left|\sum_{j=n+1}^m z_j \right| < \varepsilon
  $$

## Series with Non-negative Terms

Series with terms being real and non-negative has some immediate consequence.

> *Proposition.*{: .prop}
> Suppose that $(a_n)$ is a sequence of non-negative real numbers, then $(s_n)$ is an increasing sequence.
> Either $(s_n)$ is bounded and $s_n \to \sup_n s_n$ or $s_n \to \infty$.

> *Proposition.*{: .prop}
> **[Comparison Test]**
> Suppose $0 \le b_n \le a_n$ for all $n \ge N$.
> If $\sum a_n$ is convergent, then $\sum b_n$ is convergent and $\sum b_n \le \sum a_n$.
> If $\sum b_n$ is divergent, then $\sum a_n$ is divergent.

For example, $1 / n^2 \le 2 / n(n+1)$, so $\sum 1/n^2$ is convergent.
When $n \ge 3$, $\ln n / n > 1 / n$, so $\sum \ln n / n$ is divergent.

> *Corollary.*{: .cor}
> If $a_n / b_n \to c$ as $n \to \infty$, where $c > 0$,
> then the corresponding series are either both convergent or both divergent.

The comparison test can be turned into the following applicable forms.

> *Corollary.*{: .cor}
> **[Cauchy's Test]**
> Suppose that $(a_n)$ is a bounded sequence of non-negative real numbers.
> If $\limsup_{n \to \infty} a_n^{1/n} < 1$ then $\sum a_n$ converges.
> If $\limsup_{n \to \infty} a_n^{1/n} > 1$ then $\sum a_n = \infty$.
>
> *Proof.*{: .prf}
>
> In the first case, choose $r$ such that $\limsup_{n \to \infty} a_n^{1/n} < r < 1$.
> Then there exists $N$ such that $a_n^{1/n} < r$ for all $n \ge N$.
> Hence, $0 \le a_n \le r^n$ for $n \ge N$ and $\sum a_n$ converges by comparison test.
>
> In the second case, for each $n$ there exists $m \ge n$ such that $a_m^{1/m} > 1$ so $a_m > 1$.
> Hence, $a_n$ is not a null sequence and $\sum a_n$ diverges to $\infty$.

> *Corollary.*{: .cor}
> **[D'Alembert's Ratio Test]**
> Suppose that $(a_n)$ is a sequence of positive real numbers.
> If $\limsup_{n \to \infty} a_{n+1}/a_n < 1$ then $\sum a_n$ converges.
> If $\liminf_{n \to \infty} a_{n+1}/a_n > 1$ then $\sum a_n = \infty$.
>
> *Proof.*{: .prf}
>
> In the first case, choose $r$ such that $\limsup_{n \to \infty} a_{n+1}/a_n < r < 1$.
> Then there exists $N$ such that $a_{n+1}/a_n < r$ for all $n \ge N$.
> Thus, if $n > N$ then
>
> $$
  a_n = \left( {a_n \over a_{n-1}} \right) \left( {a_{n-1} \over a_{n-2}} \right) \cdots \left( {a_{N+1} \over a_{N}} \right) a_N
  \le r^{n - N} a_N = M r^n
  $$
>
> Hence, $0 \le a_n \le M r^n$ for $n \ge N$ and $\sum a_n$ converges by comparison test.

In practice, we can check if $a_n^{1/n}$ or $a_{n+1}/a_n$ tends to a limit less than $1$. If so, $\sum a_n$ converges.

## Absolute Convergence

> *Definition.*{: .def}
> A series $\sum a_n$ is **absolutely convergent** if the series $\sum \vert a_n \vert$ is convergent.

For example, alternating harmonic series is conditionally convergent.

> *Proposition.*{: .prop}
> If a series is absolutely convergent, then it is convergent.
>
> *Proof.*{: .prf}
>
> Consider
>
> $$
  0 \le a_n + |a_n| \le 2|a_n|
  $$
>
> By Comparison Test, we have $\sum (a_n + \vert a_n \vert)$ convergent.
> Hence,
>
> $$
  \sum a_n = \sum (a_n + |a_n|) - \sum |a_n|
  $$
>
> is the difference of two convergent series and therefore the series itself is convergent.

Therefore, for series with negative terms, we can prove convergence by showing it is absolutely convengent.

> *Definition.*{: .def}
> A series is **conditionally convergent** if it is convergent but not absolutely convergent.

> *Proposition.*{: .prop}
> For a sequence $(a_n)$, denote
>
> $$
  a_n^+ = \begin{cases}
  a_n & \text{for } a_n \ge 0 \\
  0 & \text{for } a_n < 0
  \end{cases}
  \quad \text{and} \quad
  a_n^- = \begin{cases}
  0 & \text{for } a_n \ge 0 \\
  -a_n & \text{for } a_n < 0
  \end{cases}
  $$
>
> i.e. $(a_n^+)$ are the positive terms and $(a_n^-)$ are the negated negative terms.
>
> If the series converges conditionally, then $\sum a_n^+ = +\infty$ and $\sum a_n^- = +\infty$,
> meaning the sum of only positive terms and the sum of only negative terms both diverges.
>
> *Proof.*{: .prf}
>
> As $s_n = \sum a_n^+ - \sum a_n^-$, at least one of the sums must diverge.
> Suppose $\sum a_n^+$ diverges and $\sum a_n^- = s_-$, we can always find an $N$ such that $s_n > M$ for $n > N$.
> Therefore, $(s_n)$ is unbounded and doesn't converge, which is a contradiction.
> A similar argument applies if $\sum a_n^+$ converges but $\sum a_n^-$ diverges.
> Hence, both of them has to diverge.

## Alternating Series Test

> *Proposition.*{: .prop}
> **[Alternating Series Test]**
> Suppose $(a_n)$ is a decreasing null sequence of positive real numbers.
> Then $s_n = \sum (-1)^n a_n$ converges, say, to $s$.
> Further, the sequence $(s_{2n+1})$ increases to $s$ and $(s_{2n})$ decreases to $s$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  s_{2n+1} &= s_{2n-1} + (a_{2n} - a_{2n+1}) \ge s_{2n-1} \\
  s_{2n+2} &= s_{2n} - (a_{2n+1} - a_{2n+2}) \le s_{2n}
  \end{align*}
  $$
>
> and
>
> $$
  \begin{align*}
  s_{2n+1} &= s_{2n} - a_{2n+1} \le s_{2n} \le s_0 \\
  s_{2n+2} &= s_{2n+1} + a_{2n+2} \ge s_{2n+1} \ge s_1 \\
  \end{align*}
  $$
>
> so $(s_{2n+1})$ is an increasing sequence bounded above and $(s_{2n})$ is a decreasing sequence bounded below.
> Both of them converges, and to the same value because $s_{2n} - s_{2n+1} = a_{2n+1} \to 0$, and so as $s_n$.

Therefore for alternating series, we can find the sum of even terms $s_{2n}$ (or odd terms $s_{2n+1}$) and the series will converge to the same value.

> *Proposition.*{: .prop}
> The remainder of the $n$th partial sum estimation is
>
> $$
  |R_n| \le a_{n+1}
  $$

## Ratio/Root Test

To check for absolute convergence, we can use the ratio/root test.

> *Proposition.*{: .prop}
> **[Ratio Test]**
> Suppose a series $\sum a_n$ satisfies
>
> $$
  \lim_{n \to \infty} \left| {a_{n+1} \over a_n} \right| = L
  $$
>
> + If $L < 1$, the series is absolutely convergent.
>
> + If $L > 1$, the series is divergent.
>
> + If $L = 1$, the test is inconclusive.

When $n$ appears in the power, the root test will be useful.

> *Proposition.*{: .prop}
> **[Root Test]**
> Suppose a series $\sum a_n$ satisfies
>
> $$
  \lim_{n \to \infty} \sqrt[n]{\left| a_n \right|} = L
  $$
>
> + If $L < 1$, the series is absolutely convergent.
>
> + If $L > 1$, then the series is divergent.
>
> + If $L = 1$, the test is inconclusive.

## Integral Test

> *Proposition.*{: .prop}
> **[Integral Test]**
> Suppose $f$ is a continuous, positive, decreasing function on $[1, \infty)$ such that $f(n) = a_n$.
> If $\int_{1}^{\infty} f(x) \mathrm{d}x$ is convengent/divergent, so as $\sum_{n=1}^{\infty} a_n$.

For example, consider the series

$$
\sum_{n=1}^{\infty} {1 \over n^2} = {1 \over 1^2} + {1 \over 2^2} + {1 \over 3^2} + ...
$$

Geometrically, we can form rectangles under the graph of $y = 1/x^2$, each with a unit width and height eqauls to the value of function.
The sum of the area of the rectangles equals to the sum of the series. Consider all the terms excluding the first one $1/1^2$,
it has to be less than the area under the function from $1$ to $\infty$. Hence,

$$
\sum_{n=1}^{\infty} {1 \over n^2} < {1 \over 1^2} + \int_{1}^{\infty} { 1 \over x^2} \mathrm{d}x = 1 + 1 = 2
$$

As the partial sum $\Set{s_n}$ is increasing and bounded above, the series is convengent.

![Integral Test Below](../images/integral-test-below.png)

On the other hand, we can also form rectangles with tops lie above the curve to show the series is divergent. Consider the series

$$
\sum_{n=1}^{\infty} {1 \over \sqrt{n}} = {1 \over \sqrt{1}} + {1 \over \sqrt{2}} + {1 \over \sqrt{3}} + ...
$$

We have

$$
\sum_{n=1}^{\infty} {1 \over \sqrt{n}} > \int_{1}^{\infty} {1 \over \sqrt{x}} \mathrm{d}x = \infty
$$

So, the series is divergent.

![Integral Test Above](../images/integral-test-below.png)

We can also use the integral to estimate the sum.

> *Proposition.*{: .prop}
> Let $R_n$ be the remainder of the partial sum $s_n$, i.e.
>
> $$
  R_n = s - s_n = a_{n+1} + a_{n+2} + ...
  $$
>
> By forming rectangles with top above/below the curve, we have
>
> $$
  \int_{n+1}^{\infty} f(x) \mathrm{d}x \le R_n \le \int_{n}^{\infty} f(x) \mathrm{d}x
  $$
>
> By adding $s_n$ to the inequalities, the upper bound and lower bound for $s$ is given by
>
> $$
  s_n + \int_{n+1}^{\infty} f(x) \mathrm{d}x \le s \le s_n + \int_{n}^{\infty} f(x) \mathrm{d}x
  $$

## Rearrangements

As series involve infinite sums, rearrangement of the terms might affect the results.
By Riemann, if $\sum a_n$ is conditionally convergent, then there is a rearrangement that has a sum equals to any real number.
However, if $\sum a_n$ is absolutely convergent, then rearrangement will not check the sum.

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 11
