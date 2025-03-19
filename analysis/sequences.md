---
layout: base
title: Sequences &#124; Analysis
---

# Sequences
{: .page-title}

> *Definition.*{: .def}
> A **sequence** is a function $a: \mathbb{N} \to A$, denoted by $(a_n)$ or $(a_n)\_1^\infty$ or $(a_n)_{n=1}^\infty$.

We want to study what it means for a real sequence to converge.

> *Definition.*{: .def}
> Let $(a_n)$ be a sequence and $L \in \mathbb{R}$.
> Then $(a_n)$ **converges** to $L$ or $a_n \to L$ if
>
> $$
  (\forall \varepsilon > 0)(\exists N \in \mathbb{N})(\forall n \ge N)\;|a_n - L| < \varepsilon
  $$
>
> We then also write
>
> $$
  \lim a_n = L
  $$
>
> The sequence is said to be **convergent**, otherwise it is **divergent**.

It is similar to the definition of limit of a function $f(x)$, therefore

$$
\lim_{x \to \infty} f(x) = L \text{ and } f(n) = a_n \implies \lim_{n \to \infty} a_n = L
$$

> *Definition.*{: .def}
> $(a_n)$ is a **null sequence** if
>
> $$
  (\forall \varepsilon > 0)(\exists N \in \mathbb{N})(\forall n \ge N)\;|a_n| < \varepsilon
  $$

> *Proposition.*{: .prop}
> $\lim a_n = L$ iff $a_n - L$ is a null sequence.

## Bounded Sequences

> *Definition.*{: .def}
> A sequence is **bounded above** if
>
> $$
  (\exists M)(\forall n)\;a_n \le M
  $$

> *Definition.*{: .def}
> A sequence is **bounded below** if
>
> $$
  (\exists m)(\forall n)\;a_n \ge m
  $$

> *Definition.*{: .def}
> A sequence is **bounded** if it is bounded above and below, i.e.
>
> $$
  (\exists M)(\forall n)\; |a_n| \le M
  $$
>
> Otherwise it is **unbounded**.

> *Definition.*{: .def}
> A sequence is **eventually bounded** if
>
> $$
  (\exists M)(\exists N)(\forall n \ge N)\; |a_n| \le M
  $$

> *Lemma.*{: .lem}
> Every eventually bounded sequence is bounded.
>
> *Proof.*{: .prf}
>
> Obviously, the eventually bounded sequence is bounded by $\max(\vert a_1 \vert, ..., \vert a_{N-1} \vert, M)$.

It can be useful for proving sequence to be bounded by showing it is eventually bounded.

> *Lemma.*{: .lem}
> Every convengent sequence is bounded.
>
> *Proof.*{: .prf}
>
> Let $\varepsilon = 1$, there exists $N$ such that for all $n > N$, $\vert a_{n} - L \vert < 1$ and hence $(a_{n})$ is eventually bounded by $L + 1$.

## Divergent Sequences

There are two cases for a sequence to be divergent.

> *Definition.*{: .def}
> The sequence $a_n$ is said to diverge to $+\infty$ or tend to infinity if
>
> $$
  (\forall A \in \mathbb{R})(\exists N \in \mathbb{N})(\forall n > N)\; a_n > A
  $$

Similarily,

$$
a_n \to -\infty \implies (\forall A \in \mathbb{R})(\exists N \in \mathbb{N})(\forall n > N)\; a_n < A
$$

> *Definition.*{: .def}
> If the sequence $(a_n)$ does not tend to a limit or to $\pm \infty$, it is said to be **oscillating**.
> If $(a_n)$ oscillates and bounded, it oscillates finitely.
> If $(a_n)$ oscillates and is not bounded, it oscillates infinitely.

## Sums and Products

> *Lemma.*{: .lem}
> If $(a_n)$ and $(b_n)$ are null sequences, then $(a_n + b_n)$ is also a null sequence.
>
> *Proof.*{: .prf}
>
> For any $\varepsilon > 0$, there exists $N_1$ and $N_2$ such that
>
> $$
  (\forall n > N_1)\; |a_n| < \varepsilon / 2
  \quad \text{and} \quad
  (\forall n > N_2)\; |b_n| < \varepsilon / 2
  $$
>
> Let $N = \max(N_1, N_2)$, then by triangle inequality,
>
> $$
  (\forall n > N)\; |(a_n + b_n)| \le |a_n| + |b_n| < \varepsilon
  $$

> *Theorem.*{: .thm}
> **[Sum of Sequences]**
> If $a_n \to a$ and $b_n \to b$, then $a_n + b_n \to a + b$.
>
> *Proof.*{: .prf}
>
> $$
  (a_n + b_n) - (a + b) = (a_n - a) + (b_n - b)
  $$
>
> $(a_n - a)$ and $(b_n - b)$ are null sequences and hence $((a_n + b_n) - (a + b))$ is also a null sequence.

> *Lemma.*{: .lem}
> If $(a_n)$ is a null sequence and $(b_n)$ is a bounded sequence, then $(a_nb_n)$ is a null sequence.
>
> *Proof.*{: .prf}
>
> Let $(b_n)$ be bounded by $M$.
> For any $\varepsilon > 0$, there exists $N$ such that
>
> $$
  (\forall n > N)\; |a_n| < \varepsilon / M
  $$
>
> Therefore,
>
> $$
  (\forall n > N)\; |a_nb_n| = |a_n||b_n| < (\varepsilon / M)(M) = \varepsilon
  $$

> *Corollary.*{: .cor}
> If $(a_n)$ is a null sequence and $c$ is a constant, then $(ca_n)$ is a null sequence.

> *Theorem.*{: .thm}
> **[Product of Sequences]**
> If $a_n \to a$ and $b_n \to b$, then $a_nb_n \to ab$.
>
> *Proof.*{: .prf}
>
> $$
  a_nb_n - ab = (a_n - a)b_n + a(b_n - b)
  $$
>
> $(a_n - a)$ is a null sequence and $(b_n)$ is bounded, therefore $(a_n - a)b_n$ is a null sequence.
>
> $(b_n - b)$ is a null sequence and $a$ is a constant, therefore $a(b_n - b)$ is a null sequence.
>
> Hence, $(a_nb_n - ab)$ is also a null sequence.

> *Theorem.*{: .cor}
> **[Quotient of Sequences]**
> If $a_n \to a$ and $b_n \to b$, and $b \not= 0$, then $a_n / b_n \to a / b$.

## Convergence Test

> *Property.*{: .prop}
> Let $\Set{a_n}$ be a sequence. Then
>
> $$
  \lim_{n \to \infty} |a_n| = 0 \implies \lim_{n \to \infty} a_n = 0
  $$
>
> *Proof.*{: .prf}
>
> As
>
> $$
  -|a_n| \le a_n \le |a_n| \quad \text{and} \quad \lim_{n \to \infty} |a_n| = 0 \implies \lim_{n \to \infty} -|a_n| = 0
  $$
>
> By Squeeze Theorem, $\lim_{n \to \infty} a_n = 0$.

It is useful for finding limits of alternating sequence, for example

$$
\lim_{n \to \infty} \left| {(-1)^n \over n} \right| = 0 \implies \lim_{n \to \infty} {(-1)^n \over n} = 0
$$

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

## Monotonic and Bounded Sequences

> *Definition.*{: .def}
> A sequence is **increasing** if
>
> $$
  \forall n \ge 1, \quad a_n < a_{n+1}
  $$

> *Definition.*{: .def}
> A sequence is **decreasing** if
>
> $$
  \forall n \ge 1, \quad a_n > a_{n+1}
  $$

> *Definition.*{: .def}
> A sequence is **monotonic** if it is either increasing or decreasing.
> *Proposition.*{: .prop}
> Every monotonic, bounded sequence is convergent.
>
> *Proof.*{: .prf}
>
> If $\Set{a_n}$ is bounded above, there exists a least upper bound $L$.
> Given $\varepsilon > 0$, $L - \varepsilon$ is not an upper bound, so for some integer $N$
>
> $$
  L - \varepsilon < a_N \le L
  $$
>
> As $\Set{a_n}$ is increasing, $a_n \ge a_N$ for all $n > N$. Thus,
>
> $$
  L - \varepsilon < a_n \le L
  $$
>
> Hence, $\lim_{n \to \infty} a_n = L$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 2
* James Stewart _Single Variable Calculus_, 2015 - Chapter 11
