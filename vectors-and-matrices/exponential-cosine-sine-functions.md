---
layout: base
title: Exponential, Cosine and Sine Functions &#124; Vectors and Matrices
---

# Exponential, Cosine and Sine Functions
{: .page-title}

The intuition on the meaning of $e^x$ with $x \in \mathbb{Z}^{+}$ is multiplying $e$ by itself $x$ times and $e^{-x} = 1/e^x$ being the inverse of that.
However, when $x$ is irrational, or even complex, this intuition doesn't work very well and hence we need a better definition which caters that.

Similarily, the trigonometric functions $\cos(x)$ and $\sin(x)$ can also be extended beyond $x$ being some sort of angles, e.g. $x \in \mathbb{C}$.
The definition of them by [power series](../differential-equations/power-series.md) provides a great extension to evaluate them on different kinds of numbers, with the basic properties preserved.

## Exponential Function

> *Definition.*{: .def}
> The exponential function, $\exp(x)$, is defined by the power series
>
> $$
  \exp(x) = \sum_{n=0}^{\infty} {x^n \over n!} = 1 + x + {x^2 \over 2!} + ...
  $$

> *Lemma.*{: .lem}
>
> $$
  \sum_{n=0}^\infty \sum_{m=0}^\infty a_{mn} = \sum_{n=0}^\infty \sum_{r=0}^n a_{n-r, r}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \sum_{n=0}^\infty \sum_{m=0}^\infty a_{mn}
  &= a_{00} + a_{01} + a_{02} + \cdots \\
  &+ a_{10} + a_{11} + a_{12} + \cdots \\
  &+ a_{20} + a_{21} + a_{22} + \cdots \\
  &= a_{00} + (a_{10} + a_{01}) + (a_{20} + a_{11} + a_{02}) + \cdots \\
  &= \sum_{n=0}^\infty \sum_{r=0}^n a_{n-r, r}
  \end{align*}
  $$

> *Theorem.*{: .thm}
> $\exp(x)\exp(y) = \exp(x+y)$.
>
> *Proof.*{: .prf}
>
> For $x, y \in \mathbb{R}$,
>
> $$
  \begin{align*}
  \exp(x)\exp(y) &= \left( \sum {x^n \over n!} \right) \left( \sum {y^n \over n!} \right) \\
                 &= \sum_{n=0}^{\infty}\sum_{m=0}^{\infty} {x^n \over n!}{y^m \over m!} \\
                 &= \sum_{n=0}^{\infty}\sum_{r=0}^{n} {x^{n-r} \over (n-r)!}{y^{r} \over (r)!} \\
                 &= \sum_{n=0}^{\infty} {1 \over n!} \sum_{r=0}^{n} {n! \over r!(n-r)!}x^{n-r}y^{r} \\
                 &= \sum_{n=0}^{\infty} {(x+y)^n \over n!} \\
                 &= \exp(x+y)
  \end{align*}
  $$

The power series definition is consistent with the intuition described above.

> *Theorem.*{: .lem}
> For $x \in \mathbb{Q}$, $\exp(x) = e^x$.
>
> *Proof.*{: .prf}
>
> + $\exp(a)\exp(b) = \exp(a + b)$ as proved above.
>
> + Substituting $x = 0$ into the definition, we have $\exp(0) = 1$.
>
> + Let $\exp(1) = e$. As $\exp(0) = \exp(1 - 1) = \exp(1)\exp(-1) = (e)\exp(-1) = 1$, we have
>
> $$
  \exp(-1) = 1/e = e^{-1}
  $$
>
> By induction, we have $\exp(x) = e^x$ for $x \in \mathbb{Q}$.

We can then define $e^x$ beyond rational numbers, i.e.

> *Definition.*{: .def}
> For $x \in \mathbb{C}$, $e^x \equiv \exp(x)$.

## Trigonometric Functions

Similarily, we have

> *Definition.*{: .def}
> The cosine and sine functions are defined by the power series
>
> $$
  \cos(x) = \sum_{n=0}^{\infty} (-1)^n {x^{2n} \over (2n)!}
  $$
>
> $$
  \sin(x) = \sum_{n=0}^{\infty} (-1)^n {x^{2n+1} \over (2n+1)!}
  $$

which allows us to extend the definition to having $x \in \mathbb{C}$.

## Relationship between them

When $x \in \mathbb{R}$, we don't really see a relationship between them as $\exp(x)$ appears to be ever-increasing function while $\cos(x)$ and $\sin(x)$ are periodic functions oscillating between $1$ and $-1$.

However, with the extension of defintion to complex number, we see an astonishing connection between them:

> *Theorem.*{: .thm}
> $\exp(ix) = \cos(x) + i\sin(x)$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \exp(ix) &= \sum_{n=0}^{\infty} {(ix)^n \over n!} \\
           &= 1 + ix - {x^2 \over 2!} - i{x^3 \over 3!} + ... \\
           &= \left( 1 - {x^2 \over 2!} + {x^4 \over 4!} + ...\right) + i\left( x - { x^3 \over 3!} + {x^5 \over 5!} + ... \right) \\
           &= \sum_{n=0}^{\infty} (-1)^n {x^{2n} \over (2n)!} + i \sum_{n=0}^{\infty} (-1)^n {x^{2n+1} \over (2n+1)!} \\
           &= \cos(x) + i\sin(x)
  \end{align*}
  $$

It produces what is probably the most striking formula in mathematics, namely

> *Theorem.*{: .thm}
> **[Euler Identity]**
>
> $$
  e^{i\pi} = -1
  $$

## Remarks

Most of the proof above aims to illustrate the ideas behind and should not be considered rigorous.
As the power series are infinite sum, a rigorous proof has to consider the convergence of the series in different situations.
