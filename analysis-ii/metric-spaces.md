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

* Any set can be equipped with the _discrete metric_:

  $$
  \rho(x, y) = \begin{cases}
  0 & \text{if}\; x = y \\
  1 & \text{if}\; x \not= y \\
  \end{cases}
  $$

+ For $\mathbf{R}$, the usual metric is given by $\rho(x, y) = \vert x - y \vert$.

+ For $\mathbf{R}^n$, the usual metric is the _norm_, i.e. $\rho(x, y) = \sqrt{(x_1 - y_1)^2 + ... + (x_n - y_n)^2}$.

+ For $\mathbf{C}$, the usual metric is the same as $\mathbf{R}^2$, i.e. $\rho(z, z') = \vert z - z' \vert = \sqrt{(x - x')^2 + (y - y')^2}$.

+ For $B[a, b]$ being the set of bounded real functions on the interval $[a, b]$, we can have $\rho(f, g) = \sup \vert f(x) - g(x) \vert$, i.e. the maximum vertical distance between the two functions.

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $Y \subset X$ and $\sigma: Y \times Y \to \mathbf{R}$ be the restriction of $\rho$ to $Y \times Y$, i.e. $\sigma(y, y') = \rho(y, y')$ for $y, y' \in Y$.
> Then $\sigma$ is a metric _induced_ by $(X, \rho)$ on $Y$ and $(Y, \sigma)$ is a **metric subspace** of $(X, \rho)$.

## Open Ball

The following definition is handy when we study topological properties.

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $a \in X$ and $r \in \mathbf{R}_{> 0}$.
> The **open ball** with centre $a$ and radius $r$ is defined by
>
> $$
  B_r(a) = \Set{x \in X : \rho(a, x) < r}
  $$

The open ball might not be exactly a ball, for example the open "ball" of metric space $(B[a, b], \rho)$ above is a strip.

## Convergence

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
  (\forall \varepsilon > 0)(\exists N)(\forall n > N)\;\rho(x_n, x) < \varepsilon
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
> Suppose that $\rho$ and $\sigma$ are both metrics on the set $X$ such that a sequence converges in $(X, \rho)$ iff it converges in $(X, \sigma)$ (to the same limit).
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

It can be confusing sometimes for real number sets as metric function is also real-valued.
One way to think about it is that the elements of a real number set are "labels" which is equivalent to any objects like apple or orange, and the metric function describes the distance between them.
When we talk about limits, we mean which element of the set the sequence converges to, so we can have full control by tweaking the metric function.
For example, for the set $[0, 1]$, under usual metric $\vert x - y \vert$, $1/n \to 0$ as $n \to \infty$. If we define

$$
\sigma(x) = \begin{cases}
0 & x = 1 \\
1 & x = 0 \\
x & 0 < x < 1
\end{cases}
$$

and $\rho(x, y) = \vert \sigma(x) - \sigma(y) \vert$, we have the distance $\rho(1/n, 1) = 1/n \to 0$ and hence the element $1/n \to 1$ as $n \to \infty$ .

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 2.1
