# Discrete-Time Fourier Transform

## Definition

Let $\large x[n]$ be a discrete-time signal. Then,
$$
\Large DTFT\{x[n]\} = X(e^{j\omega}) = \sum\limits_{n = -\infty}^\infty x[n]e^{-j\omega n}
$$
where $\large DTFT\{x[n]\} = X(e^{j\omega})$ is the **Discrete-Time Fourier Transform** of $\large x[n]$.

Conversely,
$$
\Large x[n] = \frac{1}{2\pi} \int\limits^\pi_{-\pi} X(e^{j\omega}) e^{j\omega n} d\omega
$$
Note that the Discrete-Time Fourier Transform is obtained by restricting the **$\large \mathcal{Z}$-Transform** to the unit circle on the complex plane.

## Properties

### Linearity

- $\Large DTFT\{c_1x_1[n] + c_2x_2[n]\} = c_1X_1(e^{j\omega}) + c_2X_2(e^{j\omega})$

### Time Advance

- $\Large DTFT\{x[n + k]\} = e^{jk\omega}X(e^{j\omega})$ 

### Time Delay

- $\Large DTFT\{x[n - k]\} = e^{-jk\omega}X(e^{j\omega})$ 

### Frequency Shifting

- $\Large DTFT\{e^{j\omega_0 n}x[n]\} = X(e^{j(\omega - \omega_0)})$

### Modulation

- $\Large DTFT\{x[n]cos(\omega_0 n)\} = \frac{1}{2}X(e^{j(\omega + \omega_0)}) + \frac{1}{2}X(e^{j(\omega - \omega_0)})$

### Multiplication by $n$

- $\Large DTFT\{nx[n]\} = -j\frac{dX(e^{j\omega})}{d\omega}$

### Folding

- $\Large DTFT\{x[-n]\} = X(e^{-j\omega})$

### Convolution

- $\Large DTFT\{x*y\} = X(e^{j\omega})Y(e^{j\omega})$

### Windowing

- $\Large DTFT\{x[n] w[n]\} = \frac{1}{2\pi}\int_{2\pi} X(e^{j\theta}) W(e^{j(\omega - \theta)}) d\theta$

### Parseval's Theorem

- $\Large \sum\limits_{n = -\infty}^\infty x_1[n] x^*_2[n] = \frac{1}{2\pi} \int_{2\pi} X_1(e^{j\omega}) X^*_2(e^{j\omega}) d\omega$

- $\Large \sum\limits_{n = -\infty}^\infty \abs{x[n]}^2 = \frac{1}{2\pi} \int_{2\pi} \abs{X(e^{j\omega})}^2 d\omega$