---
layout: base
title: Power Series &#124; Analysis
---

# Power Series
{: .page-title}

Power series are briefly discussed in [differential equations](../differential-equations/power-series.md) as [solutions](../differential-equations/series-solutions.md) to some of the problems.
We now have the tools to study rigorously about them.

> *Definition.*{: .def}
> A **power series** is a series of the form
>
> $$
  \sum_{n=0}^{\infty} a_n z^n
  $$
>
> where $z \in \mathbb{C}$ and $a_n \in \mathbb{C}$ for all $n$.

## Convergence

> *Lemma.*{: .lem}
> If a power series converges for a particular value of $w$, the it converges absolutely for all values of $z$ in the circle $\vert z \vert < \vert w \vert$.
>
> *Proof.*{: .prf}
>
> We have
>
> $$
  |a_n z^n| = |a_n w^n| \left| {z \over w} \right|^n
  $$
>
> Since $\sum a_n w^n$ converges, the terms $a_n w^n$ are bounded, say
>
> $$
  |a_n w^n| < C
  $$
>
> Then
>
> $$
  0 \le \sum_{n=0}^{\infty} |a_n z^n| < \sum_{n=0}^{\infty} C \left| {z \over w} \right|^n
  $$
>
> which converges as it is a geometric series. By comparison test, $\sum a_n z^n$ converges absolutely.

> *Theorem.*{: .thm}
> A power series either
>
> + convergess absolutely for all $z$, or
>
> + convergess absolutely for all $z$ inside a circle $\vert z \vert = R$ and diverges for all $z$ outside it, or
>
> + converges for $z = 0$ only.
>
> *Proof.*{: .prf}
>

> *Definition.*{: .def}
> The circle $\vert z \vert = R$ is called the **circle of convergence** and $R$ is called the **radius of convergence**.

> *Proposition.*{: .prop}
> If $\vert a_{n+1} / a_n \vert$ tends to a limit $l$ as $n \to \infty$,
> then the radius of convergence of $\sum a_n z^n$ is $1 / l$.
>
> *Proof.*{: .prf}
>
> By d'Alembert's ratio test, we have absolute convergence iff
>
> $$
  \left| {a_{n+1} z^{n+1} \over a_n z^n} \right| = \left| {a_{n+1} \over a_n} \right| |z| < 1 \quad \implies \quad |z| < {1 \over l}
  $$

It is to be noted that the convergence of values on the circle of convergence requires special investigation for any particular series.

## Multiplication

When we have two power series, it is useful if we can write the product of them as

$$
(a_0 + a_1z + a_2z^2 + \cdots)(b_0 + b_1z + b_2z^2 + \cdots) = a_0b_0 + (a_1b_0 + a_0b_1)z + (a_2b_0 + a_1b_1 + a_0b_2)z^2 + \cdots
$$

The following theorem works for any absolutely convergent series which need not be power series

> *Theorem.*{: .thm}
> If $\sum u_n$ and $\sum v_n$ converges absolutely to sums $s$ and $t$,
> then the series consisting of their products (in any other) converges absolutely to $st$.
>
> *Proof.*{: .prf}
>
> The products of pairs of terms form a doubly infinite array
>
> $$
  \begin{vmatrix}
  u_0 v_0 & u_0 v_1 & u_0 v_2 & \cdots \\
  u_1 v_0 & u_1 v_1 & u_1 v_2 & \cdots \\
  u_2 v_0 & u_2 v_1 & u_2 v_2 & \cdots \\
  \cdots & \cdots & \cdots & \cdots
  \end{vmatrix}
  $$
>
> The sum of all these terms can be arranged in infinitely many ways, but whatever the arrangement, it doesn't exceed
>
> $$
  \left( \sum_0^\infty |u_n| \right)\left( \sum_0^\infty |v_n| \right)
  $$
>
> so the series consisting of their products converges absolutely. Thus the sum is the same for whatever order of the terms.
> One particular order, namely, summation by squares, gives an evident sum that all terms with suffices not exceeding $n$ is
>
> $$
  (u_0 + u_1 + \cdots + u_n)(v_0 + v_1 + \cdots + v_n)
  $$
>
> and hence the limit of the sum is $st$.

> *Corollary.*{: .cor}
> If $\sum a_n z^n$ and $\sum b_n z^n$ have radii of convergence $R$ and $S$, then their product is
>
> $$
  \sum_{n=0} (a_n b_0 + a_{n-1} b_1 + \cdots + a_0b_n) z^n
  $$
>
> for $\vert z \vert < \min(R, S)$.

## Taylor's Series

In the discussion of [Taylor's Theorem](differentiation-theorems.md#taylor-theorem), we have shown the way to approximate a function by polynomials, which is indeed a power series.

> *Theorem.*{: .thm}
> **[Taylor's Series]**
> Suppose $f$ has derivatives of every order for neighbourhood $(a - k, a + k)$.
> For $\vert h \vert < k$, if the remainder $r_n$ (the term in $h^n$) tends to $0$ as $n$ tends to $\infty$, then
>
> $$
  f(a + h) = f(a) + hf'(a) + \cdots + {h^n \over n!}f^{(n)}(a) + \cdots
  $$
>
> For the case of $a = 0$, the expansion cound be called **Maclaurin's series**.

We can use this to determine the radius of convergence of the Taylor's series of $f(x)$, by checking in what values $r_n \to 0$ as $n \to \infty$.
We have proved the [binomial series](../differential-equations/power-series.md#binomial-series) before but this time we focus on the remainder term.

> *Lemma.*{: .lem}
> If $-1 < x < 1$,
>
> $$
  {m \choose n} x^n = {m(m-1)...(m-n+1) \over n!} x^n
  $$
>
> tends to $0$ as $n \to \infty$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \lim_{n \to \infty} \left| {a_{n+1} \over a_n} \right|
  &= \lim_{n \to \infty} \left| {m-n \over n+1} \right| |x| \\
  &= \lim_{n \to \infty} \left| {1 - m/n \over 1 + 1/n} \right| |x| \\
  &= |x|
  \end{align*}
  $$
>
> As $\vert x \vert < 1$, the series $\sum a_n$ converges by d'Alembert's ratio test.
> Hence, the underlying sequence is a null sequence.

> *Proposition.*{: .prop}
> **[Binomial Theorem]**
> Given $m \in \mathbb{Q}$. For $-1 < x < 1$,
>
> $$
  (1 + x)^m = 1 + {m \choose 1} x + \cdots + {m \choose n} x^n + \cdots
  $$
>
> *Proof.*{: .prf}
>
> If $m$ is positive integer, $f^{(m+1)}(x) \equiv 0$ and we have a polynomial of degree $m$.
>
> In the general case, we have
>
> $$
  r_n = {x^n \over n!} f^{(n)}(\theta x) = {m \choose n} { x^n \over (1 + \theta x)^{n-m} }
  $$
>
> where $\theta$ depends on $n$.
>
> For $0 \le x < 1$, $(1 + \theta x)^{n - m} \ge 1$ for $n > m$ and ${m \choose n} x^n \to 0$ as $n \to \infty$ so $r_n \to 0$.
>
> For $-1 < x < 0$, the above argument doesn't work as $(1 + \theta x) < 1$.
> Instead, consider the Cauchy's remainder with $k = 1$ (which actually applies for the full range $-1 < x < 1$), we have
>
> $$
  r_n = { m(m-1)...(m-n+1) \over (n - 1)! } {(1 - \theta)^{n-1} x^n \over (1 + \theta x)^{n-m} }
  $$
>
> We have $(1 - \theta)/(1 + \theta x) < 1$ and so
>
> $$
  |r_n| < K_m \left| {m-1 \choose n-1} \right| |x|^n
  $$
>
> which tends to $0$ as $n \to \infty$.

## Differentiation

We wish to show that the derivative of $\sum a_n x^n$ is indeed $\sum n a_n x^{n-1}$ inside the circle of convergence.
Practically, there can be more straightforward arguments to find the derivatives of certain power series.

> *Proposition.*{: .prop}
> Suppose $\sum a_n z^n$ has radius of convergence $R$.
> Then $\sum n a_n z^{n-1}$ converges absolutely for $\vert z \vert < R$.

> *Proposition.*{: .prop}
> Suppose $f(z) = \sum a_n z^n$ has radius of convergence $R$.
> Then $f$ is differential and has derivative $f'(z) = \sum n a_n z^{n-1}$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 5.5, 5.6, 5.7, 5.8
