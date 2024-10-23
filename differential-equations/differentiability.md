---
layout: base
title: Differentiability &#124; Differential Equations
---

# Differentiability

Elementary calculus books normally state that a function $f$ is differentiable at $a$ if $f'(a)$ exists, which means the limit

$$
f'(a) = \lim_{h \to 0} {f(a + h) - f(a) \over h}
$$

exists, and $f'(a)$ is called the derivative of $f$ at $a$.

There is another notion of derivative which is very useful and leads to proper notion of differentiability for functions of several variables.

## Differentiability in One Variable

A function $f: \mathbb{R} \to \mathbb{R}$ is differentiable at $x = a$ if it is _approximately linear_ near $x = a$.
Geometrically, this means that the graph of $f$ has a tangent line at $x = a$.
Analytically, this means there is a linear function $l(x) = mx + b$ satisfying the following two conditions:

* $l(a) = f(a)$, so we have $b = f(a) - ma$ and

$$
l(x) = f(a) + m(x - a)
$$

* the difference $f(x) - l(x)$ tends to zero at a faster rate than $x - a$ as $x \to a$, that is

$$
{f(x) - l(x) \over x - a} \to 0 \text{ as } x \to a
$$

Denoting the increment $x - a$ by $h$, we have

$$
f(x) - l(x) = f(a + h) - (f(a) + mh)
$$

We think of this difference as a function of $h$ and denote it by $E(h)$, which represents the error when we approximate $f(a + h)$ by the linear function $f(a) + mh$.

[Formal Definition] Suppose $f$ is a real-valued function defined on some open interval in $\mathbb{R}$ containing the point $a$.
It is _differentiable_ at $a$ if these is a number $m$ such that

$$
\begin{equation} \tag{1} \label{eq1}
f(a + h) = f(a) + mh + E(h), \quad \text{where } \quad \lim_{h \to 0} {E(h) \over h} = 0
\end{equation}
$$

In other words, $f$ is differentiable at $a$ if we can represent $f(a + h)$ as the sum of the linear function $f(a) + mh$ and an error term $E(h)$ that tends to zero more rapidly than $h$ as $h \to 0$.
In this case, we have

$$
m = {f(a + h) - f(a) \over h} - {E(h) \over h}
$$

When $h \to 0$, the last term vanishes, so

$$
m = \lim_{h \to 0} {f(a + h) - f(a) \over h}
$$

Thus, the number $m$ is uniquely determinted and it is called the _derivative_ of $f$ at $a$, denoted by $f'(a)$.

Coversely, if the limit $m$ exists, we set $E(h) = f(a + h) - f(a) - mh$ and

$$
\lim_{h \to 0} {E(h) \over h} = \lim_{h \to 0} {f(a + h) - f(a) \over h} - m = m - m = 0
$$

so $\eqref{eq1}$ holds and it is like the usual definition.

Also, as $E(h) / h$ vanishes as $h \to 0$, so as $E(h)$ itself and hence so does $f(a + h) - f(a)$.
It means differentiability at $a$ implies continuity at $a$.

## Little-o notation

The statement $f(h) = o(g(h))$ as $h \to 0$ means that

$$
\lim_{h \to 0} {f(h) \over g(h)} = 0
$$

Some general properties are as follow (suppose $h \to 0$):

* If $f(h) = o(h^a)$ and $g(h) = o(h^a)$ then $f(h) + g(h) = o(h^a)$
* If $f(h) = o(h^a)$ and $g(h) = o(h^b)$ then $f(h)g(h) = o(h^{a+b})$
* If $f(h) = o(h)$ then $cf(h) = o(h)$
* If $f_1(h) = o(f_2(h))$ and $f_2(h) = o(f_3(h))$ then $f_1(h) = o(f_3(h))$
* If $f(h) = o(h^a)$ where $a \in \mathbb{N}$ then $f(h) = o(h)$

Base on the definition, we can see that $E(h) = o(h)$ and we have the following theorem:

If $f$ is differentiable at $x = a$, then

$$
f(a + h) = f(a) + f'(a)h + o(h)
$$

Conversely, if there exist constants $A$ and $B$ such that

$$
f(a + h) = A + Bh + o(h)
$$

then $f$ is differentiable at $a$, with $A = f(a)$ and $B = f'(a)$.

This theorem means that the tangent line is a good linear approximation to $f$ and the tangent line is the _only_ line that gives such a good approximation.

This notation is handy for deriving basic laws of differentiation.

### Product rule proof

If $f$ and $g$ are differentiable at $x = a$, then

$$
f(a + h) = f(a) + f'(a)h + o(h) \quad \text{and} \quad g(a + h) = g(a) + g'(a)h + o(h)
$$

Hence,

$$
\begin{align*}
f(a + h)g(a + h) &= [f(a) + f'(a)h + o(h)][g(a) + g'(a)h + o(h)] \\
&= f(a)g(a) + [f(a)g'(a) + f'(a)g(a)]h + \left\{ [f(a) + f'(a)h]o(h) + [g(a) + g'(a)h]o(h) + o(h^2) \right\} \\
&= f(a)g(a) + [f(a)g'(a) + f'(a)g(a)]h + o(h)
\end{align*}
$$

By the theorem, $fg$ is differentiable at $x = a$ and its derivative is $f(a)g'(a) + f'(a)g(a)$.

### Chain rule proof

If $f$ is differentiable at $x = a$ and $g$ is differentiable at $x = f(a)$, we have

$$
f(a + h) = f(a) + f'(a)h + o(h) \quad \text{and} \quad g(f(a) + k) = g(f(a)) + g'(f(a))k + o(k)
$$

Substitude $k = f(a + h) - f(a)$ in the second formula,

$$
g(f(a + h)) = g(f(a)) + g'(f(a))[f(a + h) - f(a)] + o(f(a + h) - f(a))
$$

Then substitude $f(a + h) - f(a) = f'(a)h + o(h)$,

$$
\begin{align*}
g(f(a + h)) &= g(f(a)) + g'(f(a))[f'(a)h + o(h)] + o(f'(a)h + o(h))
&= g(f(a)) + [g'(f(a))f'(a)]h + o(h)
\end{align*}
$$

By the theorem, $g \circ f$ is differentiable at $x = a$ and its derivative is $g'(f(a))f'(a)$.

## References

* [Gerald B. Folland _Advanced Calculus_, 2022 - Chapter 2](http://www.math.washington.edu/~folland/Homepage/AdvCalc24.pdf)