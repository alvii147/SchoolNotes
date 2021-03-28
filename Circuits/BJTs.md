# Bipolar Junction Transistors (NPN)

## Symbol

<img src = "img/npn/npnbjt_light.png" alt = "NPN BJT Symbol" width = "350px">

## Active Mode

### Conditions:

$$
\Large
V_C \gt V_B \gt V_E
$$

### Equations:

$$
\Large
V_{BE} = 0.7\:\text{V} \\[25pt]
\Large
I_C = I_Se^{\frac{V_{BE}}{V_T}} \\[25pt]
\Large
I_B = \frac{1}{\beta}I_Se^{\frac{V_{BE}}{V_T}} \\[25pt]
\Large
I_E = I_C + I_B \\[25pt]
\Large
I_C = \beta I_B \\[25pt]
\Large
I_E = \frac{I_C}{\alpha} \\[25pt]
\Large
\alpha = \frac{\beta}{\beta + 1}
$$

## Saturations Mode

### Conditions:

$$
\Large
V_E \lt V_B \\[25pt]
\Large
V_C \lt V_B \\[25pt]
\Large
\frac{I_C}{I_B} \lt \beta
$$

### Equations:

$$
\Large
V_{BE} = 0.7\:\text{V} \\[25pt]
\Large
V_{CEsat} = 0.2\:\text{V}
$$

## Large Signal Model

<img src = "img/npn/npnbjt_large_signal.png" alt = "NPN BJT Large Signal" width = "400px">

<img src = "img/npn/npnbjt_large_signal2.png" alt = "NPN BJT Large Signal" width = "400px">

## Small Signal Model

### $\pi$-model

<img src = "img/npn/npn_smallsignal_pi_gm.png" alt = "BJT Small Signal Pi" width = "400px">

<img src = "img/npn/npn_smallsignal_pi_B.png" alt = "BJT Small Signal Pi" width = "400px">
$$
\Large
g_m = \frac{I_C}{V_T} \\[25pt]
\Large
r_\pi = \frac{V_T}{I_B} = \frac{\beta}{g_m} \\[25pt]
\Large
r_o = \frac{V_A}{I_C}
$$


### T-model

<p style = "text-align: center;">
<img src = "img/npn/npn_smallsignal_t_gm.png" alt = "BJT Symbol" width = "300px">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src = "img/npn/npn_smallsignal_t_a.png" alt = "BJT Symbol" width = "300px">
</p>

$$
\Large
g_m = \frac{I_C}{V_T} \\[25pt]
\Large
r_e = \frac{V_T}{I_E} = \frac{\alpha}{g_m} \\[25pt]
\Large
r_o = \frac{V_A}{I_C}
$$


# Bipolar Junction Transistors (PNP)

## Symbol

<img src = "img/pnp/pnpbjt_light.png" alt = "BJT Symbol" width = "350px">

## Active Mode

### Conditions:

$$
\Large
V_E \gt V_B \gt V_C
$$

### Equations:

$$
\Large
V_{EB} = 0.7\:\text{V} \\[25pt]
\Large
I_C = I_Se^{\frac{V_{EB}}{V_T}} \\[25pt]
\Large
I_B = \frac{1}{\beta}I_Se^{\frac{V_{EB}}{V_T}} \\[25pt]
\Large
I_C = I_E + I_B \\[25pt]
\Large
I_C = \beta I_B \\[25pt]
\Large
I_E = \frac{I_C}{\alpha} \\[25pt]
\Large
\alpha = \frac{\beta}{\beta + 1}
$$

## Saturations Mode (PNP)

### Conditions:

$$
\Large
V_B \lt V_E \\[25pt]
\Large
V_B \lt V_E \\[25pt]
\Large
\frac{I_C}{I_B} \lt \beta
$$

### Equations:

$$
\Large
V_{EB} = 0.7\:\text{V} \\[25pt]
\Large
V_{CEsat} = 0.2\:\text{V}
$$

## Large Signal Model

<img src = "img/pnp/pnpbjt_large_signal.png" alt = "BJT Symbol" width = "400px">

<img src = "img/pnp/pnpbjt_large_signal2.png" alt = "BJT Symbol" width = "400px">