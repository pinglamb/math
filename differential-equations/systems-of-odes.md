---
layout: base
title: Systems of First Order Differential Equations &#124; Differential Equations
---

# Systems of First Order Differential Equations
{: .page-title}

A general system of first order differential equation is of the form

$$
\begin{align*}
x_1' &= F_1(t, x_1, x_2, ..., x_n) \\
x_2' &= F_2(t, x_1, x_2, ..., x_n) \\
&\quad \vdots \\
x_n' &= F_n(t, x_1, x_2, ..., x_n) \\
\end{align*}
$$

It is important to focus of first order differential equations
because any arbitrary $n$th order equation $y^{(n)} = F(t, y, y', ..., y^{(n-1)})$ can be transformed into a system of $n$ first order equations.
Let $x_1 = y$, $x_2 = y'$, ..., $x_n = y^{(n-1)}$ then we have

$$
\begin{align*}
x_1' &= x_2 \\
x_2' &= x_3 \\
&\quad \vdots \\
x_n' &= F(t, x_1, x_2, ..., x_{n-1})
\end{align*}
$$

which is a system of $n$ first order differential equations.
