---
layout: base
title: Congruences &#124; Numbers and Sets
---

# Congruences
{: .page-title}

> *Definition.*{: .def}
> Let $m$ be a positive integer. For integers $a$ and $b$, $a$ is **congruent** to $b$ modulo $m$, denoted by
>
> $$
  a \equiv b \pmod m
  $$
>
> if $m \mid (a-b)$ or equivalently $a = b + km$.

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

## Complete System of Residues

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

> *Lemma.*{: .lem}
> A set of $m$ incongruent integers modulo $m$ forms a complete system of residues modulo $m$.
>
> *Proof.*{: .prf}
>
> Assume it is not a complete system of residues modulo $m$, then there is an integer $a$ such that it is not congruent to any integer in the set.
> It is impossible as there can only be $m$ possible remainders when dividing $m$, thus $a$ has to have the same remainder as one of the integer when dividing $m$ and congruent to it.
>
> It means if we can show that a set of $m$ integers are pairwise incongruent, then it is a complete system of residues.

> *Theorem.*{: .thm}
> If $r_1, r_2, \ldots, r_m$ is a complete system of residues modulo $m$, then
>
> $$
  ar_1 + b, ar_2 + b, \ldots, ar_m + b
  $$
>
> in which $(a, m) = 1$  is a complete system of residues modulo $m$.
>
> *Proof.*{: .prf}
>
> For any $0 < i, j \le m$,
>
> $$
  \begin{align*}
  ar_i + b &\equiv ar_j + b &\pmod m \\
  ar_i &\equiv ar_j &\pmod m \\
  r_i &\equiv r_j &\pmod m \\
  \end{align*}
  $$
>
> which is possible only if $i = j$.
>
> Hence, all $m$ integers $ar_k + b$ are pairwise incongruent and forms a complete system of residues modulo $m$.

## Linear Congruences

> *Definition.*{: .def}
> A **linear congruence** in one variable is a congruence of the form
>
> $$
  ax \equiv b \pmod m
  $$
>
> where $x$ is an unknown integer.

> *Definition.*{: .def}
> The **modular inverse** of $a$ modulo $m$ is the integer solution $x$ of $ax \equiv 1 \pmod m$.

> *Theorem.*{: .thm}
> An integer $a$ has an inverse modulo $m$ iff $(a, m) = 1$.
> The inverse is unique if it exists.
>
> *Proof.*{: .prf}
>
> ($\Leftarrow$) If $ax \equiv 1 \pmod m$ has a solution $x \equiv b \pmod m$, then $ab - my = 1$ and hence $(a, m) = 1$ as $ab - my$ is a linear combination of $a$ and $m$.
>
> ($\Rightarrow$) If $(a, m) = 1$, by Euclid Algorithm, we can derive the linear combination $ab - my = 1$ and hence $x \equiv b \pmod m$ is the inverse.
>
> Suppose $x = b$ is one of the solution for $x$ of the linear diophantine equation $ax + my = 1$.
> As $(a, m) = 1$, the general solution for $x = b + (m/1)k$ which implies $x \equiv b \pmod m$ is the unique solution.

> *Corollary.*{: .cor}
> If $(a, m) = 1$, the solution of $ax \equiv b \pmod m$ is unique, namely $x \equiv a^{-1}b \pmod m$.

> *Theorem.*{: .thm}
> Suppose $ax \equiv b \pmod m$ with $(a, m) = d$.
> If $d \not \mid b$, the congruence has no solution.
> If $d \mid b$, the congruence has exactly $d$ solutions, namely
>
> $$
  x \equiv (a/d)^{-1}(b/d) + (m/d)k \pmod m
  $$
>
> with $k = 0, 1, ..., d - 1$.
>
> *Proof.*{: .prf}
>
> The linear diophantine equation $ax - my = b$ has no solution if $(a, m) \not \mid b$.
>
> As $(a/d, m/d) = 1$, the congruence $(a/d)x \equiv (b/d) \pmod{m/d}$ has a unique solution $x = (a/d)^{-1}(b/d) \pmod{m/d}$.
> It is still a solution to the original congruence by adding multiples of $m/d$, and there are exactly $d$ of them modulo $m$.

## Chinese Remainder Theorem

## Systems of Linear Congruences

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 4
