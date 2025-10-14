---
layout: base
title: Complex Sequences &#124; Analysis I
---

# Complex Sequences
{: .page-title}

The definition of convergence of complex-valued sequences is a straightforward generalizations of that of real sequences.

> *Definition.*{: .def}
> Let $(z_n)$ is a sequence of complex numbers.
> Then $(z_n)$ **converges** to $z$ or $z_n \to z$ if
>
> $$
  (\forall \varepsilon > 0)(\exists N \in \mathbb{N})(\forall n \ge N)\;|z_n - z| < \varepsilon
  $$

> *Definition.*{: .def}
> $(z_n)$ is a Cauchy sequence if
>
> $$
  (\forall \varepsilon > 0)(\exists N \in \mathbb{N})(\forall m, n \ge N)\; |z_m - z_n| < \varepsilon
  $$

The following elementary result associates complex sequences with real sequences.

> *Proposition.*{:.prop}
> Suppose that $(z_n = x_n + i y_n)$ is a sequence in $\mathbb{C}$ and $z = x + iy \in \mathbb{C}$.
> Then $z_n \to z$ iff $x_n \to x$ and $y_n \to y$.
> $(z_n)$ is a Cauchy sequence iff $(x_n)$ and $(y_n)$ are Cauchy sequences.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Since $\vert x_n - x \vert \le \vert z_n - z \vert$ and $\vert y_n - y \vert \le \vert z_n - z \vert$.
> If $z_n \to z$, then $x_n \to x$ and $y_n \to y$.
>
> ($\Leftarrow$) Since $\vert z_n - z \vert \le \vert x_n - x \vert + \vert y_n - y \vert$.
> If $x_n \to x$ and $y_n \to y$, then $z_n \to z$.
>
> The proof for the result concerning Cauchy sequences is essentially the same.

> *Definition.*{: .def}
> A sequence $(z_n)$ is **bounded** if the set $\Set{\vert z_n \vert : n \in \mathbb{N}}$ is bounded in $\mathbb{R}$.

With the above results, all the properties such as addition and multiplication of real sequences is applicable to complex sequences.

> *Proposition.*{: .prop}
> **[Bolzano-Weierstrass Theorem]**
> Suppose $(z_n)$ is a bounded sequence of complex numbers. Then there is a subsequence $(z_{n_k})$ which converges.
>
> *Proof.*{: .prf}
>
> By real Bolzano-Weierstrass Theorem, there exists a subsequence $(z_{m_k})$ such that $(x_{m_k})$ converges and a subsequence $(z_{n_k})$ such that $(y_{n_k})$ converges.
> Hence, $(z_{n_k})$ converges.

> *Proposition.*{: .prop}
> **[General Principle of Convergence]**
> A sequence $(z_n)$ of complex numbers is convergent iff it is a Cauchy sequence.

> *Proposition.*{: .prop}
> Let $z_n = z^n$. Then $z_n \to 0$ if $\vert z \vert < 1$, $z_n \to 1$ if $z = 1$, otherwise it diverges.
>
> *Proof.*{: .prf}
>
> We have $\vert z_n - 0 \vert = \vert z \vert^n$.
>
> If $\vert z \vert < 1$, $\vert z \vert^n \to 0$, therefore $z_n \to 0$.
>
> Obviously, if $z = 1$, $z_n = 1$ and therefore $z_n \to 1$.
>
> If $\vert z \vert \ge 1$ and $z \not= 1$, then $\vert z_{n+1} - z_n \vert = \vert z^n \vert \vert z - 1 \vert \ge \vert z - 1 \vert$. So it is not a Cauchy sequence and diverges.

## References

* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 3.8
