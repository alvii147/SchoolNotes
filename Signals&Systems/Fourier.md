# Fourier Series

## Definition

### Exponential Form

Let $x(t)$ be a complex-valued periodic signal with period $T > 0$ and angular frequency $\omega_0 = \frac{2\pi}{T}$. Then,
$$
\Large \widetilde{x}(t) = \sum_{n=-\infty}^{\infty}X_ne^{jn\omega_0t}
$$
where,
$$
\Large X_n = \frac{1}{T}\int_{-\frac{T}{2}}^{\frac{T}{2}}x(t)e^{-jn\omega_0t}dt
$$

and $\widetilde{x}(t)$ is the **Fourier Series** of $x(t)$.

### Special Case for Real Periodic Signals

Let $x(t)$ be a real-valued periodic signal with period $T > 0$ and angular frequency $\omega_0 = \frac{2\pi}{T}$. Then,
$$
\Large \widetilde{x}(t) = X_0 + 2\sum_{n=1}^{\infty}Re(X_ne^{jn\omega_0t})
$$
where,
$$
\Large X_n = \frac{1}{T}\int_{-\frac{T}{2}}^{\frac{T}{2}}x(t)e^{-jn\omega_0t}dt
$$
and $\widetilde{x}(t)$ is the **Fourier Series** of $x(t)$.

### Trigonometric Form

Let $x(t)$ be a complex-valued periodic signal with period $T > 0$ and angular frequency $\omega_0 = \frac{2\pi}{T}$. Then,
$$
\Large \widetilde{x}(t) = \frac{1}{2}a_0 + \sum_{n=1}^{\infty}(a_ncos(n\omega_0t) + b_nsin(n\omega_0t)) \\[15pt]
\Large \widetilde{x}(t) = \frac{1}{2}a_0 + \sum_{n=1}^{\infty}(a_ncos(2\pi nf_0t) + b_nsin(2\pi nf_0t)) \\[15pt]
$$
where,
$$
\begin{align*}
\Large a_0 &\Large = \frac{1}{T}\underset{T}{\int}x(t)dt \\[15pt]
\Large a_n &\Large = \frac{2}{T}\underset{T}{\int}x(t)cos(n\omega_0t)dt = \frac{2}{T}\underset{T}{\int}x(t)cos(2\pi nf_0t)dt\\[15pt]
\Large b_n &\Large = \frac{2}{T}\underset{T}{\int}x(t)sin(n\omega_0t)dt = \frac{2}{T}\underset{T}{\int}x(t)sin(2\pi nf_0t)dt\\[15pt]
\end{align*}
$$
and $\widetilde{x}(t)$ is the **Fourier Series** of $x(t)$.

# Fourier Transform

## Definition

Let $x(t)$ be a complex-valued signal and $\omega = 2\pi f$. Then,
$$
\Large \mathcal{F}\{x(t)\} = X(\omega) = \int_{-\infty}^{\infty}x(t)e^{-j\omega t}dt,\hspace{1cm}for\:all -\infty<\omega<\infty \\[15pt]
\Large \mathcal{F}\{x(t)\} = X(f) = \int_{-\infty}^{\infty}x(t)e^{-j2\pi ft}dt,\hspace{1cm}for\:all -\infty<f<\infty
$$
and,
$$
\Large x(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\omega)e^{j\omega t}d\omega,\hspace{1cm}for\:all-\infty<t<\infty \\[15pt]
\Large x(t) = \int_{-\infty}^{\infty}X(f)e^{j2\pi ft}df,\hspace{1cm}for\:all-\infty<t<\infty
$$

where $\mathcal{F}\{x(t)\} = X(\omega)$ and $\mathcal{F}\{x(t)\} = X(f)$ are **Fourier Transforms** of $x(t)$.

## Properties

### Linearity

- $\Large \mathcal{F}\{c_1x_1(t)+c_2x_2(t)\} = c_1\mathcal{F}\{x_1(t)\}+c_2\mathcal{F}\{x_2(t)\}$

### Duality

- $\Large \mathcal{F}\{X(t)\} = 2\pi x(-\omega)$
- $\Large \mathcal{F}\{X(t)\} = x(-f)$

### Complex Conjugate

- $\Large \mathcal{F}\{x^*(t)\} = X^*(-\omega)$
- $\Large \mathcal{F}\{x^*(t)\} = X^*(-f)$

### Symmetry

- $\Large X(-\omega) = X^*(\omega)$
- $\Large X(-f) = X^*(f)$

### Time Scaling

- $\Large \mathcal{F}\{x(\alpha t)\} = \frac{1}{|a|}X(\frac{\omega}{\alpha})$
- $\Large \mathcal{F}\{x(\alpha t)\} = \frac{1}{|a|}X(\frac{f}{\alpha})$

### Time Shift

- $\Large \mathcal{F}\{x(t-t_0)\} = e^{-j\omega t_0}X(\omega)$
- $\Large \mathcal{F}\{x(t-t_0)\} = e^{-j2\pi ft_0}X(f)$

### Frequency Shift

- $\Large \mathcal{F}\{e^{j\omega_0 t}x(t)\} = X(\omega - \omega_0)$
- $\Large \mathcal{F}\{e^{j2\pi f_0t}x(t)\} = X(f - f_0)$
- $\Large \mathcal{F}\{cos(\omega_0t)x(t)\} = \frac{X(\omega + \omega_0) + X(\omega - \omega_0)}{2}$
- $\Large\mathcal{F}\{cos(2\pi f_0t)x(t)\} = \frac{X(f + f_0) + X(f - f_0)}{2}$
- $\Large \mathcal{F}\{sin(\omega_0t)x(t)\} = j\frac{X(\omega + \omega_0) - X(\omega - \omega_0)}{2}$
- $\Large \mathcal{F}\{sin(2\pi f_0t)x(t)\} = j\frac{X(f + f_0) - X(f - f_0)}{2}$

### Derivatives

- $\Large \mathcal{F}\{x^{(n)}(t)\} =(j\omega)^nX(\omega)$
- $\Large \mathcal{F}\{x^{(n)}(t)\} =(j2\pi ft)^nX(f)$

### Integrals

- $\Large \mathcal{F}\{\int_{-\infty}^{t}x(\tau)d\tau\} = \frac{X(\omega)}{j\omega}+\pi X(0)\delta(\omega)$
- $\Large \mathcal{F}\{\int_{-\infty}^{t}x(\tau)d\tau\} = \frac{X(f)}{j2\pi ft}+\frac{1}{2}X(0)\delta(f)$

### Convolution

- $\Large \mathcal{F}\{x(t)*y(t)\} = X(\omega)Y(\omega)$
- $\Large \mathcal{F}\{x(t)*y(t)\} = X(f)Y(f)$

### Multiplication

- $\Large \mathcal{F}\{x(t)y(t)\} = \frac{1}{2\pi}(X(\omega)*Y(\omega)) = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\lambda)Y(\omega-\lambda)d\lambda = \frac{1}{2\pi}\int_{-\infty}^{\infty}Y(\lambda)X(\omega-\lambda)d\lambda$
- $\Large \mathcal{F}\{x(t)y(t)\} = X(f)*Y(f) = \int_{-\infty}^{\infty}X(\lambda)Y(f-\lambda)d\lambda = \int_{-\infty}^{\infty}Y(\lambda)X(f-\lambda)d\lambda$

### Multiplication by $t$

- $\Large \mathcal{F}\{tx(t)\} = jX'(\omega)$
- $\Large \mathcal{F}\{t^nx(t)\} = j^nX^{(n)}(\omega)$
- $\Large \mathcal{F}\{tx(t)\} = \frac{j}{2\pi}X'(f)$
- $\Large \mathcal{F}\{t^nx(t)\} = (\frac{j}{2\pi})^nX^{(n)}(f)$

### Parseval's Theorem

- $\Large \int_{-\infty}^{\infty}x(t)y^*(t)dt = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\omega)Y^*(\omega)d\omega$
- $\Large \int_{-\infty}^{\infty}x(t)y^*(t)dt = \int_{-\infty}^{\infty}X(f)Y^*(f)df$

## Fourier Transform Table

Signal $\Large x(t)$ for $\Large t\geq 0$ | Fourier Transform $\Large X(\omega)$ | Fourier Transform $\Large X(f)$ 
--- | --- | --- 
$\Large \delta(t)$ | $\Large 1$ | $\Large 1$ 
$\Large 1$ | $\Large 2\pi\delta(\omega)$ | $\Large \delta(f)$ 
$\Large \delta(t-t_0)$ | $\Large e^{-j\omega t_0}$ | $\Large e^{-j2\pi ft_0}$ 
$\Large cos(\omega_0t),\:cos(2\pi f_0t)$ | $\Large \pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)]$ | $\Large \frac{1}{2}[\delta(f-f_0)+\delta(f+f_0)]$ 
$\Large sin(\omega_0t),\:sin(2\pi f_0t)$ | $\Large -j\pi[\delta(\omega-\omega_0)-\delta(\omega+\omega_0)]$ | $\Large \frac{1}{2j}[\delta(f-f_0)-\delta(f+f_0)]$ 
$\Large u(t)$ | $\Large \pi\delta(\omega)+\frac{1}{j\omega}$ | $\Large \frac{1}{2}\delta(f)+\frac{1}{j2\pi f}$ 
$\Large \prod(t)$ | $\Large \pi sinc(\frac{\omega}{2\pi})$* | $\Large sinc(f)$* 
$\Large \Lambda(t)$ | $\Large \pi^2sinc^2(\frac{\omega}{2\pi})$* | $\Large sinc^2(f)$* 
$\Large sgn(t)$ | $\Large \frac{2}{j\omega}$ | $\Large \frac{1}{j\pi f}$ 
$\Large e^{-\alpha t}u(t),\:[\alpha>0]$ | $\Large \frac{1}{\alpha+j\omega}$ | $\Large \frac{1}{\alpha+j2\pi f}$ 
$\Large e^{-\alpha t}u(-t),\:[\alpha>0]$ | $\Large \frac{1}{\alpha-j\omega}$ | $\Large \frac{1}{\alpha-j2\pi f}$ 
$\Large e^{-\alpha |t|},\:[\alpha>0]$ | $\Large \frac{2\alpha}{\alpha^2+\omega^2}$ | $\Large \frac{2\alpha}{\alpha^2+(2\pi f)^2}$ 
$\Large e^{-\alpha t^2}$ | $\Large \sqrt{\frac{\pi}{\alpha}}e^{\frac{-\omega^2}{4\alpha}}$ | $\Large \sqrt{\frac{\pi}{\alpha}}e^{\frac{-(2\pi f)^2}{4\alpha}}$ 
$\Large te^{-\alpha t}u(t),\:[\alpha>0]$ | $\Large \frac{1}{(\alpha+j\omega)^2}$ | $\Large \frac{1}{(\alpha+j2\pi f)^2}$ 
$\Large t^ne^{-\alpha t}u(t),\:[\alpha>0]$ | $\Large \frac{n!}{(\alpha+j\omega)^{n+1}}$ | $\Large \frac{n!}{(\alpha+j2\pi ft)^{n+1}}$ 
$\Large \sum\limits_{n=-\infty}^{\infty}\delta(t-nT_0)$ | $\Large \omega_0\sum\limits_{n=-\infty}^{\infty}\delta(\omega-n\omega_0),\:\omega_0=\frac{2\pi}{T_0}$ | $\Large \frac{1}{T_0}\sum\limits_{n=-\infty}^{\infty}\delta(f-\frac{n}{T_0})$ 

*$\Large  sinc(t) = \frac{sin(\pi t)}{\pi t}$

