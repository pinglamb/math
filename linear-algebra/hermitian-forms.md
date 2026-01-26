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

## Matrix Representation

Notice that if $\phi$ is a Hermitian form then $\phi(v, v) \in \mathbf{R}$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 7.2
