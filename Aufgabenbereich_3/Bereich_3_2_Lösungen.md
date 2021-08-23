# Informations und Kommunkationstherorie - Aufgabensammlung Lösungen

## 3. Übertragungskanal

### 3.2. Kanalkapazität bei diskreter Quelle

#### Aufgabe 1

Es handelt sich um einen binären Kanal (also Z = 2), bei dem die Wahrscheinlichkeit, dass das Zeichen sich ändert (0 -> 1 oder 1 -> 0) gleich $p_s$ ist.

GESICHERTE ÜBERTRAGUNG

a)
$$
\begin{align*}
p_s &= 0.02 , N = 64 , f_Q = 100 \frac{QZ}{s}\\
\\ 
H(Y|X) &= 2 \cdot \frac{1}{2} \cdot (0.02 \cdot \log_2 \frac{1}{0.02} + 0.98 \cdot \log_2 \frac{1}{0.98})\\
&= 0.141 \frac{bit}{KZ} \\
\\
H_T &= H(Y) - H(Y|X) = 1 \frac{bit}{KZ} - 0.141 \frac{bit}{KZ} = 0.859 \frac{bit}{KZ} \\
\\
l &= \lceil \log_2 N \rceil = \lceil \log_2 64 \rceil = 6 \frac{KZ}{QZ}\\
\\
H_K &= \log_2 2 = 1 \frac{bit}{KZ} \\
\\
v_s &= f_q \cdot l \cdot \frac{H_K}{H_T} = 100 \frac{QZ}{s} \cdot 6 \frac{KZ}{QZ} \cdot \frac{1 \frac{bit}{KZ}}{0.859 \frac{bit}{KZ}} \\
&= 698 \frac{KZ}{s}
\end{align*}
$$
b)
$$
I_T = v_s \cdot H_T = 698 \frac{KZ}{s} \cdot 0.859 \frac{bit}{KZ} = 600 \frac{bit}{s}
$$
c)
$$
\begin{align*}
Kapazitätsauslastung: A  \\
\\
A &= \frac{I_T}{C} \cdot 100\% = \frac{v_s \cdot H_T}{2B \cdot H_T} \cdot 100 \% = \frac{v_s}{2B} \cdot 100 \% \\
A &= \frac{698.5}{2 \cdot 2 \cdot 10^3} \cdot 100 \% = 17.5 \% 
\end{align*}
$$


UNGESICHERTE ÜBERTRAGUNG

a)
$$
v_s = f_Q \cdot l = 100 \frac{QZ}{s} \cdot 6 \frac{KZ}{QZ} = 600 \frac{KZ}{s}
$$
b)
$$
I_T = v_s \cdot H_T = 600 \frac{KZ}{s} \cdot 0.859 \frac{bit}{KZ} = 515,4 \frac{bit}{s}
$$
c)
$$
A = \frac{v_s}{2B} \cdot 100 \% = \frac{600}{2 \cdot 2 \cdot 10^3} \cdot 100\% = 15 \%
$$


#### Aufgabe 2

a)
$$
\begin{align*}
f_Q &= \frac{1}{t_ü} = \frac{1}{10} = 0.1 \frac{Bild}{s} \\
\\
I_{KQ} &\leq C \\
f_Q \cdot l \cdot H_K &\leq C \\
l &\leq \frac{C}{f_Q \cdot H_K} \leq \frac{50 \cdot 10^3}{0.1 \cdot 1} \\
l &\leq 500000 \frac{KZ}{Bild} \\
l &\leq 5 \frac{KZ}{Bildpunkt} => 2^5 = 32 = N
\end{align*}
$$
b)
$$
\begin{align*}
f_Q &\leq \frac{C}{l \cdot H_K} \leq \frac{50 \cdot 10^3}{6 \cdot 10^5 \cdot 1} \\
&\leq 0.083 \\
\\
t_ü &= \frac{1}{f_Q} = \frac{1}{0.083} = 12 \frac{s}{Bild}  
\end{align*}
$$
c)

Zur Berechnung der mittleren Codewortlänge siehe Abbildung. 

![2_3](/home/tieschne/Dokumente/Seafile/Studium/4_Semester/1_IKT/LösungenAufgabensammlung/Aufgabenbereich_3/2_3.png)
$$
\begin{align*}
l_m &= 2 \\
\\
f_Q &\leq \frac{C}{l_m \cdot H_K} \leq \frac{50 \cdot 10^3}{2 \cdot 10^5 \cdot 1} \\
& \leq 0.25 \\
\\
t_ü &= \frac{1}{f_Q} = \frac{1}{0.25} = 4 \frac{s}{Bild} 
\end{align*}
$$


#### Aufgabe 3

$gegeben: p_s = 0.02 , v_ü = 2400 \frac{bit}{s}, H_Q = 8 \frac{bit}{QZ}, \mbox{QZ gleichverteilt}, H_K = 1$

$gesucht: f_{Q,ges} \mbox{ und } f_{Q,unges}$



UNGESICHERT:
$$
\begin{align*}
I_K &= v_ü = v_s \cdot H_K  \\ 
\to I_K &= v_s = 2400 \frac{bit}{s} \\
\\
I_{KQ} &= f_Q \cdot l \cdot H_K \\ \\
\to \mbox{wegen } H_Q &= l \cdot H_K \mbox{ und } I_Q = f_Q \cdot H_Q \\
\to I_{KQ} &= f_Q \cdot H_Q \\
\\
\to f_Q &= \frac{I_{KQ}}{H_Q} = \frac{2400}{8} \\
f_{Q,unges} &= 300 \frac{QZ}{s} \\
\\
\Delta l_{unges} &= 0
\end{align*}
$$


GESICHERT:
$$
\begin{align*}
H_T &= 0,86 \mbox{ (Berechnung wie in Aufgabe 1 mit } p_s= 0.02 \mbox{ und } p(x_0)= p(x_1)= 0,5 \\
\\
l &\geq \lceil \frac{H_Q}{H_K} \rceil \geq 8 \\
&\to l = 8 \mbox{ Annahme der Gleichheit, weil maximale Frequenz gesucht ist} \\
\\
v_s &= f_Q \cdot l \cdot \frac{H_K}{H_T} \\
\to f_Q &= \frac{v_s \cdot H_T}{l \cdot H_K} = \frac{2400 \cdot 0.86}{8}\\
f_{Q,ges} &= 258 \frac{QZ}{s} \\
\\
n &= l + (\frac{H_k}{H_T} - 1) \cdot l = 8 + (\frac{1}{0.86} - 1) \cdot 8 = 9,3 \\
\Delta l &= n - l = 9,3 - 8 = 1,3 \frac{KZ}{QZ}
\end{align*}
$$
