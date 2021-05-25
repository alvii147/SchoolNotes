# $\mathcal{Z}$-Transforms

## Definition

Let $\large x[k]$ be a discrete-time signal. Then,
$$
\Large \mathcal{Z}\{x[k]\} = \sum\limits^\infty_{k=0}x[k]z^{-k}
$$
where $\large \mathcal{Z}\{x[k]\}= X(z) $ is the **$\mathcal{Z}$-Transform** of  $\large x[k]$, assuming the sum converges.

## Properties

### Linearity

- $\Large \mathcal{Z}\{c_1x_1[k] + c_2x_2[k]\} = c_1X_1(x) + c_2X_2(z)$

### Time Advance

- $\Large \mathcal{Z}\{x[k+N]\} = z^NX(z) - \sum\limits^{N-1}_{i=0}z^{N-i}x[i]$ 

### Time Delay

- $\Large \mathcal{Z}\{x[k-N]\} = z^{-N}X(z) + \sum\limits^{N-1}_{i=0}z^{-i}x[i-N]$ 

### Multiplication by $k$

- $\Large \mathcal{Z}\{kx[k]\} = -z\frac{dX(z)}{dz}$

### Multiplication by $a^k$

- $\Large \mathcal{Z}\{a^kx[k]\} = X(\frac{z}{\alpha})$

### Convolution

- $\Large \mathcal{Z}\{x*y\} = X(z)Y(z)$

### Initial Value Theorem

- $\Large x[0] = \lim\limits_{z \to \infty} X(z)$

### Final Value Theorem

- $\Large \lim\limits_{k \to \infty} x[k] = \lim\limits_{z \to 1} (z-1)X(z)$

Condition: $\large x[k]$ must converge to a finite value as $\large k \to \infty$.

## $\mathcal{Z}$-Transform Table

Signal $\large x[k]$ for $k \ge 0$ | $\mathcal{Z}$-Transform X(z)
--- | ---
$\Large \delta [k]$ | $\Large 1$
$\Large \delta_n [k]$ | $\Large z^{-n}$
$\Large u[k]$ | $\huge \frac{z}{z-1}$
$\Large \alpha^k$ | $\huge \frac{z}{z-\alpha}$
$\huge \frac{(k)_{n-1}a^{k-n+1}}{(n-1)!}$ | $\huge \frac{z}{(z-\alpha)^n}$
$\Large sin(k\omega T)$ | $\huge \frac{z\:sin(\omega T)}{z^2-2z\:cos(\omega T) + 1}$ 
$\Large cos(k\omega T)$ | $\huge \frac{z^2-z\:cos(\omega T)}{z^2-2z\:cos(\omega T) + 1}$ 
$\Large a^ksin(k\omega T)$ | $\huge \frac{\alpha z\:sin(\omega T)}{z^2-2\alpha z\:cos(\omega T) + \alpha^2}$
$\Large a^kcos(k\omega T)$ | $\huge \frac{z^2-\alpha z\:cos(\omega T)}{z^2-2\alpha z\:cos(\omega T) + \alpha^2}$

## Power Series

Consider a geometric progression with common ratio, $\large \rho$, where $\large |\rho| < 1$. Then,
$$
\Large \sum\limits^\infty_{k = 0}\rho^k = \frac{1}{1-\rho}
$$
