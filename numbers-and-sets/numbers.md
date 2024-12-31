---
layout: base
title: Numbers &#124; Numbers and Sets
---

# Numbers
{: .page-title}

The philosophical goal is to define the "real numbers" rigorously as a set with some operations that satisfies some particular properties, known as _axioms_.
The approach is to have explicit construction of different kinds of "numbers" and prove them they satisfy certain properties (and not satisfying some so we have to continue to extend that).

## Natural Numbers

> *Definition.*{: .def}
> The **natural numbers** $\mathbb{N}$ is defined by _Peano's axioms_.
> which is a set having a special element $0$ and a map $S: \mathbb{N} \to \mathbb{N}$ that maps $n$ to its successor (+1) such that
>
> + $S(n) \not= 0$ for all $n \in \mathbb{N}$.
>
> + $(\forall n, m \in \mathbb{N})\, S(m) = S(n) \implies m = n$.
>
> + For any $A \subseteq \mathbb{N}$, if $0 \in A$ and $n \in A \implies S(n) \in A$, then $A = N$.

The last axiom is the axiom of induction, which implies the following theorem:

> *Theorem.*{: .thm}
> **[Weak Principle of Induction]** Let $P(n)$ be a statement about the natural number $n$. Suppose that
>
> + $P(1)$ is true
>
> + $(\forall n)\,P(n) \implies P(n+1)$
>
> Then $P(n)$ is true for all $n \ge 1$.

A slight variant of the principle of induction is also sometimes useful in proofs.

> *Theorem.*{: .thm}
> **[Strong Principle of Induction]** Let $P(n)$ be a statement about the natural number $n$. Suppose that
>
> + $P(1)$ is true
>
> + $(\forall n \in \mathbb(N))$, if $P(k)$ is true $\forall k \le n$ then $P(k + 1)$ is true
>
> Then $P(n)$ is true for all $n \in N$.

They are disinct in the sense that weak induction is base on succession ($+1$) and strong induction is base on ordering of natural numbers.
Before digging into the well-ordering principle, we need to define what is means to be an order.

> *Definition.*{: .def}
> A **partial order** on a set is a reflexive, [antisymmetric](relations.md#definition-of-antisymmetric) and transitive relation.

> *Definition.*{: .def}
> A **total order** is a partial order where $\forall x \not= y$, exactly one of $xRy$ or $yRx$ holds.
> This means that every two elements must be related.

> *Definition.*{: .def}
> A total order is **well-ordered** if every non-empty subset has a minimal element, i.e.
>
> $$
  S \not = \emptyset \implies \exists m \in S, x < m \implies x \not \in S
  $$

> *Theorem.*{: .thm}
> **[Well-ordering Principle]** $\mathbb{N}$ is well-ordered under the usual order,
> i.e. every non-empty subset of $\mathbb{N}$ has a minimal element.

> *Theorem.*{: .thm}
> Well-ordering principle is equivalent to strong induction.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose $P(k)$ is true $\forall k < n$ implies $P(n)$ is true.
> Assume $P(n)$ is not true for all $n \in \mathbb{N}$, i.e. the set $S = \set{n \in \mathbb{N} : \neg P(n)}$ is non-empty and has a minimal element $m$ by the Well-ordering principle.
> Since $m$ is the minimal counterexample to $P$, $P(k)$ is true $\forall k < m$.
> However, it implies $P(m)$ is true, which is a contradiction.
> Hence, $P(n)$ is true for all $n$.
>
> ($\Leftarrow$) Suppose $S \subseteq \mathbb{N}$ has no minimal element.
> Let $P(n)$ be the statement $n \not \in S$.
> $P(1)$ is true otherwise $1$ is the minimal element in $S$.
> Assume $P(k)$ is true $\forall k < n$, which means $\forall k < n, k \not \in S$.
> $P(n)$ is true otherwise $n$ is the minimal element in $S$.
> By strong induction, $P(n)$ is true for all $n$ and $S$ can only be empty.

By similar technique, we can also show that weak induction is equivalent to well-ordering principle.

We can define recursively addition as

$$
\begin{align*}
n + 0 &= n \\
n + S(m) &= S(n + m)
\end{align*}
$$

and mulitplication as

$$
\begin{align*}
n \times 0 &= 0 \\
n \times S(m) &= n \times m + n
\end{align*}
$$

but subtraction and division is not well-defined, which leads to the following kinds of "numbers".

## Integers

> *Definition.*{: .def}
> The **integers** $\mathbb{Z}$ is obtained from $\mathbb{N}$ by allowing subtraction.
> Formally, $\mathbb{Z}$ is defined to be the equivalence classes of $\mathbb{N} \times \mathbb{N}$ under the relation
>
> $$
  (a, b) \sim (c, d) \iff a + d = b + c
  $$

Intuitively, $(a, b)$ is $a - b$, $a = [(a, 0)]$ and $-a = [(0, a)]$. We define

$$
\begin{align*}
(a, b) + (c, d) &= (a + c, b + d) \\
(a, b) \times (c, d) &= (ac + bd, bd + ad)
\end{align*}
$$

## Rationals

> *Definition.*{: .def}
> The **rationals** $\mathbb{Q}$ is obtained from $\mathbb{Z}$ by allowing division.
> Formally, $\mathbb{Q}$ is defined to be the equivalence classes of $\mathbb{Z} \times \mathbb{N}$ under the relation
>
> $$
  (a, b) \sim (c, d) \iff ad = bc
  $$

Intuitively, $a/b = [(a, b)]$. We define

$$
\begin{align*}
(a, b) + (c, d) &= (ad + bc, bd) \\
(a, b) \times (c, d) &= (ac, bd)
\end{align*}
$$

Algebraically, $\mathbb{Q}$ is a _totally ordered field_.

> *Theorem.*{: .thm}
> The natural ordering of $\mathbb{Q}$ is **dense**,
> i.e. given $x, y \in \mathbb{Q}$ with $x < y$, there is a $z \in \mathbb{Q}$ such that $x < z$ and $z < y$
>
> *Proof.*{: .prf}
>
> Take $z = (x + y) / 2$, we have $z - x = (y - x)/2 \in \mathbb{Q}^{+}$ and $y - z = (y - x)/2 \in \mathbb{Q}^{+}$ as $y - x \in \mathbb{Q}^{+}$.
> Hence, $x < z$ and $z < y$.
>
> It means there is always a rational in between two rationals.

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 1
* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 6](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
