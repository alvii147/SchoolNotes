# Steady State Waves

## Reflection Coefficient

The reflection coefficient $\large \Gamma_L$ in a transmission line is given by,
$$
\Large \Gamma_L = \frac{Z_L - Z_0}{Z_L + Z_0} = \rho e^{j\psi} \\[30pt]
\Large \rho = \sqrt{\frac{(R_L - Z_0)^2 + X_L^2}{(R_L + Z_0)^2 + X_L^2}} \\[30pt]
\Large \psi = arctan\Bigg(\frac{X_L}{R_L - Z_0}\Bigg) - arctan\Bigg(\frac{X_L}{R_L + Z_0}\Bigg)
$$
where $\large Z_0$ is the characteristic impedance and $\large Z_L = R_L + jX_L$ is the load impedance.

## Input Impedance

The input impedance $\large Z(z)$ at any point along a transmission line is given by,
$$
\Large Z(z) = Z_0 \frac{Z_L - jZ_0 tan(\beta z)}{Z_0 - jZ_Ltan(\beta z)} \\[20pt]
\Large \beta = \frac{2\pi}{\lambda}
$$
where $\large z$ is the negative distance from the load and $\large \lambda$ is the wavelength.

## Voltage Standing Wave Ratio

The voltage standing wave ratio $\large S$ is given by,
$$
\Large S = \frac{1 + \rho}{1 - \rho}
$$