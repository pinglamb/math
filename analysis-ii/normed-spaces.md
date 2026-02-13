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

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 2.2
