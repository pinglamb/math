---
layout: base
title: Sets &#124; Numbers and Sets
---

# Functions
{: .page-title}

> *Definition.*{: .def}
> Given $X, Y$ be two sets, a function $f: X \to Y$ maps $x \in X$ to **exactly one** $y \in Y$, denoted by $x \mapsto y$.
> $X$ is called the **domain** of $f$ and $Y$ is called the **codomain** of $f$.

## Composition of Functions

> *Definition.*{: .def}
> Functions can be composed by by applying one after another,
> e.g. let $f: X \to Y$ and $g: Y \to Z$ be two functions,
> then $g \circ f: X \to Z$ is a function with $(g \circ f)(x) = g(f(x))$.

> *Lemma.*{: .lem}
> Function composition is _associative_.
>
> *Proof.*{: .prf}
>
> We have
>
> $$
  (h \circ (g \circ f))(x) = h(g(f(x))) = (h \circ g)(f(x)) = ((h \circ g) \circ f)(x)
  $$

It is NOT commutative however, e.g. $f(x) = x + 1$, $g(x) = 2x$, $(g \circ f)(x) = 2x + 2$ but $(f \circ g)(x) = 2x + 1$.

## Injection, Surjection and Bijection

> *Definition.*{: .def}
> A function $f$ is **injective** if it maps everything in $Y$ **at most once**, i.e. $\forall x, y \in X$
>
> $$
  f(x) = f(y) \implies x = y
  $$

> *Definition.*{: .def}
> A function $f$ is **surjective** if it maps everything in $Y$ **at least once**, i.e.
>
> $$
  (\forall y \in Y, \exists x \in X) \, f(x) = y
  $$

> *Definition.*{: .def}
> A function $f$ is **bijective** if it is both injective and surjective, i.e. it hits everything **exactly once**.

> *Lemma.*{: .lem}
> The composition of bijections is a bijection.
>
> *Proof.*{: .prf}
>

## Inverses

> *Definition.*{: .def}
> The **identity map** $\text{id}_A : A \to A$ is defined as the map $a \mapsto a$.

> *Definition.*{: .def}
> Given $f: A \to B$, a **left inverse** of $f$ is a function $g: B \to A$ such that $g \circ f = \text{id}_A$.

> *Definition.*{: .def}
> Given $f: A \to B$, a **right inverse** of $f$ is a function $g: B \to A$ such that $f \circ g = \text{id}_B$.

> *Lemma.*{: .lem}
> The left inverse of $f$ exists iff $f$ is injective.
>
> *Proof.*{: .prf}
>

> *Lemma.*{: .lem}
> The right inverse of $f$ exists iff $f$ is surjective.
>
> *Proof.*{: .prf}
>

> *Definition.*{: .def}
> An **inverse** of $f$ is a function that is both a left inverse and a right inverse, denoted by $f^{-1}: B \to A$,
> i.e. $f^{-1} \circ f = \text{id}_A$ and $f \circ f^{-1} = \text{id}_B$.
> We say $f$ is **invertible**.

> *Lemma.*{: .lem}
> $f$ is invertible iff $f$ is bijective.
>
> *Proof.*{: .prf}
>
> Base on the above, the left and right inverses of $f$ exists iff $f$ is injective and surjective and hence bijective.

## References

* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 2](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 1](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
