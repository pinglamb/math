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
> $m$ is called the **modulus** of the congruence (plural: _moduli_).

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
> in which $(a, m) = 1$ is also a complete system of residues modulo $m$.
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

The Chinese Remainder Theorem is for solving system of congruences in one variable but multiple moduli, e.g.

$$
\begin{align*}
x &\equiv 1 \pmod 3 \\
x &\equiv 2 \pmod 5 \\
x &\equiv 3 \pmod 7 \\
\end{align*}
$$

> *Theorem.*{: .thm}
> **[Chinese Remainder Theorem]**
> Let $m_1, m_2, ..., m_r$ be pairwise relatively prime positive integers. The system of congruences
>
> $$
  \begin{align*}
  x &\equiv a_1 \pmod{m_1} \\
  x &\equiv a_2 \pmod{m_2} \\
  &\vdots \\
  x &\equiv a_r \pmod{m_r} \\
  \end{align*}
  $$
>
> has a unique solution
>
> $$
  x \equiv a_1M_1y_1 + a_2M_2y_2 + \dots + a_rM_ry_r \pmod M
  $$
>
> where $M = m_1m_2...m_k$, $M_k = m_1m_2...m_{k-1}m_{k+1}...m_r$ and $y_k$ is the inverse of $M_k$ modulo $m_k$.
>
> *Proof.*{: .prf}
>
> For $1 \le k \le r$, $y_k$ exists because $(M_k, m_k) = 1$.
>
> We can see that $x = a_1M_1y_1 + a_2M_2y_2 + \dots + a_rM_ry_r$ satisfies all the $r$ congruences
> because all the terms except $a_kM_ky_k$ are eliminated as $(M_i, m_k) = m_k$ when $i \not = k$.
> By construction, $M_ky_k \equiv 1 \pmod{m_k}$, so $x \equiv a_k \pmod{m_k}$.
>
> Assume $x_0$ and $x_1$ are both solutions, i.e. $m_k \mid (x_0 - x_1)$ for $k = 1, 2, ..., r$.
> As $m_1, m_2, ..., m_r$ are pairwise relatively prime, $M \mid (x_0 - x_1)$ and $x_0 \equiv x_1 \pmod M$ so the solution is unique.

The way to apply C.R.T. is that we have to find all the $M_k$ and $y_k$. Using the system of congruences from the above as example,

$$
\begin{align*}
a_1 &= 1 &\quad M_1 &= 5 \cdot 7 = 35 &\quad y_1 &= (35 \bmod 3)^{-1} = 2 \\
a_2 &= 2 &\quad M_2 &= 3 \cdot 7 = 21 &\quad y_2 &= (21 \bmod 5)^{-1} = 1 \\
a_3 &= 3 &\quad M_3 &= 3 \cdot 5 = 15 &\quad y_3 &= (15 \bmod 7)^{-1} = 1 \\
\end{align*}
$$

so $x \equiv 1 \cdot 35 \cdot 2 + 2 \cdot 21 \cdot 1 + 3 \cdot 15 \cdot 1 \equiv 157 \equiv 52 \pmod{105}$.

## Systems of Linear Congruences

For system of linear congruences with same modolus, e.g.

$$
\begin{align*}
3x + 4y &\equiv 5 \pmod{13} \\
2x + 5y &\equiv 7 \pmod{13}
\end{align*}
$$

As we can do modular arithmetic the same way as normal integer operation, we can apply the same technique to eliminate $y$ by multiplications, i.e.

$$
\begin{align*}
5(3x + 4y) - 4(2x + 5y) &\equiv 5(5) - 4(7) \pmod{13} \\
7x &\equiv -3 \pmod{13}
\end{align*}
$$

which is a linear congruence we can solve, with the answers being $x \equiv 7 \pmod{13}$ and $y \equiv 9 \pmod{13}$.

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 4
