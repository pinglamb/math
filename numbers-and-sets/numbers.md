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
> i.e. given $x, y \in \mathbb{Q}$ with $x < y$, there is a $z \in \mathbb{Q}$ such that $x < z$ and $z < y$.
>
> *Proof.*{: .prf}
>
> Take $z = (x + y) / 2$, we have $z - x = (y - x)/2 \in \mathbb{Q}^{+}$ and $y - z = (y - x)/2 \in \mathbb{Q}^{+}$ as $y - x \in \mathbb{Q}^{+}$.
> Hence, $x < z$ and $z < y$.

It means there is always a rational in between two rationals.

> *Theorem.*{: .thm}
> The natural ordering of $\mathbb{Q}$ is **Archimedean**,
> i.e. given $x, y \in \mathbb{Q}^{+}$, there is a positive integer $n$ such that $y < nx$.
>
> *Proof.*{: .prf}
>
> Let $x = a/b, y = c/d$ with $a, b, c, d \in \mathbb{Z}$ and $b \not= 0, d \not= 0$.
> As $x, y \in \mathbb{Q}^{+}$, we can assume that $a, b, c, d \in \mathbb{Z}^{+}$.
> We require $n/1 \in \mathbb{Q}$ such that
>
> $$
  c/d < (n/1)(a/b)
  $$
>
> which implies
>
> $$
  (nad - bc)/bd \in \mathbb{Q}^{+}
  $$
>
> As we can write $bc = q(ad) + r$ where $q \in \mathbb{N}$ and $0 \le r < ad$, we have
>
> $$
  bc < qad + ad = (q + 1)ad
  $$
>
> Hence, if $n = q + 1$, then $y < nx$.

It means there is no infinitely large or infinitely small element in $\mathbb{Q}$.

However, the set of rational numbers doesn't contain all the numbers we know, for example:

> *Theorem.*{: .thm}
> There is no $q \in \mathbb{Q}$ with $q^2 = 2$.
>
> *Proof.*{: .prf}
>
> Suppose $(a/b)^2 = 2$, where $b$ is chosen as small as possible.
> We have $a^2 = 2b^2$, so $a$ is even and $a = 2a'$.
> We then have $2a'^2 = b^2$, so $b$ is even and $b = 2b'$.
> Thus, $a/b = a'/b'$ and we have found a smaller $b'$ which contradicts with the assumption.

> *Theorem.*{: .thm}
> The Euler's number $e$ is irrational.
>
> *Proof.*{: .prf}
>
> By definition,
>
> $$
  e = 1 + {1 \over 1!} + {1 \over 2!} + ...
  $$
>
> Suppose $e = a/b$, with $b \ge 2$ as $e$ is not an integer. Then $b!e \in \mathbb{N}$ and
>
> $$
  b!e = b! + {b! \over 1!} + ... + {b! \over b!} + {b! \over (b+1)!} + {b! \over (b+2)!} + ...
  $$
>
> The sum of the terms until $b!/b!$ is a positive integer, and the sum of remaining terms
>
> $$
  \begin{align*}
  {b! \over (b+1)!} + {b! \over (b+2)!} + \cdots &= {1 \over b+1} + {1 \over (b+1)(b+2)} + {1 \over (b+1)(b+2)(b+3)} + \cdots \\
  &< {1 \over b+1} + {1 \over (b+1)^2} + {1 \over (b+1)^3} + \cdots \\
  &= {1 \over b+1}\left({1 \over 1 - 1/(b+1)}\right) = {1 \over b} < 1
  \end{align*}
  $$
>
> is not an integer, which is a contradiction.

The general limitation of $\mathbb{Q}$ is that convergent sequences may not have limits.
Another way of expressing this is that subsets of $\mathbb{Q}$ which are bounded above
(i.e. there is a rational number greater than every member of the set), need not have a least upper bounds in $\mathbb{Q}$.
It leads to the construction of the set of real numbers.

## Real Numbers

> *Definition.*{: .def}
> A sequence $(x_n) = x_1, x_2, x_3, ...$ of rational numbers is a **Cauchy sequence** if $x_m - x_n \to 0$ as $m, n \to \infty$,
> i.e., given any $\varepsilon \in \mathbb{Q}^{+}$, there exists $N \in \mathbb{N}$ such that
>
> $$
  \vert x_m -x_n \vert < \varepsilon, \forall m, n > N
  $$

> *Definition.*{: .def}
> Two Cauchy sequences $(a_n)$ and $(b_n)$ are equivalent, denoted by $(a_n) \approx (b_n)$,
> if the sequence whose $n$th term is $a_n - b_n$ converges to zero,
> i.e. given any $\varepsilon \in \mathbb{Q}^{+}$, there exists $N \in \mathbb{N}$ such that
>
> $$
  \vert a_n - b_n \vert < \varepsilon, \forall n \in N
  $$

> *Theorem.*{: .thm}
> The relation $\approx$ is an equivalence relation on the set of all Cauchy sequences in $\mathbb{Q}$.
>
> *Proof.*{: .prf}
>
> $\approx$ is reflexive as $\vert a_n - a_n \vert = 0$ and symmetric as $\vert a_n - b_n \vert = \vert b_n - a_n \vert$.
>
> Suppose $(a_n) \approx (b_n)$ and $(b_n) \approx (c_n)$ and let $x_n = a_n - b_n$ and $y_n = b_n - c_n$.
> As $x_n$ and $y_n$ are converging to zero, $x_n + y_n = a_n - c_n$ is converging to zero so $(a_n) \approx (c_n)$ and $\approx$ is transitive.

> *Definition.*{: .def}
> The **real numbers** $\mathbb{R}$ is the set of all the equivalence classes of Cauchy sequences in $\mathbb{Q}$ under the relation $\approx$.

Addition and multiplication of real numbers are defined by

$$
[x_n] + [y_n] = [x_n + y_n]
$$

and

$$
[x_n] \times [y_n] = [x_ny_n]
$$

The proofs regarding the algebraic and order properties of real numbers are omitted and
we jump straight to the most important property of real numbers that rational numbers don't have:

> *Theorem.*{: .thm}
> Given any non-empty subset of $A$ of $\mathbb{R}$ which is bounded above,
> there is a **least upper bound** (or **supremum** in $\mathbb{R}$ for $A$, denoted by $\sup A$.

This theorem can be used to prove the existence of "missing" numbers in $\mathbb{Q}$.

> *Theorem.*{: .thm}
> There exists $x \in \mathbb{R}$ such that $x^2 = 2$.
>
> *Proof.*{: .prf}
>
> Let $A = \set{a \in \mathbb{R} : a^2 \le 2}$. $1 \in A$ so $A \not = \emptyset$.
> If $a \ge 2$, $a^2 \ge 4$, so $A$ is bounded above by $2$ and the supremum $s = \sup A$ exists in which $1 \le s \le 2$.
>
> By trichotomy, $s^2 < 2$, $s^2 = 2$ or $s^2 > 2$.
>
> Suppose $s^2 < 2$. Let $0 < \delta < (2 - s^2)/5 < 1$, we have $\delta^2 < \delta$ and
>
> $$
  (s + \delta)^2 = s^2 + 2s\delta + \delta^2 \le s^2 + 5\delta < 2
  $$
>
> So $s + \delta > s \in A$, contradicting with the fact that $s$ is the supremum.
>
> Suppose $x^2 > 2$. Let $0 < \delta < (s^2 - 2)/4 < 1$, we have
>
> $$
  (s - \delta)^2 = s^2 - 2s\delta + \delta^2 \ge s^2 - 4\delta > 2
  $$
>
> So $s - \delta < s$ is a upper bound, contradicting with the fact that $s$ is the supremum.
>
> Hence, it is only possible that $s^2 = 2$.

## Algebraic Numbers

> *Definition.*{: .def}
> An **algebraic number** is a root of a polynomial with integer/rational coefficients.

> *Definition.*{: .def}
> A **transcendental number** is a number which is not algebraic.

> *Theorem.*{: .thm}
> All rational numbers are algebraic.
>
> *Proof.*{: .prf}
>
> Let $q = a/b$, it is the root of equation $bx - a = 0$.

> *Theorem.*{: .thm}
> $\sqrt{2}$ is algebraic.
>
> *Proof.*{: .prf}
>
> $\sqrt{2}$ is irrational but it is the root of $x^2 - 2 = 0$.

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 1
* A G Hamilton _Numbers, sets and axioms_, 1982 - Chapter 1
* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 6](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
