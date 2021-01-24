# Fourier Series

## Definition

### Exponential Form

Let $x(t)$ be a complex-valued periodic signal with period $T > 0$ and angular frequency $\omega_0 = \frac{2\pi}{T}$. Then,
$$
\widetilde{x}(t) = \sum_{k=-\infty}^{\infty}X_ne^{jn\omega_0t}
$$
where,
$$
X_n = \frac{1}{T}\int_{-\frac{T}{2}}^{\frac{T}{2}}x(t)e^{-jn\omega_0t}dt,\hspace{1cm}n\in\mathbb{Z}
$$

and $\widetilde{x}(t)$ is the **Fourier Series** of $x(t)$.

### Special Case for Real Periodic Signals

Let $x(t)$ be a real-valued periodic signal with period $T > 0$ and angular frequency $\omega_0 = \frac{2\pi}{T}$. Then,
$$
\widetilde{x}(t) = X_0 + 2\sum_{n=1}^{\infty}Re(X_ne^{jn\omega_0t})
$$
where,
$$
X_n = \frac{1}{T}\int_{-\frac{T}{2}}^{\frac{T}{2}}x(t)e^{-jn\omega_0t}dt,\hspace{1cm}n\in\mathbb{Z}
$$
and $\widetilde{x}(t)$ is the **Fourier Series** of $x(t)$.

### Trigonometric Form

Let $x(t)$ be a complex-valued periodic signal with period $T > 0$ and angular frequency $\omega_0 = \frac{2\pi}{T}$. Then,
$$
\widetilde{x}(t) = \frac{1}{2}a_0 + \sum_{n=1}^{\infty}(a_ncos(n\omega_0t) + b_nsin(n\omega_0t))
$$
where,
$$
\begin{align*}
a_0 &= \frac{1}{T}\int_{-T}^{T}x(t)dt \\[15pt]
a_n &= \frac{1}{T}\int_{-T}^{T}x(t)cos(n\omega_0t)dt \\[15pt]
b_n &= \frac{1}{T}\int_{-T}^{T}x(t)sin(n\omega_0t)dt
\end{align*}
$$
and $\widetilde{x}(t)$ is the **Fourier Series** of $x(t)$.

# Fourier Transform

## Definition

Let $x(t)$ be a complex-valued signal and $\omega = 2\pi f$. Then,
$$
\mathcal{F}\{x(t)\} = X(\omega) = \int_{-\infty}^{\infty}x(t)e^{-j\omega t}dt,\hspace{1cm}for\:all -\infty<\omega<\infty \\[15pt]
\mathcal{F}\{x(t)\} = X(f) = \int_{-\infty}^{\infty}x(t)e^{-j2\pi ft}dt,\hspace{1cm}for\:all -\infty<f<\infty
$$
and,
$$
x(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\omega)e^{j\omega t}d\omega,\hspace{1cm}for\:all-\infty<t<\infty \\[15pt]
x(t) = \int_{-\infty}^{\infty}X(f)e^{j2\pi ft}df,\hspace{1cm}for\:all-\infty<t<\infty
$$

where $\mathcal{F}\{x(t)\} = X(\omega)$ and $\mathcal{F}\{x(t)\} = X(f)$ are **Fourier Transforms** of $x(t)$.

## Properties

#### Linearity

- $\mathcal{F}\{c_1x_1(t)+c_2x_2(t)\} = c_1\mathcal{F}\{x_1(t)\}+c_2\mathcal{F}\{x_2(t)\}$

#### Duality

- $\mathcal{F}\{X(t)\} = 2\pi x(-\omega)$
- $\mathcal{F}\{X(t)\} = x(-f)$

#### Complex Conjugate

- $\mathcal{F}\{x^*(t)\} = X^*(-\omega)$
- $\mathcal{F}\{x^*(t)\} = X^*(-f)$

#### Symmetry

- $X(-\omega) = X^*(\omega)$
- $X(-f) = X^*(f)$

#### Time Scaling

- $\mathcal{F}\{x(\alpha t)\} = \frac{1}{|a|}X(\frac{\omega}{\alpha})$
- $\mathcal{F}\{x(\alpha t)\} = \frac{1}{|a|}X(\frac{f}{\alpha})$

#### Time Shift

- $\mathcal{F}\{x(t-t_0)\} = e^{-j\omega t_0}X(\omega)$
- $\mathcal{F}\{x(t-t_0)\} = e^{-j2\pi ft_0}X(f)$

#### Frequency Shift

- $\mathcal{F}\{e^{j\omega t}x(t)\} = X(\omega - \omega_0)$
- $\mathcal{F}\{e^{j2\pi ft}x(t)\} = X(f - f_0)$
- $\mathcal{F}\{cos(\omega_0t)x(t)\} = \frac{X(\omega + \omega_0) + X(\omega - \omega_0)}{2}$
- $\mathcal{F}\{cos(2\pi f_0t)x(t)\} = \frac{X(f + f_0) + X(f - f_0)}{2}$
- $\mathcal{F}\{sin(\omega_0t)x(t)\} = j\frac{X(\omega + \omega_0) - X(\omega - \omega_0)}{2}$
- $\mathcal{F}\{sin(2\pi f_0t)x(t)\} = j\frac{X(f + f_0) - X(f - f_0)}{2}$

#### Derivatives

- $\mathcal{F}\{x^{(n)}(t)\} =(j\omega)^nX(\omega)$
- $\mathcal{F}\{x^{(n)}(t)\} =(j2\pi ft)^nX(f)$

#### Integrals

- $\mathcal{F}\{\int_{-\infty}^{t}x(\tau)d\tau\} = \frac{X(\omega)}{j\omega}+\pi X(0)\delta(\omega)$
- $\mathcal{F}\{\int_{-\infty}^{t}x(\tau)d\tau\} = \frac{X(f)}{j2\pi ft}+\frac{1}{2}X(0)\delta(f)$

#### Convolution

- $\mathcal{F}\{x(t)*y(t)\} = X(\omega)Y(\omega)$
- $\mathcal{F}\{x(t)*y(t)\} = X(f)Y(f)$

#### Multiplication

- $\mathcal{F}\{x(t)y(t)\} = \frac{1}{2\pi}(X(\omega)*Y(\omega)) = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\lambda)Y(\omega-\lambda)d\lambda = \frac{1}{2\pi}\int_{-\infty}^{\infty}Y(\lambda)X(\omega-\lambda)d\lambda$
- $\mathcal{F}\{x(t)y(t)\} = X(f)*Y(f) = \int_{-\infty}^{\infty}X(\lambda)Y(f-\lambda)d\lambda = \int_{-\infty}^{\infty}Y(\lambda)X(f-\lambda)d\lambda$

#### Parseval's Theorem

- $\int_{-\infty}^{\infty}x(t)y^*(t)dt = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\omega)Y^*(\omega)d\omega$
- $\int_{-\infty}^{\infty}x(t)y^*(t)dt = \int_{-\infty}^{\infty}X(f)Y^*(f)df$

## Fourier Transform Table

Signal $x(t)$ for $t\geq 0$ | Fourier Transform $X(\omega)$ | Fourier Transform $X(f)$
--- | --- | --- 
$\delta(t)$ | $1$ | $1$
$1$ | $2\pi\delta(\omega)$ | $\delta(f)$
$\delta(t-t_0)$ | $e^{-j\omega t_0}$ | $e^{-j2\pi ft_0}$
$cos(\omega_0t),\:cos(2\pi f_0t)$ | $\pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)]$ | $\frac{1}{2}[\delta(f-f_0)+\delta(f+f_0)]$
$sin(\omega_0t),\:sin(2\pi f_0t)$ | $-j\pi[\delta(\omega-\omega_0)-\delta(\omega+\omega_0)]$ | $\frac{1}{2j}[\delta(f-f_0)-\delta(f+f_0)]$
$u(t)$ | $\pi\delta(\omega)+\frac{1}{j\omega}$ | $\frac{1}{2}\delta(f)+\frac{1}{j2\pi f}$
$\prod(t)$ | $\pi sinc(\frac{\omega}{2\pi})$* | $sinc(f)$*
$\Lambda(t)$ | $\pi^2sinc^2(\frac{\omega}{2\pi})$* | $sinc^2(f)$*
$sgn(t)$ | $\frac{2}{j\omega}$ | $\frac{1}{j\pi f}$

*$sinc(t) = \frac{sin(\pi t)}{\pi t}$