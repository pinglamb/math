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

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 7
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 8.4 - 8.8
