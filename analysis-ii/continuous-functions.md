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

We can now naturally extend the definition of continuity to functions of metric spaces.

> *Definition.*{: .def}
> Let $(X, \rho)$ and $(Y, \sigma)$ be metric spaces and $f: X \to Y$ be a function.
> Then $f$ is **continuous** at the point $x_0 \in X$ if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta > 0)(\forall x \in X: \rho(x, x_0) < \delta) \; \sigma(f(x), f(x_0)) < \varepsilon
  $$
>
> (or $f(B_\delta(x_0)) \subset B_\varepsilon(f(x_0))$).

The definition implies that $f$ is continuous at a limit point $x_0$ if $f(x) \to f(x_0)$ as $x \to x_0$.
Also, $f$ is continuous at all isolated points of $X$ since there is always $\delta$ such that $x_0$ is the only point in $B_\delta(x_0)$.

Similarily, continuity can be characterized by sequences just like limits using similar proof.

> *Proposition.*{: .prop}
> $f: X \to Y$ is continuous at the point $x_0$ iff for every sequence $(x_n)$ in $X$ such that $x_n \to x_0$, $f(x_n) \to f(x_0)$ as $n \to \infty$.

From the above we can see that continuity is a topological property which we can also characterized that by open/closed sets.

> *Proposition.*{: .prop}
> $f: X \to Y$ is continuous on $X$ iff
>
> + whenver $G$ is open in $Y$, then $f^{-1}(G)$ is open in $X$; or
>
> + whenver $F$ is closed in $Y$, then $f^{-1}(F)$ is closed in $X$; or
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose that $f$ is continuous and $G$ is open in $Y$. If $f^{-1}(G)$ is empty then it is open.
> Let $x_0 \in f^{-1}(G)$ so that $f(x_0) \in G$, then there exists $\varepsilon$ such that $B_\varepsilon(f(x_0)) \subset G$.
> Since $f$ is continuous, there exists $\delta$ such that $\sigma(f(x_0), f(x)) < \varepsilon$ whenever $\rho(x_0, x) < \delta$,
> therefore $f(x) \in G$ and $x \in f^{-1}(G)$ so $B_\delta(x_0) \subset X$ and $x_0$ is an interior point. Hence, $f^{-1}(G)$ is open.
>
> ($\Leftarrow$) Suppose that $G$ is open implies $f^{-1}(G)$ is open. Given $x_0 \in X$ and $\varepsilon > 0$.
> Since $B_\varepsilon(f(x_0))$ is open in $Y$, $f^{-1}(B_\varepsilon(f(x_0)))$ is open in $X$.
> Therefore, there exists $\delta$ such that $x \in B_\delta(x_0)$ then $f(x) \in B_\varepsilon(f(x_0))$ which implies $f$ is continuous.
>
> The case for closed set can be derived from complements, i.e. if $E$ is any set, $f^{-1}(E) \cap f^{-1}(E') = \emptyset$ and $f^{-1}(E) \cup f^{-1}(E') = X$.

Note that it is not true that $S$ being open in $X$ implies $f(S)$ being open in $Y$.

In general for a bijective continuous function $f$, its inverse $f^{-1}$ needs not be continuous. We have a special notion if that is the case.

> *Definition.*{: .def}
> A continuous function $f: X \to Y$ is called a **homeomorphism** if its inverse $f^{-1}$ is also continuous.
> The metric spaces $X$ and $Y$ are said to be **homeomorphic** if there exists a homeomorphism between them.

By the above theorem we can see that if two metric spaces are homeomorphic then there is a bijection between the open (respectively closed) sets in the two spaces.

> *Definition.*{: .def}
> A bijection $f: X \to Y$ such that $\sigma(f(x_1), f(x_2)) = \rho(x_1, x_2)$ for all $x_1, x_2 \in X$ is called an **isometry**.
> The metric spaces $X$ and $Y$ are said to be **isometric** if there eixsts an isometry between them.

## Uniform Continuity

Similar to pointwise convergence and uniform convergence of functions, we can do the same to define uniform continuity.

> *Definition.*{: .def}
> **[Uniform Continuity]**
> Suppose that $f: X \to Y$ is a function of metric spaces $X$ and $Y$.
> Then $f$ is said to be **uniformly continuous** on $X$ if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta)(\forall x_1, x_2 : \rho(x_1, x_2) < \delta) \; \sigma(f(x_1), f(x_2)) < \varepsilon
  $$

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 3
