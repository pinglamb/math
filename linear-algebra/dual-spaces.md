---
layout: base
title: Dual Spaces &#124; Linear Algebra
---

# Dual Spaces
{: .page-title}

The other way to construct is base on the idea that every vector space $V$ and linear map $\alpha$,
there is a vector space $V^\ast$ which mirrors $V$, and a linear map $\alpha^\ast$ of $V^\ast$ which mirrors $\alpha$.

> *Definition.*{: .def}
> Let $V$ be a finite dimensional vector space over $\mathbb{F}$.
> The **dual space** $V^\ast$ of $V$ is defined to be the vector space $\mathcal{L}(V, \mathbb{F})$.
> The elements of $V^\ast$ are **linear forms/functions** from $V$ into $\mathbb{F}$,
> i.e. $f: V \to \mathbb{F} \in V^\ast$ such that $f(v_1 + v_2) = f(v_1) + f(v_2)$ and $f(\lambda v) = \lambda f(v)$.
> The addition and scalar multiplication of $V^\ast$ are $(f_1 + f_2)(v) = f_1(v) + f_2(v)$ and $(\lambda f)(v) = f(\lambda v)$.

## Reference

* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.26
