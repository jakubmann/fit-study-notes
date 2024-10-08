# 1.
Graf $G$ se stupni vrcholů $(0, 2, 2, 2, n)$ $n \in \mathbb{N}_0$

## $n = 0$
graf se stupni $(0, 2, 2, 2, 0)$ - kružnice délky 3 a 2 izolované vrcholy

![[hw01_graph1.png]]

## $n = 1$
To by znamenalo jeden z izolovaných vrcholů napojit na kružnici, tím bychom se ale musel změnit stupeň jednoho z vrcholů v kružnici na 3. Zároveň by byl porušen princip sudosti, protože  $\sum_{v \in V(G)} \text{deg}(v) = 7$, což se nikdy nemůže rovnat $2 |E(G)|$.

## $n = 2$
Graf s kružnicí délky 4 a jedním izolovaným vrcholem.
![[hw01_graph2.png]]


## $n = 3$
Porušuje princip sudosti. ($\sum_{v \in V(G)} = 9$).

## $n \geq 4$
V takovémto případě bychom potřebovali v grafu vrchol, který je napojený na všechny ostatní vrcholy, což by ale porušovalo podmínku existence jednoho izolovaného vrcholu, takže takové grafy  **nemohou existovat**.
# 2
## a)
Má smysl brát v potaz pouze grafy $K_{n,n}$ pro $n \geq 2$, pro menší hodnoty $n$ nebudou obsahovat žádné kružnice.

Větší úplné bipartitní grafy $K_{n,n}$ budou vždy jako podgraf obsahovat kružnice délek $2m, m > 1 \land m \leq n$.

Vybereme-li cestu $P_n, n > 2$ jako podgraf $K_{n,n}$, její hrany budou muset mít podobu $\{u, v \mid u \in A, v \in B\}$, kde $A$ a $B$ jsou množiny vrcholů jednotlivých partit grafu $G$. Pokud bychom chtěli vést hranu z posledního vrcholu cesty ($w$) do prvního vrcholu cesty ($x$), čímž by vznikla kružnice a zároveň by platilo $(w \in A \land x \in A) \lor (w \in B \land x \in B)$, výsledná kružnice by nemohla být podgrafem úplného bipartitního grafu, protože dle definice úplného bipartitního grafu nemůže vést hrana mezi dvěma vrcholy náležícími do stejné partity grafu. Zároveň víme, že v takovém případě by cesta měla sudý počet hran, jinak by nemohly oba koncové vrcholy ležet ve stejné partitě grafu. Abychom tedy mohli vést v takovém podgrafu hranu z $w$ do $x$, musí tyto vrcholy ležet v odlišných partitách grafu a počet hran v $P$ musí být lichý. Z toho přímo plyne, že aby kružnice vytvořená zavedením hrany mezi $w$ a $x$ byla podgrafem $K_{n,n}$, musí mít sudý počet hran a tím pádem i sudý počet vrcholů (dle definice kružnice) = sudou délku. Maximální délka kružnice bude tedy $2n$.

## b)
Pokud bychom hledali kružnice jako indukované podgrafy, maximální délka kružnice bude 4. Pokud bychom totiž vybrali pro podgraf z původní množiny vrcholů více vrcholů než 4, a zároveň bychom chtěli zachovat veškeré hrany původního grafu, graf by již neměl podobu kružnice (obsahoval by více hran, než potřebujeme, jediný případ kdy se jedná zároveň o úplný biparitní graf a kružnici je v případě izomorfních grafů $K_{2,2}$ = $C_4$).