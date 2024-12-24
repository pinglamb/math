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

## Image and Pre-image

> *Definition.*{: .def}
> Given $f: X \to Y$ and $A \subseteq X$, the **image** of $A$ under $f$ is defined by
>
> $$
  f(A) = \set{f(a) : a \in A} \subseteq Y
  $$
>
> Hence, $f$ is surjective if $f(X) = Y$.

> *Definition.*{: .def}
> Given $f: X \to Y$ and $B \subseteq Y$, the **pre-image** of $B$ under $f$ is defined by
>
> $$
  f^{-1}(B) = \set{x \in X : f(x) \in B} \subseteq X
  $$

The image and pre-image is associated with a specific set, which is different from domain and codomain which is part of the function definition.

## Inverses

> *Definition.*{: .def}
> The **identity map** $\text{id}_X : X \to X$ is defined as the map $x \mapsto x$.

> *Definition.*{: .def}
> Given $f: X \to Y$, a **left inverse** of $f$ is a function $g: Y \to X$ such that $g \circ f = \text{id}_X$.

> *Definition.*{: .def}
> Given $f: X \to Y$, a **right inverse** of $f$ is a function $g: Y \to X$ such that $f \circ g = \text{id}_Y$.

> *Definition.*{: .def}
> An **inverse** of $f$ is a function that is both a left inverse and a right inverse, denoted by $f^{-1}: Y \to X$,
> i.e. $f^{-1} \circ f = \text{id}_X$ and $f \circ f^{-1} = \text{id}_Y$.
> We say $f$ is **invertible**.

> *Lemma.*{: .lem}
> The left inverse of $f$ exists iff $f$ is injective.
>
> *Proof.*{: .prf}
>
> ($\Leftarrow$) If $f$ has left inverse $g$, for $f(x) = f(y) \implies g(f(x)) = g(f(y)) \implies x = y$.
> Therefore, $f$ is injective.
>
> ($\Rightarrow$) If $f$ is injective, we can construct a $g: Y \to X$ defined as
>
> $$
  g = \begin{cases}
  g(y) = x & \text{if } y \in f(X), \text{where } f(x) = y \\
  g(y) = \text{anything} & \text{otherwise}
  \end{cases}
  $$
>
> $g$ is well defined only if $f$ is injective and is the left inverse of $f$.

> *Lemma.*{: .lem}
> The right inverse of $f$ exists iff $f$ is surjective.
>
> *Proof.*{: .prf}
>
> ($\Leftarrow$) If $f$ has right inverse $g$, we have $f(g(Y)) = \text{id}_Y(Y) = Y$.
> Therefore, $f$ is surjective.
>
> ($\Rightarrow$) If $f$ is surjective, we can construct a $g$ such that for each $y \in Y$ with $f(x) = y$, we have $g(y) = x$, which is the right inverse of $f$.

> *Lemma.*{: .lem}
> $f$ is invertible iff $f$ is bijective.
>
> *Proof.*{: .prf}
>
> Base on the above, the left and right inverses of $f$ exists iff $f$ is injective and surjective and hence bijective.

> *Lemma.*{: .lem}
> The inverse $f^{-1}$ of $f$ is bijective.
>
> *Proof.*{: .prf}
>
> From the definition we can see that $f$ is the inverse of $f^{-1}$,
> so $f^{-1}$ is also invertible and hence is bijective.

> *Lemma.*{: .lem}
> The composition of bijections is a bijection.
>
> *Proof.*{: .prf}
>
> Given $f: X \to Y$ and $g: Y \to Z$ which are both bijective, as composition of functions is associative, we have
>
> $$
  \begin{align*}
  (f^{-1}g^{-1})(gf) = f^{-1}f &= \text{id}_X \\
  (gf)(f^{-1}g^{-1}) = g^{-1}g &= \text{id}_Z
  \end{align*}
  $$
>
> So $f^{-1}g^{-1}$ is the inverse of the composition $fg$ and hence $fg$ is invertible and bijective.

## References

* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 2](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 1](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
