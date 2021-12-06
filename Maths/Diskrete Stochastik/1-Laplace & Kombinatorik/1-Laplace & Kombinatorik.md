---
date updated: '2021-10-04T19:54:01+02:00'

---

# Zufallsexperimente

**Zufallsexperiment** = kann beliebig oft wiederholt werden, bei jeder Durchführung gibt es ein Ergebnis aus bestimmten Ergebnismenge.
**Ergebnismenge** = $\Omega$
**Ereignis** = $E \in \Omega$ = Aussage die entweder wahr oder falsch je nach Ergebnis.

# Wahrscheinlichkeiten

**Wahrscheinlichkeit** = Funktion $P$, die jedem Ereignis eine Zahl von [0, 1] zurodnet.

# Laplace-Experiment

**Laplace-Experiment** = Zufallsexperiment mit $n$ verschiedene Ergebnisse, alle mit gleicher Wahrscheinlichkeit $1 \over n$ (_Gleichverteilung_).
Wahrscheinlichkeit eines Eregnisses = $P(E)={|E| \over |\Omega|}={Anzahl Ergebnisse \over Anzahl aller Ergebnisse}$
**Laplace Raum** = Dieses mathematische Modell mit $P$ und $\Omega$

```ad-example
**Würfelwurf**
$\Omega = \{1,2,3,4,5,6\}$
Ereignis = Augenzahl grösser als 4? $E=\{5,6\}$
Im Laplace-Raum gilt: $P(E) = {2 \over 6}$
```

# Kombinatorik

Systematische Abzählverfahren.

## Produktregel

Bei einem mehrstufigen Auswahlprozess für das 1. Objekt $n_1$ Möglichkeiten,
für das 2. Objekt $n_2$ Möglichkeiten, ... , für das $k$-te Objekt $n_k$ Möglichkeiten,
dann gibt es für den gesamten Auswahlprozess $n_1 * n_2 * ... * n_k$ Möglichkeiten.

```ad-example
Zuerst zahl zwischen 1 und 3 wählen, dann ein Vokal. $3*5=15$ Möglichkeiten
![[Pasted image 20211004121433.png]]
```

## Summenregel

Wenn $n_1$ Objekte mit Eigenschaft 1, $n_2$ Objekte mit Eigenschaft 2, ... ,  $n_k$ Objekte mit Eigenschaft $k$ gibt, und kein Objekt zwei der Eigenschaften gleichzeitig hat (disjoint). Dann gibts $n_1+n_2+ ... +n_k$ Objekte die eine der Eigenschaften besitzt.

```ad-example
Wie viele Passwörter aus 3 Zeichen, die entweder nur aus Kleinbuchstaben oder nur aus Ziffern bestehen. $26^3$ Passwörter nur mit Kleinbuchstaben $10^3$ Passwörter nur aus Ziffern. $26^3 + 10^3$ mögliche Passwörter gesamt.
```

```ad-example
Wie viele Passwörter aus 3 Zeichen, die aus 2 Kleinbuchstaben und 1 Ziffer bestehen. $10*26*26$ Mit Ziffer an erster Stelle, $26*10*26$ an zweiter Stelle und $26*26*10$ an dritter Stelle. $3*10*26^2$ mögliche Passwörter gesamt.
```

## Urnenmodell

Beim Urnenmodell ist eine Urne mit $n$ unterschiedlichen Kugeln, dabei wird $k$ mal eine Kugel gezogen. ![[Pasted image 20211004182806.png]]
Mit Reihenfolge heisst, $(1, 2) \neq (2, 1)$. Also Variationen. Ohne Reihenfolge sind Kombinationen.

### Mit Zurücklegen, mit Reihenfolge

Anzahl Variationen  =  $n^k$

```ad-example
Gibt 3 unterschiedliche Bonbons und 4 Kinder. Wieviele Arten können die Bonbons an die Kinder verteilt werden. $4^3 = 64$, Kind 1 alle, Kind 2 alle etc.
```

### Ohne Zurücklegen, mit Reihenfolge

Anzahl Variationen = ${n! \over (n-k)!}$
_Im Taschenrechner n nPr k_

```ad-example
Wie viele Arten kann man 10 Bücher anordnen. ${10! \over (10-10)!} = 10!$ due to $0! = 1$
```

### Ohne Zurücklegen, ohne Reihenfolge

Anzahl Kombinationen = ${n! \over (n-k)!k!} = \begin{pmatrix}n \\ k \end{pmatrix}$ = **Binomialkoeffizient**
Anzahl aller $k$-elementigen Teilmengen einer $n$-elementigen Menge.
_Im Taschenrechner n nCr k_

```ad-example
Im Turnen werden aus einer Gruppe von 12, 5 gewählt. $\begin{pmatrix}12 \\ 5 \end{pmatrix} = 792$
```

```ad-example
Aus einer Gruppe von 8 Frauen und 4 Männer werden 3 Frauen und 2 Männer gewählt.
1. Frauen ziehen: $\begin{pmatrix} 8 \\ 3 \end{pmatrix}$ Möglichkeiten
2. Männer ziehen: $\begin{pmatrix} 4 \\ 2 \end{pmatrix}$ Möglichkeiten
Insgesamt gibt es also $\begin{pmatrix} 8 \\ 3 \end{pmatrix}*\begin{pmatrix} 4 \\ 2 \end{pmatrix} = 336$ Möglichkeiten.
```

### Mit Zurücklegen, ohne Reihenfolge

Anzahl Kombinationen = $\begin{pmatrix} k+n-1 \\ k \end{pmatrix}$
Alle $k$-elementigen Multimengen von $\{1,2,...,n\}$, so with (2,2) etc. but only (1,2) not also (2,1).

### Geburtstagsparadoxon

Wahrscheinlichkeit, dass in einer Gruppe von $n$ Leuten 2 am selben Tag Geburtstag haben.
**Nicht am gleichen Geburtstag:**
2 Leute = ${365 \over 365}*{364 \over 365}$
3 Leute = ${365 \over 365}*{364 \over 365}*{363 \over 365}$
etc...
$P(min.\space2\space selben\space Geburtstag) = 1 - P (alle\space an\space verschiedene)$
$P(A)=1- {365*(365-1)*...*(365-n+1)\over 365^n}$ = ${n! \over (n-k)!}\over{n^k}$
n=365 und k=Anz. Leute, der Teil im Nenner ist wie [[1-Laplace & Kombinatorik#Ohne Zurücklegen mit Reihenfolge]]
