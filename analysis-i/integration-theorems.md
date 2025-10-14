---
layout: base
title: Integration Theorems &#124; Analysis I
---

# Integration Theorems
{: .page-title}

> *Proposition.*{: .prop}
> A continuous function $f$ on $[a, b]$ is Riemann integrable.
>
> *Proof.*{: .prf}
>
> Since $f$ is continuous, it is uniformly continuous.
>
> Suppose that $\varepsilon > 0$. There exists $\delta$ such that if $\vert x_1 - x_2 \vert < \delta$, $\vert f(x_1) - f(x_2) \vert < \varepsilon / (b - a)$.
> Thus, any dissection $D$ with subintervals $\Set{I_1, ..., I_k}$ and $\delta^\ast(D_n) < \delta$, for each subinterval $I_r$,
>
> $$
  M_{I_r} - m_{I_r} < {\varepsilon \over b - a}
  $$
>
> Hence,
>
> $$
  S_D - s_D = \sum_{r = 1}^k (M_{I_r} - m_{I_r}) \delta_r < {\varepsilon \over b - a} \sum_{r=1}^k \delta_r = \varepsilon
  $$

> *Proposition.*{: .prop}
> A monotonic function $f$ on $[a, b]$ is Riemann integrable.
>
> *Proof.*{: .prf}
>
> wlog. Suppose $f$ is increasing.
>
> Suppose that $\varepsilon > 0$. Choose $N$ so that $N > (f(b) - f(a))(b - a)/\varepsilon$.
> Let $D$ be a dissection with $N$ intervals of equal length, i.e. $\delta_r = (b - a) / N$.
> Then $M_{I_r} = f(x_r)$ and $m_{I_r} \ge f(x_{r-1})$.
> Hence,
>
> $$
  S_D - s_D \le \sum_{r=1}^N \left( f(x_r) - f(x_{r-1}) \right) {(b - a) \over N} = {(f(b) - f(a))(b - a) \over N} < \varepsilon
  $$

> *Proposition.*{: .prop}
> A bounded function $f$ that is continuous except at finitely many points on $[a, b]$ is Riemann integrable.
>
> *Proof.*{: .prf}
>
> Assume $\vert f(x) \vert \le C$ for every $x \in [a, b]$ and $f$ is not continuous at points $\Set{c_1, c_2, ..., c_k}$.
>
> Suppose that $\varepsilon > 0$.
> Choose $\delta < \varepsilon / 8kC$, by subtracting the subintervals $(c_r - \delta, c_r + \delta)$ from $[a, b]$,
> we have a finite disjoint union of closed intervals such that $f$ is continuous and therefore integrable.
> Thus, we can find a dissection $D'$ of that union of intervals such that $S_{D'} - s_{D'} < \varepsilon/2$.
> Hence, there exists a dissection $D$ of $[a, b]$ such that
>
> $$
  S_D - s_D \le {2\varepsilon \over 8kC} (k) (C - (-C)) + (S_{D'} - s_{D'}) < {\varepsilon \over 2} + {\varepsilon \over 2} < \varepsilon
  $$

For example, $f(x) = \sin(1/x)$ with $f(0) = 0$ is Riemann integrable on $[-1, 1]$ since $f(0)$ is the only point that $f$ is discontinuous.

## Algebraic Properties

> *Definition.*{: .def}
> Suppose that $f$ is integrable and if $a < b$,
>
> $$
  \int_a^b f(x) \, dx = - \int_b^a f(x) \, dx
  $$

> *Proposition.*{: .prop}
> If $a \le c < d \le b$ and $f$ is integrable in $[a, b]$, then $f$ is integrable in $[c, d]$.
>
> *Proof.*{: .prf}
>
> Suppose that $\varepsilon > 0$.
> There exists $\delta$ such that any dissection on $[a, b]$ with $\delta^\ast(D) < \delta$, we have
>
> $$
  S_D - s_D < \varepsilon
  $$
>
> Consider a dissection $D'$ on $[c, d]$ with $\delta^\ast(D') < \delta$,
> we can form a dissection $D$ on $[a, b]$ by adding subintervals with length less than $\delta$ on $[a, c]$ and $[d, b]$ to $D'$.
> Since $D$ contains all the subintervals of $D'$, we have
>
> $$
  S_{D'} - s_{D'} \le S_D - s_D < \varepsilon
  $$

> *Proposition.*{: .prop}
> If $a < c < b$, and $f$ is integrable in $[a, b]$, then
>
> $$
  \int_a^b f = \int_a^c f + \int_c^b f
  $$
>
> *Proof.*{: .prf}
>
> Suppose that $\varepsilon > 0$.
> Consider a dissection $D$ on $[a, b]$ with $\delta^\ast(D) < \delta$ and form another dissection $D'$ by adding $c$ as point of division to $D$.
> Further, let $D_1$ and $D_2$ be the dissection on $[a, c]$ and $[c, b]$ base made of points of $D'$.
> Since $D'$ refines $D$,
>
> $$
  S_{D'} - s_{D'} = (S_{D_1} - s_{D_1}) + (S_{D_2} - s_{D_2}) \le S_D - s_D < \varepsilon
  $$
>
> Both $S_{D_1} - s_{D_1}$ and $S_{D_2} - s_{D_2}$ are non-negative, and hence
>
> $$
  S_{D_1} - s_{D_1} < \varepsilon \quad \text{and} \quad S_{D_2} - s_{D_2} < \varepsilon
  $$

Next, we want to prove that integration is linear, i.e.

$$
\int_a^b (\lambda f + \mu g) = \lambda \int_a^b f + \mu \int_a^b g
$$

> *Proposition.*{: .prop}
> Suppose that $\lambda \ge 0$ is a constant.
> If $f$ is integrable, then $\lambda f$ is integrable and
>
> $$
  \int_a^b \lambda f = \lambda \int_a^b f
  $$
>
> *Proof.*{: .prf}
>
> $$
  \sup \lambda f = \lambda \sup f \quad \text{and} \quad \inf \lambda f = \lambda \inf f
  $$
>
> Suppose that $\varepsilon > 0$.
> Consider a dissection $D$ on $[a, b]$ with $S_D(f) - s_D(f) < \varepsilon / \lambda$, then
>
> $$
  S_D(\lambda f) - s_D(\lambda f) = \lambda (S_D(f) - s_D(f)) < \lambda \left( { \varepsilon \over \lambda} \right) = \varepsilon
  $$

> *Proposition.*{: .prop}
> If $f$ is integrable, then $-f$ is integrable and
>
> $$
  \int_a^b -f = - \int_a^b f
  $$
>
> *Proof.*{: .prf}
>
> $$
  \sup -f = -\inf f \quad \text{and} \quad \inf -f = -\sup f
  $$
>
> Suppose that $\varepsilon > 0$.
> Consider a dissection $D$ on $[a, b]$ with $S_D - s_D < \varepsilon$, then
>
> $$
  S_D(-f) - s_D(-f) = S_D(f) - s_D(f) < \varepsilon
  $$

> *Proposition.*{: .prop}
> If $f$ and $g$ are integrable in $[a, b]$, then $f + g$ is integrable and
>
> $$
  \int_a^b (f + g) = \int_a^b f + \int_a^b g
  $$
>
> *Proof.*{: .prf}
>
> $$
  \sup (f + g) \le \sup f + \sup g \quad \text{and} \quad \inf (f + g) \ge \inf f + \inf g
  $$
>
> Then,
>
> $$
  \underline{\int_a^b} (f + g) \ge \underline{\int_a^b} f + \underline{\int_a^b} g = \overline{\int_a^b} f + \overline{\int_a^b} g \ge \overline{\int_a^b} (f + g)
  $$
>
> But $\overline{\int_a^b} (f + g) \ge \underline{\int_a^b} (f + g)$ so $\overline{\int_a^b} (f + g) = \underline{\int_a^b} (f + g)$.

We would like to prove that the product of two integrable functions is again integrable.
If we can prove that the square is integrable, then the result will follow since

$$
4fg = (f + g)^2 - (f - g)^2
$$

> *Proposition.*{: .prop}
> If $f$ is integrable in $[a, b]$, then $f^2$ is integrable.
>
> *Proof.*{: .prf}
>
> Let $K = \sup \vert f \vert$ in $[a, b]$.
>
> Suppose that $\varepsilon > 0$.
> There exists $\delta$ such that for any dissection $D$ with $\delta^\ast(D) < \delta$,
>
> $$
  S_D(f) - s_D(f) < {\varepsilon \over 2K}
  $$
>
> Suppose that $f^2$ attains its supremum and infimum at $s_r$ and $t_r$ in interval $I_r$.
> Since $f(s_r) \le M_r$ and $f(t_r) \ge m_r$ and $f(\xi_r) \le K$ for any $\xi_r$,
>
> $$
  \vert f(s_r)^2 - f(t_r)^2 \vert = \vert f(s_r) + f(t_r) \vert \vert f(s_r) - f(t_r) \vert \le 2K(M_r - m_r)
  $$
>
> Hence,
>
> $$
  S_D(f^2) - s_D(f^2) \le 2K (s_D(f) - s_D(f)) < \varepsilon
  $$

> *Corollary.*{: .cor}
> If $f$ and $g$ are integrable in $[a, b]$, then $fg$ is integrable.

## Inequalities

> *Proposition.*{: .prop}
> If $f \le g$ for all $x \in [a, b]$, then
>
> $$
  \int_a^b f \le \int_a^b g
  $$
>
> *Proof.*{: .prf}
>
> $\sup f \le \sup g$.

> *Proposition.*{: .prop}
> If $m \le f \le M$ for all $x \in [a, b]$, then
>
> $$
  m(b - a) \le \int_a^b f \le M(b - a)
  $$
>
> *Proof.*{: .prf}
>
> $$
  m(b - a) = \int_a^b m \le \int_a^b f \le \int_a^b M = M(b - a)
  $$

> *Corollary.*{: .cor}
> **[Mean Value Theorem]**
> If $f$ is continuous, then there exists $c \in [a, b]$ such that
>
> $$
  \int_a^b f = f(c)(b - a)
  $$
>
> *Proof.*{: .prf}
>
> It is obviously true when $a = b$ so assume $a \not= b$, then
>
> $$
  m \le {1 \over b - a} \int_a^b f \le M
  $$
>
> Hence, the result follows from intermediate value theorem.

> *Proposition.*{: .prop}
> If $f$ is integrable in $[a, b]$, then $\vert f \vert$ is integrable and
>
> $$
  \left| \int_a^b f \right| \le \int_a^b |f|
  $$
>
> *Proof.*{: .prf}
>
> $\sup \vert f \vert - \inf \vert f \vert \le \sup f - \inf f$ and $-\vert f \vert \le f \le \vert f \vert$.

> *Proposition.*{: .prop}
> **[Schwarz's Inequality]**
>
> $$
  \left( \int_a^b fg \right)^2 \le \left( \int_a^b f^2 \right) \left( \int_a^b g^2 \right)
  $$
>
> *Proof.*{: .prf}
>
> Since
>
> $$
  \int_a^b (f + \lambda g)^2 = \int_a^b f^2 + 2\lambda \int_a^b fg + \lambda^2 \int_a^b g^2 \ge 0
  $$
>
> the quadratic equation in $\lambda$ has at most one root.
> Hence, the determinant
>
> $$
  \left( 2 \int_a^b fg \right)^2 - 4 \left( \int_a^b f^2 \right) \left( \int_a^b g^2 \right) \le 0
  $$

## Fundamental Theorem of Calculus

> *Theorem.*{: .prop}
> **[Fundamental Theorem of Calculus]**
> Suppose that $f$ is integrable on $[a, b]$. Set
>
> $$
  F(x) = \int_a^x f(t) \,dt
  $$
>
> for $a \le x \le b$. Then
>
> + $F$ is continuous.
>
> + If $f$ is continuous at $x$ then $F$ is differentiable at $x$, with $F'(x) = f(x)$.
>
> *Proof.*{: .prf}
>
> $$
  F(x + h) - F(x) = \int_x^{x+h} f(t) \,dt \quad \text{and} \quad \left| \int_x^{x+h} f(t) \,dt \right| \le \int_x^{x+h} |f(t)| \,dt \le \max(|Mh|, |mh|)
  $$
>
> Hence, $F(x + h) - F(x) \to 0$ as $h \to 0$ and $F$ is continuous.
>
> Suppose that $\varepsilon > 0$.
> Since $f$ is continuous at $x$, there exists $\delta$ such that for $\vert t - x \vert < \delta$ implies $\vert f(t) - f(x) \vert < \varepsilon$.
> If $\vert h \vert < \delta$, then
>
> $$
  \begin{align*}
  \left| {F(x + h) - F(x) \over h} - f(x) \right| &= \left| {1 \over h} \left( \int_x^{x+h} f(t) \,dt - hf(x) \right) \right| \\
  &\le {1 \over |h|} \left| \int_x^{x+h} |f(t) - f(x)| \,dt \right| \\
  &< { \varepsilon |h| \over |h| } = \varepsilon
  \end{align*}
  $$

> *Corollary.*{: .cor}
> Suppose that $f$ is differentiable and $f'$ is continuous on $[a, b]$. Then
>
> $$
  \int_a^x f'(t) \,dt = f(x) - f(a)
  $$
>
> *Proof.*{: .prf}
>
> Let
>
> $$
  g(x) = \int_a^x f(t) \, dt
  $$
>
> Then $g'(x) = f'(x)$ by the F.T.C. and $g(x) - f(x)$ is a constant function by M.V.T.
>
> Since $g(a) = 0$, $g(a) - f(a) = 0 - f(a) = c$ and so $g(x) = f(x) - f(a)$.

> *Theorem.*{: .prop}
> Suppose that $f$ is differentiable on $[a, b]$ and $f'$ is integrable then
>
> $$
  \int_a^x f'(t) \,dt = f(x) - f(a)
  $$
>
> *Proof.*{: .prf}
>
> Let $D$ be a dissection $a = t_0 < t_1 < ... < t_n = x$. We have
>
> $$
  f(x) - f(a) = \sum_{i=1}^n (f(t_i) - f(t_{i-1}))
  $$
>
> By M.V.T., there exists $c_i \in (t_{i-1}, t_i]$ such that $f(t_i) - f(t_{i-1}) = f'(c_i)(t_i - t_{i-1})$.
> Since $f'$ is integrable, by definition as $\delta^\ast(D) \to 0$,
>
> $$
  f(x) - f(a) = \sum f'(c_i)(t_i - t_{i-1}) = \int_a^x f'(t) \,dt
  $$

This is a stronger result since it doesn't require the derivative to be continuous.

> *Definition.*{: .def}
> The **indefinite integral** of $f$, denoted by
>
> $$
  \int f(x) \,dx
  $$
>
> is a function with integrable derivative $f$ that is deterministic up to an additive constant.

The existence of such function is established by F.C.T. and determined by the relationship $\int_a^x f'(t) \,dt = f(x) - f(a)$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 7
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 8.4 - 8.8
