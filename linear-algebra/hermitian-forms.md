---
layout: base
title: Hermitian Forms &#124; Linear Algebra
---

# Hermitian Forms
{: .page-title}

The standard inner product of $\mathbf{C}^n$ is given by

$$
\langle x, y \rangle = \sum_{i=1}^n \overline{x_i} y_i
$$

which is not a bilinear form since it is not linear in the first variable.
However, it is linear up to complex conjugate in which we can develop similar properties as that of symmetric bilinear forms.

> *Definition.*{: .def}
> Let $V$ and $W$ be vector spaces over $\mathbf{C}$. Then a **sesquilinear** is a function $\phi: V \times W \to \mathbf{C}$ such that
>
> $$
  \begin{align*}
  \phi(\lambda_1 v_1 + \lambda_2 v_2, w) &= \overline{\lambda_1} \phi(v_1, w) + \overline{\lambda_2} \phi(v_2, w) \\
  \phi(v, \mu_1 w_1 + \mu_2 w_2) &= \mu_1 \phi(v, w_1) + \mu_2 \phi(v, w_2)
  \end{align*}
  $$
>
> for all $\lambda_1, \lambda_2, \mu_1, \mu_2 \in \mathbf{C}$, $v, v_1, v_2 \in V$ and $w, w_1, w_2 \in W$.

> *Definition.*{: .def}
> A sesquilinear form $\phi: V \times V \to \mathbf{C}$ is **Hermitian** if $\phi(x, y) = \overline{\phi(y, x)}$ for all $x, y \in V$.

> *Proposition.*{: .prop}
> If $\phi$ is a Hermitian form on $V$ then $\phi(v, v) \in \mathbf{R}$ for all $v \in V$ and $\phi(\lambda v, \lambda v) = \vert \lambda \vert^2 \phi(v, v)$.
>
> *Proof.*{: .prf}
>
> By definition, we have $\phi(v, v) = \overline{\phi(v, v)}$ so $\phi(v, v) \in \mathbf{R}$ and $\phi(\lambda v, \lambda v) = \overline{\lambda} \lambda \phi(v, v) = \vert \lambda \vert^2 \phi(v, v)$.

Therefore, it is also meaning to speak of positive/negative (semi-)definite Hermitian forms.

## Matrix Representation

> *Definition.*{: .def}
> Suppose that $V$ has a basis $(v_1, ..., v_m)$ and $W$ has a basis $(w_1, ..., w_n)$.
> Then the matrix $A$ representing $\phi$ with respect to these bases is defined by $A_{ij} = \phi(v_i, w_j)$.

Similarity, let $x = \sum \lambda_i v_i$ and $y = \sum \mu_j w_j$, we have

$$
\phi(x, y) = \phi \left(\sum_i \lambda_i v_i, \sum_j \mu_j w_j \right) = \sum_{i,j} \overline{\lambda_i} \phi(v_i, w_j) \mu_j = \overline{x}^\intercal A y
$$

> *Proposition.*{: .prop}
> Suppose that $\phi: V \times V \to \mathbf{C}$ is a sesquilinear form on a $\mathbf{C}$-vector space with basis $(v_1, ..., v_n)$.
> Then $\phi$ is Hermitian iff the matrix representing $\phi$ with respect to this basis satisfies $A = A^\dagger = \overline{A}^\intercal$,
> and the matrix is said to be Hermitian.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $\phi$ is Hermitian, then
>
> $$
  A_{ij} = \phi(v_i, v_j) = \overline{\phi(v_j, v_i)} = \overline{A_{ji}}
  $$
>
> ($\Leftarrow$) If $A$ is Hermitian, then
>
> $$
  \phi(x, y) = \sum_{i, j} \overline{x_i} A_{ij} y_j = \sum_{j, i} \overline{\overline{y_j} A_{ji} x_i} = \overline{\phi(y, x)}
  $$

> *Proposition.*{: .prop}
> **[Change of Basis]**
> Suppose that $\phi$ is a Hermitian form on a finite dimensional complex vector space $V$ and $(e_i)$ and $(f_i)$ are bases for $V$ such that $f_i = \sum P_{ki} e_k$.
> If $A$ is the matrix representing $\phi$ with respect to $(e_i)$ and $B$ is that with respect to $(f_i)$ then
>
> $$
  B = P^\dagger A P
  $$
>
> *Proof.*{: .prf}
>
> $$
  B_{ij} = \phi(f_i, f_j) = \phi \left( \sum_k P_{ki} e_k, \sum_l P_{lj} e_l \right) = \sum_{k, l} \overline{P_{ki}} A_{kl} P_{lj} = (P^\dagger A P)_{ij}
  $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 7.2
