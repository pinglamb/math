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

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 7
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 8.4 - 8.8
