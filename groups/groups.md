---
layout: base
title: Groups &#124; Groups
---

# Groups

## Concrete Definition

A group is the set of symmetries of something,
and symmetry of something is just a way of mapping something to itself preserving all the structures.

For example, consider the symmetries of an equilateral triangles.

![Equilateral Triangle](../images/equilateral-triangle.png)

If we limit ourselves to preserve everything, we would only be allowed to do nothing.
When studying the symmetries of the equilateral triangle, we only care about how the resultant objects look,
but don't care about where the individual vertices went.
Hence, we have six symmetries: three rotations (by $0^\circ, 120^\circ, 240^\circ$) and three reflections along the above axes.
These six form the underlying set of the group of symmetries.
With that, we can then define the operation being the combination of two symmetries to give a new symmetry,
naturally meaning to do one after another, e.g. combining two $120^\circ$ rotation to get a $240^\circ$ rotation.

First of all, the new symmetry we got after combining any two symmetries must be the same as one of the symmetry in the set.
We say the group is "closed" with respect to the operation.

Secondly, we must have a "do nothing" symmetry, which when combined with another symmetry, the other symmetry is unchanged.
It is called the identity element, normally named as $1, 0$ or $e$.

Thirdly, given a symmetry, we should have the reverse symmetry, which when combined the two together,
we will end up "doing nothing", i.e. getting the identity element.
It is called the inverse and normally named as $a^{-1}$.

Finally, let $\ast$ denote the group operation, given three symmetries, we can combine them, one after another, i.e. $$x \ast y \ast z$$.
There are two ways to combine them, which are $(x \ast y) \ast z$ or $x \ast (y \ast z)$.
However, intuitively they should yield the same result as we are always applying $x$ after $y$ after $z$,
we have the associative rule $(x \ast y) \ast z = x \ast (y \ast z)$.

With the above, we can define the axioms of a group.

## Axioms

**[Definition of binary operation]** A (binary) operation is a ways of combining two elements to get a new element.
Formally, it is a map $\ast: S \times S \to S$.

**[Definition of Group]** A group is a set $G$ with a binary operation $\ast$ satifying the following axioms:

0\. **[Closure]** For all $a, b \in G$, we have

$$
a \ast b \in G
$$

1\. **[Identity]** There is a unique $e \in G$ such that for all $a \in G$, we have

$$
a \ast e = e \ast a = a
$$

2\. **[Inverse]** For all $a \in G$, there is some $a^{-1} \in G$ such that

$$
a^{-1} \ast a = a \ast a^{-1} = e
$$

3\. **[Associativity]** For all $a, b, c \in G$, we have

$$
(a \ast b) \ast c = a \ast (b \ast c)
$$

Technically, the closure axiom is always true by the definition of binary operation $\ast$ so sometimes we will just omit it.
However, in practice it is something we might have to check to make sure it is true.

The identity axiom can be replaced with a weaker statement that there exists $e \in G$ such that $a \ast e = e \ast a = a$ for all $a \in G$ and from that we will see $e$ is necessarily unique.
Hence, in the proof of a group, we only need to show the existence of such $e$ without the need to show such $e$ is unique.

For the inverse axiom to be unambigious, we have to state the uniqueness of $e$ in the identity axiom.
On the other hand, the notation $a^{-1}$ can only be unambigious if the inverse of $a$ is unique.

To conclude, we dervied the abstract notion of a group from its concrete notion by taking the combination of symmetries as the binary operation.
Conversely, by Cayley's Theorem, we can show that these are the only axioms we need for a concrete group.
Also, with this abstract definition, we can already study lots of properties about groups.

## Properties of Groups

### Uniqueness of Identity
