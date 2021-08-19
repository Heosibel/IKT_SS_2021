# Informations und Kommunkationstherorie - Aufgabensammlung Lösungen

## 4. Kanalkodierung



### 4.2. Zyklische Kodes - primitive BCH-Kodes

#### Aufgabe 1

zyklischer Hamming-Kode: 

- $g(x) = x^3+x+1$
- $M(x) = x^3 + x + 1$​​​ ,primitv 

a) Bestimmung der Kodeparameter
$$
(n,l,d_{min}) = (7,4,3) \\
\\

k_1 = \mbox{grad M(x)} = 3 \\
n = 2^{k_{1}} - 1 = 2^3 - 1 = 7
$$

$$
\begin{array}{rcl}
k &=& \mbox{grad} g(x) = 3 \\
l &=& n - k = 7 - 3 = 4
\end{array}
$$

$d_{min} = $ Anzahl aufeinander folgender Nullstellen + 1 ist beim Hamming-Code immer 3



b) Fehlererkennung
$$
f_e = d_{min} - 1 = 2 \\
f_b \le k = 3
$$




c) Multiplikationsverfahren
$$
a(x) = a^*(x) \cdot g(x)
$$

$$
\begin{array}{rcl}
a(x) &=& (x^3+x)(x^3+x+1)\\
&=& x^6+x^4+x^3+x^4+x^2+x \\
&=& x^6+x^3+x^2+x \\
a &=& (\,1\,0\,0\,1\,1\,1\,0) 

\end{array}
$$

Es kann auch über die binäre Form berechnet werden $(1010)\cdot(1011) = (1001110)$



d) Divisionsverfahren
$$
a(x) = a^*(x) \cdot x^k + r(x) \\
r(x) = a^*(x) \cdot x^k \mod g(x)
$$
Beispiel:
$$
a^*(x) = (x^3+x) \\
a^*(x) \cdot x^k =(x^3+x)\cdot x^3 = x^6 + x^4\\
$$

$$
\begin{array}{l}
(x^6+x^4) : (x^3+x+1) = x^3 + 1 \\
r(x) = x + 1 \\
a(x) = a^*(x) \cdot x^k + r(x) =  x^6+x^4+x+1
\end{array}
$$



e)

das Quellencodewort kann direkt aus dem Kanalcodewort abgelesen werden



#### Aufgabe 2

zyklischer ABRAMSON-Kode mit: $g(x) = m_1(x)(x+1); M(x)= x^4+x+1$​

Aufbau ABRAMSON-Kode
$$
g(x) = m_0(x)\cdot m_1(x) \\
m_0(x) = (x+1) \\
m_1(x) = M(x) 
$$
Kodeparameter:
$$
(n,l,d_{min})
$$

$$
k_1 = \mbox{grad } M(x) = 4 \\
n = 2^{k_1} - 1 = 15 \\
k = \mbox{grad } g(x) = 5 \\
l = 15 - 5 = 10
$$

$$
\begin{align*}
g(x) &= m_0(x)m_1(x) \\
&m_0(x) : \alpha^0 \\
&m_1(x) : \alpha^1 , \alpha^2, \alpha^4, \alpha^8 , (\alpha^{16 \mod 2^{k_1}} = \alpha^1)\\
d_{min} &: \alpha^0,\alpha^1, \alpha^2 = 3 + 1 = 4
\end{align*}
$$



Fehlererkennungseigenschaften
$$
f_e = d_{min} - 1 = 3 \\
f_b \le 5
$$

####################### in Progress #############################

Berechnung der Fehler von b_1 bis b_5

1. g(x) berechnen
2. Binärfolge durch g(x) berechnen 
3. wenn der Rest nicht 0 ist -> nicht im Alphabet 

$$
g(x) = (x+1)(x^4+x+1) = x^5+x^4+x^2+1 \\
$$





Dekodierung im Fall Divisionverfahren: ersten 10 Stellen +

Dekodierung im Fall Multiplikationsverfahren: teilen durch das Generatorpolynom



#### Aufgabe 3

Paritätskode: 
$$
\mbox{grad } g(x) = k = 1
$$

$$
g(x) = x  \mbox{ oder } g(x) = x+1
$$

Beispiel für l = 2 ausprobieren
$$
A^* = \{00,10,01,11 \}
$$

$$
g(x) = x + 1; x+1 = m_0(x) 
$$

#### Aufgabe 4

$$
k_1 = 9 = \mbox{grad } M(x)
$$

$$
g(x) = kgV \{m_0,m_1(x),m_2(x) \} = m_0(x) \cdot m_1(x)
$$

$$
k = \mbox{grad }g(x) = \mbox{grad }m_0(x) +\mbox{grad }m_1(x) = 1 + 9 = 10  
$$

