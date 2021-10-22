# $\mathcal{Z}$-Transforms

## Definition

Let $\large x[n]$ be a discrete-time signal. Then,
$$
\Large \mathcal{Z}\{x[n]\} = \sum\limits^\infty_{k=0}x[k]z^{-k}
$$
where $\large \mathcal{Z}\{x[n]\}= X(z) $ is the **$\mathcal{Z}$-Transform** of  $\large x[n]$, assuming the sum converges.

## Properties

### Linearity

- $\Large \mathcal{Z}\{c_1x_1[n] + c_2x_2[n]\} = c_1X_1(z) + c_2X_2(z)$

### Time Advance

- $\Large \mathcal{Z}\{x[n+N]\} = z^NX(z) - \sum\limits^{N-1}_{k=0}z^{N-k}x[k]$ 

### Time Delay

- $\Large \mathcal{Z}\{x[n-N]\} = z^{-N}X(z) + \sum\limits^{N-1}_{k=0}z^{-k}x[k-N]$ 

### Multiplication by $k$

- $\Large \mathcal{Z}\{nx[n]\} = -z\frac{dX(z)}{dz}$

### Multiplication by $a^k$

- $\Large \mathcal{Z}\{a^n x[n]\} = X(\frac{z}{\alpha})$

### Convolution

- $\Large \mathcal{Z}\{x*y\} = X(z)Y(z)$

### Initial Value Theorem

- $\Large x[0] = \lim\limits_{z \to \infty} X(z)$

### Final Value Theorem

- $\Large \lim\limits_{n \to \infty} x[n] = \lim\limits_{z \to 1} (z-1)X(z)$

Condition: $\large x[n]$ must converge to a finite value as $\large n \to \infty$.

## $\mathcal{Z}$-Transform Table

Signal $\large x[n]$ | $\mathcal{Z}$-Transform $X(z)$ | Region of Convergence
--- | --- | ---
$\Large \delta [n]$ | $\Large 1$ | $\large \text{All } z$
$\Large \delta_k [n]$ | $\Large z^{-k}$ | $\large z \ne 0, \: z \ne \infty$
$\Large u[n]$ | $\huge \frac{z}{z-1}$ | $\large \abs{z} \gt 1$
$\Large \alpha^n u[n]$ | $\huge \frac{z}{z-\alpha}$ | $\large \abs{z} \gt \alpha$
$\Large - \alpha^n u[- n - 1]$ | $\huge \frac{z}{z-\alpha}$ | $\large \abs{z} \lt \alpha$
$\Large n \alpha^n u[n]$ | $\huge \frac{\alpha z}{(z-\alpha)^2}$ | $\large \abs{z} \gt \alpha$
$\Large - n \alpha^n u[- n - 1]$ | $\huge \frac{\alpha z}{(z-\alpha)^2}$ | $\large \abs{z} \lt \alpha$
$\Large u[n] sin(\omega_0 n)$ | $\huge \frac{z\:sin(\omega_0)}{z^2-2z\:cos(\omega_0) + 1}$ | $\large \abs{z} \gt 1$
$\Large u[n] cos(\omega_0 n)$ | $\huge \frac{z^2-z\:cos(\omega_0)}{z^2-2z\:cos(\omega_0) + 1}$ | $\large \abs{z} \gt 1$
$\Large a^n u[n] sin(\omega_0 n)$ | $\huge \frac{\alpha z\:sin(\omega_0)}{z^2-2\alpha z\:cos(\omega_0) + \alpha^2}$ | $\large \abs{z} \gt \alpha$
$\Large a^n u[n] cos(\omega_0 n)$ | $\huge \frac{z^2-\alpha z\:cos(\omega_0)}{z^2-2\alpha z\:cos(\omega_0) + \alpha^2}$ | $\large \abs{z} \gt \alpha$

## Power Series

Consider a geometric progression with common ratio, $\large \rho$, where $\large |\rho| < 1$. Then,
$$
\Large \sum\limits^\infty_{k = 0}\rho^k = \frac{1}{1-\rho}
$$
By taking the derivative, we can also derive:
$$
\Large \sum\limits^\infty_{k=0}k\rho^k = \frac{\rho}{(1- \rho)^2}
$$
