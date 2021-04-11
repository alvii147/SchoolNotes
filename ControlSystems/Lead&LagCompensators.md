# Lead Compensators

## Definition

Consider a unity feedback system with reference signal $\large r(t)$, output signal $\large y(t)$, plant $\large P(s)$ and controller $\large C(s)$.

![Unity feedback block diagram](img/ReferenceTracking/UnityFeedbackDark.png)

A lead compensator controller $\large C(s)$ is of the form:
$$
\Large C(s) = K_c \frac{s + z}{s + p}
$$
where $\large p > z$.

By setting $\large z = \alpha p$ and $\large K = K_c \alpha$ where $\large 0 \lt \alpha \lt 1$, we can rewrite it in Bode form:
$$
\Large C(s) = K \frac{\frac{s}{\alpha p} + 1}{\frac{s}{p} + 1}
$$
Lead compensation **approximates a PD controller**, is used to **stabilize a system** and **improve the transient response (i.e improve phase margin).**

## Design

Steps to design a lead compensator under given specifications:

1. Choose $\large K$ to meet a steady state error specification
2. Find phase margin of $\large KP(s)$ (either analytically or from the Bode plot)
3. Find how much extra phase is required to meet the phase margin specification. Set $\large \phi_{max}$ to be the required phase + an additional $\large 10^\circ$
4. Find $\large \alpha = \frac{1 - sin(\phi_{max})}{1 + sin(\phi_{max})}$
5. Set $\large \omega_{max}$ to be $\large \omega_{cg}$ of $\large KP(s)$ and calculate $\large p = \frac{\omega_{max}}{\sqrt{\alpha}}$ and $\large z = \sqrt{\alpha} \omega_{max}$
6. Check if the compensator achieves the specifications. If not, iterate.

# Lag Compensators

## Definition

Consider a unity feedback system with reference signal $\large r(t)$, output signal $\large y(t)$, plant $\large P(s)$ and controller $\large C(s)$.

![Unity feedback block diagram](img/ReferenceTracking/UnityFeedbackDark.png)

A lag compensator controller $\large C(s)$ is of the form:
$$
\Large C(s) = K_c \frac{s + z}{s + p}
$$
where $\large z > p$.

By setting $\large z = \beta p$ where $\large \beta \gt 1$, we can rewrite it in Bode form:
$$
\Large C(s) = K_c \beta \frac{\frac{s}{\beta p} + 1}{\frac{s}{p} + 1}
$$
Lag compensation **approximates a PI controller**, is used to **boost the DC gain.**

## Design

Steps to design a lead compensator under given specifications:

1. Choose $\large K_c$ to meet the phase margin specification (with $10^\circ$ buffer) by moving $\large \omega_{cg}$ to the left
2. Find the low frequency gain of $\large K_cP(s)$, and determine how much extra gain $\large \beta$ is needed for tracking specification
3. Choose $\large z = \beta p$ to be one decade below $\large \omega_{cg}$ of $\large K_cP(s)$
4. Choose $\large p = \frac{z}{\beta}$
5. Check if the compensator achieves the specifications. If not, iterate.