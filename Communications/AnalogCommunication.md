# Energy Signals

The **Average Energy** $E_x$ of a signal $x(t)$ is defined as,
$$
E_x = \int\limits^{\infty}_{-\infty} |x(t)|^2dt
$$
If $0<E_x<\infty$, then $x(t)$ is an **Energy Signal.**

# Power Signals

The **Average Power** $P_x$ of a signal $x(t)$ is defined as,
$$
P_x = \lim\limits_{T \to \infty}\frac{1}{T}\int\limits^{\frac{T}{2}}_{-\frac{T}{2}}|x(t)|^2dt
$$
If $0<P_x<\infty$, then $x(t)$ is a **Power Signal.**

**NOTE:** a signal cannot be both an energy and a power signal. It can, however, be neither.

# Energy Spectral Density

The **Energy Spectral Density** $\Psi_x(f)$ of a signal $x(t)$ is defined as,
$$
\Psi_x(f) = |X(f)|^2
$$

# Power Spectral Density

The **Power Spectral Density** $S_x(f)$ of a signal $x(t)$ is defined as,
$$
S_x(f) = \lim\limits_{T \to \infty} \frac{1}{T}|X_T(f)|^2
$$
where, $X_T(f)$ is the Fourier transform of $x_T(t)$ and,
$$
x_T(t) = x(t)\Pi(\frac{t}{T})
$$
In other words, $x_T(t)$ is the function that has value $x(t)$ for $-\frac{T}{2}<t<\frac{T}{2}$ and $0$ for all other values of $t$:
$$
x_T(t) = 
\begin{cases}
x(t),&if\:\:-\frac{T}{2}<t<\frac{T}{2} \\[5pt]
0,&otherwise
\end{cases}
$$

## Periodic Signals
In the special case where $x(t)$ is a periodic signal, the Average Power is defined as,
$$
P_x=\sum\limits^{\infty}_{n=-\infty}|X_n|^2
$$
and the Power Spectral Density is defined as,
$$
S_x(f)=\sum\limits^{\infty}_{n=-\infty}|X_n|^2\delta(f-\frac{n}{T})
$$

## Linear Time-Invariant System

For a linear time-invariant system $y(t)$ with input $x(t)$ and impulse response $h(t)$,
$$
S_y(f) = S_x(f)|H(f)|^2
$$


# Autocorrelation Function

The **Autocorrelation** $R_x(T)$ of a signal $x(t)$ is defined as,
$$
R_x(\tau) = \lim\limits_{T \to \infty}\frac{1}{T}\int\limits^{\frac{T}{2}}_{-\frac{T}{2}}x^*(t)x(t+\tau)dt
$$

## Periodic Signals

In the special case where $x(t)$ is a periodic signal, the Autocorrelation is defined as,
$$
R_x(\tau) = \sum\limits^{\infty}_{n = -\infty}|X_n|^2e^{j\frac{2n\pi}{T}\tau}
$$

## Wiener-Khinchin Theorem

The inverse Fourier transform of the Power Spectral Density of signal $x(t)$ is equal to the Autocorrelation of signal $x(t)$:
$$
R_x(\tau) = \mathcal{F}^{-1}\{S_x(f)\}
$$

## Linear Time-Invariant System

For a linear time-invariant system $y(t)$ with input $x(t)$ and impulse response h(t),
$$
R_y(\tau) = R_x(\tau) * h(\tau) * h^*(-\tau)
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
R_{xy}(\tau) = \lim\limits_{T \to \infty}\frac{1}{T}\int\limits^{\frac{T}{2}}_{-\frac{T}{2}}x^*(t)y(t+\tau)dt
$$
The Crosscorrelation Function measures the *similarity* between two signals. $R_{xy}(\tau) = 0$ implies $x(t)$ and $y(t)$ are uncorrelated.
