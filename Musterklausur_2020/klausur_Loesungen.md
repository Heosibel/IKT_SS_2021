# Musterklausur - Lösungen

#### Aufgabe 1

a)

$H_m = 2,82$

$l_m = 4$

$H_k = 1$

$R_k = l_m \cdot H_k - H_m = 1,18$



b) Umsetzung mittels der Huffmann-Codierung

| p(xi) | Code  | Länge |
| ----- | ----- | ----- |
| 0,3   | 00    | 2     |
| 0,18  | 10    | 2     |
| 0,15  | 010   | 3     |
| 0,1   | 110   | 3     |
| 0,08  | 0110  | 4     |
| 0,07  | 1110  | 4     |
| 0,05  | 1111  | 4     |
| 0,04  | 01110 | 5     |
| 0,03  | 01111 | 5     |

$l_m = 3,05$

$R_k = 3,05 \cdot 1 - 2,82 = 0,23$



c)

$(1 - \frac{l_m}{l}) \cdot 100\% = (1 - \frac{3,05}{4}) \cdot 100\% = 23,75\%$​



d) 

die maximale Einsparung ist, wenn $l_m = H_m$ ist. Dies kann z.B. mit der Erweiterung einer Quelle geschafft werden.  ​ 



#### Aufgabe 2

a)

geg: 

- $f_k = 1$​
- Hamming Gruppencode $\to d_{min} = 3$
- 150 Zeichen

ges.:

- l, n ,k



Rechnung:

$ 2^l \geq 150 Zeichen \to l = 8$​



$k \geq \log_2 \sum_0 ^{f_k} {n \choose i}$

$k \geq \log_2 ({n \choose 0 } + {n \choose 1})$

$k \geq \log_2 (1 + l + k)$

$k:1 \to 1 \geq \log_2 (10) \to 1 \ngeq 3,32$

$k:4 \to 4 \geq \log_2 (13) \to 4 \geq 3,7$​

$\to k=4$



Ergebnis: (12,8,3) Code und $|A^*|$​ würde tatsächlich 256 Elemente fassen jedoch werden nur 150 genutzt.



b)

Kontrollmatrix: $H_{k \times n} = H_{4 \times 12} = \begin{pmatrix} n_{12}&n_{11}&n_{10}&n_{9}&n_{8}&n_{7}&n_{6}&n_{5}&n_{4}&n_{3}&n_{2}&n_{1} \\1&1&1&1&1&0&0&0&0&0&0&0 \\ 1&0&0&0&0&1&1&1&1&0&0&0 \\ 0&1&1&0&0&1&1&0&0&1&1&0\\ 0&1&0&1&0&1&0&1&0&1&0&1 \\ l_{8}&l_{7}&l_{6}&l_{5}&k_{4}&l_{4}&l_{3}&l_{2}&k_{3}&l_{1}&k_{2}&k_{1} \end{pmatrix}$



$s_1 = n_{11} \oplus n_{9} \oplus n_{7} \oplus n_{5} \oplus n_{3} \oplus n_{1}$​

$s_2 = n_{11} \oplus n_{10} \oplus n_{7} \oplus n_{6} \oplus n_{3} \oplus n_{2}$

$s_3 = n_{12} \oplus n_{7} \oplus n_{6} \oplus n_{5} \oplus n_{4}$

$s_4 = n_{12} \oplus n_{11} \oplus n_{10} \oplus n_{9} \oplus n_{8}$



$a^* = 0000000100111 \to \mbox{striechen der Kontrollstellen: } a = 000000101$​​



c)

$\begin{pmatrix} n_{12}&n_{11}&n_{10}&n_{9}&n_{8}&n_{7}&n_{6}&n_{5}&n_{4}&n_{3}&n_{2}&n_{1} \\ 0&1&0&0&0&1&1&1&0&0&1&0 \end{pmatrix}$

$s_1 = 1 \oplus 0 \oplus 1 \oplus 1 \oplus 0 \oplus 0 = 1$

$s_2 = 1 \oplus 0 \oplus 1 \oplus 1 \oplus 0 \oplus 1 = 0$

$s_3 = 0 \oplus 1 \oplus 1 \oplus 1 \oplus 0 = 1$

$s_4 = 0 \oplus 1 \oplus 0 \oplus 0 \oplus 0 = 1$



Fehler erkannt an $n_{11} \to b_{korr} = 011001110010 \to b^* = 01101110$​​   

Es wurde zwar ein Fehler erkannt, da aber der Hamming Code nur Einfachfehler erkennt bzw. korrigieren kann wurde hier eine falsche Korrektur durchgeführt.



#### Aufgabe 3

a)

$n= l+k \\ \to 26 = 15 +k \\ \to k = 11$

Generatorpolynom: hat den Grad 11 

Abschätzung  $k_1$ 

$k_1 \leq 2^{k_1} - 1 $

| $k_1 $ | $n \leq 2^{k_1} - 1 $  | - |
| ----- | ----- |  ----- | 
| 4  | $26 \leq 15$    | wrong|
| 5  | $26 \leq 31$    | right |

-> k1 = 5 -> grad M(x)


| m | $\alpha$ | grad m  | 
| ----- | ----- | ----- |
| $m_0$ | $\alpha^0$    |1|
| $m_1$  | $\alpha^1, \alpha^2, \alpha^4, \alpha^8, \alpha^{16}$    |5| 
| $m_3$  | $\alpha^3, \alpha^6, \alpha^{12}, \alpha^{24}, \alpha^{17}$    |5| 

-> längster Zyklus von $\alpha^0$ bis $\alpha^4$ -> $d_{min}$ = 5 + 1 = 6

#### Aufgabe 4

| Möglichkeiten der Fehlerkorrektur        | Nutzen von redundanten Stellen zur Kontrolle                 |
| ---------------------------------------- | ------------------------------------------------------------ |
| Was bedeutet systematischer Kode + 2 Bsp | jedem Quellencodewort der Länge l wird ein Kanalcodewort der Länge n zugeordet. Bsp: dichtegepackter Hamming Code, Parittätscode |
| Paritätskode für N=80                    | (n,l,d_min) = (8,7,1)                                        |
| Ist A* = {01,101,011} dekordierbar       | Nein da es nicht präfixfrei ist durch die Elemente 01 und 011. |













