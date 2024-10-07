# a)
Graf $G$ se stupni vrcholů $(0, 2, 2, 2, n)$ $n \in \mathbb{N}_0$

## $n = 0$,
graf se stupni $(0, 2, 2, 2, 0)$ - kružnice délky 3 a 2 izolované vrcholy
- todo obrazek


## $n = 1$
To by znamenalo jeden z izolovaných vrcholů napojit na kružnici, tím bychom se ale musel změnit stupeň jednoho z vrcholů v kružnici na 3. Zároveň by byl porušen princip sudosti, protože  $\sum_{v \in V(G)} \text{deg}(v) = 7$, což se nikdy nemůže rovnat $2 |E(G)|$.

## $n = 2$
Graf s kružnicí délky 4 a jedním izolovaným vrcholem.
- todo obrázek

## $n = 3$
Porušuje princip sudosti. ($\sum_{v \in V(G)} = 9$).

## $n \geq 4$
V takovémto případě bychom potřebovali v grafu vrchol, který je napojený na všechny ostatní vrcholy, což by ale porušovalo podmínku existence jednoho izolovaného vrcholu, takže takové grafy  **nemohou existovat**.
# b)
Má smysl brát v potaz pouze grafy $K_{n,n}$ pro $n \geq 2$, pro menší hodnoty $n$ nebudou obsahovat žádné kružnice.

Větší úplné bipartitní grafy budou vždy jako podgraf obsahovat kružnice délek $2m, m > 1 \land m \leq n$. Pro vytvoření kružnice budeme muset vést cestu z počátečního vrcholu střídáním mezi dvěma množinami vrcholů a zakončit tuto cestu zpět v počátečním vrcholu. Nejmenší taková kružnice bude mít délku 4 (kružnici délky 3 nevytvoříme, protože v úplném bipartitním grafu nevedou hrany navzájem mezi vrcholy v jedné množině).
Největší možná kružnice pro daný graf bude mít délku $2n$, protože střídavým vedením hran mezi dvěma množinami můžeme projít všechny vrcholy v grafu a vrátit se zpět do počátečního vrcholu - kružnice bude obsahovat všechny vrcholy grafu = $2n$.
Pokud bychom hledali kružnice jako indukované podgrafy, maximální délka kružnice bude 4. Pokud bychom totiž vybrali větší množinu vrcholů než 4, a zároveň bychom chtěli zachovat veškeré hrany původního grafu, graf by již neměl podobu kružnice (obsahoval by více hran, než potřebujeme, jediný případ kdy se jedná zároveň o úplný biparitní graf a kružnici je v případě izomorfních grafů $K_{2,2}$ = $C_4$).