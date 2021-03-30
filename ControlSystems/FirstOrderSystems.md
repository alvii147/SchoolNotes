# First Order Systems

## Transfer function

$$
\Large H(s) = \frac{b_0}{s+a_0},\:\:\:\:a_0 \ne 0
$$

## Step Response

Frequency response:
$$
\begin{align*}
\Large Y(s) &\Large= H(s)U(s) \\[15pt]
&\Large= \frac{b_0}{s+a_0}\times\frac{1}{s} \\[15pt]
&\Large= \frac{b_0}{a_0}(\frac{1}{s} - \frac{1}{s+a_0})
\end{align*}
$$
Taking the Laplace transform:
$$
\Large y(t) = \frac{b_0}{a_0}(1 - e^{-a_0t}),\:\:\:\:t\ge0
$$

## Performance Measures

### Rise Time, $t_r$

**Rise time** is the time required to go from 10% to 90% of the final value.
$$
\Large t_r = \frac{ln(9)}{a_0}
$$

### Settling Time, $t_s$

**Settling time** is the time required to get within 2% of the final value and stay there.
$$
\Large t_s \approx \frac{3.91}{a_0}
$$

### Time Constant, $\tau$

**Time constant** is the time at which output becomes $\frac{b_0}{a_0}(1-e^{-1})$, i.e. roughly 63% of the final value.
$$
\Large \tau = \frac{1}{a_0}
$$

### Bandwidth, $\omega_{BW}$

**Bandwidth** is the frequency where,
$$
\Large |H(j\omega_{BW})| = \frac{1}{\sqrt{2}}H(0)
$$
For a first order system,
$$
\Large \omega_{BW} = a_0
$$
