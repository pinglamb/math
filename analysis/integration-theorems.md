---
layout: base
title: Integration Theorems &#124; Analysis
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

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 7
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 8.4 - 8.8
