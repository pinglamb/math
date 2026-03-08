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
