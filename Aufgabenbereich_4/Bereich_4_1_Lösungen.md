# Informations und Kommunkationstherorie - Aufgabensammlung Lösungen

## 4. Kanalkodierung



### 4.1. Lineare Gruppenkodes, HAMMING-Kodes

#### Aufgabe 1

a) Prüfen ob die Axiome erfüllt sind

- Abgeschlossenheit: 
  - $\forall a_i , a_j \in A: a_i \oplus a_j = a_k \in A$ 
  - nicht erfüllt da $a_1 \oplus a_2 \notin A$
- Assoziativität: 
  - erfüllt
- inverses Element: 
  - $ \forall a_i \in A: a_i \oplus -a_i = 0$
  - erfüllt: alle Elemente sind zu sich selbst invers
- neutrales Element: 
  - 000000 (Nullvektor) 
  - $ \exist e \in A \forall a_i \in A: a_i \oplus e = a_i$
  - nicht enthalten deshalb ist es kein Linearcode

b) $d_{min} = 1$ 
$$
\begin{array}{rcl}
a_6 &=& (000110) \\
\oplus a_9 &=& (000111) \\
\hline
&=& (000001) \rightarrow  d_{min} = 1
\end{array}
$$
Fehlererkennung: $f_e = d_{min} - 1 = 0$

$\rightarrow$ es sind auch Einfachfehler nicht mit Sicherheit erkennbar, z.B. 
$$
\begin{array}{rcl}
a_6 &=& (000110) \\
\oplus e &=& (000001) \\

&=& (000111) \; = \; a_9 \in A
\end{array}
$$


#### Aufgabe 2

systematischer Code: durch Streichung der redundanten Stellen, kann das Kanalcodewort ermittelt werden

$l = 3 \rightarrow L = 2^l = 8$

Die Länge $l$ der Codewörter, ist definiert durch die 3 unabhängigen Codewörter $a_1 , a_2, a_3$

a)

Berechnung aller Codewörter $a_1 - a_8$, diese bilden die Menge A
$$
\begin{array}{rcl}
a_1 &=& (0011110) \\
a_2 &=& (1011001) \\
a_3 &=& (1110100) \\
a_4 &=& (1000111) = a_1 \oplus a_2 \\
a_5 &=& (1101010) = a_5 \oplus a_3 \\
a_6 &=& (0101101) = a_2 \oplus a_3 \\
a_7 &=& (0110011) = a_1 \oplus a_6 \\
a_8 &=& (0000000) = a_1 \oplus a_1
\end{array}
$$
Binärfolgen prüfen ob sie in A enthalten sind:

- $b_1 \notin A$ 
- $b_2 \notin A$
- $ b_3 \in A $



Codeparameter:  d_min ist das minimale Gewicht in einem linear Code

$(n,l,d_{min}) = (7, 3, 4)$



b)

Generatormatrix: $G_{l \times n} = [I_lC]$

Kontrollmatrix: $H_{k \times n} = [C^T I_K]$

Orthogonalitätsbedingung: $G \cdot H^T = (H \cdot G^T)^T = 0$



Bildung der Generatormatrix:

- Jede Zeile der Generatormatrix entsteht aus einem Codewort der Menge A 
- Dabei muss sich am Anfang eine Einheitsmatrix $I_3$ bilden
- Es wurden die Elemente: $a_4 , a_6,  a_1 \in A$ für die Erstellung von G verwendet  
- mittels der Generatormatrix kann ein Codewort $a_i^*$ zu einem Codewort $a_i$ codiert werden $a_i = a_i^* \cdot G$

$G_{3 \times 7} = [I_3C] = \begin{pmatrix} 1 & 0 & 0 & 0 & 1 & 1 & 1 \\ 0 & 1 & 0 & 1 & 1 & 0 & 1 \\ 0 & 0 & 1 & 1 & 1 &  1 & 0 \end{pmatrix}$



Bildung der Kontrollmatrix:

- Das C aus der Generatormatrix wird transponiert und bildet die ersten Spalten
- Zur Auffüllung wird eine Einheitsmatrix genutzt
- mittels der Kontrollmatrix kann ein empfangenes Codewort darauf geprüft werden ob ein Fehler aufgetreten ist
- ist s das Fehlersyndrom gleich dem Nullvektor liegt kein Fehler oder ein nicht erkennbarer Fehler vor

$H_{4 \times 7} = [C^TI_4] = \begin{pmatrix} 0 & 1 & 1 & 1 & 0 & 0 & 0 \\ 1 & 1 & 1 & 0 & 1 & 0 & 0 \\ 1 & 0 & 1 & 0 & 0 & 1 & 0 \\ 1 & 1 & 0 & 0 & 0 & 0 & 1 \\ \end{pmatrix} $



Zur Prüfung ob eine empfangene Binärfolge  ein Codewort ist muss diese mit der Kontrollmatrix multipliziert werden

$b_1:$
$$
\begin{pmatrix}
0 & 1 & 1 & 1 & 0 & 0 & 0 \\
1 & 1 & 1 & 0 & 1 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 & 1 & 0 \\
1 & 1 & 0 & 0 & 0 & 0 & 1 \\
\end{pmatrix}
\cdot 
\begin{pmatrix}
0 \\ 1 \\ 1 \\ 1 \\ 1 \\ 1 \\ 0
\end{pmatrix}
= 
\begin{pmatrix}
1 \\ 1 \\ 0 \\ 1
\end{pmatrix}
$$


s entspricht Spalte $n_2$ in H $\rightarrow$ Korrektur: $n_2$ kippen: $b_{1,korr} = (0\;0\;1\;1\;1\;1\;0)$

Dekodierung: $b_{1,korr}^* = (0\;0\;1)$



$b_2:$
$$
\begin{pmatrix}
0 & 1 & 1 & 1 & 0 & 0 & 0 \\
1 & 1 & 1 & 0 & 1 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 & 1 & 0 \\
1 & 1 & 0 & 0 & 0 & 0 & 1 \\
\end{pmatrix}
\cdot 
\begin{pmatrix}
0 \\ 1 \\ 1 \\ 1 \\ 1 \\ 1 \\ 0
\end{pmatrix}
= 
\begin{pmatrix}
1 \\ 0 \\ 0 \\ 1
\end{pmatrix}
not= 0 
\rightarrow b_2 \notin A, Fehler
$$
keine Übereinstimmung mit einer Spalte in H:

$\rightarrow$ nicht korrigierbar

$\rightarrow$ nicht korrigierbarer Mehrfachfehler 

Rekronstruktionsergebnis: Rekonstruktionsversagen 



$b_3:$
$$
\begin{pmatrix}
0 & 1 & 1 & 1 & 0 & 0 & 0 \\
1 & 1 & 1 & 0 & 1 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 & 1 & 0 \\
1 & 1 & 0 & 0 & 0 & 0 & 1 \\
\end{pmatrix}
\cdot 
\begin{pmatrix}
0 \\ 1 \\ 1 \\ 1 \\ 1 \\ 1 \\ 0
\end{pmatrix}
= 
\begin{pmatrix}
0 \\ 0 \\ 0 \\ 0
\end{pmatrix}
= 0 
\rightarrow b_3 \in A
$$
$\rightarrow$ kein Fehler oder der Fehler ist nicht erkennbar 

Dekodierung: $ b_3^* = (0\;1\;1)$



#### Aufgabe 3

in der Vorlesung behandelt  Beispiele mit $l = 2$ 



#### Aufgabe 4

a)

HAMMING-Code: $(d_{min} = 3 \rightarrow f_k = 1)$
$$
\begin{align*}
k &\ge  \log_2 \sum_{i=0}^{f_k = 1} {n \choose i} \\
k &\ge \log_2 ({n \choose 0} + {n \choose 1}) \\
k &\ge \log_2 (1+l + k) \\
k &\ge \log_2 (5 + k) \\
\rightarrow k &= 3
\end{align*}
$$
Der Code ist dicht gepackt, da $k = 3 = log_2 (5 +3)$



b)

- Bei einem HAMMING-Code entsteht die Kontrollmatrix H durch die Aneinanderreihung der Binärzahlen von 1 (001) bis 7 (111) von rechts nach links  ($H_{3 \times 7}$)
- In diesem Beispiel ist die Matrix somit $l_4, l_3, l_2, k_3, l_1, k_2, k_1$
- die Kontrollstellen $k$ befinden sie jeweils an Spalte der 2er Potenzen (1, 2, 4 , 8 ,16 ...)

$$
H_{3 \times 7} = 
\begin{pmatrix}
1 & 1 & 1 & 1 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 & 1 & 1 & 0 \\
1 & 0 & 1 & 0 & 1 & 0 & 1 \\
\end{pmatrix}\\
$$

$$
k_3 = l_4 \oplus l_3 \oplus l_2\\
k_2 = l_4 \oplus l_3 \oplus l_1 \\
k_1 = l_4 \oplus l_2 \oplus l_1
$$



c)

Kontrollgleichungen
$$
s_3 = l_4 \oplus l_3 \oplus l_2 \oplus k_3 = n_7 \oplus n_6 \oplus n_5 \oplus n_4\\
s_2 = l_4 \oplus l_3 \oplus l_1 \oplus k_2 = n_7 \oplus n_6 \oplus n_3 \oplus n_2\\
s_1 = l_4 \oplus l_2 \oplus l_1 \oplus k_1 = n_7 \oplus n_5 \oplus n_3 \oplus n_1\\
$$


$b_1:$
$$
s_3 = n_7 \oplus n_6 \oplus n_5 \oplus n_4 = 1 \oplus 1 \oplus 0 = 0\\
s_2 = n_7 \oplus n_6 \oplus n_3 \oplus n_2 = 1 \oplus 0 \oplus 1 \oplus 0 = 0 \\
s_1 =  n_7 \oplus n_5 \oplus n_3 \oplus n_1 = 1 \oplus 1 \oplus 1 \oplus 1 = 0\\
$$
$\rightarrow $ es liegt kein Fehler vor oder nicht erkennbar

Codewort:  $b_1^* = (1011)$



$b_2: (0\;0\;1\;0\;1\;1\;0)$
$$
s_3 = 0 \oplus 0 \oplus 1 \oplus 0 = 1 \\
s_2 = 0 \oplus 0 \oplus 1 \oplus 1 = 0\\
s_1 = 0 \oplus 1 \oplus 1 \oplus 0 = 0
$$
$\rightarrow$ es liegt ein Fehler vor an der Stelle $n_4$ diese muss von einer 0 zu einer 1 gewechselt werden

$\rightarrow$ $b_{2,korr} = (0\;0\;1\;1\;1\;1\;0)$

Codewort: $b_2^* = (0\;0\;1\;1)$



$b_3: (1\;0\;0\;0\;1\;0\;1)$
$$
s_3 = 1 \oplus 0 \oplus 0 \oplus 0 = 1 \\
s_2 = 1 \oplus 0 \oplus 1 \oplus 0 = 0 \\
s_1 = 1 \oplus 0 \oplus 1 \oplus 1 = 1 \\
$$
$\rightarrow$ es liegt ein Fehler vor an der Stelle $n_5$, diese muss von einer 0 zu einer 1 gewechselt werden

$\rightarrow$ $b_{3,korr} = (1\;0\;1\;0\;1\;0\;1)$

Codewort: $b_2^* = (1\;0\;1\;1)$



#### Aufgabe 5

a)

$l = 8, f_k = 1 , d_{min} = 3, n = ?$

Zur Berechnung der Redundanzstellen muss für $k$ verschiedene Werte ausprobiert werden  
$$
\begin{align*}
k &\ge \log_2 \sum_{i=0}^{f_k = 1} {n \choose i} \\
k &\ge \log_2 ({n \choose 0} + {n \choose 1}) \\
k &\ge \log_2 (1 + n) \\
k &\ge \log_2 (1 + l + k) \\
k &\ge \log_2 (1 + 8 + k) \\
\\
k:1 &\rightarrow 1 \ge \log_2(9) \rightarrow 1 \ngeq 3.16 \\
k:2 &\rightarrow 2 \ge \log_2(10) \rightarrow 2 \ngeq 3.32 \\
k:3 &\rightarrow 3 \ge \log_2(11) \rightarrow 3 \ngeq 3.45 \\
k:4 &\rightarrow 4 \ge \log_2(12) \rightarrow 4 \geq 3.58

\end{align*}
$$


$\rightarrow (n,l.d_{min}) = (12,8,3)$



b)

Wenn 2 Fehlerstellen erkannt werden müssen ist $f_k = 2$
$$
\begin{align*}
k &\ge \log_2 \sum_{i=0}^{f_k = 1} {n \choose i} \\
k &\ge \log_2 ({n \choose 0} + {n \choose 1} + {n \choose 2}) \\
k &\ge \log_2 (1 + n + 0.5 \cdot (n-1) \cdot n) \\
k &\ge \log_2 (1 + (l + k) + 0.5 \cdot (l + k - 1) \cdot (l+k)) \\
k &\ge \log_2 (1 + (8 + k) + 0.5 \cdot (7 + k) \cdot (8+k)) \\
\\
k:1 &\rightarrow 1 \ge \log_2(46) \rightarrow 1 \ngeq 5.52 \\
k:2 &\rightarrow 2 \ge \log_2(56) \rightarrow 2 \ngeq 5.8 \\
... \\
k:5 &\rightarrow 5 \ge \log_2(92) \rightarrow 5 \ngeq 6.5 \\
k:6 &\rightarrow 6 \ge \log_2(106) \rightarrow 6 \ngeq 6.72\\
k:7 &\rightarrow 7 \ge \log_2(121) \rightarrow 7 \geq 6.91

\end{align*}
$$


Um 2 Fehlerstellen zu erkennen müssen 7 redundante Stellen hinzugefügt werden.



#### Aufgabe 6

- Um 32 Zeichen zu codieren werden $2^l = 32$​ Stellen benötigt $\to l = 5$

- einfehlerkorrigierender Hamming Kode $\to d_{min} = 3$

- bestimmten der Redundanten Stellen:

$$
\begin{align*}
k &\geq \log_2 \sum_{i=0}^{f_k = 1} {n \choose i} \\
k &\geq \log_2 ( {n \choose 0} + {n \choose 1}) \\
k &\geq \log_2 (1 + l + k) \\
\\
k:1 &\to 1 \geq \log_2 (7) \to 1 \ngeq 2,8 \\
k:2 &\to 2 \geq \log_2 (8) \to 2 \ngeq 3 \\
k:3 &\to 3 \geq \log_2 (9) \to 3 \ngeq 3,1 \\
k:4 &\to 4 \geq \log_2 (10) \to 4 \geq 3,32 \\
\end{align*}
$$

- $k = 4$ redundante Stellen

- Ergebnis: (9,5,3) Hamming Code 



#### Aufgabe 7

- Um 200 Zeichen zu kodieren müssen $2^l >= 200$ Stellen benötigt $\to l = 8$
- Somit sind maximal 256 Kanalcodewörter definiert 
- einfehlerkorrigierender Hamming Code $\to d_{min} = 3$
- bestimmten der Redundanten Stellen:

$$
\begin{align*}
k &\geq \log_2 \sum_{i=0}^{f_k = 1} {n \choose i} \\
k &\geq \log_2 ( {n \choose 0} + {n \choose 1}) \\
k &\geq \log_2 (1 + l + k) \\
k &\geq \log_2 (1 + 8 + k) \\
\\
k:1 &\to 1 \geq \log_2 (10) \to 1 \ngeq 3,32 \\
k:4 &\to 4 \geq \log_2 (13) \to 4 \geq 3,7 \\
\end{align*}
$$

- $k = 4$​​ redundante Stellen
- Ergebnis: (12,8,3) Hamming Code 





















