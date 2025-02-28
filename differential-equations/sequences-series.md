---
layout: base
title: Sequences and Series &#124; Differential Equations
---

# Sequences and Series
{: .page-title}

## Limit of Sequences

> *Definition.*{: .def}
> A sequence $\Set{a_n}$ has a limit $L$ and we write
>
> $$
  \lim_{n \to \infty} a_n = L
  $$
>
> if for every $\varepsilon > 0$ there is a corresponding integer $N$ such that
>
> $$
  \forall n > N, \quad |a_n - L| < \varepsilon
  $$
>
> The sequence is said to be **convergent** if the limit exists, otherwise it is **divergent**.

It is similar to the definition of limit of a function $f(x)$, therefore

$$
\lim_{x \to \infty} f(x) = L \text{ and } f(n) = a_n \implies \lim_{n \to \infty} a_n = L
$$

> *Definition.*{: .def}
> If a sequence diverges to $\infty$, then for all positive number $M$, there is an integer $N$ such that
>
> $$
  \forall n > N, \quad a_n > M
  $$

> *Property.*{: .prop}
> Let $\Set{a_n}$ be a sequence. Then
>
> $$
  \lim_{n \to \infty} |a_n| = 0 \implies \lim_{n \to \infty} a_n = 0
  $$
>
> *Proof.*{: .prf}
>
> As
>
> $$
  -|a_n| \le a_n \le |a_n| \quad \text{and} \quad \lim_{n \to \infty} |a_n| = 0 \implies \lim_{n \to \infty} -|a_n| = 0
  $$
>
> By Squeeze Theorem, $\lim_{n \to \infty} a_n = 0$.

It is useful for finding limits of alternating sequence, for example

$$
\lim_{n \to \infty} \left| {(-1)^n \over n} \right| = 0 \implies \lim_{n \to \infty} {(-1)^n \over n} = 0
$$

> *Property.*{: .prop}
> If $\lim_{n \to \infty} a_n = L$ and function $f$ is continuous at $L$, then
>
> $$
  \lim_{n \to \infty} f(a_n) = f(L)
  $$
>
> *Proof.*{: .prf}
>
> As $f$ is continuous at $L$, i.e.
>
> $$
  \lim_{x \to L} f(x) = f(L)
  $$
>
> Given an $\varepsilon$, there exists $\delta$ such that
>
> $$
  0 < |x - L| < \delta \implies |f(x) - f(L)| < \varepsilon
  $$
>
> Since $\lim_{n \to \infty} a_n = L$, there exists $N$ such that
>
> $$
  n > N \implies |a_n - L| < \delta
  $$
>
> Combining the above, given any $\varepsilon > 0$, we can find $N$ such that whenever $n > N$,
>
> $$
  |a_n - L| < \delta \implies |f(a_n) - f(L)| < \varepsilon
  $$
>
> Hence, $\lim_{n \to \infty} f(a_n) = f(L)$.

## Monotonic and Bounded Sequences

> *Definition.*{: .def}
> A sequence is **increasing** if
>
> $$
  \forall n \ge 1, \quad a_n < a_{n+1}
  $$

> *Definition.*{: .def}
> A sequence is **decreasing** if
>
> $$
  \forall n \ge 1, \quad a_n > a_{n+1}
  $$

> *Definition.*{: .def}
> A sequence is **monotonic** if it is either increasing or decreasing.

> *Definition.*{: .def}
> A sequence is **bounded above** if
>
> $$
  \forall n \ge 1, \quad a_n \le M
  $$

> *Definition.*{: .def}
> A sequence is **bounded below** if
>
> $$
  \forall n \ge 1, \quad m \le a_n
  $$

> *Definition.*{: .def}
> A sequence is bounded if it is bounded above and below.

> *Proposition.*{: .prop}
> Every monotonic, bounded sequence is convergent.
>
> *Proof.*{: .prf}
>
> If $\Set{a_n}$ is bounded above, there exists a least upper bound $L$.
> Given $\varepsilon > 0$, $L - \varepsilon$ is not an upper bound, so for some integer $N$
>
> $$
  L - \varepsilon < a_N \le L
  $$
>
> As $\Set{a_n}$ is increasing, $a_n \ge a_N$ for all $n > N$. Thus,
>
> $$
  L - \varepsilon < a_n \le L
  $$
>
> Hence, $\lim_{n \to \infty} a_n = L$.

## Series

> *Definition.*{: .def}
> A series is the infinite sum of a sequence $\Set{a_n}$.
> Let $s_n$ denote its $n$th partial sum, i.e.
>
> $$
  s_n = a_1 + a_2 + ... + a_n
  $$
>
> If the sequence $\Set{s_n}$ is convergent, then the sum of the series is defined by $s = \lim_{n \to \infty} s_n$.

> *Proposition.*{: .prop}
> The series is convergent if the underlying sequence $\Set{a_n}$ has limit $\lim_{n \to \infty} a_n = 0$.
>
> *Proof.*{: .prf}
>
> $$
  \lim_{n \to \infty} a_n = \lim_{n \to \infty} (s_n - s_{n-1}) = s - s = 0
  $$

The converse is not true though for example the harmonic series has the terms approaching $0$ but the sum is divergent.

## Divergence Test

> *Proposition.*{: .prop}
> **[Divergence Test]**
> If for the underlying sequence, $\lim_{n \to \infty} a_n \not = 0$, then the series is divergent.
>
> *Proof.*{: .prf}
>
> It is the contrapositive of the above statement about convergence of series.

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

## Comparison Test

> *Proposition.*{: .prop}
> **[Comparison Test]**
> Given two series $\sum a_n$ and $\sum b_n$ with positive terms.
> If $a_n \le b_n$ for all $n > N$ and $\sum b_n$ is convergent, then $\sum a_n$ is convergent.
> If $a_n \ge b_n$ for all $n > N$ and $\sum b_n$ is divergent, $\sum a_n$ is divergent.

For example, for $k \ge 3$,

$$
{\ln k \over k } > {1 \over k}
$$

As $\sum {1 \over k}$ is divergent, $\sum {\ln k \over k}$ is divergent.

> *Proposition.*{: .prop}
> If the limit
>
> $$
  \lim_{n \to \infty} {a_n \over b_n}
  $$
>
> exists and is equal to a finite number $c > 0$, then series are either both convergent or both divergent.

> *Proposition.*{: .prop}
> Suppose $\sum a_n$ converges because of the comparison test with $\sum b_n$.
> Consider the remainders of the two series $R_{(a, n)}$ and $R_{(b, n)}$, we have
>
> $$
  R_{(a, n)} \le R_{(b, n)}
  $$
>
> and hence we can find the upper bound of $R_{(a, n)}$ by estimating/finding $R_{(b,n)}$.

## Alternating Series

> *Proposition.*{: .prop}
> If the alternating series
>
> $$
  \sum_{n=1}^{\infty} (-1)^{n-1} a_n = a_1 - a_2 + a_3 - a_4 + ...
  $$
>
> with $a_n > 0$ satisfies
>
> $$
  a_{n+1} < a_n \quad \text{and} \quad \lim_{n \to \infty} a_n = 0
  $$
>
> then the series is convergent.

To find the limit of the alternating series, for example

$$
s_n = \sum_{n=1}^{\infty} (-1)^{n-1} a_n
$$

We have to find the limit of even partial sum $s_{2n}$. The odd partial sum will also approach the same limit because

$$
\lim_{n \to \infty} s_{2n+1} = \lim_{n \to \infty} s_{2n} + \lim_{n \to \infty} a_{2n+1} = s + 0 = s
$$

> *Proposition.*{: .prop}
> The remainder of the $n$th partial sum estimation is
>
> $$
  |R_n| \le a_{n+1}
  $$

## Absolute Convergence

> *Definition.*{: .def}
> A series $\sum a_n$ is **absolutely convergent** if the series of absolute values $\sum \| a_n \|$ is convergent.

> *Definition.*{: .def}
> A series is **conditionally convergent** if it is convergent but not absolutely convergent.

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
> By Comparison Test, we have $\sum a_n + \|a_n\|$ convergent.
>
> Also, we can write
>
> $$
  \sum a_n = \sum (a_n + |a_n|) - \sum |a_n|
  $$
>
> which is the difference of two convergent series and therefore the series itself is convergent.

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

## Rearrangements

As series involve infinite sums, rearrangement of the terms might affect the results.
By Riemann, if $\sum a_n$ is conditionally convergent, then there is a rearrangement that has a sum equals to any real number.
However, if $\sum a_n$ is absolutely convergent, then rearrangement will not check the sum.

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 11
