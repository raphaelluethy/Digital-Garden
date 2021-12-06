---
date updated: '2021-10-08T17:50:12+02:00'

---

# Allgemeine Wahrscheinlichkeit

**Wahrscheinlichkeitsverteilung** = $P: 2^\Omega \mapsto [0,1]$
Menge aller Teilmengen = $2^\Omega$

**Regeln**:

1. $P(\Omega)=1$
2. When $E_1,E_2,E_3...$ Ergebnisse sind ohne gemeinsame Elemente then $P(E_1 \cup E_2) = P(E_1)+P(E_2)$
3. $\forall E \subseteq \Omega: P(E^c) = 1-P(E)$
   _Beweis_: $1=P(\Omega)=P(E \cup E^c)=P(E)+P(E^c)$
4. $P(\emptyset) = 0$
5. $\forall E_1, E_2 \subseteq \Omega: P(E_1 \cup E_2) = P(E_1) + P(E_2) - P(E_1 \cap E_2)$
6. When $E=\{e_1,e_2,...\}$(_Elementarereignisse_) then $P(E)=P(\{e_1\}) + P(\{e_2\}) + ...$

**Zähldichte** = $f_P: \Omega \mapsto [0,1]$ with $f_P(\omega)=P(\{\omega\})$
Also gilt $P(E)=\sum_{e \in E} f_P(e)$ so if $E=\Omega$ its 1

```ad-example
![[Pasted image 20211008133548.png|200]]
$\Omega = \{a,b,c\}$
Zähldichten: $f_P(a)={1 \over 2}$  $f_P(b)={1 \over 4}$ $f_P(c)={1 \over 4}$
$P(\emptyset) = 0$
$P(\{a,b\})={1\over2}+{1\over4}={3\over4}$
etc.
```

# Bedingte Wahrscheinlichkeit

(elementare)**Bedingte Wahrscheinlichkeit** A unter B = Wenn $B \subseteq \Omega$ und $P(B) > 0$ dann $P(A|B)={P(A \cap B)\over P(B)}$

```ad-example
Bei zweimaliges würfeln, wie hoch ist die Wahrscheinlichkeit Augensumme=7 wenn das Produkt der Augen 12 ist?
$\Omega=\{1,2,3,4,5,6\}^2$ $P=Gleichverteilung$
$A={(1,6),(2,5),(3,4),(4,3)...}$ $B={(2,6),(3,4),(3,4),(6,2)}$
$P(A|B)={P(A \cap B)\over P(B)}={2\over4}$
```

**Formel von Bayes** Wenn $A,B \subseteq \Omega$ und $P(A),P(B) > 0$ dann $P(A|B)={P(A)\over P(B)}*P(B|A)$
_Beweis_: $P(A|B)={P(A \cap B)\over P(B)}={P(B \cap A)\over P(B)}={P(A) \over P(B)}*{P(B \cap A)\over P(B)}={P(A)\over P(B)}*P(B|A)$
**Herleitung**: 
$A=$Mathe mögen, $A^c=$ Mathe nicht mögen, $B=$Männlich, $B^c=$Weiblich
![[Pasted image 20211019104431.png]]

```ad-example
Population=40% weiblich und 60% männlich
Von weiblichen wiegen 10% mehr als 70kg, von männlichen 80%.
Wieviel Prozent der population ist mehr als 70kg.
(weiblich und 70kg+)$0.1*0.4+0.8*0.6$(männlich und 70kg+)
Andere Interpretation
(Wahrscheinlichkeit 70kg+ unter weiblich)$0.1*0.4$(Wahrscheinlichtkeit weiblich)
+
(Wahrscheinlichkeit 70kg+ unter männlich)$0.8*0.6$(Wahrscheinlichtkeit männlich)
```

**Formel der totalen Wahrscheinlichkeit**
Genau so für P(A)
![[Pasted image 20211019105710.png]]
![[Pasted image 20211019105752.png]]




$B_i$ mit $i\in I$ eine Zerlegung von $\Omega$ (d.h die $B_i$ sind paarweise disjunkt und $\Omega= \cup$ of all $B_i$ ) mit $P(B_i) > 0$. Dann gilt $P(A)=\sum_{i\in I} P(A|B_i) *P(B_i)$
$$P(A|B)={P(A)*P(B|A)\over P(B|A)*P(A)+P(B|A^c)*P(A^c)}$$
```ad-example
Eine Krankheit tritt bei 2 von 10000 Personen auf. $K$=Sachverhalt das eine Person diese Krankheit trägt.
Also gilt: $P(K)=0.0002$

$T$ bezeichnet das bei einem Screening-Test eine Person positiv ausgefallen ist.
Der Hersteller des Tests versichert, dass die Krankheit zu 99% erkennt wird (**Sensitivität $P(T|K)=0.99$**) und in 99% der Fälle richtig liegt (**Spezifität** $P(T^c |K^c)=0.99$) also nur in 1% falschlicherweise anschlägt, obwohl nicht krank ($P(T|K^c)=0.01$)

Wir wissen also, dass wenn Krank der Test zu 99% positiv ausschlägt. 
Die Frage ist, wie wahrscheinlich ist das Vorliegen der Krankheit wenn der Test positiv ausfällt. Also $P(K|T)$

$$P(K|T)={0.0002*0.99 \over 0.99*0.0002+0.01*0.998}=0.019=1.9\%$$
```

# Stochastische Unabhängigkeit

A und B sind **Stochastische Unabhängigkeit** = $A,B \subseteq \Omega$ falls $P(A \cap B)=P(A)*P(B)$. Wenn $P(B) \neq 0$ ist dies aquivalant zu $P(A|B)=P(A)$

```ad-example
32 Karten Set
$\Omega=\{7_{heart}, 8_{heart}, ... Ace_{spades}\}$
King=$\{K_{heart}, K_{diamond}, K_{clubs}, K_{spades}\}$
Heart=$\{7_{heart}, 8_{heart}, ...\}$
${1\over32}={4\over32}*{8\over32}$ => stochastisch Unabhängig
```

# Mehrstufige Zufallsexperimente
Ein $n$-stufiger Veruch mit Ergebnismenge $\Omega_i$ für den $i$-ten Versuch wird meist wie folgt modelliert:
1. Man legt die Dichte $f_1(\omega_1)$ auf $\Omega_1$ für den 1. Versuch.
2. Man legt die Dichte $f_2(\omega_2 |\omega_1)$ auf $\Omega_2$ für den 2. Versuch in Abhängigkeit vom Ergebnis $\omega_1$.
3. etc...
4. Man left die Dichte $f_n(\omega_n |\omega_1,...\omega_{n-1})$ auf $\Omega_n$ für den $n$-ten Versuch.

```ad-example
Gegeben ist eine Urne mit 4 weissen und 2 schwarzen Kugeln. Wir ziehen dreimal ohne Zurücklegen.
![[Pasted image 20211018110146.png]]
![[Pasted image 20211018110219.png]]
```