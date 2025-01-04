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
> The union of any finite collection of countable sets is countable.
>
> *Proof.*{: .prf}
>

> *Corollary.*{: .cor}
> The set of integers $\mathbb{Z}$ is countable.

> *Theorem.*{: .thm}
> The Cartesian product of any finite number of countable sets is countable.

> *Theorem.*{: .thm}
> The union of a countable set of countable sets is countable.

> *Theorem.*{: .thm}
> The set of rational numbers $\mathbb{Q}$ is countable.

## Uncountable Sets

## References

* A G Hamilton _Numbers, sets and axioms_, 1982 - Chapter 2
