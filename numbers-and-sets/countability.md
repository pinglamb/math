---
layout: base
title: Countability &#124; Numbers and Sets
---

# Countability
{: .page-title}

## Countable Sets

> *Definition.*{: .def}
> A non-empty set $A$ is **finite** if there is a positive integer $n$ and a bijection $f: \set{1,...,n} \to A$.
> Otherwise it is **infinite**. The empty set is by convention taken to be finite.

> *Definition.*{: .def}
> Two sets $A$ and $B$ are **equinumerous** if there is a bijection from $A$ to $B$, denoted by $A \sim B$.

> *Theorem.*{: .thm}
> $~$ is an equivalence relation.
>
> *Proof.*{: .prf}
>
> + The identity function is a bijection from $A$ to $A$.
>
> + If $f: A \to B$ is a bijection, then $f^{-1}: B \to A$ exists and is a bijection.
>
> + If $f: A \to B$ and $g: B \to C$ are bijections, $g \circ f: A \to C$ is a bijection.

An infinite set can be equinumerous with a proper subset of itself,
e.g. $\mathbb{N} \sim 2\mathbb{N}$ with the bijection $f: \mathbb{N} \to 2\mathbb{N}$ given by $f(n) = 2n$.
It is clearly impossible for finite sets so this property is propsed as the definition of infiniteness.

Obviously, a finite set can be counted, and we shall extend the notion of counting to infinite set as follows.

> *Definition.*{: .def}
> A set $A$ is **countable** if either it is finite or it is infinite and $\mathbb{N} \sim A$.

This definition is cumbersome to apply will lead to two results yield more convenient criteria.

> *Definition.*{: .def}
> For sets $A$ and $B$, $A$ is **dominated** by $B$ if there is an injection from $A$ to $B$, denoted by $A \preceq B$.

> *Theorem.*{: .thm}
> A set $A$ is countable iff there is an injection $A \to \mathbb{N}$, i.e. $A \preceq \mathbb{N}$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose $A$ is countable. If $A$ is finite, $f: A \to \mathbb{N}$ defined by $f(a_k) = k$ is an injection.
> If $A$ is infinite, by defintion, there is a bijection $g: \mathbb{N} \to A$, and the inverse is an injection from $A$ to $\mathbb{N}$.
>
> ($\Leftarrow$) If there is an injection $h: A \to \mathbb{N}$, then $h(A)$ is a subset of $\mathbb{N}$.
> All subsets like $h(A)$ is countable because either $h(A)$ is finite,
> or if it is infinite, we can count it by listing all elements of $\mathbb{N}$ in order and deleting elements in $\mathbb{N} \setminus h(A)$ as we proceed.
> As $h: A \to h(A)$ is a bijection, either $h(A)$ is finite, $A$ must be finite and countable,
> or $h(A)$ is infinite and $A \sim h(A)$ and $h(A) \sim \mathbb{N}$, which implies $A \sim \mathbb{N}$ and $A$ is countable.

> *Corollary.*{: .cor}
> A non-empty set $A$ is countable iff there is a surjection $\mathbb{N} \to A$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $A$ is countable, there is an injection $f: A \to \mathbb{N}$, then $f: A \to f(A)$ is a bijection.
> So, the function $g: \mathbb{N} \to A$ defined by
>
> $$
  g(n) = \begin{cases}
  f^{-1}(n) & \text{if } n \in f(A) \\
  a_0 & \text{if } n \not \in f(A) \\
  \end{cases}
  $$
>
> is a surjection.
>
> ($\Leftarrow$) If there is an surjection $g: \mathbb{N} \to A$, then the function $f: A \to \mathbb{N}$ defined by
>
> $$
  f(a) = \min(n) \text{ such that } g(n) = a
  $$
>
> is an injection.

The above theorem provides a necessary and sufficient condition for countability.
Here are proofs that certain familiar sets are countable.

> *Theorem.*{: .thm}
> The union of any finite number of countable sets is countable.
>
> *Proof.*{: .prf}
>
> Let $A$ and $B$ be two countable sets, then there are surjections $f: \mathbb{N} \to A$ and $g: \mathbb{N} \to B$,
> the function $h: \mathbb{N} \to A \cup B$ defined by
>
> $$
  h(n) = \begin{cases}
  f(k) & \text{if } n = 2k + 1 \\
  g(k) & \text{if } n = 2k \\
  \end{cases}
  $$
>
> is a surjection. So $A \cup B$ is countable.
>
> Assume $A_1, A_2, ..., A_k$ are countable sets where $A_1 \cup A_2 \cup \cdots \cup A_k$ is countable.
> Let $A_{k+1}$ be another countable set,
> then $A_1 \cup \cdots \cup A_k \cup A_{k+1} = (A_1 \cup \cdots \cup A_k) \cup A_{k+1}$ is a union of two countable sets and hence is countable.
> By induction, any finite number of countable sets is countable.

> *Corollary.*{: .cor}
> The set of integers $\mathbb{Z}$ is countable.
>
> *Proof.*{: .prf}
>
> $\mathbb{Z}^{+}$ is a subset of $\mathbb{N}$ so it is countable.
> $\mathbb{Z}^{-} \sim \mathbb{Z}^{+}$ by the bijection $n \mapsto -n$ so $\mathbb{Z}^{-}$ is countable.
> $\set{0}$ is finite so it is countable.
>
> Hence, $\mathbb{Z} = \mathbb{Z}^{+} \cup \set{0} \cup \mathbb{Z}^{-}$ is countable.

Another useful techinque on constructing the injection is the use of product of primes or powers of primes.
We can also use it to construct surjection by using the fact that factorization of $n$ into product of primes is unique up to order.
The following demonstrates the use of them.

> *Theorem.*{: .thm}
> The Cartesian product of any finite number of countable sets is countable.
>
> *Proof.*{: .prf}
>
> Let $A$ and $B$ be two countable sets, then there are injections $f: A \to \mathbb{N}$ and $g: B \to \mathbb{N}$,
> the function $h: A \times B \to \mathbb{N}$ defined by
>
> $$
  h(a, b) = 2^{f(a)} \cdot 3^{g(b)}
  $$
>
> is an injection. So $A \times B$ is countable.
>
> Similarily, let $A_1, A_2, ..., A_n$ be countable sets and $p_1, p_2, ..., p_n$ be prime numbers in order,
> then the function $f: A_1 \times \cdots \times A_n \to \mathbb{N}$ defined by $f(a_1, a_2, ..., a_n) = p_1^{f_1(a_1)}p_2^{f_2(a_2)}...p_n^{f_n(a_n)}$ is an injection.
> Hence, the Cartesian product of any finite number of countable sets is countable.

> *Theorem.*{: .thm}
> The union of a countable set of countable sets is countable.
>
> *Proof.*{: .prf}
>
> The case of finite collection of countable sets is countable has been proved above.
>
> Let $A_0, A_1, ...$ be countable sets, to label the elements, we need two indices, i.e.
>
> $$
  \begin{align*}
  A_0 &= \set{a_{00}, a_{01}, ...} \\
  A_1 &= \set{a_{10}, a_{11}, ...} \\
  &\vdots
  \end{align*}
  $$
>
> Let $f_1, f_2, ...$ be the corresponding surjections and $A = \bigcup A_i$,
> the function $f: \mathbb{N} \to A$ defined by
>
> $$
  f(n) = \begin{cases}
  f_0(0) & \text{if } n = 0 \\
  f_k(l) & \text{if } n = 2^k \cdot 3^l \cdot m
  \end{cases}
  $$
>
> is a surjection. It is becasue every $n$ can be factorized uniquely as $2^k \cdot 3^l \cdot m$ where $m$ is not divisible by $2, 3$ and it loops through all the indices $(k, l)$ (not uniquely though).
>
> Hence, the union of countable set of countable sets is countable.

> *Theorem.*{: .thm}
> The set of rational numbers $\mathbb{Q}$ is countable.
>
> *Proof.*{: .prf}
>
> Given $x \in \mathbb{Q}^{+}$, there exist a unique pair of positive integers $p, q$ such that $x = p/q$ where $(p, q) = 1$.
> Consider the function $f: \mathbb{Q}^{+} to \mathbb{N}$ defined by $f(x) = 2^p \cdot 3^q$, it is an injection so $\mathbb{Q}^{+}$ is countable.
> Similarily, $\mathbb{Q}^{-} \sim \mathbb{Q}^{+}$ by the bijection $x \mapsto -x$ and $\set{0}$ is finite.
> Hence, $\mathbb{Q} = \mathbb{Q}^{+} \cup \set{0} \cup \mathbb{Q}^{-}$ is countable.
>
> A less formal way to count positive rational numbers is by listing them as
>
> $$
  \begin{align*}
  &{1 \over 1}, {1 \over 2}, {1 \over 3}, ..., \\
  &{2 \over 1}, {2 \over 2}, {2 \over 3}, ..., \\
  &{3 \over 1}, {3 \over 2}, {3 \over 3}, ..., \\
  &\; \vdots
  \end{align*}
  $$
>
> and count them diagonally as ${1 \over 1}, {1 \over 2}, {2 \over 1}, {3 \over 1}, {2 \over 2}, \cdots$.

## Uncountable Sets

## References

* A G Hamilton _Numbers, sets and axioms_, 1982 - Chapter 2
