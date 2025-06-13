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

## Taylor Series

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 5.5, 5.6, 5.7, 5.8
