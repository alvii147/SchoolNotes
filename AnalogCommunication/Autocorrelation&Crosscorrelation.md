# Autocorrelation Function

The **Autocorrelation** $R_x(T)$ of a signal $x(t)$ is defined as,
$$
\Large R_x(\tau) = \lim\limits_{T \to \infty}\frac{1}{T}\int\limits^{\frac{T}{2}}_{-\frac{T}{2}}x^*(t)x(t+\tau)dt
$$

## Periodic Signals

In the special case where $x(t)$ is a periodic signal, the Autocorrelation is defined as,
$$
\Large R_x(\tau) = \sum\limits^{\infty}_{n = -\infty}|X_n|^2e^{j\frac{2n\pi}{T}\tau}
$$

## Wiener-Khinchin Theorem

The inverse Fourier transform of the Power Spectral Density of signal $x(t)$ is equal to the Autocorrelation of signal $x(t)$:
$$
\Large R_x(\tau) = \mathcal{F}^{-1}\{S_x(f)\}
$$

## Linear Time-Invariant System

For a linear time-invariant system $y(t)$ with input $x(t)$ and impulse response h(t),
$$
\Large R_y(\tau) = R_x(\tau) * h(\tau) * h^*(-\tau)
$$

## Properties

### Symmetry

- $R_x^*(\tau)=R_x(-\tau)$

### Mean-Squared Value

- $R_x(\tau)|_{\tau=0} = P_x$

### Periodicity

- If $x(t)$ is periodic with time period $T$, then $R_x(\tau+T) = R_x(\tau)$

### Maximum Value

- $|R_x(\tau)| \le R_x(0)$

# Crosscorrelation Function

The **Crosscorrelation Function** $R_{xy}(\tau)$ of two signals $x(t)$ and $y(t)$ is defined as,
$$
\Large R_{xy}(\tau) = \lim\limits_{T \to \infty}\frac{1}{T}\int\limits^{\frac{T}{2}}_{-\frac{T}{2}}x^*(t)y(t+\tau)dt
$$
The Crosscorrelation Function measures the *similarity* between two signals. $R_{xy}(\tau) = 0$ implies $x(t)$ and $y(t)$ are uncorrelated.

