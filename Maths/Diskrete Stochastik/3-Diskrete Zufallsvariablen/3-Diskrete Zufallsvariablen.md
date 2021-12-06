# Zufallsvariablen
Eine **Zufallsvariable** $X$ über $\Omega$ ist eine Abbildung von $\Omega$ auf $X$.
**Reelwertige Zufallsvariable** wenn $X\subseteq R$
$P^X$ = Verteilung von $X$ oder Bildmass von $X$ unter $P$.
$P^X(A)=P(X^{-1}(A))$ wobei $X^{-1}(A)$ das Urbild von A bezeichnet.
Andere Schreibweise: $P(X=a)=P^X(\{a\}), a \in X$
**Zähldichte von X** = $f(x)=P(X=x)=P^X(\{x\})$
```ad-example
![[Pasted image 20211018122612.png]]
$X={-5,10}$ und $X(a)=10, X(b)=X(c)=-5$
$X$ induziert eine Wahrscheinlichkeitsverteilung $P^X$ auf $X$ durch 

$P^X(\{-5\})=P(X^{-1}\{-5\})=P(\{b,c\})={1\over 2}$

```
```ad-example
Zweimaliges Würfeln, man gewinnt CHF $i$ bei Augensumme $i$.
Gesucht: Wahrschienlichkeit für Gewinn = $k$
$\Omega=\{1,2,3,4,5,6\}^2$ $f_P(i,j)= {{1\over 6} * {1\over 6}}$
$X: \Omega \mapsto R$ mit $X(i,j)=i+j$

Zum Beispiel $P(X=6)=P(\{(i,j)|i+j=6\})=P(\{(1,5),(2,4),(3,3),(4,2)(5,1)\})={5 \over 36}$
```
# Verteilungsfunktion
Die Zähldichte einer diskreten Zufallsvariable bestimmt die Verteilung eindeutig. Oft wird diese in einer Tabellete oder mit einem Stabdiagram dargstellt.
![[Pasted image 20211018124210.png|400]]
**Verteilungsfunktion von X** heisst:
$F(x)=P(X \leq x)= \sum_{t\in X:t\leq x}{f(t)}$
![[Pasted image 20211018124920.png|400]]
# Erwartungswert
**Erwartunswert von X**: $E(X)= \sum_{x \in X}{x*f(x)}=\sum_{x \in X}{x*P(X=x)}$
```ad-example
Zweimaliges Würfeln, man gewinnt CHF $i$ wenn beide Würfel $i$ zeigen osnst nichts.
$\Omega=\{1,2,3,4,5,6\}^2$ $f_P(i,j)= {{1\over 6} * {1\over 6}}$
$X: \Omega \mapsto R$ mit $X(i,j)=i, i=j$ sonst 0.

$E(X)=0*P(X=0)+1*P(X=1)...={21 \over 36}$
```
# Varianz und Standardabweichung
$\mu =$ Erwartungwert
**Varianz von X**: $V(X)=\sum_{x\in X}{(x-\mu)^2*P(X=x)}$
oder $V(X)=E(X^2)-E(X)^2$
**Standardabweichung**: $\sigma(X)=\sqrt{V(X)}$
```ad-example
![[Pasted image 20211018133813.png]]
```

