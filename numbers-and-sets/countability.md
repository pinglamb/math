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
> A set $A$ is **countable** if either it is finite or it is infinite in which $\mathbb{N} \to A$.

This definition is cumbersome to apply will lead to two results yield more convenient criteria.

> *Definition.*{: .def}
> For sets $A$ and $B$, $A$ is **dominated** by $B$ if there is an injection from $A$ to $B$, denoted by $A \preceq B$.

> *Theorem.*{: .thm}
> A set $A$ is countable iff there is an injection $A \to \mathbb{N}$, i.e. $A \preceq \mathbb{N}$.
>
> *Proof.*{: .prf}
>

> *Corollary.*{: .cor}
> A non-empty set $A$ is countable iff there is a surjection $\mathbb{N} \to A$.
>
> *Proof.*{: .prf}
>

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
