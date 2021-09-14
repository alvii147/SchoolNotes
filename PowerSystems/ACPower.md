# AC Power

## Magnitude & Root-Mean-Square Voltage & Current

The **magnitude voltage** $\large V_m$ and **magnitude current** $\large I_m$ are defined as peak values of voltage and current respectively.

The **root-mean-square voltage** $\large V_{rms}$ and **root-mean-square current** $\large I_{rms}$ are then defined as:
$$
\Large V_{rms} = \sqrt{\frac{1}{T} \int\limits^T_0 (v(t))^2 dt} \\[15pt]
\Large I_{rms} = \sqrt{\frac{1}{T} \int\limits^T_0 (i(t))^2 dt}
$$
where $\large v(t)$ and $\large i(t)$ are voltage and current as functions of time respectively.

For a sinusoidal voltage and current:
$$
\Large V_{rms} = \frac{1}{\sqrt{2}} V_{rms} \\[10pt]
\Large I_{rms} = \frac{1}{\sqrt{2}} I_{rms}
$$

## Complex Power

Consider an AC power system with an AC voltage $\large \vec{V}$ across it and an AC current $\large \vec{I}$ flowing through it, such that:
$$
\Large \vec{V} = V_m \angle{\theta_v} = \sqrt{2} V_{rms} \angle{\theta_v} \\
\Large \vec{I} = I_m \angle{\theta_i} = \sqrt{2} I_{rms} \angle{\theta_i}
$$
where $\large V_m$ and $\large I_m$ are magnitude voltage and current respectively,  $\large V_{rms}$ and $\large I_{rms}$ are root-mean-square voltage and current respectively, and $\large \theta_v$ and $\large \theta_i$ are voltage and current phase angles respectively.

Then, the **apparent power** $\large \vec{S}$ of the system is given by:
$$
\Large \vec{S} = P + jQ = \vec{V} \vec{I}^*
$$
where $\large P$ and $\large Q$ are the **real power** and **reactive power** respectively. They are given by:
$$
\Large P = \frac{V_m I_m}{2} cos(\phi) = V_{rms} \: I_{rms} \: cos(\phi) \\[15pt]
\Large Q = \frac{V_m I_m}{2} sin(\phi) = V_{rms} \: I_{rms} \: sin(\phi)
$$
where $\large \phi$ is the phase difference between voltage and current:
$$
\Large \phi = \theta_v - \theta_i
$$
The **power factor** $\large pf$ is given by:
$$
\Large pf = cos(\phi) = \frac{P}{\abs{S}} \\[10pt]
\Large \theta_v - \theta_i < 0 \implies \text{leading power factor} \\
\Large \theta_v - \theta_i > 0 \implies \text{lagging power factor}
$$
