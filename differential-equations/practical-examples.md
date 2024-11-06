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

## References

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 1
