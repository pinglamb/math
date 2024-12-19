---
layout: base
title: Product Groups &#124; Groups
---

# Product Groups
{: .page-title}

Groups can be combined to form new product group or decomposed to simpler groups for analysis.

> *Theorem.*{: .thm}
> Given $G_1$ and $G_2$ are groups, the product $G_1 \times G_2$ is a group under operation
>
> $$
  (a_1, a_2) \ast (b_1, b_2) = (a_1 \ast_1 b_1, a_2 \ast_2 b_2)
  $$
>
> where $a_1, b_1 \in G_1$ and $a_2, b_2 \in G_2$.
>
> *Proof.*{: .prf}
>
> 0\. As $c_1 = a_1 \ast_1 b_1 \in G_1$ and $c_2 = a_2 \ast_2 b_2 \in G_2$, $(c_1, c_2) \in G_1 \times G_2$ and is closed.
>
> 1\. $(e_1, e_2)$ is the identity element
>
> 2\. $(a^{-1}, b^{-1})$ is the inverse.
>
> 3\. $G_1 \times G_2$ is associative as
>
> $$
  \begin{align*}
  ((a_1, a_2) \ast (b_1, b_2)) \ast (c_1, c_2) &= ((a_1 \ast_1 b_1) \ast_1 c_1, (a_2 \ast_2 b_2) \ast_2 c_2) \\
  &= (a_1 \ast_1 (b_1 \ast_1 c_1), a_2 \ast_2 (b_2 \ast_2 c_2)) \\
  &= (a_1, a_2) \ast ((b_1, b_2) \ast (c_1, c_2))
  \end{align*}
  $$
>
> Hence, $G_1 \times G_2$ is a group.

## Direct Product Theorem

In order to check if a group is direct product of two groups, we have the following conditions:

> *Theorem.*{: .thm}
> Let $H_1, H_2 \le G$ such that
>
> 1. $H_1 \cap H_2 = \set{e}$
>
> 2. $\forall a_1 \in H_1$ and $\forall a_2 \in H_2$, $a_1a_2 = a_2a_1$
>
> 3. $\forall a \in G$, $\exists a_1 \in H_1$ and $\exists a_2 \in H_2$, $a = a_1a_2$
>
> Then $G \cong H_1 \times H_2$.
>
> *Proof.*{: .prf}
>
> Let $f: H_1 \times H_2 \to G$ defined by $f((a_1, a_2)) = a_1a_2$. $G \cong H_1 \times H_2$ if $f$ is an isomorphism.
>
> By (2),
>
> $$
  f((a_1, a_2)(b_1, b_2)) = f((a_1b_1, a_2b_2)) = a_1b_1a_2b_2 = a_1a_2b_1b_2 = f((a_1, a_2))f((b_1, b_2))
  $$
>
> and hence $f$ is a homomorphism.
>
> By (3), $f$ is surjective.
>
> When $f((a_1, a_2)) = a_1a_2 = e$, $a_2 = a_1^{-1}$. By (1), it is only possible if $a_1 = a_2 = e$. Hence, $\ker f = \set{(e, e)}$ and $f$ is injective.
>
> Therefore, $f$ is a bijection and $G \cong H_1 \times H_2$.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12.7
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 1](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
