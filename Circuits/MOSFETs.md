# Metal-Oxide-Semiconductor Field-Effect Transistor (N-Channel)

## Symbol

<img src="img/nmos/nchannelmosfet_light.png" width="450px">

## Saturation Region

### Conditions:

$$
\Large
V_{GS} \gt V_t \\[15pt]
\Large
V_{DS} \gt V_{GS} - V_t
$$

### Equations:

$$
\Large
I_{DS} = \frac{1}{2}k_nV_{OV}^2 = \frac{1}{2}k_n(V_{GS}-V_t)^2
$$

### Where:

$$
\Large
V_t = \text{threshold voltage} \\[10pt]
\Large
V_{OV} = V_{GS} - V_t \\[10pt]
\Large
k_n = \mu_nC_{ox}\frac{W}{L}
$$



## Triode Region

### Conditions:

$$
\Large
V_{GS} \gt V_t \\[15pt]
\Large
V_{DS} \lt V_{GS} - V_t
$$



### Equations:

$$
\Large
\begin{align*}
I_{DS} &= k_n(V_{OV}-\frac{1}{2}V_{DS})V_{DS}\\
&= k_n((V_{GS}-V_t)V_{DS}-\frac{1}{2}V_{DS}^2)
\end{align*}
$$

### Where:

$$
\Large
V_t = \text{threshold voltage} \\[10pt]
\Large
V_{OV} = V_{GS} - V_t \\[10pt]
\Large
k_n = \mu_nC_{ox}\frac{W}{L}
$$

## Large Signal Model

<img src = "img/nmos/nmos_large_signal.png" alt = "NMOS Large Signal" width = "500px">

## Small Signal Model

### $\pi$-model

<img src = "img/nmos/nmos_smallsignal_pi.png" alt = "NMOS Small Signal Pi" width = "500px">

### T-model

<img src = "img/nmos/nmos_smallsignal_t.png" alt = "NMOS Small Signal T" width = "500px">

# Metal-Oxide-Semiconductor Field-Effect Transistor (P-Channel)

## Symbol

<img src="img/pmos/pchannelmosfet_light.png" width="450px">

## Saturation Region

### Conditions:

$$
\Large
V_{SG} \gt |V_{tp}| \\[15pt]
\Large
V_{SD} \gt V_{SG} - |V_{tp}|
$$

### Equations:

$$
\Large
I_{DS} = \frac{1}{2}k_n(V_{SG}-V_{tp})^2
$$

### Where:

$$
\Large
V_{tp} = \text{threshold voltage} \\[10pt]
\Large
k_n = \mu_nC_{ox}\frac{W}{L}
$$



## Triode Region

### Conditions:

$$
\Large
V_{SG} \gt V_{tp} \\[15pt]
\Large
V_{SD} \lt V_{SG} - V_{tp}
$$



### Equations:

$$
\Large
I_{DS} = k_n((V_{SG}-V_{tp})V_{SD}-\frac{1}{2}V_{SD}^2)
$$

### Where:

$$
\Large
V_{tp} = \text{threshold voltage} \\[10pt]
\Large
k_n = \mu_nC_{ox}\frac{W}{L}
$$

## Large Signal Model

<img src = "img/pmos/pmos_large_signal.png" alt = "PMOS Large Signal" width = "500px">