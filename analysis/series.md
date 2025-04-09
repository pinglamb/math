---
layout: base
title: Series &#124; Analysis
---

# Series
{: .page-title}

The convergence of a sequence allows us to consider infinite sums, or series.

> *Definition.*{: .def}
> A **series** is the infinite sum of a sequence $(a_k)$.
> Let $s_n$ denote its $n$th **partial sum**, i.e.
>
> $$
  s_n = \sum_{k=1}^n a_k = a_1 + a_2 + \cdots + a_n
  $$
>
> If $s_n \to s$, then we say the series converges to $s$, otherwise the series diverges.

> *Proposition.*{: .prop}
> If a series $\sum a_k$ converges, then $a_n \to 0$.
>
> *Proof.*{: .prf}
>
> Let $\sum a_k = s$. Then $s_n \to s$ and $s_{n-1} \to s$, so $a_n = s_n - s_{n-1} \to 0$.

It provides an easy check for divergence when we know the explicit formula of $a_k$.

> *Proposition.*{: .prop}
> **[Divergence Test]**
> If the underlying sequence is not a null sequence, i.e. $a_n \not \to 0$, then the series is divergent.

The converse of the statement is not true though, for example the harmonic series has the terms approaching $0$ but the sum is divergent.

> *Proposition.*{: .prop}
> **[Harmonic Series]**
> The sequence $(a_k = 1/k)$ converges to $0$ but the series
>
> $$
  \sum_{k=1}^\infty {1 \over k} = 1 + {1 \over 2} + {1 \over 3} + \cdots = \infty
  $$
>
> *Proof.*{: .prf}
>
> Consider the terms $a_{2^k + 1}$ to $a_{2^{k+1}}$, their sum is
>
> $$
  {1 \over 2^k + 1} + {1 \over 2^k + 2} + \cdots + {1 \over 2^{k+1}} \ge {2^k \over 2^{k+1}} = {1 \over 2}
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
  \sum_{k=0}^\infty r^k = {1 \over 1 - r}
  $$
>
> *Proof.*{: .prf}
>
> $(1 - r)s_n = 1 - r^{n+1}$. As $n \to \infty$, $r^{n+1} \to 0$, hence $s_n \to 1 / (1 - r)$.

> *Proposition.*{: .prop}
> Let
>
> $$
  a_k = {1 \over k(k+1)} = {1 \over k} - {1 \over k+1}
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
> + $\sum (a_k + b_k) = s + t$;
>
> + $\sum ca_k = cs$;
>
> + if $a_n \le b_n$ for all $n$, then $s \le t$.

Complex series converge iff the sum of real parts and the sum of imaginary parts both converge.

> *Proposition.*{: .prop}
> Suppose that $z_k = x_k + i y_k$ and $s = \sigma + i\tau$.
> Then $\sum z_k$ converges to $s$ if $\sum x_k$ converges to $\sigma$ and $\sum y_k$ converges to $\tau$.

> *Proposition.*{: .prop}
> **[General Principle of Convergence]**
> Suppose that $(z_k)$ is a sequence of complex numbers.
> Then $\sum z_k$ converges iff
>
> $$
  (\forall \varepsilon > 0)(\exists N \in \mathbb{N})(\forall m, n : m > n \ge N)\;|s_m - s_n| = \left|\sum_{k=n+1}^m z_k \right| < \varepsilon
  $$

## Series with Non-negative Terms

Series with terms being real and non-negative has some immediate consequence.

> *Proposition.*{: .prop}
> Suppose that $(a_k)$ is a sequence of non-negative real numbers, then $(s_n)$ is an increasing sequence.
> Either $(s_n)$ is bounded and $s_n \to \sup_n s_n$ or $s_n \to \infty$.

> *Proposition.*{: .prop}
> **[Comparison Test]**
> Suppose $0 \le b_k \le a_k$ for all $k \ge K$.
>
> + If $\sum a_k$ is convergent, then $\sum b_k$ is convergent and $\sum b_k \le \sum a_k$.
>
> + If $\sum b_k$ is divergent, then $\sum a_k$ is divergent.
>
> *Proof.*{: .prf}
>
> It is obvious by the Sandwich Principle on the partial sum sequences.

For example, $1 / k^2 \le 2 / k(k+1)$, so $\sum 1/k^2$ is convergent.
When $k \ge 3$, $\ln k / k > 1 / k$, so $\sum \ln k / k$ is divergent.

> *Corollary.*{: .cor}
> If $a_k / b_k \to c$ as $n \to \infty$, where $c > 0$,
> then the corresponding series are either both convergent or both divergent.

The comparison test can be turned into the following applicable forms.

> *Corollary.*{: .cor}
> **[Cauchy's Test]**
> Suppose that $(a_k)$ is a bounded sequence of non-negative real numbers.
>
> + If $\limsup_{k \to \infty} a_k^{1/k} < 1$ then $\sum a_k$ converges.
>
> + If $\limsup_{k \to \infty} a_k^{1/k} > 1$ then $\sum a_k = \infty$.
>
> *Proof.*{: .prf}
>
> In the first case, choose $r$ such that $\limsup_{n \to \infty} a_k^{1/k} < r < 1$.
> Then there exists $K$ such that $a_k^{1/k} < r$ for all $k \ge K$.
> Hence, $0 \le a_k \le r^k$ for $k \ge K$ and $\sum a_k$ converges by comparison test.
>
> In the second case, for each $k$ there exists $h \ge k$ such that $a_h^{1/h} > 1$ so $a_h > 1$.
> Hence, $a_k$ is not a null sequence and $\sum a_k$ diverges to $\infty$.

> *Corollary.*{: .cor}
> **[D'Alembert's Ratio Test]**
> Suppose that $(a_k)$ is a sequence of positive real numbers.
>
> + If $\limsup_{k \to \infty} a_{k+1}/a_k < 1$ then $\sum a_k$ converges.
>
> + If $\liminf_{k \to \infty} a_{k+1}/a_k > 1$ then $\sum a_k = \infty$.
>
> *Proof.*{: .prf}
>
> In the first case, choose $r$ such that $\limsup_{n \to \infty} a_{k+1}/a_k < r < 1$.
> Then there exists $K$ such that $a_{k+1}/a_k < r$ for all $k \ge K$.
> Thus, if $k > K$ then
>
> $$
  a_k = \left( {a_k \over a_{k-1}} \right) \left( {a_{k-1} \over a_{k-2}} \right) \cdots \left( {a_{K+1} \over a_{K}} \right) a_K
  \le r^{k - K} a_K = (a_K / r^K) r^k = M r^k
  $$
>
> Hence, $0 \le a_k \le M r^k$ for $k \ge K$ and $\sum a_k$ converges by comparison test.
>
> In the second case, there exists $K$ such that $a_{k+1} > a_k$ for $k \ge K$.
> So $a_k \ge a_K$ for $k \ge K$ and $(a_k)$ is not a null sequence and $\sum a_k$ diverges to $\infty$.

In practice, we can check if $a_k^{1/k}$ or $a_{k+1}/a_k$ tends to a limit less than $1$. If so, $\sum a_k$ converges.
The test is inconclusive if they are equal to $1$.

## Absolute Convergence

We now consider series with both positive and negative terms, or even complex terms.

> *Definition.*{: .def}
> A series $\sum z_k$ is **absolutely convergent** if the series $\sum \vert z_k \vert$ is convergent.

Suppose $\sum a_k$ is a real series with both positive and negative terms, it is useful we first define

$$
a_k^+ = \begin{cases}
a_k & \text{for } a_k \ge 0 \\
0 & \text{for } a_k < 0
\end{cases}
\quad \text{and} \quad
a_k^- = \begin{cases}
0 & \text{for } a_k \ge 0 \\
-a_k & \text{for } a_k < 0
\end{cases}
$$

such that $(a_k^+)$ is the sequence of the positive terms and $(a_k^-)$ is the sequence of negated negative terms and $a_k = a_k^+ - a_k^-$.

> *Proposition.*{: .prop}
> If a series $\sum z_k$ is absolutely convergent then it converges, and $\vert \sum z_k \vert \le \sum \vert z_k \vert$.
>
> *Proof.*{: .prf}
>
> If $z_k = x_k + i y_k$, we have both $\vert x_k \vert \le \vert z_k \vert$ and $\vert y_k \vert \le \vert z_k \vert$.
> So $\sum \vert z_k \vert$ converges iff $\sum \vert x_k \vert$ and $\sum \vert y_k \vert$ do and it is enough to consider real series.
>
> Suppose $\sum \vert a_k \vert$ converges, we have $\sum a_k^+$ and $\sum a_k^-$ both converges, so $\sum a_k = \sum a_k^+ - \sum a_k^-$ also converges.
>
> Since the partial sums $\vert \sum^n a_k \vert \le \sum^n \vert a_k \vert$ for all $n$, the limits $\vert \sum^\infty z_k \vert \le \sum^\infty \vert z_k \vert$.

Absolutely convergent series are generally as well behaved as series with non-negative terms.
The comparison test, D'Alembert's test and Cauchy's test can be used to test for absolute convergence.

Series can still converge if it is not absolutely convergent, but the arguments are generally more delicate.

> *Definition.*{: .def}
> A series is **conditionally convergent** if it is convergent but not absolutely convergent.

For example, alternating harmonic series is conditionally convergent.

> *Proposition.*{: .prop}
> If a series $\sum a_k$ converges conditionally, then $\sum a_k^+ = +\infty$ and $\sum a_k^- = +\infty$.
>
> *Proof.*{: .prf}
>
> As $s_n = \sum a_k^+ - \sum a_k^-$, at least one of the sums must diverge.
> Suppose $\sum a_k^+$ diverges and $\sum a_k^- = s_-$.
> For any $M > 0$, there exists $N$ such that $\sum^n a_k^+ > M + s_-$ for $n > N$, we have
>
> $$
  s_n = \sum^n (a_k^+ - a_k^-) \ge \sum^n a_k^+ - s_- > M
  $$
>
> Therefore, $(s_n)$ diverges to $\infty$, which is a contradiction.
> A similar argument applies if $\sum a_n^+$ converges but $\sum a_n^-$ diverges.
> Hence, both of them has to diverge.

Thus conditional convergence depends on cancellation of positive and negative quantities.
We still have some tests for convergence in such cases.

> *Proposition.*{: .prop}
> **[Alternating Series Test]**
> Suppose that
>
> + $(a_k)$ is a decreasing null sequence of positive real numbers.
>
> Then $\sum (-1)^k a_k$ converges, say, to $s$.
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
> Both of them converges, and to the same limit because $s_{2n} - s_{2n+1} = a_{2n+1} \to 0$, and $s_n$ converges to the common limit.

> *Proposition.*{: .prop}
> **[Hardy's Test]**
> Suppose that
>
> + $(w_k)$ is a null sequence of complex numbers for which $\sum \vert a_k - a_{k-1} \vert < \infty$;
>
> + $(z_k)$ is a sequence of complex numbers for which the sequence of partial sums $(\sum^n z_k)$ is bounded.
>
> Then $\sum w_k z_k$ converges.

> *Proposition.*{: .prop}
> **[Dirichlet's Test]**
> Suppose that
>
> + $(a_k)$ is a decreasing null sequence of positive numbers;
>
> + $(z_k)$ is a sequence of complex numbers for which the sequence of partial sums $(\sum^n z_k)$ is bounded.
>
> Then $\sum a_k z_k$ converges, say, to $s$.
> Further, if $s_m = \sum^m a_k z_k$ and $M = \sup_n \vert t_n \vert$ then $\vert s - s_m \vert \le 2 a_{m+1} M$.

> *Proposition.*{: .prop}
> **[Abel's Test]**
> Suppose that
>
> + $(a_k)$ is a decreasing null sequence of positive numbers;
>
> + $\sum z_k$ converges.
>
> Then $\sum a_k z_k$ converges.

## Integral Test

> *Proposition.*{: .prop}
> **[Integral Test]**
> Suppose $f$ is a continuous, positive, decreasing function on $[1, \infty)$ such that $f(n) = a_n$.
> If $\int_{1}^{\infty} f(x) \mathrm{d}x$ is convergent/divergent, so as $\sum_{n=1}^{\infty} a_n$.

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

As the partial sum $\Set{s_n}$ is increasing and bounded above, the series is convergent.

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
