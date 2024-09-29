---
layout: base
title: Exponential, Cosine and Sine Functions
---

# Exponential, Cosine and Sine Functions

The intuition on the meaning of $e^x$ with $x \in \mathbb{Z}_{>0}$ is multiplying $e$ by itself $x$ times and we also have $e^{-x} = 1/e^x$.
However, when $$x$$ is irrational, or even complex, this definition is not clear and hence we need a better definition which caters for that.
Similarily, the trigonometric functions $\cos(x)$ and $\sin(x)$ can also be extended beyond $x$ being some sort of angles, e.g. $x \in \mathbb{C}$.
The definition of them by power series provides a great extension to evaluate them on different kinds of numbers, with the basic properties preserved.

# Exponential Function

The exponential function, $\exp(x)$, is defined by the power series

$$
\exp(x) = \sum_{n=0}^{\infty} {x^n \over n!} = 1 + x + {x^2 \over 2!} + ...
$$

For $x, y \in \mathbb{R}$,

$$
\begin{align*}
\exp(x)\exp(y) &= \left( \sum {x^n \over n!} \right) \left( \sum {y^n \over n!} \right) \\
               &= \sum_{n=0}^{\infty}\sum_{r=0}^{n} {x^{n-r} \over (n-r)!}{y^{r} \over (r)!} \\
               &= \sum_{n=0}^{\infty} {1 \over n!} \sum_{r=0}^{n} {n! \over r!(n-r)!}x^{n-r}y^{r} \\
               &= \sum_{n=0}^{\infty} {(x+y)^n \over n!} \\
               &= \exp(x+y)
\end{align*}
$$

From the power series definition, we have

$$
\exp(0) = 1
$$

We then define

$$
\exp(1) = e
$$

As $\exp(0) = \exp(1 - 1) = \exp(1)\exp(-1) = (e)\exp(-1) = 1$, we have

$$
\exp(-1) = 1/e = e^{-1}
$$

We can see that, by induction, for $n \in \mathbb{Z}$,

$$
e^n = \exp(n)
$$

Similarily, we can continue to extend the defintion for $x$ being rational, irrational and even complex number, with the consistency maintained.
Eventually, we have for $z \in \mathbb{C}$,

$$
\exp(z) = \sum_{n=0}^{\infty} {z^n \over n!}
$$

# Trigonometric Functions

Similarily, we have the definion of cosine and sine base on power series

$$
\cos(x) = \sum_{n=0}^{\infty} (-1)^n {x^{2n} \over (2n)!}
$$

$$
\sin(x) = \sum_{n=0}^{\infty} (-1)^n {x^{2n+1} \over (2n+1)!}
$$

which allows us to extend the definition to having $x \in \mathbb{C}$.

# Relationship between them

When $x \in \mathbb{R}$, we don't really see a relationship between them as $\exp(x)$ appears to be ever-growing function and $\cos(x)$ and $\sin(x)$ are periodic functions oscillating between $1$ and $-1$.

However, with the extension of defintion to complex number, we see an astonishing connection between them:

$$
\begin{align*}
\exp(ix) &= \sum_{n=0}^{\infty} {(ix)^n \over n!} \\
         &= 1 + ix - {x^2 \over 2!} - i{x^3 \over 3!} + ... \\
         &= \left( 1 - {x^2 \over 2!} + {x^4 \over 4!} + ...\right) + i\left( x - { x^3 \over 3!} + {x^5 \over 5!} + ... \right) \\
         &= \sum_{n=0}^{\infty} (-1)^n {x^{2n} \over (2n)!} + i \sum_{n=0}^{\infty} (-1)^n {x^{2n+1} \over (2n+1)!} \\
         &= \cos(x) + i\sin(x)
\end{align*}
$$

It is such an important result that we have to state again,

$$
\exp(ix) = e^{ix} = \cos x + i \sin x
$$

It produces what is probably the most striking formula in mathematics, namely

$$
e^{i\pi} = -1
$$

# Remarks

Most of the proof above aims to illustrate the ideas behind and should not be considered rigorous.
As the power series are infinite sum, a rigorous proof has to consider the convergence of the series in different situations.
