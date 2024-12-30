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

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 6
* [Richard E Borcherds _Introduction to number theory_ - Lecture 10](https://youtu.be/fgHEKAdErbU