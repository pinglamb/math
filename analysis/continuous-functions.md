---
layout: base
title: Continuous Functions &#124; Analysis
---

# Continous Functions
{: .page-title}

## Convergence

> *Definition.*{: .def}
> **[Limit of a Function]**
> A function $f$ tends to a limit $l$ as $x \to c$ if
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

The convergence of function can be characterized in terms of convergent sequences.

> *Proposition.*{: .prop}
> $f(x) \to l$ as $x \to c$ iff for all sequences $(a_n)$ in which $a_n \to c$ then $f(a_n) \to l$ as $n \to \infty$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose $f(x) \to l$ as $x \to c$ and $(a_n)$ is a sequence in which $a_n \to c$.
> Then for all $\varepsilon > 0$, there exists a $\delta > 0$ such that $\vert f(x) - l \vert < \varepsilon$ when $0 < \vert x - c \vert < \delta$.
> As $a_n \to c$, there exists an $N$ such that for all $n > N$, $\vert a_n - c \vert < \delta$ and therefore $\vert f(a_n) - l \vert < \varepsilon$.
>
> ($\Leftarrow$) Suppose $(a_n)$ is a sequence in which $a_n \to c$ and $f(a_n) \to l$ as $n \to \infty$.
> Then for all $\delta, \varepsilon > 0$, there exists a $n > N$ such that both $\vert a_n - c \vert < \delta$ and $\vert f(a_n) - l \vert < \varepsilon$.
> Therefore, for all $x$ such that $\vert x - c \vert \le \vert a_n - c \vert < \delta$, $\vert f(x) - l \vert < \varepsilon$ and $f(x) \to l$.

We can conclude the general principle of convergence for functions similar to that for [sequences](general-principle-of-convergence.md#general-principle-of-convergence-thm).

> *Theorem.*{: .thm}
> The following statements are equivalent.
>
> + There exists a $l$ such that $f(x) \to l$ as $x \to c$.
>
> + Whenever $(a_n)$ is a sequence which tends to $c$ then $(f(a_n))$ is a Cauchy sequence.
>
> + Given $\varepsilon > 0$, there exists $\delta > 0$ such that if $\vert x - c \vert < \delta$ and $\vert y - c \vert < \delta$ then $\vert f(x) - f(y) \vert < \varepsilon$.

Different from sequences, we can have one-sided convergence.

> *Definition.*{: .def}
> A function $f$ tends to a limit $l$ as $x$ tends to $c$ from the right if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta > 0)(\forall x : c < x < c + \delta)\;|f(x) - l| < \varepsilon
  $$
>
> and denoted by
>
> $$
  \lim_{x \to c+} f(x) = l
  $$
>
> Similarily we can define that $x$ tends to $c$ from the left, i.e.
>
> $$
  \lim_{x \to c-} f(x) = l
  $$
>
> The limit of function exists iff $\lim_{x \to c+} f(x) = \lim_{x \to c-} f(x) = l$.

## Continuity

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

> *Proposition.*{: .prop}
> Similar to convergence of sequences,
>
> + sum of two continuous functions is continuous;
>
> + product of two continuous functions is continuous;
>
> + quotient of two continuous functions is continuous wherever the denominator is not zero.

Base on that we can conclude any polynomials and quotient of two polynomials (except for points where denominator is zero) are continuous.

> *Proposition.*{: .prop}
> Suppose that $g(x)$ is continuous for $x = \xi$ and $g(\xi) = \eta$ and $f(y)$ is continuous at $y = \eta$.
> Then $f(g(x))$ is continuous at $x = \xi$.
>
> *Proof.*{: .prf}
>
> For all $\varepsilon > 0$, there exists $\delta > 0$ such that when $\vert y - \eta \vert < \delta$, $\vert f(y) - f(\eta) \vert < \varepsilon$.
> Also, there exists $\tau > 0$ such that when $\vert x - \xi \vert < \tau$, $\vert g(x) - g(\xi) \vert < \delta$.
> Combining the two we can conclude $f(g(x))$ is continuous at $x = \xi$.

## Intermediate Value Theorem

> *Theorem.*{: .thm}
> **[Intermediate Value Theorem]**
> Suppose that $f$ is continuous in the closed interval $(a, b)$ and $\eta$ is a number such that $f(a) < \eta < f(b)$.
> Then there exists $a < \xi < b$ such that $f(\xi) = \eta$.
>
> *Proof.*{: .prf}
>
> Let $S = \Set{a \le x \le b : f(x) < \eta}$. $a \in S$ so $S$ is non-empty, and bounded above by $b$. Thus, the set $S$ has a supremum $\xi$.
>
> Since $f$ is continuous at $a$, there is an interval $a \le x \le a + \delta$ such that $f(x) < \eta$ so $\xi \ge a + \delta > a$.
> Similarily there is an interval $b - \delta \le x \le b$ such that $f(x) > \eta$ so $\xi \le b - \delta < b$.
> Therefore, $a < \xi < b$ and $f$ is continuous at $\xi$.
>
> If $f(\xi) > \eta$, say $f(\xi) = \eta + \varepsilon$.
> By continuity, there exists $\delta$ such that for $\xi - \delta < x < \xi$, $\vert f(\xi) - f(x) \vert < \varepsilon$.
> As $\xi$ is the supremum of $S$, there exists $x' \in S$ such that $\xi - \delta < x' < \xi$.
> Thus, $f(\xi) - f(x') < \varepsilon$ which implies $f(x') > \eta$ which is a contradiction.
> If $f(\xi) < \eta$, say $f(\xi) = \eta - \varepsilon$.
> By continuity, there exists $\delta$ such that for $\xi < x < \xi + \delta$, $f(x) - f(\xi) < \varepsilon$ and such $x$ is in $S$ which contradicts with $\xi$ being supremum.
> Hence, by trichotomy, $f\xi) = \eta$.
>
> Alternatively, we can use the technique repeated bisection to prove that.
> Let $a_0 = a$ and $b_0 = b$ and $m_0 = (a_0 + b_0) / 2$.
> If $f(m_0) < \eta$, we set $a_1 = m_0$ and $b_1 = b_0$, otherwise we set $a_1 = a_0$ and $b_1 = m_0$.
> Repeat this process recursively and the sequences $(a_n)$ is increasing and $(b_n)$ is decreasing.
> As $f(a_n) \le \eta \le f(b_n)$ and both $(a_n)$ and $(b_n)$ converges to a common limit $\xi$, we have $f(\xi) = \eta$.

## Maximum Value Theorem

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 3
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 6.1, 6.3, 6.4
