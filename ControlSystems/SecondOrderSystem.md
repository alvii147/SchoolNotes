# Second Order System

## Transfer Function

$$
\Large H(s) = \frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2},\:\:\:\:\omega_n\gt0
$$

### Poles

$$
\Large s = -\zeta\omega_n\pm\omega_n\sqrt{\zeta^2-1}
$$

where $\zeta$ is the **damping ratio** and $\omega_n$ is the **undamped natural frequency.**

**Underdamped System:** $0\ge\zeta<1$

**Critically Damped System:** $\zeta=1$

**Overdamped System:** $\zeta\gt1$

## Underdamped & Critically Damped System, $0\ge\zeta\ge1$

Define poles at,
$$
\Large s = -\sigma\pm j\omega_d
$$
such that,
$$
\Large \sigma = \zeta\omega_n,\:\:\:\:\omega_d=\omega_n\sqrt{1-\zeta^2}
$$
where $\omega_d$ is the **damped natural frequency.**

The transfer function becomes:
$$
\Large H(s) = \frac{\omega_n^2}{(s+\sigma+j\omega_d)(s+\sigma-j\omega_d)} = \frac{\omega_n^2}{(s+\sigma)^2+\omega_d}
$$

### Step Response

$$
\Large y(t) = 1 - e^{-\sigma t}(cos(\omega_dt) + \frac{\sigma}{\omega_d}sin(\omega_d t))
$$

## Overdamped System, $\zeta\gt1$

Poles are at,
$$
\Large -\zeta\omega_n\pm\omega_n\sqrt{\zeta^2-1}
$$
The transfer function becomes:
$$
\Large H(s) = \frac{\omega_n^2}{(s+\zeta\omega_n+\omega_n\sqrt{\zeta^2-1})(s+\zeta\omega_n-\omega_n\sqrt{\zeta^2-1})}
$$

### Step Response

$$
\Large y(t) = 1 - k_1e^{(-\zeta\omega-\omega_n\sqrt{\zeta^2-1})t} - k_2e^{(-\zeta\omega+\omega_n\sqrt{\zeta^2-1})t}
$$

For some constants $k_1$ and $k_2$.

## Performance Measures

### Rise Time, $t_r$

**Rise time** is the time required to go from 10% to 90% of the final value.
$$
\Large t_r \approx \frac{2.16\zeta + 0.6}{\omega_n}
$$
which is good for $0.3 \gt \zeta \gt 0.8$.

Cruder approximation:
$$
\Large t_r \approx \frac{1.8}{\omega_n}
$$

### Peak Time, $t_p$

**Peak time** is the time at which the maximum value is reached.
$$
\Large t_p = \frac{\pi}{\omega_d} = \frac{\pi}{\omega_n\sqrt{1-\zeta^2}}
$$

### Peak Value, $M_p$

**Peak value** is the maximum value the output reaches.
$$
\Large M_p = 1+e^{-\sigma \frac{\pi}{\omega_d}} = 1+e^{-\frac{\pi\zeta}{\sqrt{1-\zeta^2}}}
$$

### Overshoot Percentage, $\%OS$

**Overshoot​ percentage** is the percentage by which the response overshoots from the steady state value in the first peak.
$$
\Large \%OS = e^{-\frac{\pi\zeta}{\sqrt{1-\zeta^2}}}\times100
$$


### Settling Time, $t_s$

**Settling time** is the time required to get within 2% of the final value and stay there.
$$
\Large t_s \approx \frac{4}{\sigma} = \frac{4}{\zeta\omega_n}
$$
