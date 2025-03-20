---
layout: base
title: Continuous Functions &#124; Analysis
---

# Continous Functions
{: .page-title}

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
