---
layout: base
title: Series &#124; Analysis
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
