# Grammars

Regole generali:

* Se devo produrre più $a$ che $b$ produco prima tante $a$ quante $b$ ( $S \rightarrow aSb$) poi produco le $a$ in eccesso 
* Per contari pari/dispari usare $P \rightarrow D$ e $D \rightarrow P​$

### Dyck Languages

Dyck strings where consecutive open parenthesis have an even length 
$$
\begin{equation}
  G: \begin{cases}
    S  \rightarrow (A)S \ | \ \varepsilon \\
    A \rightarrow (S)S
  \end{cases}
\end{equation}
$$

------

Dyck strings where consecutive closed parenthesis have an odd length 
$$
\begin{equation}
  G: \begin{cases}
    S  \rightarrow S(A) \ | \ (A)  \\
    A \rightarrow (S)S \ | \ (S) \ | \ \varepsilon
  \end{cases}
\end{equation}
$$

------

Dyck strings con due tipi di parentesi ($a$$b$ e $cd$):
$$
G:  S \rightarrow aSbS \ | \ cSdS \ | \ \varepsilon
\\
oppure
\\
  G:  S \rightarrow SaSb \ | \ ScSd \ | \ \varepsilon
$$
$G$ ma senza nessuna coppia $ac$ :
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow aS_1bS \ | \ cSdS \ | \ \varepsilon \\
    S_1 \rightarrow aS_1bS \ | \ \varepsilon \\
  \end{cases}
\end{equation}
$$
$G$ ma senza nessuna coppia $bd$ :
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow SaSb \ | D \\
    D \rightarrow ScDd \ | \ \varepsilon \\
  \end{cases}
\end{equation}
$$

----

### Prefixes & Suffixes

Mirror language $L = \{ xx^R \ | \ x \in \Sigma^*\}$ con $\Sigma = \{ a,b\}$:
$$
G: 
    S  \rightarrow aSa \ | \ bSb \ | \varepsilon
$$
**Prefixes** of the mirror language (**ambiguous**)
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow XP \\
    P \rightarrow aPa \ | \ bPb \ | \varepsilon \\
    X   \rightarrow aX \ | \ bX \ | \ \varepsilon
  \end{cases}
\end{equation}
$$
**Substrings** of the mirror language (**ambiguous**)
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow XP \ | \ PX \\
    P \rightarrow aPa \ | \ bPb \ | \varepsilon \\
    X   \rightarrow aX \ | \ bX \ | \ \varepsilon
  \end{cases}
\end{equation}
$$

------

Language $L = \{  x^Rcy \ | \ x,y \in \{ a,b\}^+ \and \ ( x=y$  or $x$ is a substring of  $y )\  \}$

Grammar (**ambiguous**):
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow PX \\
    P \rightarrow aPa \ | \ bPb \ | \ acXa \ | \ bcXb \\
    X   \rightarrow aX \ | \ bX \ | \ \varepsilon
  \end{cases}
\end{equation}
$$

-----

### Counting

Same number of $a$ and $b$ (no order)
$$
\begin{equation}
  G:
    S \rightarrow aSb \ | \ bSa \ | \ SS \ | \ \varepsilon
\end{equation}
$$
Al massimo 2 $a$ o 2 $b$ di fila:
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow aS_bb \ | \ bS_aa \ | \ SS \ | \ \varepsilon \\
    S_b \rightarrow bSa \ | \ \varepsilon \\
    S_a \rightarrow aSb \ | \ \varepsilon \\
  \end{cases}
\end{equation}
$$

----

Language $L_1$ (less $c$ than $a$):
$$
L_1 = \{ \ a^ib^jc^k \ | \ i,j,k \geq 0 \ \and \ k \leq i \}
$$

$$
\begin{equation}
  G: \begin{cases}
    S_1 \rightarrow aS_1c \ | \ A  \\
    A   \rightarrow aA \ | \ B \\
    B   \rightarrow bB \ | \ \varepsilon
  \end{cases}
\end{equation}
$$

Language $L_2$ (less $c$ than $b$):
$$
L_1 = \{ \ a^ib^jc^k \ | \ i,j,k \geq 0 \ \and \ k \leq j \}
$$

$$
\begin{equation}
  G: \begin{cases}
    S_2  \rightarrow XB_1 \\
    B_1 \rightarrow bB_1c \ | \ B_2 \\
    B_2 \rightarrow bB_2 \ | \ \varepsilon \\
    X \rightarrow aX \ | \ \varepsilon \\
  \end{cases}
\end{equation}
$$

Language $L_3 = L_1 \cup L_2$ 

Grammar (**ambiguous**):
$$
L_1 = \{ \ a^ib^jc^k \ | \ i,j,k \geq 0 \ \and \ (k \leq i \ \or \ k \leq j) \}
$$

$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow S_1 \ | \ S_2 \\
    \\
    S_1 \rightarrow aS_1c \ | \ A  \\
    A   \rightarrow aA \ | \ B \\
    B   \rightarrow bB \ | \ \varepsilon \\
    \\
    S_2  \rightarrow XB_1 \\
    B_1 \rightarrow bB_1c \ | \ B_2 \\
    B_2 \rightarrow bB_2 \ | \ \varepsilon \\
    X \rightarrow aX \ | \ \varepsilon \\
  \end{cases}
\end{equation}
$$

------

$$
L = \{ a^hb^k \ | \ \ h > k \geq 1 \ \and \ h\ is\ even\ \and\ k\ is\ odd\ \}
$$

Grammar (**ambiguous**):
$$
   G:  S \rightarrow aaS \ | \ aaSbb \ | \ aab
$$
Grammar (**unambiguous**):
$$
\begin{equation}
  G: \begin{cases}
    S \rightarrow aaS \ | \ X \\
    X \rightarrow aaXbb \ | \ aab  \\
  \end{cases}
\end{equation}
$$
