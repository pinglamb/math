---
layout: base
title: Normed Spaces &#124; Analysis II
---

# Normed Spaces
{: .page-title}

In order to extend the analytical study about functions of single variable to multiple variables, we need to study the structure of vector spaces.
There is no harm to do so under a more abstract setting, which leads to the _normed spaces_.
More in-depth study of vector spaces itself can be found in [linear algebra](../linear-algebra/vector-spaces.md).

> *Definition.*{: .def}
> Let $V$ be a vector space over a field $\mathbf{F}$. The real valued function $\Vert \cdot \Vert: V \to \mathbf{R}$ on $V$ is called a **norm** on $V$ and $V$ is called a **normed vector space** if
>
> + $\Vert x \Vert \ge 0$ for all $x \in V$ with equality iff $x = 0$;
>
> + $\Vert x + y \Vert \le \Vert x \Vert + \Vert y \Vert$ for all $x, y \in V$;
>
> + $\Vert \lambda x \Vert = \vert \lambda \vert \Vert x \Vert$ for $\lambda \in \mathbf{F}$ and $x \in V$.

In a normed vector space, a metric $\rho$ may be defined by $\rho(x, y) = \Vert x - y \Vert$.
Similarily, two norms on the same space can be equivalent and the topological properties of the space do not depend on which norm we choose.

> *Definition.*{: .def}
> Let $V$ be a vector space. Two norms $\Vert \cdot \Vert$ and $\Vert \cdot \Vert'$ on $V$ are **Lipschitz equivalent** if there exists positive real constants $\lambda$ and $\mu$ such that
>
> $$
  \lambda \Vert x \Vert \le \Vert x \Vert' \le \mu \Vert x \Vert
  $$
>
> for all $x \in V$.

> *Definition.*{: .def}
> Let $(V, \Vert \cdot \Vert)$ be a normed space. A subset $E \subseteq V$ is **bounded** if there is some $r > 0$ such that
>
> $$
  E \subseteq B_r(0)
  $$

> *Definition.*{: .def}
> Let $(V, \Vert \cdot \Vert)$ be a normed space. A sequence $(x_n)$ in $V$ is **convergent** to $x \in V$, denoted by $x_n \to x$, if $\Vert x_n - x \Vert \to 0$, i.e.
>
> $$
  (\forall \varepsilon > 0)(\exists N)(\forall n > N)\; \Vert x_n - x \Vert < \varepsilon
  $$

> *Proposition.*{: .prop}
> Let $(V, \Vert \cdot \Vert)$ be a normed space. Then
>
> + $x_n \to x$ and $x_n \to y$ implies $x = y$;
>
> + $x_n \to x$ implies $\lambda x_n \to \lambda x$;
>
> + $x_n \to x$ and $y_n \to y$ implies $x_n + y_n \to x + y$.
>
> *Proof.*{: .prf}
>
> + $\Vert x - y \Vert \le \Vert x - x_n \Vert + \Vert x_n - y \Vert \to 0$ so $\Vert x - y \Vert = 0$ and $x = y$.
>
> + $\Vert \lambda x_n - \lambda x \Vert = \vert \lambda \vert \Vert x_n - x \Vert \to 0$.
>
> + $\Vert (x_n + y_n) - (x + y) \Vert \le \Vert x_n - x \Vert + \Vert y_n - y \Vert \to 0$.

Equivalent norms on the same space preserve boundedness and convergence.

> *Proposition.*{: .prop}
> If $\Vert \cdot \Vert$ and $\Vert \cdot \Vert'$ are Lipschitz equivalent norms on a vector space $V$, then
>
> + A subset $E \subseteq V$ is bounded with respect to $\Vert \cdot \Vert$ iff it is bounded with respect to $\Vert \cdot \Vert'$;
>
> + A sequence $(x_n)$ converges to $x$ with respect to $\Vert \cdot \Vert$ iff it converges to $x$ with respect to $\Vert \cdot \Vert'$.
>
> *Proof.*{: .prf}
>
> Both are direct from the definition of equivalence.

## $\mathbf{R}^n$

For $\mathbf{R}^n$, the _Euclidean_/_usual_ norm is defined by

$$
\Vert x \Vert_2 = \sqrt{x_1^2 + ... + x_n^2}
$$

The triangle inequality can be proved by using Cauchy-Schwarz inequality, i.e.

$$
\begin{align*}
\Vert x + y \Vert^2 &= \sum_{i=1}^n (x_i + y_i)^2 \\
&= \Vert x \Vert^2 + \Vert y \Vert^2 + 2 \sum_{i=1}^n x_i y_i \\
&\le \Vert x \Vert^2 + \Vert y \Vert^2 + 2 \Vert x \Vert \Vert y \Vert \\
&= \left( \Vert x \Vert + \Vert y \Vert \right)^2
\end{align*}
$$

We can also have the following norm

$$
\Vert x \Vert_1 = \sum_{i=1}^n \vert x_i \vert
$$

+ For , the usual norm is given by .
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

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 2.2
