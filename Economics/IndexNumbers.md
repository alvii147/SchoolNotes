# Index Numbers

## Quantity Index Numbers

### Paasche Quantity Index

$$
\huge PQ_{t/0} = \frac{\sum^N_{i = 1} P_{\color{yellow}it}Q_{\color{yellow}it}}{\sum^N_{i = 1} P_{\color{yellow}it}Q_{\color{pink}i0}} \times 100
$$

### Laspeyres Quantity Index

$$
\huge LQ_{t/0} = \frac{\sum^N_{i = 1} P_{\color{pink}i0}Q_{\color{yellow}it}}{\sum^N_{i = 1} P_{\color{pink}i0}Q_{\color{pink}i0}} \times 100
$$

### Chained Quantity Index

$$
\LARGE CPQ_{t/0} = PQ_{1/0} \times PQ_{2/1} \times PQ_{3/2} \times ... \times PQ_{t/t-1} \times 100
$$

$$
\LARGE CLQ_{t/0} = LQ_{1/0} \times LQ_{2/1} \times LQ_{3/2} \times ... \times PQ_{t/t-1} \times 100
$$

### Fisher Quantity Index

$$
\LARGE FQ_{t/0} = \sqrt{PQ_{t/0} \times LQ_{t/0}} \times 100
$$

$$
\LARGE CFQ_{t/0} = \sqrt{CPQ_{t/0} \times CLQ_{t/0}} \times 100
$$

## Price Index Numbers

### Paasche Price Index

$$
\huge PP_{t/0} = \frac{\sum^N_{i = 1} P_{\color{yellow}it}Q_{\color{yellow}it}}{\sum^N_{i = 1} P_{\color{pink}i0}Q_{\color{yellow}it}} \times 100
$$

### Laspeyres Price Index

$$
\huge LP_{t/0} = \frac{\sum^N_{i = 1} P_{\color{yellow}it}Q_{\color{pink}i0}}{\sum^N_{i = 1} P_{\color{pink}i0}Q_{\color{pink}i0}} \times 100
$$

### Chained Price Index

$$
\LARGE CPP_{t/0} = PP_{1/0} \times PP_{2/1} \times PP_{3/2} \times ... \times PP_{t/t-1} \times 100
$$

$$
\LARGE CLP_{t/0} = LP_{1/0} \times LP_{2/1} \times LP_{3/2} \times ... \times LP_{t/t-1} \times 100
$$

### Fisher Quantity Index

$$
\LARGE FP_{t/0} = \sqrt{PP_{t/0} \times LP_{t/0}} \times 1000
$$

$$
\LARGE CFP_{t/0} = \sqrt{CPP_{t/0} \times CLP_{t/0}} \times 100
$$