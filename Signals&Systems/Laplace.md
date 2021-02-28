# Laplace Transforms

## Definition

Let $x(t)$ be a continuous-time signal and let $s$ be a complex number such that $s = \sigma + j\omega$. Then,
$$
\Large \mathcal{L}\{x(t)\} = X(s) = \int_{0}^{\infty}x(\tau)e^{-s\tau}d\tau
$$
where $\mathcal{L}\{x(t)\} = X(s)$ is the **Laplace Transform** of $x(t)$.

## Properties

### Linearity

- $\Large \mathcal{L}\{c_1x_1(t) + c_2x_2(t)\} = c_1\mathcal{L}\{x_1(t)\} + c_2\mathcal{L}\{x_2(t)\}$

### Exponential Shift

- $\Large \mathcal{L}\{e^{\alpha t}x(t)\} = X(s-\alpha)$

### Derivatives

- $\Large \mathcal{L}\{\frac{d}{dx}(x(t))\} = sX(s) - x(0)$

### Integrals

- $\Large \mathcal{L}\{\int_{0}^{t}x(\tau)\:d\tau\} = \frac{X(s)}{s}$

### Convolution

- $\Large \mathcal{L}\{(x*y)(t)\} = X(s)Y(s)$

### Initial Value Theorem

- $\Large x(0) = \lim\limits_{s \to \infty}sX(s)$

### Final Value Theorem

- $\Large \lim\limits_{t \to \infty} x(t) = \lim\limits_{s \to 0} sX(s)$

Condition: all poles of $sX(s)$ must have strictly negative real parts.

## Laplace Transform Table

Signal $\Large x(t)$ for $t\Large \geq 0$ | Laplace Transform $\Large X(s)$ 
---|---
$\Large \delta(t)$ | $\Large 1$ 
$\Large \delta^{(n)}(t)$ | $\Large s^n$ 
$\Large u(t)$ | $\Large \frac{1}{s}$ 
$\Large t^n$ | $\Large \frac{n!}{s^{n+1}}$ 
$\Large e^{\alpha t}f(t)$ | $\Large F(s-\alpha)$ 
$\Large e^{\alpha t}$  | $\Large \frac{n!}{(s-\alpha)^{n+1}}$ 
$\Large sin(\omega_0t)$ | $\Large \frac{\omega_0}{s^2+\omega_0^2}$ 
$\Large cos(\omega_0t)$ | $\Large \frac{s}{s^2+\omega_0^2}$ 

