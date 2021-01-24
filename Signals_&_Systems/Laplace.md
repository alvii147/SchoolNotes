# Laplace Transforms

## Definition

Let $x(t)$ be a continuous-time signal and let $s$ be a complex number such that $s = \sigma + j\omega$. Then,
$$
\mathcal{L}\{x(t)\} = X(s) = \int_{0}^{\infty}x(\tau)e^{-s\tau}d\tau
$$
where $\mathcal{L}\{x(t)\} = X(s)$ is the **Laplace Transform** of $x(t)$.

## Properties

#### Linearity

- $\mathcal{L}\{c_1x_1(t) + c_2x_2(t)\} = c_1\mathcal{L}\{x_1(t)\} + c_2\mathcal{L}\{x_2(t)\}$

#### Exponential Shift

- $\mathcal{L}\{e^{\alpha t}x(t)\} = X(s-\alpha)$

#### Derivatives

- $\mathcal{L}\{\frac{d}{dx}(x(t))\} = sX(s) - x(0)$

#### Integrals

- $\mathcal{L}\{\int_{0}^{t}x(\tau)\:d\tau\} = \frac{X(s)}{s}$

#### Convolution

- $\mathcal{L}\{(x*y)(t)\} = X(s)Y(s)$

#### Initial Value Theorem

- $x(0) = \lim\limits_{s \to \infty}sX(s)$

#### Final Value Theorem

- $\lim\limits_{t \to \infty} x(t) = \lim\limits_{s \to 0} sX{s}$

## Laplace Transform Table

Signal $x(t)$ for $t\geq 0$ | Laplace Transform $X(s)$
---|---
$\delta(t)$ | $1$
$\delta^{(n)}(t)$ | $s^n$
$u(t)$ | $\frac{1}{s}$
$t^n$ | $\frac{n!}{s^{n+1}}$
$e^{\alpha t}f(t)$ | $F(s-\alpha)$
$e^{\alpha t}$  | $\frac{n!}{(s-\alpha)^{n+1}}$
$sin(\omega t)$ | $\frac{\omega}{s^2+\omega^2}$
$cos(\omega t)$ | $\frac{s}{s^2+\omega^2}$

