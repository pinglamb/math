---
layout: base
title: Metric Spaces &#124; Analysis II
---

# Metric Spaces
{: .page-title}

So far the theory of analysis are developed with points and functions base on Euclidean space or complex plane.
Metric spaces provide a more general setup for analysis, in which the fundamental property is that there is a distance between any two points.

> *Definition.*{: .def}
> Suppose that $X$ is a (non-empty) set and that $\rho: X \times X \to \mathbf{R}$ is a real valued function with the following properties:
>
> + $\rho(x, y) \ge 0$ for all $x, y \in X$ with equality iff $x = y$;
>
> + $\rho(x, y) = \rho(y, x)$ for all $x, y \in X$;
>
> + $\rho(x, z) \le \rho(x, y) + \rho(y, z)$ for all $x, y, z \in X$ (triangle inequality).
>
> Then the function $\rho$ is called a **metric/distance** on $X$ and $(X, \rho)$ is called a **metric space**.

+ For $\mathbf{R}$, the usual metric is given by $\rho(x, y) = \vert x - y \vert$.

+ For $\mathbf{R}^n$, the usual metric is the _norm_, i.e. $\rho(x, y) = \sqrt{(x_1 - y_1)^2 + ... + (x_n - y_n)^2}$.

+ For $\mathbf{C}$, the usual metric is the same as $\mathbf{R}^2$, i.e. $\rho(z, z') = \vert z - z' \vert = \sqrt{(x - x')^2 + (y - y')^2}$.

+ For $B[a, b]$ being the set of bounded real functions on the interval $[a, b]$, we can have $\rho(f, g) = \sup \vert f(x) - g(x) \vert$, i.e. the maximum vertical distance between the two functions.

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $Y \subset X$ and $\sigma: Y \times Y \to \mathbf{R}$ be the restriction of $\rho$ to $Y \times Y$, i.e. $\sigma(y, y') = \rho(y, y')$ for $y, y' \in Y$.
> Then $\sigma$ is a metric _induced_ by $(X, \rho)$ on $Y$ and $(Y, \sigma)$ is a **metric subspace** of $(X, \rho)$.

We can now then extend the definition of convergence of sequences of real numbers to sequences of points in a metric space.

> *Definition.*{: .def}
> The sequence $(x_n)$ of points in the metric space $(X, \rho)$ is **convergent** to the point $x \in X$ if
>
> $$
  \rho(x_n, x) \to 0 \quad\text{as}\quad n \to \infty
  $$
>
> We write $x_n \to x$ as $n \to \infty$ or $\lim_{n \to \infty} x_n = x$ as in classical analysis.
> Alternatively, we can also define it as
>
> $$
  (\forall \varepsilon > 0)(\exists N)(\forall n > N)\,\rho(x_n, x) < \varepsilon
  $$

> *Proposition.*{: .prop}
> A sequence cannot converge to two distinct limits.
>
> *Proof.*{: .prf}
>
> Suppose that the sequence $(x_n)$ converges to two different limits $L_1$ and $L_2$ so $\rho(L_1, L_2)$ is non-zero.
> By triangle inequality, we have
>
> $$
  \rho(L_1, L_2) \le \rho(L_1, x_n) + \rho(x_n, L_2)
  $$
>
> By definition, we have both $\rho(L_1, x_n) \to 0$ and $\rho(x_n, L_2) \to 0$ so $\rho(L_1, L_2) \to 0$ which implies $L_1 = L_2$.

> *Definition.*{: .def}
> Suppose that $\rho$ and $\sigma$ are both metrics on the set $X$ such that a sequence converges in $(X, \rho)$ iff it converges in $(X, \sigma)$.
> Then $\rho$ and $\sigma$ are said to be **equivalent metrics**.

A sufficient but not necessary condition for metrics to be equivalent is stated below.

> *Definition.*{: .def}
> Suppose that $\rho$ and $\sigma$ are both metrics on the set $X$.
> Then $\rho$ and $\sigma$ are **Lipschitz equivalent** if there exists positive real constants $\lambda$ and $\mu$ such that
>
> $$
  \lambda \rho(x, y) \le \sigma(x, y) \le \mu \rho(x, y)
  $$
>
> for all $x, y \in X$.

If two metrics are equivalent, the topological properties are preserved between them.

## Normed Vector Spaces

We will generalize the basic algebraic ideas about vector spaces that are related to analysis and more in-depth study of vector spaces can be found in [linear algebra](../linear-algebra/vector-spaces.md).

> *Definition.*{: .def}
> Let $V$ be a vector space over a field $\mathbf{F}$. The real valued function $\Vert \cdot \Vert: V \to \mathbf{R}$ on $V$ is called a **norm** on $V$ and $V$ is called a **normed vector space** if
>
> + $\Vert x \Vert \ge 0$ for all $x \in V$ with equality iff $x = 0$;
>
> + $\Vert x + y \Vert \le \Vert x \Vert + \Vert y \Vert$ for all $x, y \in V$;
>
> + $\Vert \lambda x \Vert = \vert \lambda \vert \Vert x \Vert$ for $\lambda \in \mathbf{F}$ and $x \in V$.

In a normed vector space, a metric $\rho$ may be defined by $\rho(x, y) = \Vert x - y \Vert$.

+ For $\mathbf{R}^n$, the usual norm is given by $\Vert x \Vert = \sqrt{x_1^2 + ... + x_n^2}$.
  We can in general define $p$ norm by

  $$
  \Vert x \Vert_p = (x_1^p + ... + x_n^p)^{1/p}
  $$

  and as $p \to \infty$, $\Vert x \Vert_{\infty} = \max\Set{\vert x_i \vert : 1 \le i \le n}$.

+ For bounded functions $B[a, b]$, $\Vert f \Vert = \sup \vert f(x) \vert$.

Even though we can define many different norms for the same space like $\mathbf{R}^n$, these norms can be _Lipschitz equivalent_ which simplifies the study of their topological structure.

For $\mathbf{R}$ and $\mathbf{C}$, we can have more specialized normed vector spaces which is called _inner product spaces_.

> *Definition.*{: .def}
> Let $V$ be a complex normed vector space. Then $V$ is called a complex **inner product space** if for every ordered pair $(x, y)$ of elements in $V$,
> there is an associated complex number, i.e. the **inner product** $x \cdot y$, satisfying
>
> + $x \cdot y = \overline{y \cdot x}$ for all $x, y \in V$;
>
> + $(\lambda x + \mu y) \cdot z = \lambda (x \cdot z) + \mu (y \cdot z)$ for all $\lambda, \mu \in \mathbf{C}$ and $x, y, z \in V$;
>
> + $x \cdot x = \Vert x \Vert^2$ for all $x \in V$.

The inner product associated with a given norm is unique.
For inner product spaces, the triangle inequality can be written as the following famous result.

> *Theorem.*{: .thm}
> **[Cauthy-Schwarz Inequality]**
> Suppose that $V$ is a inner product space then for all $x, y \in V$,
>
> $$
  \vert x \cdot y \vert \le \Vert x \Vert \Vert y \Vert
  $$
>
> with equality holds iff $x, y$ is a scalar multiple of the other.

We can go further by restricting our attention to finite-dimensional spaces.

> *Definition.*{: .def}
> A **Euclidean space** is a finite-dimensional real inner product space.
> A **unitary space** is a finite-dimensional complex inner product space.

More results regarding these specialized spaces can be found in [inner product spaces](../linear-algebra/inner-product-spaces.md).

## Open and Closed Sets

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $a \in X$ and $r \in \mathbf{R}_{> 0}$.
> The **open ball** with centre $a$ and radius $r$ is defined by
>
> $$
  B_r(a) = \Set{x \in X : \rho(a, x) < r}
  $$

> *Definition.*{: .def}
> Given $E \subseteq X$, then $a \in X$ is said to be a **limit point** of $E$ if
>
> $$
  (\forall \varepsilon > 0)(\exists e \in E)\; 0 < \rho(a, e) < \varepsilon
  $$
>
> i.e. $(B_\varepsilon(a) - \Set{a}) \cap E \not= \emptyset$ for all $\varepsilon > 0$.

> *Proposition.*{: .prop}
> $a \in X$ is a limit point of $E \subseteq X$ iff
>
> + every open ball $B_\varepsilon(a)$ contains infinitely many points of $E$;
>
> + there is a sequence of points $\Set{e_n \in E}$ such that $e_n \not= a$ and $e_n \to a$ as $n \to \infty$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $a$ is a limit point, then for every $n$, there exists a point $e_n \in E$ such that
>
> $$
  0 < \rho(a, e_n) < 1/n
  $$
>
> The sequence $\Set{x_n}$ satisfies the second condition, in which implies the first.
>
> ($\Leftarrow$)

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 2
