---
layout: base
title: Continuous Functions &#124; Analysis II
---

# Continuous Functions
{: .page-title}

The notion of continuity is based on that of limit so we define that for functions of arbitrary metric spaces first.

> *Definition.*{: .def}
> **[Limit of Function]**
> Let $(X, \rho)$ and $(Y, \sigma)$ be metric spaces and $f: E \to Y$ with $E \subseteq X$ be a function and $x_0$ be a limit point of $E$ and $y_0 \in Y$.
> Then $f(x) \to y_0$ as $x \to x_0$ or $\lim_{x \to x_0} f(x) = y_0$ if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta > 0)(\forall x \in E) \; 0 < \rho(x, x_0) < \delta \implies \sigma(f(x), y_0) < \varepsilon
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
> On the other hand, for a sequence such that $x_n \to x_0$ as $n \to \infty$, there exists $N > 0$ such that for all $n > N$,
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
  (\forall \varepsilon > 0)(\exists \delta > 0)(\forall x \in X) \; \rho(x, x_0) < \delta \implies \sigma(f(x), f(x_0)) < \varepsilon
  $$
>
> or equivalently $f(B_\delta(x_0)) \subset B_\varepsilon(f(x_0))$.

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
  (\forall \varepsilon > 0)(\exists \delta)(\forall x_1, x_2) \; \rho(x_1, x_2) < \delta \implies \sigma(f(x_1), f(x_2)) < \varepsilon
  $$

Apart from proving uniform continuity by the $\delta-\varepsilon$ condition, there are few other sufficient conditions we can check.

> *Proposition.*{: .prop}
> Any continuous function on a closed and bounded interval (i.e. compact) is uniformly continuous.
>
> *Proof.*{:. prf}
>
> Suppose $f: X \to Y$ is a continuous function with $X$ being compact. Suppose $f$ is not uniformly continuous,
> then there is some $\varepsilon > 0$ such that for all $\delta = 1/n$, there is some $x_n, y_n$ such that
> $\vert x_n - y_n \vert < 1/n$ but $\vert f(x_n) - f(y_n) \vert > \varepsilon$.
>
> Since $X$ is compact, by Bolzano-Weierstrass, there are subsequences $(x_{n_i}) \to x$ and $(y_{n_i}) \to x$.
> By continuity, we have $f(x_{n_i}) \to f(x)$ and $f(y_{n_i}) \to f(x)$ but $\vert f(x_{n_i}) - f(y_{n_i}) \vert > \varepsilon$ for all $n_i$ which is a contradiction.

> *Proposition.*{: .prop}
> Suppose that $(f_n: X \to Y)$ is a sequence of uniformly continuous functions.
> If $f_n \to f: X \to Y$ uniformly, then $f$ is uniformly continuous.
>
> *Proof.*{:. prf}
>
> Given $\varepsilon > 0$, $\exists \delta$ such that $\forall x, y$ with $\vert x - y \vert < \delta$, $\vert f_n(x) - f_n(y) \vert < \varepsilon$.
> Also, $\exists N$ such that $\forall n \ge N$ and $\forall x$, $\vert f_n(x) - f(x) \vert < \varepsilon$.
> Therefore,
>
> $$
  \vert f(x) - f(y) \vert \le \vert f(x) - f_N(x) \vert + \vert f_N(x) - f_N(y) \vert + \vert f_N(y) - f(y) \vert < 3 \varepsilon
  $$

The following works for real-valued functions on $\mathbb{R}$.

> *Proposition.*{: .prop}
> **[Domain Splitting]** Suppose that $f: [a, \infty) \to \mathbb{R}$ is continuous and $f(x)$ tends to a finite limit as $x \to \infty$.
> Then $f$ is uniformly continuous on $[a, \infty)$.
>
> *Proof.*{:. prf}
>
> Since $f(x) \to L$ as $x \to \infty$, $\exists X$ such that $\forall x > X$, $\vert f(x) - L \vert < \varepsilon$.
> Therefore, $\exists \delta$ such that $\vert x - y \vert < \delta$ and $x, y > X$,
>
> $$
  \vert f(x) - f(y) \vert \le \vert f(x) - L \vert + \vert L - f(y) \vert < 2\varepsilon
  $$
>
> and $f$ is uniformly continuous on $(X, \infty)$. Since $[a, X+1]$ is compact, we also have $f$ being uniformly continuous on $[a, X+1]$.
> Hence, $f$ is uniformly continuous on $[a, \infty)$.

> *Proposition.*{: .prop}
> Suppose that $f$ be differentiable and $f'$ is bounded. Then $f$ is uniformly continuous.
>
> *proof.*{:. prf}
>
> By Mean Value Theorem, $\forall x, y$, there exists $c \in [x, y]$ such that $f(x) - f(y) = f'(c) (x - y) \le M (x - y)$.
> Therefore, $\forall x, y$ such that $\vert x - y \vert < \varepsilon / \vert M \vert$, we have
>
> $$
  \vert f(x) - f(y) \vert \le \vert M \vert \vert x - y \vert < M \left( {\varepsilon \over M} \right) = \varepsilon
  $$

## Lipschitz Functions

> *Definition.*{: .def}
> **[Lipschitz Function]**
> Suppose that $f: X \to Y$ is a function of metric spaces $X$ and $Y$.
> Then $f$ is said to be **Lipschitz** on $X$ if
>
> $$
  (\exists K \in [0, \infty))(\forall x_1, x_2 \in X) \; \sigma(f(x_1), f(x_2)) \le K \rho(x_1, x_2)
  $$
>
> Any such $K$ is called a **Lipschitz constant**.

> *Proposition.*{: .prop}
> All Lipschitz functions are uniformly continuous.
>
> *proof.*{:. prf}
>
> By choosing $\delta < \varepsilon / K$, for all $x, y$ such that $\rho(x, y) < \varepsilon / K$,
>
> $$
  \sigma(f(x), f(y)) \le K \rho(x, y) < \varepsilon
  $$

The converse is not true similar to continuity doesn't imply uniform continuity.

For two metrics to be Lipschitz equivalent is the same of saying the two identity maps $i : (X, \rho\_1) \to (X, \rho\_2)$ and $i' : (X, \rho\_2) \to (X, \rho\_1)$ are Lipschitz, hence the name.

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 3
* [Dexter Chua _Part IB - Analysis II_, 2015 - Chapter 3.1](https://dec41.user.srcf.net/notes/IB_M/analysis_ii.pdf)
