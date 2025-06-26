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
> A bounded function $f$ that is continuous on $(a, b)$ is Riemann integrable on $[a, b]$.
>
> *Proof.*{: .prf}
>
> Suppose that $\varepsilon > 0$ and $\vert f(x) \vert \le C$ for every $x \in [a, b]$.
> Choose $a'$ such that $a' - a < \varepsilon / 8C$ and $b'$ such that $b - b' < \varepsilon/8C$.
> Since $f$ is continuous on $[a', b']$, it is integrable and
> we can find a dissection $D'$ with points $x_1 = a' < ... < x_{n-1} = b'$ such that $S_{D'} - s_{D'} < \varepsilon/2$.
>
> Let $D$ be the dissection with points $a = x_0 < x_1 < ... < x_{n-1} < x_n = b$. Hence,
>
> $$
  S_D - s_D \le (C - (-C)) {\varepsilon \over 8C} + (S_{D'} - s_{D'}) + (C - (-C)) {\varepsilon \over 8C} < \varepsilon
  $$

It means function needs not be continuous at the endpoint so to be integrable, an example will be $\int_0^1 \sin 1/x \,dx$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 7
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 8.4 - 8.8
