---
layout: base
title: Integral Calculus &#124; Analysis
---

# Integral Calculus
{: .page-title}

The concept of a definite integral was developed to represent an area bounded by curved lines.
This geometrical equivalence is helpful to visualize the meaning of the analytical expressions occura in the defintion and manipulation of integrals.

> *Definition.*{: .def}
> A **dissection** of an interval $[a, b]$ is a finite set of numbers $a, x_1, x_2, ..., x_{n-1}, b$ such that
>
> $$
  a < x_1 < x_2 < \cdots < x_{n-1} < b
  $$
>
> To complete the scheme, we write $a = x_0$ and $b = x_n$. Each $x_r$ is a **point of division**.
>
> The dissection splits $[a, b]$ into $n$ **subintervals**, i.e. $I_1 = [x_0, x_1]$ and $I_r = (x_{r-1}, x_r]$.
>
> The length of the $r$th subinterval is $\delta_r = x_r - x_{r-1}$,
> and the greatest length $\delta^\ast = \max \delta_r$ is called the **norm** of the dissection.

> *Definition.*{: .def}
> The **upper sum** $U_D$ and **lower sum** $L_D$ are defined by
>
> $$
  \begin{align*}
  U_D(f) &= \sum_{r = 1}^n \delta_r \sup_{x \in I_r} f(x) \\
  L_D(f) &= \sum_{r = 1}^n \delta_r \inf_{x \in I_r} f(x)
  \end{align*}
  $$

The upper sum is the total area of the red rectangles and lower sum is that of black rectangles.

![Upper and Lower Sums](../images/analysis-upper-lower-sums.png)

> *Definition.*{: .def}
> If every point of $D_1$ is a point of $D_2$, then $D_2$ is a **refinement** of $D_1$, i.e. $D_1 \le D_2$.

> *Proposition.*{: .prop}
> If $D_2$ refines $D_1$, then
>
> $$
  U_{D_2} \le U_{D_1} \quad \text{and} \quad L_{D_2} \ge L_{D_1}
  $$
>
> *Proof.*{: .prf}
>
> Suppose $D_2$ refines $D_1$ by introducing a new point of division $x_r'$ into $I_r$ which divides the interval into $I_{r'}$ and $I_{r'\'}$.
> Then we have $\sup_{x \in I_{r'}} f(x) \le \sup_{x \in I_r} f(x)$ and $\sup_{x \in I_{r'\'}} f(x) \le \sup_{x \in I_r} f(x)$ and
>
> $$
  \delta_{r'} \sup_{x \in I_{r'}} f(x) + \delta_{r''} \sup_{x \in I_{r''}} f(x) \le \delta_{r} \sup_{x \in I_{r}} f(x)
  $$
>
> Hence, $U_{D_2} \le U_{D_1}$. Similarily, $L_{D_2} \ge L_{D_1}$.

> *Definition.*{: .def}
> The **least common refinement** of $D_1$ and $D_2$ is the dissection made out of points of $D_1$ and $D_2$.

> *Proposition.*{: .prop}
> Let $D_1$ and $D_2$ be any two dissections of the same interval $[a, b]$. Then
>
> $$
  U_{D_1} \ge L_{D_2}
  $$
>
> *Proof.*{: .prf}
>
> Let $D_3$ be the least common refinement of $D_1$ and $D_2$.
> By the above,
>
> $$
  U_{D_1} \ge U_{D_3} \ge L_{D_3} \ge L_{D_2}
  $$
