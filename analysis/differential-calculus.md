---
layout: base
title: Differential Calculus &#124; Analysis
---

# Differential Calculus
{: .page-title}

There are some discussions already in [Differentiability](../differential-equations/differentiability.md) about the definitions of _derivatives_,
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

## Differentiation Theorems

> *Theorem.*{: .thm}
> **[Rolle's Theorem]**
> Suppose $f$ is continuous in the closed interval $[a, b]$ and $f'$ exists in open interval $(a, b)$.
> If $f(a) = f(b)$, then there is a value $c$, with $a < c < b$, for which $f'(c) = 0$.
>
> *Proof.*{: .prf}
>
> Let $M = \sup f(x)$ and $m = \inf f(x)$ for $a \le x \le b$.
> Let $f(a) = k$
>
> If $M = m = k$, then $f$ is a constant function and $f'(c) = 0$ for all $c \in (a, b)$.
>
> Suppose $M > k$. By extreme value theorem, there exists $c$ such that $f(c) = M$.
> If $f'(c) > 0$, then $f$ is strictly increasing at $c$ and there are some values on the right such that $f(x) > f(c)$, which contradicts with $f(c)$ being the supremum.
> If $f'(c) < 0$, similarily there are some values on the left such thath $f(x) > f(c)$.
> Therefore, $f'(c) = 0$.

> *Theorem.*{: .thm}
> **[Mean Value Theorem]**
> Suppose $f$ is continuous in the closed interval $[a, b]$ and $f'$ exists in open interval $(a, b)$.
> Then there is a value $c$ with $a < c < b$, for which
>
> $$
  f(b) - f(a) = (b - a) f'(c)
  $$
>
> *Proof.*{: .prf}
>
> Let $\phi(x) = f(x) - kx$. In order to have $\phi(a) = \phi(b)$,
>
> $$
  k = {f(b) - f(a) \over b - a}
  $$
>
> By Rolle's Theorem, there exists $c$ such that
>
> $$
  \phi'(c) = f'(c) - k = 0 \quad \implies \quad f'(c) = k = {f(b) - f(a) \over b - a}
  $$

Let $0 < \theta < 1$ and $b = a + h$, we can write the result as

$$
f(a + h) = f(a) + hf'(a + \theta h)
$$

> *Corollary.*{: .cor}
> If $f'(x) = 0$ for all $x \in (a, b)$, then $f(x)$ is constant for $[a, b]$.
>
> *Proof.*{: .prf}
>
> For any two points $x_1$ and $x_2$ with $a \le x_1 < x_2 \le b$, there exists $x_1 < x_3 < x_2$ such that
>
> $$
  f(x_2) - f(x_1) = (x_2 - x_1)f'(x_3) = 0
  $$
>
> Hence, $f(x_1) = f(x_2)$.

> *Corollary.*{: .cor}
> If $f'(x) > 0$ for $x \in (a, b)$, then $f(x)$ is strictly increasing in $[a, b]$.
>
> *Proof.*{: .prf}
>
> For any two points $x_1$ and $x_2$ with $a \le x_1 < x_2 \le b$, there exists $x_1 < x_3 < x_2$ such that
>
> $$
  f(x_2) - f(x_1) = (x_2 - x_1)f'(x_3) > 0
  $$
>
> Hence, $f(x_2) > f(x_1)$ and $f$ is strictly increasing in $[a, b]$.
>
> The corollary still holds if $f$ is continuous at $c$ but $f'(c)$ doesn't exist.
> By applying the theorem to two intervals $(a, c)$ and $c, b$, with $x_1 \in (a, c)$ and $x_2 \in (c, b)$,
> we still have $f(x_1) < f(c) < f(x_2)$.

> *Theorem.*{: .thm}
> **[Cauchy's Mean Value Theorem]**
> Suppose both $f$ and $g$ are continuous in $[a, b]$ and differentiable in $(a, b)$.
> Suppose $g'(x)$ doesn't vanish for all $x \in (a, b)$.
> Then there exists $c$ with $a < c < b$ such that
>
> $$
  {f(b) - f(a) \over g(b) - g(a)} = {f'(c) \over g'(c)}
  $$
>
> *Proof.*{: .prf}
>
> Similarily to the proof of Mean Value Theorem, let
>
> $$
  \phi(x) = f(x) - kg(x)
  $$
>
> Choose $k$ such that $\phi(a) = \phi(b)$ and therefore
>
> $$
  k = {f(b) - f(a) \over g(b) - g(a)}
  $$
>
> By Rolle's Theorem, there exists $c$ such that
>
> $$
  \phi'(c) = f'(c) - kg'(c) = 0 \quad \implies \quad {f(b) - f(a) \over g(b) - g(a)} = {f'(c) \over g'(c)}
  $$

> *Corollary.*{: .cor}
> **[L'Hôpital's Rule]**
> Suppose that $f$ and $g$ are continuous in $[a, b]$ and differentiable in $(a, b)$, and $f(a) = g(a) = 0$ and $g'(x) \not= 0$ for all $x \in (a, b)$.
> If $f'(x) / g'(x) \to l$ as $x \to a^{+}$, then $f(x) / g(x) \to l$ as $x \to a^{+}$.
>
> *Proof.*{: .prf}
>
> For any $\varepsilon > 0$, there exists $0 < \delta < b - a$ such that $\vert f'(x) / g'(x) - l \vert < \varepsilon$ for $a < x < a + \delta$.
> Also, by Cauchy's M.V.T., there exists $c \in (a, x)$ such that
>
> $$
  {f(x) - f(a) \over g(x) - g(a)} = {f(x) \over g(x)} = {f'(c) \over g'(c)}
  $$
>
> Hence,
>
> $$
  \left| {f(x) \over g(x)} - l \right| = \left| {f'(x) \over g'(x)} - l \right| < \varepsilon
  $$

## Taylor's Theorem

If $f$ is differentiable at $a$, then $f_a(x) = f(a) + (x - a)f'(a)$ is a good linear approximation to $f$.
We can generalize it to see if the function that has higher derivatives can be better approximated by means of a polynomial.

Let

$$
p_n(x) = f(a) + (x - a)f'(a) + {(x - a)^2 \over 2!} f''(a) + \cdots + {(x - a)^n \over n!} f^{(n)}(a)
$$

Then $p_n(x)$ is a polynomial of degree at most $n$, with $p_n(a) = f(a)$ and

$$
p_n^{(s)}(x) = f^{(s)}(a) + (x - a)f^{(s + 1)}(a) + \cdots + {(x - a)^{n - s} \over (n - s)!} f^{(n)}(a)
$$

so $p_n^{(s)}(a) = f^{(s)}(a)$ for $1 \le s \le n$.
We then have $r_{n+1}(x) = f(x) - p_n(x)$ being the remainder term in which we hope to be small so that $p_n(x)$ is a good approximation.
We will need to following lemma to prove the desired results.

> *Lemma.*{: .lem}
> **[Higher-order Rolle's Theorem]**
> Let $f$ be continuous on $[a, b]$ and $n$-times differentiable on an open interval containing $[a, b]$.
> Suppose that
>
> $$
  f(a) = f'(a) = f''(a) = \cdots = f^{(n-1)}(a) = f(b) = 0
  $$
>
> Then there exists $c$, with $a < c < b$ such that $f^{(n)}(c) = 0$.
>
> *Proof.*{: .prf}
>
> When $n = 0$, it is just Rolle's Theorem.
> Suppose $k < n$. There exists $c_k \in (a, b)$ such that $f^{(k)}(c_k) = 0$.
> As $f^{(k)}(a) = 0$, by Rolle's Theorem, there exists $c_{k+1} \in (a, c_k)$ such that $f^{(k+1)}(c_{k+1}) = 0$.
> By induction, there exists $c_n$, with $a < c_n < c_{n-1} < \cdots < c_1 < b$ such that $f^{(n)})(c_n) = 0$.

Base on different conditions that are placed on $f$ and its derivatives, we can get different results about the remainder term.

> *Theorem.*{: .thm}
> **[Taylor's Theorem with Lagrange's Remainder]**
> Suppose $f$ is a continuous function on $[a, b]$ which is $n$-times differentiable on $[a, b)$.
> Then there exists $c \in (a, b)$ such that
>
> $$
  \begin{align*}
  f(b) &= f(a) + (b - a) f'(a) + \cdots + {(b - a)^{n-1} \over (n - 1)!} f^{(n-1)}(a) + {(b - a)^{n} \over n!} f^{(n)}(c) \\
  &= p_{n-1}(b) + {(b - a)^{n} \over n!} f^{(n)}(c)
  \end{align*}
  $$
>
> Let $b = a + h$, it becomes
>
> $$
  f(a + h) = f(a) + hf'(a) + \cdots + {h^{n-1} \over (n-1)!} f^{(n-1)}(a) + {h^n \over n!} f^{(n)}(c)
  $$
>
> *Proof.*{: .prf}
>
> The theorem is like the mean value theorem for higher order and the proof is similar.
>
> Let
>
> $$
  \phi(x) = f(x) - p_{n-1}(x) - k {(x - a)^n \over n!}
  $$
>
> where $k$ is a real number chosen so that $\phi(b) = 0$.
>
> Then we have $\phi(a) = \phi'(a) = \cdots = \phi^{(n-1)}(a) = \phi(b) = 0$.
> By the higher-order Rolle's Theorem, there exists $c \in (a, b)$ such that
>
> $$
  \phi^{(n)}(c) = f^{(n)}(c) - k = 0 \quad \implies \quad k = f^{(n)}(c)
  $$
>
> Hence,
>
> $$
  f(b) = p_{n-1}(b) + {(b - a)^n \over n!} f^{(n)}(c)
  $$

> *Theorem.*{: .thm}
> **[Taylor's Theorem with Cauchy's Remainder]**
> Suppose $f$ is a continuous function on $[a, b]$ which is $n$-times differentiable on $[a, b)$,
> and for which the derivatives are bounded on $[a, b)$.
> Suppose that $k \in \mathbb{R}$ and that $k > 0$.
> Then there exists $c \in (a, b)$ such that
>
> $$
  \begin{align*}
  f(b) &= p_{n-1}(b) + {(b - c)^{n-k}(b - a)^{k} \over k(n - 1)!} f^{(n)}(c)
  \end{align*}
  $$
>
> Let $c = (1 - \theta_n)a + \theta_n b$, it becomes
>
> $$
  \begin{align*}
  f(b) &= p_{n-1}(b) + {(1 - \theta_n)^{n-k}(b - a)^{n} \over k(n - 1)!} f^{(n)}(c)
  \end{align*}
  $$
>
> *Proof.*{: .prf}
>
> Let
>
> $$
  h(x) = f(x) + \sum_{s=1}^{n-1} {(b - x)^s \over s!} f^{(s)}(x)
  $$
>
> We have $h(a) = p_{n-1}(b)$ and $h(b) = f(b)$ and
>
> $$
  {\mathrm{d} \over \mathrm{d}x}\left( {(b - x)^s \over s!} f^{(s)}(x) \right) = - {(b - x)^{s-1} \over (s-1)!} f^{(s)}(x) + {(b - x)^s \over s!} f^{(s + 1)}(x)
  $$
>
> so that
>
> $$
  h'(x) = {(b - x)^{n-1} \over (n - 1)!} f^{(n)}(x)
  $$
>
> as all the other terms are cancelling in pairs.
>
> Let
>
> $$
  g(x) = - (b - x)^k
  $$
>
> so that $g(b) - g(a) = (b - a)^k$ and $g'(x) = k(b - x)^{k-1} \not= 0$ for $x \in (a, b)$.
>
> By Cauchy's mean value theorem, there exists $c \in (a, b)$ such that
>
> $$
  {h(b) - h(a) \over g(b) - g(a)} = {h'(c) \over g'(c)}
  $$
>
> Hence,
>
> $$
  \begin{align*}
  f(b) &= h(b) = h(a) + (h(b) - h(a)) \\
  &= h(a) + (g(b) - g(a)) {h'(c) \over g'(c)} \\
  &= p_{n-1}(b) +  {(b - c)^{n-1}(b - a)^k \over k(b - c)^{k-1}(n - 1)! } f^{(n)}(c) \\
  &= p_{n-1}(b) +  {(b - c)^{n-k}(b - a)^k \over k(n - 1)! } f^{(n)}(c)
  \end{align*}
  $$

When $k = n$, we have Cauchy's remainder being the same as Lagrange's remainder.

> *Definition.*{: .def}
> Suppose that $f$ is infinitely differentiable and let $f(x) = p_n(x) + r_{n+1}(x)$.
> If $r_n(x) \to 0$ as $n \to \infty$, we can write
>
> $$
  f(x) = f(a) + \sum_{j=1}^{\infty} {(x - a)^j \over j!} f^{(j)}(a)
  $$
>
> which is called the **Taylor series** for $f$.

Taylor's theorem requires $f$ to be differentiable in an interval but we don't need that for the linear approximation $f(x) = f(a) + (x - a)f'(a) + o(\vert x - a \vert)$.
Therefore, we have the following corresponding result.

> *Theorem.*{: .thm}
> **[Young's Theorem]**
> Suppose that $f$ is $(n - 1)$-times differentiable in an interval $I$ and $f^{(n)}$ is differentiable at $a \in I$.
> Then $r_{n+1}(x) = f(x) - p_n(x) = o(\vert x - a \vert^n)$.
>
> *Proof.*{: .prf}
>
> Let $u(x) = r_{n+1}(x) / (x - a)^n$ for $x \not= a$.
> For any $\varepsilon > 0$, let
>
> $$
  v_\varepsilon(x) = r_{n+1}(x) + \varepsilon(x - a)^n
  $$
>
> Since $r_{n+1}(a) = r_{n+1}'(a) = \cdots = r_{n+1}^{(n)}(a) = 0$,
>
> $$
  v_\varepsilon(a) = v_\varepsilon'(a) = \cdots = v_\varepsilon^{(n-1)}(a) = 0 \quad \text{and} \quad v_\varepsilon^{(n)}(a) = n!\varepsilon > 0
  $$
>
> Thus, $v_\varepsilon^{(n-1)}(x)$ is strictly increasing at $x = a$ and there exists an interval $[a, a + \delta) \subseteq I$ such that $v_\varepsilon^{(n-1)}(x) > 0$ for $x \in [a, a + \delta)$.
> It implies $v_\varepsilon^{(n-2)}(x)$ is strictly increasing in the inteval $[a, a + \delta)$.
> By iterating the argument, it follows that $v_\varepsilon(x) > 0$
>
> Since $v_\varepsilon(x) = (u(x) + \varepsilon)(x - a)^n$, $u(x) > -\varepsilon$ for $x \in (a, a + \delta)$.
> Applying the same argument to $w_\varepsilon(x) = - r_{n+1}(x) + \varepsilon(x - a)^n$, we can conclude $u(x) < \varepsilon$
> Therefore, $u(x) \to 0$ as $x \to a^+$. Similarily, $u(x) \to 0$ as $x \to a^-$.
> Hence, $r_{n+1}(x) / (x - a)^n \to 0$ and $r_{n+1}(x) = o(\vert x - a \vert^n)$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 4
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 7.1, 7.3, 7.6
