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
