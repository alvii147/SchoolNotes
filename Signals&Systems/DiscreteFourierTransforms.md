# Discrete Fourier Transforms

## Definition

Let $\large x[n]$ be a discrete-time signal. Then,
$$
\Large X[k] = \sum\limits^{N - 1}_{n = 0} x[n] W_N^{kn}, \:\:\: 0 \le k \lt N
$$
where $\large W_N = e^{-j \frac{2\pi}{N}}$ and $\large X[k], \:\: 0 \le k \lt N$ are the **Discrete Fourier Transform** coefficients of $\large x[n]$.

Conversely,
$$
\Large x[n] = \frac{1}{N} \sum\limits^{N - 1}_{k = 0} X[k] W_N^{-kn}, \:\:\: 0 \le n \lt N
$$
can be defined as the **Inverse Discrete Fourier Transform** to recover $\large N$ samples of $\large x[n]$.

## Properties

### Linearity

- $\Large y[n] = c_1x_1[n] + c_2x_2[n] \iff c_1X_1[k] + c_2X_2[k]$

### Time-Reversal Circular Symmetry

- $\Large y[n] = x[\langle -n \rangle_N] \iff Y[k] = X^*[k]$

where $\large x[\langle -n \rangle_N] = n \:\text{mod}\: N$, and,
$$
\large x[\langle -n \rangle_N] = \begin{cases}
x[0], & n = 0 \\[5pt]
x[N - n], & 1 \le n \lt N
\end{cases}
$$

- $\Large x[n]$ is **circular even** $\Large \iff x[n] = x[\langle -n \rangle_N]$
- $\Large x[n]$ is **circular odd** $\Large \iff x[n] = -x[\langle -n \rangle_N]$

### Conjugation

- $\Large y[n] = x^*[n] \iff X^*[\langle -k \rangle_N]$

### Duality

- $\Large y[n] = X[n] \iff Nx[\langle -k \rangle_N]$

### Circular Time Shift

- $\Large y[n] = x[\langle n - m \rangle_N] \iff Y[k] = W_N^{mk} X[k]$

### Circular Convolution

- $\Large y[n] = (x \:\enclose{circle}{N}\: h)[n] \iff Y[k] = X[k] H[k]$

where,
$$
\large (x \:\enclose{circle}{N}\: h)[n] = \sum^{N - 1}_{m = 0} h[m] x[\langle n - m \rangle_N], \:\:\: 0 \le n \lt N
$$

### Circular Correlation

- $\Large r_{xy}[n] = x[n] \:\enclose{circle}{N}\: y[\langle -n \rangle_N] \iff R[k] = X[k] Y^*[k]$

where,
$$
\large r_{xy}[l] = \sum\limits^{N - 1}_{n = 0} x[n] y[\langle n - l \rangle_N], \:\:\: 0 \le l \lt N
$$

### Frequency Shifting

- $\Large y[n] = W_N^{-mn} x[n] \iff Y[k] = X[\langle k - m \rangle_N]$

### Frequency Modulation

- $\Large y[n] = x[n] k_0n \cos(\frac{2\pi}{N}) \iff Y[k] = \frac{1}{2} X[\langle k + k_0 \rangle_N] + \frac{1}{2} X[\langle k - k_0 \rangle_N]$

### Windowing

- $\Large y[n] = x[n] w[n] \iff \frac{1}{N} X[k] \:\enclose{circle}{N}\: W[k]$

### Parseval's Theorem

- $\Large y[n] = \sum\limits^{N - 1}_{n = 0} x[n] h^*[n] \iff Y[k] = \frac{1}{N} \sum\limits^{N - 1}_{k = 0} X[k] Y^*[k]$
- $\Large y[n] = \sum\limits^{N - 1}_{n = 0} \abs{x[n]}^2 \iff Y[k] = \frac{1}{N} \sum\limits^{N - 1}_{k = 0} \abs{X[k]}^2$