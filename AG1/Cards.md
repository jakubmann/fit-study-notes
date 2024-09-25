TARGET DECK: FIT::AG1::Základy grafů

START
Basic

Neorientovaný graf

Back:
**Neoritentovaný graf** je uspořádaná dvojice $(V, E)$, kde 
- $V$ je neprázdná množina **vrcholů**
- $E$ je množina **hran**.
Hrana je dvouprvková množina $V$, značíme $\{u, v\}$

Tags: graf
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

Tags: graf
<!--ID: 1727256165892-->
END

START
Basic

Koncové vrcholy hrany $e = \{u, v\}$ v grafu $G$, soused, vrcholy incidentní hraně
Back:
- Vrcholy $u$ a $v$ jsou **koncové vrcholy** hrany $e$,
- $u$ je **sousedem** $v$ v grafu $G$,
- $u$ i $v$ jsou **incidentní** s hranou $e$.

Tags: graf
<!--ID: 1727256165895-->
END

START
Basic

Sled v grafu
Back: **Sled** délky $k$ v grafu $G$ je sekvence $v_0, e_1, v_1, e_2, ..., e_k, v_k$ taková, že $e_i = \{v_{i-1}, v_i\}$ a $e_i \in E(G)$ pro všechna $i = 1,...,k$.

Tags: graf
<!--ID: 1727256165899-->
END

START
Basic

Cesta v grafu
Back:
**Cesta** v grafu $G$ je sled, ve kterém se neopakují vrcholy.

Tags: graf 
<!--ID: 1727256165901-->
END

START
Basic

Délka cesty v grafu
Back:
Délka $s$-$t$-cesty $d(s, t)$ je počet *hran* v této cestě.

Tags: graf
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