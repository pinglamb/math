---
layout: base
title: Congruences &#124; Numbers and Sets
---

# Congruences
{: .page-title}

> *Definition.*{: .def}
> Let $m$ be a positive integer. For integers $a$ and $b$, $a$ is **congruent** to $b$ modulo $m$ if $m \mid (a-b)$ or $a = b + km$.
> It is written as
>
> $$
  a \equiv b \pmod m
  $$

## Modular Arithmetic

> *Theorem.*{: .thm}
> If $a \equiv b \pmod m$ and $c \equiv d \pmod m$, then
>
> + $a \pm c \equiv b \pm d \pmod m$
>
> + $ac \equiv bd \pmod m$
>
> *Proof.*{: .prf}
>
> Given $a = b + km$ and $c = d + lm$,
>
> + $a + c = b + d + (k + l)m$ and $a - c = b - d + (k - l)m$
>
> + $ac = bd + (bl + dk + klm)m$

> *Theorem.*{: .thm}
> Suppose $d = (c, m)$, then
>
> $$
  ac \equiv bc \pmod m \implies a \equiv b \pmod{m/d}
  $$
>
> *Proof.*{: .prf}
>
> Given $ac - bc = km$, dividing both sides by $d$ we have
>
> $$
  (c/d)(a - b) = k(m/d)
  $$
>
> As $(c/d, m/d) = 1$, $m/d \mid (a - b)$, hence $a \equiv b \pmod{m/d}$.

> *Corollary.*{: .cor}
> If $ac \equiv bc \pmod m$ and $(c, m) = 1$, then $a \equiv b \pmod m$.

> *Theorem.*{: .thm}
> For $k > 0$,
>
> $$
  a \equiv b \pmod m \implies a^k \equiv b^k \pmod m
  $$
>
> *Proof.*{: .prf}
>
> Given $m \mid a - b$,
>
> $$
  a^k - b^k = (a - b)(a^{k-1} + a^{k-2}b + \ldots + ab^{k-2} + b^{k-1})
  $$
>
> Hence, $m \mid (a^k - b^k)$.

> *Theorem.*{: .thm}
> If $a \equiv b \pmod{m_1}, a \equiv b \pmod{m_2}, \ldots, a \equiv b \pmod{m_k}$, then
>
> $$
  a \equiv b \pmod{[m_1, m_2, \ldots, m_k]}
  $$
>
> *Proof.*{: .prf}
>
> If $m_1 \mid (a - b), m_2 \mid (a - b), \ldots, m_k \mid (a - b)$, then $[m_1, m_2, \ldots, m_k] \mid (a - b)$.

> *Corollary.*{: .cor}
> If $a \equiv b \pmod{m_1}, a \equiv b \pmod{m_2}, \ldots, a \equiv b \pmod{m_k}$, and $m_1, m_2, \ldots, m_k$ are pairwise relatively prime, then
>
> $$
  a \equiv b \pmod{m_1m_2 \ldots m_k}
  $$

## Equivalence Relation

> *Theorem.*{: .thm}
> Congruence modulo $m$ is an equivalence relation.
>
> *Proof.*{: .prf}
>
> + [Reflexive] $m \mid a - a$, so $a \equiv a \pmod m$.
>
> + [Symmetric] $a = b + km \iff b = a + (-k)m$, so $a \equiv b \pmod m \iff b \equiv a \pmod m$.
>
> + [Transitive] If $a = b + km$ and $b = c + lm$, then $a = c + (k + l)m$, so $a \equiv b \pmod m \land b \equiv c \pmod m \implies a \equiv c \pmod m$.
>
> Hence, congruence modulo $m$ is an equivalence relation.

> *Definition.*{: .def}
> The **congruence classes** modulo $m$ are the $m$ equivalence classes of the equivalence relation,
> which are mutually congruent modulo $m$ and partition $\mathbb{Z}$.

> *Definition.*{: .def}
> A **complete system of residues** modulo $m$ is a set of integers such that every integer is congruent modulo $m$ to exactly one integer of the set.
>
> Typically, it is the set of all possible remainders from the division algorithm, i.e.
>
> $$
  \set{0, 1, 2, ..., m - 1}
  $$


## Linear Congruences

## Chinese Remainder Theorem

## Polynomial Congruences

## Systems of Linear Congruences

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 4
