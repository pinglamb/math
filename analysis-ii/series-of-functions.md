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
> Let $(f_n: X \to \mathbf{R}$ be a sequence of functions.
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

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 5.3, 5.4
* [Dexter Chua _Part IB - Analysis II_, 2015 - Chapter 2](https://dec41.user.srcf.net/notes/IB_M/analysis_ii.pdf)
