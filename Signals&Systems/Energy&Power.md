# Energy Signals

The **Average Energy** $E_x$ of a signal $x(t)$ is defined as,
$$
\Large E_x = \int\limits^{\infty}_{-\infty} |x(t)|^2dt
$$
If $0<E_x<\infty$, then $x(t)$ is an **Energy Signal.**

# Power Signals

The **Average Power** $P_x$ of a signal $x(t)$ is defined as,
$$
\Large P_x = \lim\limits_{T \to \infty}\frac{1}{T}\int\limits^{\frac{T}{2}}_{-\frac{T}{2}}|x(t)|^2dt
$$
If $0<P_x<\infty$, then $x(t)$ is a **Power Signal.**

**NOTE:** a signal cannot be both an energy and a power signal. It can, however, be neither.

# Energy Spectral Density

The **Energy Spectral Density** $\Psi_x(f)$ of a signal $x(t)$ is defined as,
$$
\Large \Psi_x(f) = |X(f)|^2
$$

# Power Spectral Density

The **Power Spectral Density** $S_x(f)$ of a signal $x(t)$ is defined as,
$$
\Large S_x(f) = \lim\limits_{T \to \infty} \frac{1}{T}|X_T(f)|^2
$$
where, $X_T(f)$ is the Fourier transform of $x_T(t)$ and,
$$
\Large x_T(t) = x(t)\Pi(\frac{t}{T})
$$
In other words, $x_T(t)$ is the function that has value $x(t)$ for $-\frac{T}{2}<t<\frac{T}{2}$ and $0$ for all other values of $t$:
$$
\Large x_T(t) = 
\begin{cases}
x(t),&if\:\:-\frac{T}{2}<t<\frac{T}{2} \\[5pt]
0,&otherwise
\end{cases}
$$

## Periodic Signals
In the special case where $x(t)$ is a periodic signal, the Average Power is defined as,
$$
\Large P_x=\sum\limits^{\infty}_{n=-\infty}|X_n|^2
$$
and the Power Spectral Density is defined as,
$$
\Large S_x(f)=\sum\limits^{\infty}_{n=-\infty}|X_n|^2\delta(f-\frac{n}{T})
$$

## Linear Time-Invariant System

For a linear time-invariant system $y(t)$ with input $x(t)$ and impulse response $h(t)$,
$$
\Large S_y(f) = S_x(f)|H(f)|^2
$$