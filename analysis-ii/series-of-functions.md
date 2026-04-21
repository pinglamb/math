---
layout: base
title: Series of Functions &#124; Analysis II
---

# Series of Functions
{: .page-title}

The uniform convergence of sequence of functions can be naturally extended to uniform convergence of series of functions just like what we did for [real number series](../analysis-i/series.md).

> *Definition.*{: .def}
> Let $(f_n: X \to \mathbf{R})$ be a sequence of functions.
> Then the series $\sum_{n=1}^\infty f_n$ converges at a point $x \in X$ if the sequence of partial sums
>
> $$
  g_n = \sum_{j=1}^n f_j
  $$
>
> converges at $x$. The series converges uniformly if $(g_n)$ converges uniformly.

> *Definition.*{: .def}
> The series $\sum f_n$ converges absolutely at $x$ if $\sum \vert f_n \vert$ converges at $x$.
> The series $\sum f_n$ converges absolutely uniformly if $\sum \vert f_n \vert$ converges uniformly.

Similar to real number series, we have the following result.

> *Proposition.*{: .prop}
> If $\sum f_n$ converges absolutely uniformly, then $\sum f_n$ converges uniformly.
>
> *Proof.*{: .prf}
>
> Let $g_n = \sum_{j=1}^n f_j$ and $h_n = \sum_{j=1}^n \vert f_j \vert$. Then for $n > m$,
>
> $$
  \vert g_n - g_m \vert = \left| \sum_{j=m+1}^n f_j \right| \le \sum_{j=m+1}^n \vert f_j \vert = \vert h_n - h_m \vert
  $$
>
> Since $\sup \vert h_n - h_m \vert \to 0$, $\sup \vert g_n - g_m \vert \to 0$ so $\sum f_n$ converges uniformly.

> *Proposition.*{: .prop}
> **[Weierstrass M-test]**
> Let $(f_n: X \to \mathbf{R})$ be a sequence of functions.
> If, for each $n$, there is a constant $M_n$ such that
>
> $$
  \sup_{x \in X} \vert f_n(x) \vert \le M_n
  $$
>
> and $\sum M_n$ converges, then $\sum f_n$ converges (absolutely and) uniformly on $X$.
>
> *Proof.*{: .prf}
>
> Given $\varepsilon > 0$. Since $\sum M_n$ converges, there exists $N$ such that for all $N < m < n$,
>
> $$
  \vert M_n - M_m \vert \le \vert M_{m+1} \vert + \cdots + \vert M_n \vert < \varepsilon
  $$
>
> Let $g_n = \sum_{j=1}^n \vert f_n \vert$. For the same $N$, we have for all $N < m < n$,
>
> $$
  \sup \vert g_n - g_m \vert \le \sup(\vert f_{m+1} \vert + \cdots + \vert f_n \vert) \le \vert M_{m+1} \vert + \cdots + \vert M_n \vert < \varepsilon
  $$

> *Proposition.*{: .prop}
> **[Dirichlet Test]**
> Let $(a_n: X \to \mathbf{R})$ and $(f_n: X \to \mathbf{R})$ be sequences of functions. If
>
> + $s_n = \sum a_j$ is uniformly bounded on $X$, i.e. there is $M$ such that $\vert s_n \vert < M$ for all $n$ and $x \in X$;
>
> + for each $x$, $(f_n(x))$ is a monotonic sequence;
>
> + $f_n \to 0$ uniformly on $X$,
>
> then $\sum a_n f_n$ converges uniformly on $X$.

> *Proposition.*{: .prop}
> **[Abel Test]**
> Let $(a_n: X \to \mathbf{R})$ and $(f_n: X \to \mathbf{R})$ be sequences of functions. If
>
> + the series $\sum a_j$ converges uniformly on $X$;
>
> + for each $x$, $(f_n(x))$ is a monotonic sequence;
>
> + $f_n(x)$ is uniformly bounded on $X$,
>
> then $\sum a_n f_n$ converges uniformly on $X$.

## Power Series

With uniformity we can prove some deeper results about [power series](../analysis-i/power-series.md).

> *Proposition.*{: .prop}
> If the power series $\sum a_n z^n$ has radius of convergence $R$ and $0 < r < R$, then $\sum a_n z^n$ converges uniformly for $\vert z \vert \le r$.
>
> *Proof.*{: .prf}
>
> When $\vert z \vert \le r$, we have $\vert a_n z^n \vert \le \vert a_n \vert r^n$ in which the series $\sum a_n r^n$ converges since $0 < r < R$.
> By Weierstrass M-test, $\sum a_n z^n$ converges uniformly for $\vert z \vert \le r$.

> *Corollary.*{: .cor}
> The sum of a power series is continuous within its circle of convergence.
>
> *Proof.*{: .prf}
>
> Let $z_0$ be any point such that $\vert z_0 \vert < R$. If $\vert z_0 < r < R$, $\sum a_n z^n$ converges uniformly for $\vert z \vert \le r$ so $\sum a_n z^n$ is continuous at $z_0$.

> *Proposition.*{: .prop}
> **[Principle of equating coefficients]**
> If $\sum a_n z^n = \sum b_n z^n$ for a sequence of non-zero values of $z$ tending to $0$ as limit, then $a_n = b_n$ for all $n$.
>
> *Proof.*{: .prf}
>
> Let $(z_k)$ be the non-zero complex sequence satisfying the conditions.
> Assume the contrary that $a_m, b_m$ being the first pair of unequal coefficients. Then
>
> $$
  z_m \sum_{n = 0}^\infty (a_{m+n} - b_{m+n}) z^n = 0
  $$
>
> and therefore
>
> $$
  \sum_{n = 0}^\infty (a_{m+n} - b_{m+n}) z^n = 0
  $$
>
> for all non-zero $z_k$. The last power series clearly has a positive radius of convergence so it is continuous at $z = 0$.
> Hence, by substituting $z = 0$ we have $a_m - b_m = 0$ which is a contradiction.

> *Proposition.*{: .prop}
> **[Termwise differentiation]**
> Suppose that $\sum a_n x^n$ is a real power series converges to $f(x)$ with radius of convergence $R > 0$.
> Then $f(x)$ is differentiable in $(-R, R)$ where $f'(x) = \sum n a_n x^{n-1}$ has the same radius of convergence $R$.
>
> *Proof.*{: .prf}
>
> Let $R'$ be the radius of convergence for $g(x) = \sum n a_n x^{n-1}$. We have
>
> $$
  \vert a_n x^n \vert = \vert a_n x^{n-1} \vert \vert x \vert \le \vert n a_n x^{n-1} \vert \vert x \vert
  $$
>
> so by comparison test, if $g(x)$ converges absolutely for some $x$ then $f(x)$ also converges and $R' \le R$.
>
> If $R' < R$, then there are $R' < r' < r < R$ such that $\sum n a_n (r')^{n-1}$ diverges but $\sum a_n r^n$ converges.
> But
>
> $$
  { \vert a_n r^n \vert \over \vert n a_n (r')^{n-1} \vert } = \left( {r \over r'} \right)^{n-1} {r \over n} \ge 1
  $$
>
> so $\vert n a_n (r')^{n-1} \vert \le \vert a_n r^n \vert$ for sufficiently large $n$ so we must have $R' = R$.
>
> Let $f_n(x) = \sum_{j=0}^n a_j x^j$ and $f_n'(x) = \sum_{j=1}^n j a_j x^j$.
> $f_n(x)$ is obviously convergent at a point and $f_n'(x)$ is uniformly convergent for $\vert x \vert \le r < R$.
> So on any closed subinterval of $(-R, R)$, $f(x) = \lim_{n \to \infty} f_n(x)$ is differentiable with $f'(x) = \lim_{n \to \infty} f_n'(x)$.

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 5.3, 5.4
* [Dexter Chua _Part IB - Analysis II_, 2015 - Chapter 2](https://dec41.user.srcf.net/notes/IB_M/analysis_ii.pdf)
