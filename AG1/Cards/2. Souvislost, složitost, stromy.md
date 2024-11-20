TARGET DECK: FIT::AG1::Souvislost, složitost, stromy

START
Basic

Jaká je definice souvislého a nesouvislého grafu?

Back:
Graf $G$ je **souvislý**, jestliže v něm pro každé jeho dva vrcholy $u$, $v$ existuje $u$-$v$-cesta. Jinak je $G$ **nesouvislý**.
<!--ID: 1729869028286-->
END

START
Basic

Co je to souvislá komponenta v grafu?

Back:
Indukovaný podgraf $H$ grafu $G$ je **souvislou komponentou**, pokud:
- je souvislý a
- neexistuje žádný souvislý podgraf $F$, $F \neq H$, grafu $G$ takový, že $H \subseteq F$.

(Souvislá komponenta je tedy v inkluzi maximální souvislý podgraf grafu $G$.)
<!--ID: 1729869028292-->
END

START
Basic

Co je způsob reprezentace grafu **matice sousednosti** a jaká je její paměťová složitost?

Back:
Nechť $G = (V, E)$ je graf s $V = \{v_1, v_2, \dots, v_n\}$. **Matice sousednosti** grafu $G$ je čtvercová matice $A_G = (a_{ij})_{i,j=1}^n$ definovaná předpisem:
$$
a_{i,j} = 
\begin{cases} 
1 & \text{když } \{v_i, v_j\} \in E, \\
0 & \text{jinak}.
\end{cases}
$$

Je evidentní, že $A_G$ je symetrická matice.

Paměťová složitost: $O(n^2)$.
<!--ID: 1729869028298-->
END

START
Basic

Co je způsob reprezantace grafu **seznam sousedů** a jaká je jeho paměťová složitost?

Back:
**Seznam sousedů** grafu $G = (V, E)$ je reprezentace, kde pro každý vrchol grafu uchováváme seznam jeho sousedů (např. pomocí spojového seznamu).

Paměťová složitost: $|V|$ začátků seznamů a celkem $2|E|$ prvků v seznamech (každá hrana se vyskytuje dvakrát).

Celková paměťová složitost: $O(n + m)$.
<!--ID: 1729869028303-->
END


START
Basic

Jaká je časová složitost algoritmu BFS při reprezentaci grafu seznamem sousedů?

Back:
Algoritmus **BFS(G, s)** má při reprezentaci grafu $G$ seznamem sousedů časovou složitost $O(|V| + |E|)$.

**Důkaz:**  
- Každý vrchol je přidán do fronty $Q$ nejvýše jednou, neboť je předtím otevřen a nemůže už tedy vícekrát splnit podmínku na řádku (10), že je nenalezený.
- V každé iteraci cyklu (7)–(15) je jeden vrchol odebrán z fronty, tento cyklus má tedy nejvýše $|V|$ iterací.
- Celkový počet iterací cyklu (9)–(14) je nejvýše dvakrát tolik, kolik je v grafu hran (jednou „pohled“ hranou z jedné strany, podruhé z opačné).

Celková časová složitost je tedy $O(|V| + |E|)$.
<!--ID: 1729869028308-->
END

START
Basic

Co je symetrizace orientovaného grafu?

Back:
Symetrizace orientovaného grafu $G = (V, E)$ je neorientovaný graf $\text{sym}(G) = (V, E')$, kde:
$$
\{u, v\} \in E' \quad \text{právě tehdy, když} \quad (u, v) \in E \text{ nebo } (v, u) \in E.
$$
<!--ID: 1729869028316-->
END



START
Basic

Co je slabě souvislý orientovaný graf?

Back:
Orientovaný graf $G = (V, E)$ nazveme **slabě souvislý**, pokud je souvislá jeho symetrizace $\text{sym}(G)$.

Testovat slabou souvislost orientovaného grafu znamená testovat, například pomocí algoritmu BFS, souvislost jeho symetrizace, což je neorientovaný graf.
<!--ID: 1729869028322-->
END

START
Basic

Co je silně souvislý orientovaný graf?

Back:
Orientovaný graf $G = (V, E)$ nazveme **silně souvislý**, pokud pro každé dva vrcholy $u, v \in V$ existuje v $G$ orientovaná cesta z $u$ do $v$ a současně orientovaná cesta z $v$ do $u$.
<!--ID: 1729869028333-->
END

START
Basic

Co je izomorfismus grafů?

Back:
Nechť $G$ a $H$ jsou dva grafy. Funkce $f : V(G) \rightarrow V(H)$ je **izomorfismus grafů** $G$ a $H$, pokud:
- $f$ je bijekce, a
- pro každou dvojici vrcholů $u, v \in V(G)$ platí $\{u, v\} \in E(G)$ právě tehdy, když $\{f(u), f(v)\} \in E(H)$.

Dva grafy $G$ a $H$ jsou **izomorfní**, pokud existuje izomorfismus grafů $G$ a $H$, což značíme $G \simeq H$.
<!--ID: 1729869028344-->
END

START
Basic

Co je automorfismus grafu?

Back:
**Automorfismus** grafu $G$ je izomorfismus grafu $G$ se sebou samým, tedy funkce $f : V(G) \rightarrow V(G)$ taková, že:
- $f$ je bijekce, a
- pro každou dvojici vrcholů $u, v \in V(G)$ platí $\{u, v\} \in E(G)$ právě tehdy, když $\{f(u), f(v)\} \in E(G)$.

Neformálně řečeno: automorfismus je permutace vrcholů, která zachovává vztahy mezi vrcholy a hranami, tedy „býti hranou“.
<!--ID: 1729869028356-->
END

START
Basic

Kolik existuje různých grafů na $n$-prvkové množině vrcholů?

Back:
Na $n$-prvkové množině vrcholů $V$ existuje právě $2^{\binom{n}{2}}$ různých grafů.

**Poznámka:**  
Binomické číslo $\binom{n}{2}$ označuje počet dvojic vrcholů v $n$-prvkové množině, mezi nimiž může být hrana.
<!--ID: 1729869028368-->
END

START
Basic

Co je strom, les a list?

Back:
- Graf $G$ nazveme **stromem**, pokud je souvislý a neobsahuje žádnou kružnici (je acyklický).
- Graf $G$ nazveme **lesem**, pokud neobsahuje žádnou kružnici.
- Vrchol $v$ grafu $G$ nazveme **listem**, pokud $\deg_G(v) = 1$.
<!--ID: 1729869028378-->
END

START
Basic

Jak zní věta o trhání listů?

Back:
Nechť $G = (V, E)$ je graf na alespoň dvou vrcholech a nechť $v \in V$ je jeho list. Pak jsou následující tvrzení ekvivalentní:
1. $G$ je strom.
2. $G - v$ je strom.

**Interpretace:**  
Pokud ze stromu odebereme list nebo do stromu přidáme list, graf zůstává stromem.
<!--ID: 1729869028390-->
END

START
Basic

Jak zní věta o charakterizaci stromů?

Back:
Nechť $G = (V, E)$ je graf. Pak následující tvrzení jsou ekvivalentní:
1. $G$ je strom.
2. Pro každé dva vrcholy $u, v \in V$ existuje právě jedna $u$-$v$-cesta.
3. $G$ je souvislý a vynecháním libovolné hrany vznikne nesouvislý graf.
4. $G$ je souvislý a $|E| = |V| - 1$.
<!--ID: 1729869028401-->
END

