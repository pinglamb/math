---
layout: base
title: Continuous Functions &#124; Analysis II
---

# Continuous Functions
{: .page-title}

The notion of continuity is based on that of limit so we define that for functions of arbitrary metric spaces first.

> *Definition.*{: .def}
> Let $(X, \rho)$ and $(Y, \sigma)$ be metric spaces and $f: E \to Y$ with $E \subseteq X$ be a function and $x_0$ be a limit point of $E$ and $y_0 \in Y$.
> Then $f(x) \to y_0$ as $x \to x_0$ or $\lim_{x \to x_0} f(x) = y_0$ if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta > 0)(\forall x \in E : 0 < \rho(x, x_0) < \delta) \; \sigma(f(x), y_0) < \varepsilon
  $$

The point $x_0$ doesn't have to be in the domain of the function.

> *Proposition.*{: .prop}
> Let $(X, \rho)$ and $(Y, \sigma)$ be metric spaces and $f: E \to Y$ with $E \subseteq X$ be a function and $x_0$ be a limit point of $E$ and $y_0 \in Y$.
> Then $f(x) \to y_0$ as $x \to x_0$ iff for every sequence $(x_n)$ in $E - \Set{x_0}$ such that $x_n \to x_0$, $f(x_n) \to y_0$ as $n \to \infty$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose that $f(x) \to y_0$ as $x \to x_0$. Given $\varepsilon > 0$, there exists $\delta > 0$ such that
>
> $$
  0 < \rho(x, x_0) < \delta \implies \sigma(f(x), y_0) < \varepsilon
  $$
>
> On the other hand, for a sequence such that $x_n to x_0$ as $n \to \infty$, there exists $N > 0$ such that for all $n > N$,
> $\rho(x_n, x_0) < \delta$ and therefore $f(x_n) \to y_0$ as $n \to \infty$.
>
> ($\Leftarrow$) Suppose that whenever $x_n \to x_0$, $f(x_n) \to y_0$. Assume $f(x) \not\to y_0$ as $x \to x_0$,
> then there exists $\varepsilon > 0$ such that for all $\delta > 0$, $\rho(x, x_0) < \delta$ but $\sigma(f(x), y_0) \ge \varepsilon$.
> Therefore, there exists sequence $(x_n)$ such that for sufficiently large $n$, $\rho(x_n, x_0) < 1/n$ but $\sigma(f(x_n), y_0) \ge \varepsilon$
> so $f(x_n) \not\to y_0$ as $n \to \infty$ which is a contradiction.

For normed vector space, the algebra of elements allows the usual algebra of limits, i.e.

$$
\lim_{x \to x_0} a(x) f(x) + b(x) g(x) = ay_0 + bz_0
$$

## Continuity

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 3
