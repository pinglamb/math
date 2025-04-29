---
layout: base
title: Continuous Functions &#124; Analysis
---

# Continous Functions
{: .page-title}

> *Definition.*{: .def}
> **[Limit of a Function]**
> A function $f(x)$ tends to a limit $l$ as $x \to c$ if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta > 0)(\forall x : 0 < |x - c| < \delta)\;|f(x) - l| < \varepsilon
  $$
>
> We then also write
>
> $$
  \lim_{x \to c} f(x) = l
  $$

The value of $\delta$ depends on $\varepsilon$ and can be emphasized by writing $\delta(\varepsilon)$.
Also, the value of $f(c)$ is not necessarily defined for the limit to exist.

> *Definition.*{: .def}
> A function $f$ is **continuous** at $c$ if $f(x) \to f(c)$ as $x \to c$.

Equivalently, we can say $f$ is continuous if

$$
(\forall \varepsilon > 0)(\exists \delta > 0)(\forall x : |x - c| < \delta)\;|f(x) - f(c)| < \varepsilon
$$

We can generalize the part $\vert x - c \vert < \delta$ as $c - \delta_1 < x < c + \delta_2$, where $\delta_1$ and $\delta_2$ can be different,
and have any alternative definition of continuity.

> *Definition.*{: .def}
> An open interval is called a **neighbourhood** of any one of its points.

> *Definition.*{: .def}
> A function $f$ is continuous at $c$ if given any neighbourhood $N_1$ of $f(c)$,
> there is a neighbourhood $N_2$ of $c$ such that if $x \in N_2$ then $f(x) \in N_1$.

We can then extend the definition of continuity in an interval.

> *Definition.*{: .def}
> A function $f$ is continuous in the closed interval $[a, b]$ if
>
> + for each $c$ in $a < c < b$, $f$ is continuous at $c$;
>
> + $\lim_{x \to a+} f(x) = f(a)$ and $\lim_{x \to b-} f(x) = f(b)$.
>
> A function $f$ is continuous in the open interval if it is continuous at each point of the interval.

> *Property.*{: .prop}
> If $\lim_{n \to \infty} a_n = L$ and function $f$ is continuous at $L$, then
>
> $$
  \lim_{n \to \infty} f(a_n) = f(L)
  $$
>
> *Proof.*{: .prf}
>
> As $f$ is continuous at $L$, i.e.
>
> $$
  \lim_{x \to L} f(x) = f(L)
  $$
>
> Given an $\varepsilon$, there exists $\delta$ such that
>
> $$
  0 < |x - L| < \delta \implies |f(x) - f(L)| < \varepsilon
  $$
>
> Since $\lim_{n \to \infty} a_n = L$, there exists $N$ such that
>
> $$
  n > N \implies |a_n - L| < \delta
  $$
>
> Combining the above, given any $\varepsilon > 0$, we can find $N$ such that whenever $n > N$,
>
> $$
  |a_n - L| < \delta \implies |f(a_n) - f(L)| < \varepsilon
  $$
>
> Hence, $\lim_{n \to \infty} f(a_n) = f(L)$.
