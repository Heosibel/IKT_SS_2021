# Informations und Kommunkationstherorie - Aufgabensammlung Lösungen

## 3. Übertragungskanal



### 3.1. Diskrete Kanalmodelle

#### Aufgabe 1

a)

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_3/1_1.png" alt="1_1" style="zoom: 33%;" />
$$
\begin{align*}
p(y_0) &= 0.5 \cdot 0.9 + 0.5 \cdot 0.1 = 0.5 \\ 
p(y_1) &= 0.5 \cdot 0.9 + 0.5 \cdot 0.1 = 0.5 \\
\\
H(Y) &= \log_2 2 = 1 \frac{bit}{KZ} \\
\\
H(Y|X) &= \sum_i p(x_i) \cdot ( \sum_j p(y_j|x_i) \cdot log_2 \frac{1}{p(y_j|x_i)}) \frac {bit}{KZ} \\
&= 2 \cdot 0.5 \cdot (0.9 \cdot \log_2 \frac{1}{0.9} + 0.1 \log_2 \frac{1}{0.1})  \\
&= 0.47 \frac{bit}{KZ} \\
\\
H_T &= H(Y) - H(Y|X) \\ &= 0.53 \frac{bit}{KZ}

\end{align*}
$$
b)
$$
\begin{align*}
p(y_0) &= 0.2 \cdot 0.9 + 0.8 \cdot 0.1 = 0.26 \\
p(y_1) &= 0.8 \cdot 0.9 + 0.2 \cdot 0.1 = 0.74 \\
\\
H(Y) &= \sum_{j=1}^{M} p(y_j) \cdot log_2 \frac {1}{p(y_j)} \\
&= 0.26 \cdot \log_2 \frac{1}{0.26} + 0.74 \cdot \log_2 \frac{1}{0.74} \\
&= 0.83 \\
\\
H(Y|X) &= \sum_i p(x_i) \cdot ( \sum_j p(y_j|x_i) \cdot log_2 \frac{1}{p(y_j|x_i)}) \\
&= 0.2 \cdot (0.9 \cdot \log_2 \frac{1}{0.9} + 0.1 \cdot \log_2 \frac{1}{0.1}) + 0.8 \cdot (0.1 \cdot \log_2 \frac{1}{0.1} + 0.9 \cdot \log_2 \frac{1}{0.9}) \\
&= 0.47 \\
\\
H_T &= 0.36 \frac{bit}{KZ}
\end{align*}
$$

#### Aufgabe 2

a)

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_3/2_1.png" alt="2_1" style="zoom:33%;" />
$$
\begin{align*}
p(y_0) &= 0.5 \cdot 0.5 = 0.25 \\
p(y_1) &= 1 - p(y_0) = 0.75 \\
\\
H(Y) &= 0.75 \cdot \log_2 \frac{1}{0.75} + 0.25 \cdot \log_2 \frac{1}{0.25} \\
&= 0.81 \\
\\
H(Y|X) &= 0.5 \cdot (0.5 \cdot \log_2 \frac{1}{0.5} + 0.5 \cdot \log_2 \frac{1}{0.5}) + 0.5 \cdot (1 \cdot \log_2 \frac{1}{1}) \\
&= 0.5 \\
\\
H_T &= 0.81 - 0.5 = 0.31 \frac{bit}{KZ} 
\end{align*}
$$
b)
$$
\begin{align*}
p(y_0) &= 0.5 \cdot \frac{4}{5} = 0.4 \\
p(y_1) &= 1 - p(y_0) = 0.6 \\
\\
H(Y) &= 0.4 \cdot \log_2 \frac{1}{0.4} + 0.6 \cdot \log_2 \frac{1}{0.6} \\
&= 0.97 \\
\\
H(Y|X) &= \frac{4}{5} \cdot (2 \cdot 0.5 \cdot \log_2 \frac{1}{0.5}) + \frac{1}{5} \cdot (1 \cdot \log_2 1) \\
&= 0.8 \\
\\
H_T &= 0.97 - 0.8 = 0.17 \frac{bit}{KZ} 
\end{align*}
$$


c)
$$
\begin{align*}
p(y_0) &= 0.5 \cdot \frac{9}{10} = 0.45 \\
p(y_1) &= 1 - p(y_0) = 0.55 \\
\\
H(Y) &= 0.45 \cdot \log_2 \frac{1}{0.45} + 0.55 \cdot \log_2 \frac{1}{0.55} \\
&= 0.99 \\
\\
H(Y|X) &= \frac{9}{10} \cdot (2 \cdot 0.5 \cdot \log_2 \frac{1}{0.5}) + \frac{1}{10} \cdot (1 \cdot \log_2 1) \\
&= 0.9 \\
\\
H_T &= 0.99 - 0.9 = 0.09 \frac{bit}{KZ} 
\end{align*}
$$

#### Aufgabe 3

a)

- Da $H(Y)$ maximal sein soll ist $p(y_0) = 0.5 = p(y_1)$

- Zur Berechnung von $p(x_0)$ und $p(x_1)$ wird ein LGS aufgestellt und gelöst

LGS
$$
\begin{align*}
p(y_0) &= 0.8 \cdot p(x_0) \\
p(y_1) &= 0.2 \cdot p(x_0) + 1 \cdot p(x_1) \\
\hline 
p(x_0) &= \frac{p(y_0)}{0.8} = \frac{0.5}{0.8} = 0.625 \\
p(x_1) &= 1 - p(x_0) = 0.375
\end{align*}
$$
b)
$$
\begin{align*}
H(Y|X) &= 0.625 \cdot (0.8 \cdot \log_2 \frac{1}{0.8} + 0.2 \cdot \log_2 \frac{1}{0.2}) + 0.375 \cdot (1 \cdot \log_2 1) \\
&= 0.45 \\
\\ 
H(Y) &= 2 \cdot 0.5 \cdot \log_2 2 \\
&= 1\\
\\
H_T &= 1 - 0.45 = 0.55 \frac{bit}{KZ}
\end{align*}
$$
c)
$$
\begin{align*}
p(y_0) &= 0.5 \cdot 0.8 = 0.4\\
p(y_1) &= 0.5 \cdot 0.2 + 0.5 \cdot 1 = 0.6 \\
\\
H(Y) &= 0.4 \cdot \log_2 \frac{1}{0.4} + 0.6 \cdot \log_2 \frac{1}{0.6} \\
 &= 0.97 \\
\\
H(Y|X) &= 0.5 \cdot (0.8 \cdot \log_2 \frac{1}{0.8} + 0.2 \cdot \log_2 \frac{1}{0.2}) + 0.5 \cdot (1 \cdot \log_2 1) \\
&= 0.36 \\
\\
H_T &= 0.97 - 0.36 = 0.61 \frac{bit}{KZ}
\end{align*}
$$

#### Aufgabe 4

a)
$$
\begin{align*}
p(y_0) &= 0.5 \cdot (1 - \epsilon - \delta) + 0.5 \cdot \epsilon = 0.5 \cdot (1-\delta) \\
p(y_1) &= 0.5 \cdot (1 - \epsilon - \delta) + 0.5 \cdot \epsilon = 0.5 \cdot (1-\delta) \\
p(y_{AZ}) &= 0.5 \cdot \delta \cdot 2 = \delta \\
\\
H(Y) &= 2 \cdot 0.5 \cdot (1 - \delta) \cdot \log_2 \frac{1}{0.5 \cdot (1 - \delta)} + \delta \cdot \log_2 \frac {1}{\delta} \\
&= (1 - \delta) \cdot \log_2 \frac{1}{0.5 \cdot (1 - \delta)} + \delta \cdot \log_2 \frac {1}{\delta} &| ausklammern\\
&= (1 - \delta) \cdot \log_2 2 + (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac {1}{\delta} &| kürzen \\
&= (1 - \delta) + (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac {1}{\delta} \\
\\
H(Y|X) &= 2 \cdot 0.5 \cdot ((1 - \epsilon - \delta) \cdot \log_2 \frac{1}{(1 - \epsilon - \delta)} + \delta \cdot \log_2 \frac{1}{\delta} + \epsilon \cdot \frac{1}{\epsilon}) \\
&= (1 - \epsilon - \delta) \cdot \log_2 \frac{1}{(1 - \epsilon - \delta)} + \delta \cdot \log_2 \frac{1}{\delta} + \epsilon \cdot \frac{1}{\epsilon}\\
\\
H_T &= H(Y) - H(Y|X) \\
&= ((1 - \delta) + (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac {1}{\delta} ) - ((1 - \epsilon - \delta) \cdot ld \frac{1}{(1 - \epsilon - \delta)} + \delta \cdot \log_2 \frac{1}{\delta} + \epsilon \cdot \frac{1}{\epsilon}) &| kürzen : \delta \cdot \log_2 \frac{1}{\delta}\\
&= (1 - \delta) + (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} - \epsilon \cdot \frac{1}{\epsilon} - (1 - \epsilon - \delta) \cdot \log_2 \frac{1}{(1 - \epsilon - \delta)}

\end{align*}
$$
b)

nur $H(Y |X)$ muss neu berechnet werden -> $H(Y), p(y_0), p(y_1), p(y_{AZ})$ bleiben gleich
$$
\begin{align*}
 H(Y|X) &= 2 \cdot 0.5 \cdot (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac{1}{\delta} \\
 &= (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac{1}{\delta} \\
 \\
 H_T &= (1 - \delta) + (1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac {1}{\delta} - ((1 - \delta) \cdot \log_2 \frac{1}{(1 - \delta)} + \delta \cdot \log_2 \frac{1}{\delta}) &| kürzen \\
 &= (1-\delta)
 
\end{align*}
$$
Man kann die Gleichung aus a) ableiten in dem $\epsilon = 0$ gesetzt wird. 



#### Aufgabe 5

Berchnung mittels $p(y_j|x_i)$:
$$
\begin{align*}
p(y_0) &= \frac{1}{3} \cdot 1 + \frac{1}{3} \cdot 1 = \frac{2}{3}\\
p(y_1) &= \frac{1}{3} \cdot 1 = \frac{1}{3}\\
p(y_2) &= 0 \\
\\
H(Y) &= \frac{1}{3} \cdot \log_2 3 + \frac{2}{3} \cdot \log_2 \frac{3}{2}
&= 0.918 \\
\\
H(Y|X) &= 3 \cdot \frac{1}{3} \cdot (1 \cdot \log_2 1) = 0 \\
\\
H_T &= 0.918 \\
\end{align*}
$$


Berechnung mittels $p(x_i|y_j)$:
$$
\begin{align*}
p(x_{i},y_{j}) &= p(x_i) \cdot p(y_{j}|x_{i}) \\

p(x_{i},y_{j}) &= 
\begin{pmatrix}
\frac{1}{3} &0 & 0 \\
0 & \frac{1}{3} & 0 \\
\frac{1}{3} & 0 & 0
\end{pmatrix} \\
\\
p(x_i|y_j) &= \frac {p(x_{i},y_{j})} {p(y_j)} \\
\\
p(x_i|y_j) &=
\begin{pmatrix}
0.5 &0 & 0 \\
0 & 1 & 0 \\
0.5 & 0 & 0
\end{pmatrix}\\
\\
p(x_0) &= 0.5 \cdot \frac{2}{3} = \frac{1}{3} \\
p(x_1) &= 1 \cdot \frac{1}{3} = \frac{1}{3} \\
p(x_2) &= 0.5 \cdot \frac{2}{3} = \frac{1}{3} \\
\\
H(X) &= \frac{1}{3} \cdot \log_2 3 \cdot 3 = 1.58 \\
\\
H(X|Y) &= \sum_j p(y_j) \cdot \sum_i p(x_i|y_j) \cdot log_2 \frac{1}{p(x_i|y_j)} \\
&= \frac{2}{3} \cdot (0.5 \cdot \log_2 2 + 0.5 \cdot \log_2 2) \\
&= \frac{2}{3}
\\
H_T &= H(Y) - H(Y|X) \\
&= 1.58 -  \frac{2}{3} \\
&= 0.92
\end{align*}
$$

Alle Eregnisse wurden gerundet! Bei genauerer Berechnung kann sich eine Differenz zum aktuellen Ergebiss ab der 2ten Stelle ergeben.
