# Informations und Kommunikationstheorie - Aufgabensammlung Lösung



## 2. Quellenkodierung

#### 1. Aufgabe

Shannon-Verfahren: 

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_1.png" alt="2_1" style="zoom:50%;" />

Huffmann-Verfahren

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_1_2.png" alt="2_1_2" style="zoom:50%;" />

Beide Verfahren ergeben die selben Codewörter, desshalb wird der Rechenweg nur einmal aufgeführt.
$$
\begin{align*}
R_k &= l_m \cdot H_k - H_m  \\ \\

l_m &= \sum_i p(x_i) \cdot l \\
&= 1 \cdot 0.5 + 2 \cdot 0.25 + 3 \cdot 0.125 + 4 \cdot \frac{1}{16} + 5 \cdot \frac{1}{32} \cdot2 \\
&= 0.5 + 0.5 + 0.375 + 0.25 + \frac{5}{32} * 2 \\
&= 1.9375 \frac{Bit}{QZ} \\ \\

H_m &= \sum p(x_i) \cdot \log_2 \frac{1}{p(x_i)} \\
&= \frac{1}{2} \cdot \log_2 \frac{1}{2}  + \frac{1}{4} \cdot \log_2 \frac{1}{4} + \frac{1}{8} \cdot \log_2 \frac{1}{8} + \frac{1}{16} \cdot \log_2 \frac{1}{16} + \frac{1}{32} \cdot \log_2 \frac{1}{32} \cdot 2 \\
&= 1.9375 = 1.94 \frac{bit}{QZ} \\
\\
H_k &= 1\\
\\
R_k &= 1.94 \cdot 1 -1.94 = 0

\end{align*}
$$

#### 2. Aufgabe

a)

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_2.png" alt="2_2" style="zoom:50%;" />
$$
\begin{align*}
l_m &= \sum_i p(x_i) \cdot l \\
&= 0.3 \cdot 1 + 0.15 \cdot 1 + 0.14 \cdot 3 + 0.12 \cdot 3 + 0.1 \cdot 4 + 0.06 \cdot 4+ 0.08 \cdot 4 + 0.06 \cdot 4 + 0.05 \cdot 4 \\
&= 2,84 \frac{Bit}{QZ} \\
\\
H_m &= \sum p(x_i) \cdot \log_2 \frac{1}{p(x_i)} \\
&= 0.3 \cdot \log_2 \frac{1}{0.3} + 0.15 \cdot \log_2 \frac{1}{0.15} + 0.14 \cdot \log_2 \frac{1}{0.14} + 0.12 \cdot \log_2 \frac{1}{0.12} + 0.1 \cdot \log_2 \frac{1}{0.1} + 0.06 \cdot \log_2 \frac{1}{0.06}+ 0.08 \cdot \log_2 \frac{1}{0.08} + 0.06 \cdot \log_2 \frac{1}{0.06} + 0.05 \cdot \log_2 \frac{1}{0.05} \\
&= 2,78 \frac{bit}{QZ} \\
\\
R_k &= l_m - H_m = 2.84 - 2.78 \\
&= 0.06 \frac{Bit}{QZ} 

\end{align*}
$$


b)

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_2_2.png" alt="2_2_2" style="zoom:50%;" />
$$
\begin{align*}
l_m &= \sum_i p(x_i) \cdot l \\
&= 0.3 \cdot 2 + 0.15 \cdot 3 + 0.14 \cdot 3 + 0.12 \cdot 3 + 0.1 \cdot 3 + 0.08 \cdot 3 + 0.06 \cdot 4 + 0.06 \cdot 4 + 0.05 \cdot 4 \\
&= 2,81 \frac{Bit}{QZ}\\
\\
H_m &= \sum p(x_i) \cdot \log_2 \frac{1}{p(x_i)} \\
&= 0.3 \cdot \log_2 \frac{1}{0.3} + 0.15 \cdot \log_2 \frac{1}{0.15} + 0.14 \cdot \log_2 \frac{1}{0.14} + 0.12 \cdot \log_2 \frac{1}{0.12} + 0.1 \cdot \log_2 \frac{1}{0.1} + 0.06 \cdot \log_2 \frac{1}{0.06}+ 0.08 \cdot \log_2 \frac{1}{0.08} + 0.06 \cdot \log_2 \frac{1}{0.06} + 0.05 \cdot \log_2 \frac{1}{0.05} \\
&= 2,78 \frac{bit}{QZ} \\
\\
R_k &= l_m - H_m = 2.81 - 2.78 \\
&= 0,03 \frac{Bit}{QZ} 
\end{align*}
$$


#### Aufgabe 3

(1) nicht eindeutig dekodierbar, da $a_4^*$ und  $a_7^*$ nicht präfixfrei sind. ( $a_4^*$  bildet den Anfang von  $a_7^*$)

(2) Ist eindeutig, da Präfixfreiheit besteht und sich ein Baum aufspannen lässt.



#### Aufgabe 4

a)

$ H_Q = 0.1 \cdot \log_2 \frac{1}{0.1} + 0.9 \cdot \log_2 \frac{1}{0.9} = 0.47 \frac{bit}{QZ} $



b)

$l_m = \lceil \log_2 N \rceil = 1$

$ R_k = 1 - 0.47 = 0.53 \frac{bit}{QZ}$



c)

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_4.png" alt="2_4" style="zoom:50%;" />



$l_m^{[2]} = 0.81 \cdot 1 + 0,09 \cdot 2 + 0,09 \cdot 2 + 0,01 \cdot 3 = 1,29 \\ => l_m = \frac{l_m^{[2]}}{2} = 0,645 \\ R_k = 0.645 - 0.47 \frac{bit}{QZ} = 0.175 \frac{bit}{QZ} $



d)

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_4_2.png" alt="2_4_2" style="zoom:50%;" />



$l_m^{[3]} = 0.729 \cdot 1 + 0.081 \cdot 3 \cdot 3 + 0.009 \cdot 5 \cdot 3 + 0.01 \cdot 5 = 1.598 \frac{KZ}{Block} \\ => l_m = \frac{l_m^{[3]}}{3} = 0.533 \\ R_k = 0.533 - 0.47 = 0.063 \frac{KZ}{QZ}$



e)

Bei einer Erweiterung der Blocklänge reduziert sich die Koderedundanz bis maximal $l_m = H_m$ .



#### Aufgabe 5

a)

Shannon-Verfahren:	<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_5.png" alt="2_5" style="zoom:50%;" />
$$
\begin{align*}

H_m &= 0.7 \cdot \log_2 \frac{1}{0.7} + 0.2 \cdot \log_2 \frac{1}{0.2} + 0.1 \cdot \log_2 \frac{1}{0.1} \\ 
&= 1.157 \\
\\
l_m &= 0.7 \cdot 1 + 0.2 \cdot 2 + 0.1 \cdot 2 \\ 
&= 1.3 \frac{KZ}{QZ} \\
\\
R_k &= l_m - H_m = 1.3 - 1.157 \\ 
&= 0.143 \frac{bit}{QZ} 


\end{align*}
$$


b)

Shannon-Verfahren: <img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_5_2.png" alt="2_5_2" style="zoom:50%;" />


$$
\begin{align*}
H_m &= 1.157 \\
\\
l_m^{[2]} &= 0.49 \cdot 1 + 0.14 \cdot 3 \cdot 2 + 0.07 \cdot 4 \cdot 2 + 0.04 \cdot 4 + 0.02 \cdot 5 + 0.02 \cdot 6 + 0.01 \cdot 6 \\
&= 2.33 \\
\\
l_m &= \frac{l_m^{[2]}}{2} = \frac{2.33}{2} \\
&= 1.165 \frac{KZ}{QZ} \\
\\
R_k &= l_m - H_m = 1.165 - 1.157 \\ 
&= 0.008 \frac{bit}{QZ} 


\end{align*}
$$
c)

- durch die paarweise Kodierung kann eine Minimierung der Redundanz erziehlt werden
- die max. Reduzierung ist auf $H_m$ als untere Schranke begrenzt  





#### Aufgabe 6

$$
\begin{align*}
H_m &= 0.8 \cdot \log_2 \frac{1}{0.8} + 0.2 \cdot \log_2 \frac{1}{0.2} \\ 
&= 0.7219 \\
\\
l &= \lceil \log_2 N \rceil \\ 
&= 1
\end{align*}
$$



a)

$m=2$

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_6.png" alt="2_6" style="zoom:50%;" />

$l_m^{[2]} = 0.64 \cdot 1 + 0.16 \cdot 2 + 0.16 \cdot 3 + 0.04 \cdot 3 = 1.56 \\ l_m = \frac {l_m^{[2]}}{2} = \frac {1.56}{2} = 0.78 $



$ m=3$

<img src="/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_2/2_6_2.png" alt="2_6_2" style="zoom:50%;" />

$l_m^{[3]} = 0.512 \cdot 1 + 0.128 \cdot 3 \cdot 3 + 0.032 \cdot 5 \cdot 3 + 0.008 \cdot 5 = 2.184 \\ l_m = \frac {l_m^{[3]}}{2} = \frac {2.184}{3} = 0.728 $



$=>$ für $m=3$ ist die Voraussetzung, erfüllt mit einer Einsparung von 27.2%



b)

Die maximale Reduzierung ist durch $H_m$ begrenzt, da $R_k$ nicht negativ sein darf $R_k = l_m - H_m$

$=>$ Einsparung um max 27,8%
