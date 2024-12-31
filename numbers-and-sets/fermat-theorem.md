---
layout: base
title: Fermat's Theorem &#124; Numbers and Sets
---

# Fermat's Theorem
{: .page-title}

The Fermat's Little Theorem, together with Wilson's Theorem and Euler's Theorem, are some of the most important congruences in number theory.

## Wilson's Theorem

> *Theorem.*{: .thm}
> **[Wilson's Theorem]**
> If $p$ is prime, then
>
> $$
  (p - 1)! \equiv -1 \pmod p
  $$
>
> *Proof.*{: .prf}
>
> When $p = 2$, $1! \equiv 1 \equiv -1 \pmod 2$.
>
> When $p \ge 3$, consider the congruence $x^2 \equiv 1 \pmod p$.
> It implies $p \mid (x + 1)(x - 1)$ and the only solution to it is $x \equiv \pm 1 \pmod p$.
> It means that the positive integers $2, 3, ..., p - 2$ can be grouped in pairs so that their product is congruent to $1$ modulo $p$.
> Hence,
>
> $$
  (p - 1)! \equiv (1)(p-1) \equiv -1 \pmod p
  $$

> *Theorem.*{: .thm}
> Conversely, if $(n - 1)! \equiv -1 \pmod n$, then $n$ is prime.
>
> Assume $n$ is composite, $n = ab$ and we have $a \mid (p - 1)!$.
> As $a \mid n$ and $n \mid (n-1)! + 1$, $a \mid (p-1)! + 1$.
> Thus, we have $a \mid (p-1)! + 1 - (p-1)! = 1$, which is a contradiction.

> *Theorem.*{: .thm}
> **[Gauss's Generalization of Wilson's Theorem]**
> The product of all the positive integers less than $m$ and relatively prime to $m$ is congruent to $1 \pmod m$,
> unless $m = 4, p^n, 2p^n$, where $p$ is an odd prime and $n$ is positive integer,
> in which case it is congruent to $-1 \pmod m$, i.e.
>
> $$
  \prod_{(a, m) = 1} a \equiv \begin{cases}
  -1 & \text{if } m = 4, p^n, 2p^n \, \text{where } p \text{ is odd prime} \\
  1  &\text{otherwise}
  \end{cases}
  \pmod m
  $$
>
> *Proof.*{: .prf}
>
> The number of solutions of $x^2 \equiv 1 \pmod m$ governs the product as we can pair the rest up so that their product is congruent to $1$ modulo $m$.
>
> When $m = p^k$, we have $p^k \mid (x + 1)(x - 1)$.
> Assume $p$ divides both, i.e. $p \mid (x+1)$ and $p \mid (x-1)$, then $p \mid (x+1-x+1) = 2$, which contradicts with $p$ being an odd prime.
> Thus, $p^k$ can only divide one of them which means the congruence has two solutions $x \equiv \pm 1 \pmod m$.
>
> When $m = 2$, $1 \equiv -1 \pmod 2$ so the congruence has only one solution.
>
> When $m = 4$, by trial and error the congruence has two solutions $x \equiv \pm 1 \pmod m$.
>
> When $m = 2^k$ with $k \ge 3$, we have $2^k \mid (x + 1)(x - 1)$.
> As $(x + 1) - (x - 1) = 2$ is a linear combination of $x + 1$ and $x - 1$, $(x+1, x-1) = 2$, so we have $2 \mid x + 1$ and $2^{k-1} \mid x - 1$ or $2 \mid x - 1$ and $2^{k-1} \mid x + 1$.
> The two cases can be simplified to $x \equiv \pm 1 \pmod{2^{k-1}}$, which means $x \equiv \pm 1 \pmod{2^k}$ or $x \equiv 2^{k-1} \pm 1 \equiv \pm (2^{k-1} + 1) \pmod{2^k}$ are the four solutions of the congruence.
>
> Therefore, when $m = 2^{k_0}p_1^{k_1}p_2^{k_2}...p_r^{k_r}$, we have the system of congruences
>
> $$
  \begin{align*}
  x^2 &\equiv 1 \pmod{2^{k_0}} \\
  x^2 &\equiv 1 \pmod{p_1^{k_1}} \\
  &\vdots \\
  x^2 &\equiv 1 \pmod{p_r^{k_r}} \\
  \end{align*}
  $$
>
> Base on the above, there are in total $2^{r + s}$ solutions, where
>
> $$
  s = \begin{cases}
  0 & \text{if } k_0 = 0, 1 \\
  1 & \text{if } k_0 = 2 \\
  2 & \text{otherwise}
  \end{cases}
  $$
>
> Also, the solutions are in pairs of $x \equiv \pm x_0 \pmod m$ and therefore we have their product congruent to $(-1)^{2^{r + s - 1}}$ modulo $m$.
> Base on that, the product is congruent to $-1$ iff $r + s - 1 = 0$, which are precisely the cases when $m = 4, p^n$ and $2p^n$.

## Fermat's Theorem

> *Theorem.*{: .thm}
> **[Fermat's Little Theorem]**
> If $p$ is prime and $a$ is a positive integer with $p \not \mid a$, then
>
> $$
  a^{p-1} \equiv 1 \pmod p
  $$
>
> *Proof.*{: .prf}
>
> As $\set{0, 1, 2, ..., p-1}$ is a complete system of residues, the set $\set{0, a, 2a, ..., (p-1)a}$ is also a complete system of residues.
> Therefore, the integers $a, 2a, ..., (p-1)a$ is just a reordering of the integers $1, 2, ..., p-1$, and hence
>
> $$
  \begin{align*}
  a \cdot 2a \cdots (p-1)a &\equiv (p - 1)! \pmod p \\
  a^{p-1} (p - 1)! &\equiv (p - 1)! \pmod p
  \end{align*}
  $$
>
> As $((p - 1)!, p) = 1$, we have
>
> $$
  a^{p-1} \equiv 1 \pmod p
  $$
>
> Alternatively, we can prove this by binomial theorem.
> Consider $(x + y)^p = x^p + {n \choose 1}x^{p-1}y + ... + y^p$, as ${n \choose k}$ is divisible by $p$ for $k = 1, 2, ..., p - 1$, we have
>
> $$
  (x + y)^p \equiv x^p + y^p \pmod p
  $$
>
> When $a = 1$, $1^{p - 1} \equiv 1 \pmod p$.
>
> When $a = k$, $k^{p - 1} \equiv 1 \pmod p$.
>
> When $a = k+1$, $(k + 1)^p \equiv k^p + 1^p \equiv k + 1 \pmod p$. As $p \not \mid k + 1$, $(k + 1)^{p-1} \equiv 1 \pmod p$.
>
> By induction, $a^{p - 1} \equiv 1 \pmod p$.

> *Corollary.*{: .cor}
> If $p$ is prime and $a$ is a positive integer, then
>
> $$
  a^p \equiv a \pmod p
  $$
>
> *Proof.*{: .prf}
>
> If $p \not \mid a$, by Fermat's Theorem, $a^{p - 1} \equiv 1 \pmod p \implies a^p \equiv a \pmod p$.
>
> If $p \mid a$, $p \mid a^p$, hence $a^p \equiv a \pmod p$.

> *Corollary.*{: .cor}
> If $p$ is prime and $(a, p) = 1$, then $a^{-1} \equiv a^{p-2} \pmod p$.

## Euler's Theorem

Euler's Theorem is the generalization of Fermat's Theorem.

> *Definition.*{: .def}
> Let $m$ be a positive integer. The **Euler's totient function** $\varphi(m)$ is defined to be the number of positive integers not exceeding $m$ that are relatively prime to $m$.

> *Definition.*{: .def}
> A **reduced residue system** modulo $m$ is a set of $\varphi(m)$ integers that are relatively prime to $m$ but pairwise incongruent to each other modulo $m$.

> *Theorem.*{: .thm}
> If $r_1, r_2, \ldots, r_{\varphi(m)}$ is a reduced residue system modulo $m$, then
>
> $$
  ar_1, ar_2, \ldots, ar_{\varphi(m)}
  $$
>
> in which $(a, m) = 1$ is also a reduced residue system modulo $m$.
>
> *Proof.*{: .prf}
>
> As $(a, m) = 1$ and $r_i$ are relatively prime to $m$, we have $ar_i$ are also relatively prime to $m$, for $i = 1, 2, ..., \varphi(m)$.
>
> If $ar_i \equiv ar_j \pmod m$, then $r_i \equiv r_j \pmod m$, which is possible only when $i = j$.
>
> Hence, all $\varphi(m)$ integers $ar_1, ar_2, ..., ar_{\varphi(m)}$ are relatively prime to $m$ and pairwise incongruent modulo $m$ and is a reduced residue system.

> *Theorem.*{: .thm}
> **[Euler's Theorem]**
> If $m$ is a positive integer and $a$ is an integer with $(a, m) = 1$, then
>
> $$
  a^{\varphi(m)} \equiv 1 \pmod m
  $$
>
> *Proof.*{: .prf}
>
> Similar to the proof of Fermat's Theorem, let $r_1, r_2, ..., r_{\varphi(m)}$ be a reduced residue system modulo $m$.
> We have $ar_1, ar_2, ... ar_{\varphi(m)}$ is also a reduced residue system and is just a reordering of the integers $r_1, r_2, ..., r_{\varphi(m)}$.
>
> Hence,
>
> $$
  ar_1 \cdot ar_2 \cdots ar_{\varphi(m)} \equiv r_1r_2 \cdots r_{\varphi(m)} \pmod m
  $$
>
> As $(r_1r_2...r_{\varphi(m)}, m) = 1$, we have
>
> $$
  a^{\varphi(m)} \equiv 1 \pmod m
  $$

> *Corollary.*{: .cor}
> Similarily if $(a, m) = 1$, then $a^{-1} \equiv a^{\varphi(m)-1} \pmod m$.

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 6
* [Richard E Borcherds _Introduction to number theory_ - Lecture 10](https://youtu.be/fgHEKAdErbU)
