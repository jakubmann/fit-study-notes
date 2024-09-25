TARGET DECK: FIT::AG1::Základy grafů

START
Basic

Neorientovaný graf

Back:
**Neoritentovaný graf** je uspořádaná dvojice $(V, E)$, kde 
- $V$ je neprázdná množina **vrcholů**
- $E$ je množina **hran**.
Hrana je dvouprvková množina $V$, značíme $\{u, v\}$

Tags: graf definice
<!--ID: 1727256165886-->
END

START
Basic

Jak značíme množinu všech dvouprvkových množin množiny vrcholů ($V$)?
Back:
$\binom{V}{2}$

Tags: graf
<!--ID: 1727256165889-->
END

START
Basic

Jak značíme množinu vrcholů a hran? Jak je značen počet prvků těchto množin?
Back:
- $V(G)$, $E(G)$
- $n = |V(G)|$, $m = |E(G)|$

Tags: graf definice
<!--ID: 1727256165892-->
END

START
Basic

Koncové vrcholy hrany $e = \{u, v\}$ v grafu $G$, soused, vrcholy incidentní hraně
Back:
- Vrcholy $u$ a $v$ jsou **koncové vrcholy** hrany $e$,
- $u$ je **sousedem** $v$ v grafu $G$,
- $u$ i $v$ jsou **incidentní** s hranou $e$.

Tags: graf definice
<!--ID: 1727256165895-->
END

START
Basic

Sled v grafu
Back: **Sled** délky $k$ v grafu $G$ je sekvence $v_0, e_1, v_1, e_2, ..., e_k, v_k$ taková, že $e_i = \{v_{i-1}, v_i\}$ a $e_i \in E(G)$ pro všechna $i = 1,...,k$.

Tags: graf definice
<!--ID: 1727256165899-->
END

START
Basic

Cesta v grafu
Back:
**Cesta** v grafu $G$ je sled, ve kterém se neopakují vrcholy.

Tags: graf definice
<!--ID: 1727256165901-->
END

START
Basic

Délka cesty v grafu
Back:
Délka $s$-$t$-cesty $d(s, t)$ je počet *hran* v této cestě.

Tags: graf definice
<!--ID: 1727256165904-->
END

START
Basic

Jak vypadá vstup algoritmu BFS?
Back:
Neorientovaný graf $G = (V, E)$ a vrchol $s \in V$

Tags: bfs
<!--ID: 1727256966524-->
END

START
Basic

Jak vypadá výstup algoritmu BFS?
Back:

- Pole vzdáleností $D$ takové, že
$$
D[v] =
\begin{cases}
k & \text{\( k \) je délka nejkratší \( s \)-\( v \)-cesty v \( G \)} \\
\text{undef.} & \text{neexistuje žádná \( s \)-\( v \)-cesta v \( G \)}
\end{cases}
$$
- Pole předchůdců $P$ takové, že
$$
P[v] = 
\begin{cases}
w & \text{\( w \) je před \( v \) na nějaké nejkratší \( s \)-\( v \)-cestě v \( G \)} \\
\text{undef.} & \text{neexistuje žádná \( s \)-\( v \)-cesta v \( G \)}
\end{cases}
$$

Tags: bfs
<!--ID: 1727256966530-->
END

START
Basic

Jak vypadá pseudokód algoritmu BFS?
Back:
$$
\begin{array}{ll}
\textbf{Algoritmus} \ \text{BFS}(graf \ G, \ \text{vrchol} \ s): \\
(1) \quad \textbf{Pro každý vrchol} \ v \in V(G): \\
(2) \quad \quad \text{stav}[v] := \text{nenalezený} \\
(3) \quad \quad D[v] := P[v] := \text{undef} \\
(4) \quad Q := \text{fronta obsahující jediný vrchol} \ s \\
(5) \quad \text{stav}[s] := \text{otevřený} \\
(6) \quad D[s] := 0, P[s] := \perp \\
(7) \quad \textbf{Dokud je fronta} \ Q \ \text{neprázdná}: \\
(8) \quad \quad \text{Odeber z} \ Q \ \text{první vrchol, nechť to je} \ v \\
(9) \quad \quad \textbf{Pro všechny sousedy} \ w \ \text{vrcholu} \ v: \\
(10) \quad \quad \quad \textbf{Pokud} \ \text{stav}[w] = \text{nenalezený}: \\
(11) \quad \quad \quad \quad \text{stav}[w] := \text{otevřený} \\
(12) \quad \quad \quad \quad D[w] := D[v] + 1 \\
(13) \quad \quad \quad \quad P[w] := v \\
(14) \quad \quad \quad \quad \text{Přidej} \ w \ \text{na konec fronty} \ Q \\
(15) \quad \text{stav}[v] := \text{uzavřený} \\
(16) \quad \textbf{Vrať} \ (D, P) \\
\end{array}
$$

Tags: bfs
<!--ID: 1727257426172-->
END

START
Basic

Jaká je definice BFS fází a hladin?
Back:
- Hladina $H_0 = \{s\}$
- Fáze $F_0$ trvá od odebrání $s$ z $Q$, otevření a vložení všech jeho sousedů do $Q$ až do uzavření $s$.
- Hladina $H_i$ je množina všech vrcholů otevřených a vložených do $Q$ ve fázi $F_{i-1}$
- Fáze $F_i$ trvá od konce fáze $F_{i-1}$ až po uzavření všech vrcholů z $H_i$
- Nechť $h$ je číslo poslední fáze $\text{BFS}(G, s)$

Tags: bfs definice
<!--ID: 1727259925437-->
END

START
Basic

V čem spočívá důkaz správnosti algoritmu BFS?

Tags: bfs
<!--ID: 1727259925448-->
END

START
Basic

Co je to úplný graf?
Back:
**Úplný graf $K_n$ ("klika")**
Nechť $n \geq 1$.
**Úplný graf** na $n$ vrcholech $K_n$ je graf $(V, \binom{V}{2})$, kde $|V| = n$.

Tags: graf definice
<!--ID: 1727259925453-->
END

START
Basic

Co je to úplný bipartitní graf?
Back:
**Úplný bipartitní graf $K_{n_1,n_2}$**
Nechť $n_1 \geq 1$ a $n_2 \geq 1$.
**Úplný bipartitní graf** $K_{n_1, n_1}$ tvořený dvěma partitami o $n_1$ a $n_2$ vrcholech je graf $(A \cup B, \{\{a, b\}, \mid a \in A, b \in B\})$, kde $A \cap B = \emptyset$, $|A| = n_1$ a $|B| = n_2$

Tags: graf definice
<!--ID: 1727259925457-->
END


START
Basic

Jak vypadá graf Cesta?
Back:
**Cesta $P_n$**
Nechť $n \geq 1$.
**Cesta** s $n$ vrcholy (s $n-1$ hranami) $P_n$ je graf $(\{1, ..., n\}, \{\{i, i+1\} \mid i \in \{1, ..., n-1\} \})$ 

Tags: graf definice
<!--ID: 1727260299613-->
END

START
Basic

Jak vypadá graf Kružnice?
Back:
**Kružnice $C_n$**
Nechť $n \geq 3$.
**Kružnice** délky $n$ (s $n$ vrcholy) $C_n$ je graf $(\{1, ..., n\}, \{\{i, i+1\} \mid i \in \{1, ..., n-1\} \cup \{1, n\}\})$

Tags: graf definice
<!--ID: 1727261395296-->
END

START
Basic

Co je doplňek grafu?
Back:
**Doplňek** $\bar{G}$ grafu $G = (V, E)$ je graf $(V, \binom{V}{2} \setminus E)$

Tags: graf definice
<!--ID: 1727261395301-->
END

START
Basic

Jak definujeme stupeň vrcholu v grafu?
Back:
Nechť $G = (V, E)$ je graf a $v \in V$ jeho vrchol.
- Symbolem $\text{deg}(v)$ označíme počet hran grafu $G$ obsahující vrchol $v$.

Tags: graf definice
<!--ID: 1727261395304-->
END

START
Basic

Jak definujeme otevřené a uzavřené okolí vrcholu v grafu?
Back:
Nechť $G = (V, E)$ je graf a $v \in V$ jeho vrchol.
- Symbolem $N_G(v)$ označíme množinu všech sousedů vrcholu $v$ v grafu $G$. Tuto množinu nazveme **otevřené okolí** vrcholu $v$ v grafu $G$.
- Množinu $N_G[v] = N_G(v) \cup \{v\}$ nazveme **uzavřeným okolím** vrcholu $v$ v grafu $G$.

Tags: graf definice
<!--ID: 1727261395308-->
END

START
Basic

Jaký je vztah mezi stupňem vrcholu grafu a jeho otevřeným okolím?
Back:
$$\text{deg}_G(v) = |N_G(v)|$$

Tags: graf
<!--ID: 1727261395313-->
END

START
Basic

Jak definujeme regulární graf?
Back:
Graf je $r$-**regulární**, pokud stupeň každého jeho vrcholu je $r$.
Graf je **regulární**, pokud je r-regulární pro nějaké $r$. 

Tags: graf definice
<!--ID: 1727261395317-->
END

START
Basic

Jak definujeme izolovaný vrchol?
Back:
Vrchol stupně $0$ nazveme izolovaný (nemá žádné sousedy).

Tags: graf definice
<!--ID: 1727261395320-->
END

START
Basic

Co je princip sudosti?
Back:
Pro každý graf $G = (V, E)$ platí $$\sum_{v \in V} \text{deg}_G(v) = 2 |E|$$

Tags: graf věta
<!--ID: 1727261395324-->
END
