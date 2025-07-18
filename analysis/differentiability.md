---
layout: base
title: Differentiability &#124; Analysis
---

# Differentiability
{: .page-title}

There are some discussions already in [Differential Equations](../differential-equations/differentiability.md) about the definitions of _derivatives_,
we will recapture some of the ideas here and prove some of the fundamental rules again.

> *Definition.*{: .def}
> Suppose that $f$ is a real-valued function on interval $I$ and $a$ is an interior point of $I$,
> so that there exists $\eta > 0$ such that $(a - \eta, a + \eta) \subseteq I$.
> Then $f$ is **differentiable** at $a$, with **derivative** $f'(a)$, if
>
> $$
  (\forall \varepsilon > 0)(\exists \delta : 0 < \delta \le \eta)(\forall x: 0 < |x - a| < \delta) \, \left| {f(x) - f(a) \over x - a} - f'(a) \right| < \varepsilon
  $$
>
> In other words, $(f(x) - f(a)) / (x - a) \to f'(a)$ as $x \to a$.

> *Proposition.*{: .prop}
> If $f$ is differentiable at $a$, then $f$ is continuous at $a$.
>
> *Proof.*{: .prf}
>
> From the definition, as $x \to a$, the fraction can tend to a finite limit only if $f(x) \to f(a)$, so $f$ is continuous at $a$.

The converse is not true. For example, $f(x) = \vert x \vert$ is continuous at $0$ but not differentiable.

Alternatively, we can use the following characterization to avoid division in the definition.

> *Definition.*{: .def}
> Suppose that $f$ is a real-valued function on interval $I$ and $a$ is an interior point of $I$,
> that $(a - \eta, a + \eta) \subseteq I$.
> Then $f$ is **differentiable** at $a$, with **derivative** $f'(a)$,
> if there is a real-valued function $\varepsilon$ on $(-\eta, \eta) \setminus \Set{0}$ such that for $0 < \vert h \vert < \eta$
>
> $$
  f(a + h) = f(a) + f'(a)h + \varepsilon(h)
  $$
>
> for which $\varepsilon(h)/h \to 0$ as $h \to 0$.
{: #differentiability-linear-approximation}

We will use [small-o notation](../differential-equations/differentiability.md#little-o-notation) to represent function that satisfies $\varepsilon(h)/h \to 0$ as $h \to 0$, i.e.

$$
f(a + h) = f(a) + f'(a)h + o(h)
$$

> *Proposition.*{: .prop}
> The two definitions are equivalent.
>
> If $f$ is differentiable at $x = a$, then
>
> $$
  f(a + h) = f(a) + f'(a)h + o(h)
  $$
>
> Conversely, if there exist constants $A$ and $B$ such that
>
> $$
  f(a + h) = A + Bh + o(h)
  $$
>
> then $f$ is differentiable at $a$, with $A = f(a)$ and $B = f'(a)$.
>
> *Proof.*{: .prf}
>
> Rearranging the terms we have
>
> $$
  {\varepsilon(h) \over h} = {f(a + h) - f(a) \over h} - f'(a)
  $$

It can be interpreted as differentiability is equivalent to having the derivative being the _only_ good linear approximation.

## Elementary Rules

The usual rules of differentiation can be proved using small-o notation.

> *Proposition.*{: .prop}
> **[Sum Rule]**
> $(f + g)'(x) = f'(x) + g'(x)$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  (f + g)(x + h) &= f(x + h) + g(x + h) \\
  &= f(x) + f'(x)h + o(h) + g(x) + g'(x)h + o(h) \\
  &= f(x) + g(x) + [f'(x) + g'(x)]h + o(h) \\
  &= (f + g)(x) + [f'(x) + g'(x)]h + o(h)
  \end{align*}
  $$

> *Proposition.*{: .prop}
> **[Product Rule]**
> $(fg)'(x) = f'(x)g(x) + f(x)g'(x)$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  (fg)(x + h) &= f(x + h)g(x + h) \\
  &= (f(x) + f'(x)h + o(h))(g(x) + g'(x)h + o(h)) \\
  &= f(x)g(x) + [f'(x)g(x) + f(x)g'(x)]h \\
  & \qquad + \, o(h)[f(x) + g(x) + f'(x)h + g'(x)h + o(h)] + f'(x)g'(x)h^2 \\
  &= (fg)(x) + [f'(x)g(x) + f(x)g'(x)]h + o(h)
  \end{align*}
  $$

> *Proposition.*{: .prop}
> **[Chain Rule]**
> $(g \circ f)'(x) = g'(f(x))f'(x)$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  (g \circ f)(x + h) &= g(f(x + h)) \\
  &= g(f(x) + f'(x)h + h\varepsilon_1(h)) \\
  &= g(f(x)) + g'(f(x))[f'(x)h + h\varepsilon_1(h)] \\
  &\qquad + \, [f'(x)h + h\varepsilon_1(h)] \varepsilon_2(f'(x)h + h\varepsilon_1(h)) \\
  &= (g \circ f)(x) + g'(f(x))f'(x)h \\
  &\qquad + \, h[\varepsilon_1(h)g'(f(x)) + (f'(x) + \varepsilon_1(h))\varepsilon_2(f'(x)h + h\varepsilon_1(h))]
  \end{align*}
  $$
>
> Since $\varepsilon_1(h)g'(f(x)) \to 0$, $f'(x) + \varepsilon_1(h)$ is bounded and $\varepsilon_2(f'(x)h + h\varepsilon_1(h)) \to 0$, so the error term is $o(h)$.

> *Proposition.*{: .prop}
> Let $f(x) = 1/x$, then $f'(x) = -1/x^2$.
> Therefore $(1/g)'(x) = - g'(x) / [g(x)]^2$.
>
> *Proof.*{: .prf}
>
> $$
  {f(x + h) - f(x) \over h} = {x - x - h \over x(x + h)h} = -{1 \over x^2}
  $$
>
> Therefore, we have $(1/g)(x) = f(g(x))$. By chain rule,
>
> $$
  \left( {1 \over g} \right)'(x) = \left( - {1 \over [g(x)]^2} \right) g'(x) = - {g'(x) \over [g(x)]^2}
  $$

> *Proposition.*{: .prop}
> **[Quotient Rule]**
> $(f/g)'(x) = f(x)g'(x))f'(x)$.
>
> *Proof.*{: .prf}
>
> By product rule,
>
> $$
  \left({ f \over g} \right)'(x) = {f'(x) \over g(x)} - {f(x)g'(x) \over [g(x)]^2} = {f'(x)g(x) - f(x)g'(x) \over [g(x)^2]}
  $$

> *Proposition.*{: .prop}
> **[Inverse Rule]**
> Let $y = f(x)$ be continuous and strictly increasing for an interval $[a, b]$.
> If for a given $x \in (a, b)$ such that $f'(x) \not= 0$, then the inverse function $x = g(y)$ is differentiable for the corresponding value of $y$ and
>
> $$
  g'(y) = {1 \over f'(x)}
  $$
>
> *Proof.*{: .prf}
>
> Given $h$, define $k$ by
>
> $$
  y + k = f(x + h) \implies k = f(x + h) - f(x)
  $$
>
> Then if $k$ is given,
>
> $$
  x + h = g(y + k) \implies h = g(y + k) - g(y)
  $$
>
> Therefore,
>
> $$
  {g(y + k) - g(y) \over k} = {h \over f(x + h) - f(x)}
  $$
>
> Since $g$ is continuous, $h \to 0$ as $k \to 0$.

## Higher Derivatives

The second derivative is just the derivative of the first, and repeatedly we can define the $n$th derivative.
The $n$th derivative implies continuity of $(n-1)$th derivative.

> *Theorem.*{: .thm}
> **[Leibniz's Rule]**
> If $f$ and $g$ are functions having $n$th derivatives, then
>
> $$
  (fg)^{(n)} = \sum_{r=0}^n {n \choose r} f^{(n-r)}g^{(r)}
  $$
>
> *Proof.*{: .prf}
>
> By induction.

## Maxima and Minima

> *Definition.*{: .def}
> The function $f$ is said to be **strictly increasing** at $c$ if there is a neighbourhood of $a$
> in which $f(x) < f(a)$ for $x < a$ and $f(x) > f(a)$ for $x > a$.

> *Proposition.*{: .prop}
> If $f'(a) > 0$, then $f$ is strictly increasing at $a$.
>
> *Proof.*{: .prf}
>
> Since $(f(x) - f(a)) / (x - a)$ tends to a limit greater than $0$ as $x \to a$, the numerator and denominator have the same sign.

> *Proposition.*{: .prop}
> If $f$ is strictly increasing at $a$ and $f'(a)$ exists, then $f'(a) \ge 0$.
>
> *Proof.*{: .prf}
>
> By definition, for $x$ in the neighbourhood and $x > a$, we have
>
> $$
  {f(x) - f(a) \over x - a} > 0
  $$
>
> so the limit from the right is greater than or equal to $0$. Similar argument for the limit from the left.

$f(x) = x^3$ is an example that $f$ being strictly increasing at $x = 0$ doesn't imply $f'(0) > 0$.

> *Definition.*{: .def}
> $f$ is said to have a **maximum** at $a$ if there is a neighbourhood of $a$ in which $f(x) < f(a)$ except for $x = a$.
> A **turning value** is either a maximum or minimum.

> *Proposition.*{: .prop}
> If $f$ has a turning value at $a$ and $f'(a)$ exists, then $f'(a) = 0$.
>
> *Proof.*{: .prf}
>
> If $f'(a) > 0$ or $f'(a) < 0$, then $f$ is strictly increasing or decreasing at $x = a$ respectively.
> Either of these contradicts $a$ being a turning value.

It is possible for a function to have turning value at $a$ at which there is not derivative, e.g. $\vert x \vert$ at $x = 0$.

> *Proposition.*{: .prop}
> If there is a neighbourhood of $a$ such that $f'(a) > 0$ for $x < a$ and $f'(a) < 0$ for $x > a$,
> then $f$ has a maximum at $a$.

> *Proposition.*{: .prop}
> Let $f'(a) = 0$. If $f'\'(a) < 0$, then $f$ has maximum at $a$. If $f'\'(a) > 0$, then $f$ has minimum at $a$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 4
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 7.1, 7.3
