---
layout: base
title: Practical Examples &#124; Differential Equations
---

# Practical Examples

## Radioactive Decay

Let $N(t)$ denote the number of radioactive atoms in some material at time $t$. Then,

$$
{\mathrm{d}N \over \mathrm{d}t} = -kN
$$

is a good model to describe the number of radioactive atoms decays.

Thus,

$$
\begin{align*}
\int {\mathrm{d}N \over N} &= \int -k \mathrm{d}t \\
\ln N &= -kt + C \\
N &= A e^{-kt}
\end{align*}
$$

Assume $N_s$ be the number of isotopes at time $s$, then

$$
A = N_s e^{ks}
$$

Hence,

$$
N(t) = N_s e^{-k(t - s)}
$$

is the solution.

Suppose there are $N_0$ atoms at time $0$, then the _half life_ $t_h$ of an atom is

$$
\begin{align*}
{N_0 \over 2} &= N_0 e^{-kt_h} \\
t_h &= {\ln 2 \over k}
\end{align*}
$$

### Carbon Dating

The essence of the method is that for living matter, the carbon-14 to carbon-12 ratio is constant.
But once dead, the carbon-14 atoms will begin to decay.
Since the half life of carbon 14 is 5700 years, we have $k = \ln 2 / 5700 \approx 1.216 \times 10^{-4}$.

So if we know the sample now at $t_0$ contains only a fraction $p$ of the initial level of carbon 14 $N_s$ (not necessary to know $N_s$), we have

$$
\begin{align*}
p N_s &= N_s e^{-k(t_0 - s)} \\
s &= t_0 + {\ln p \over k}
\end{align*}
$$

## Population Model

Instead of pure expoential growth, we impose a maximum sustainable size of the population (becaue of limitation of resources).

Therefore, we have the _logistic equation_

$$
{\mathrm{d}p \over \mathrm{d} t} = kp \left( 1 - {p \over M} \right)
$$

where $M > 0$ is the maximum sustainable population.

By separating of variables,

$$
\begin{align*}
\int_{p_0}^{p} {M \over p(M - p)} \mathrm{d}p &= \int_{t_0}^t k \, \mathrm{d}t \\
\int_{p_0}^{p} {1 \over p} + {1 \over (M - p)} \mathrm{d}p &= \int_{t_0}^t k \, \mathrm{d}t \\
\ln p - \ln p_0 - \ln |M-p| + \ln |M - p_0| &= kt - kt_0 \\
{p |M - p_0| \over p_0 |M-p|} &= e^{k(t - t_0)}
\end{align*}
$$

As $\|M - p_0\|$ and $\|M - p\|$ always has the same sign base on the equation,
we can remove the absolute sign and rearrange the terms, i.e.

$$
p(t) = M \left( {p_0e^{k(t - t_0)} \over M - p_0 + p_0e^{k(t - t_0)} } \right)
$$

From the equation, we can deduce that $p \to M$ as $t \to \infty$.

## References

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 1, 8.5
