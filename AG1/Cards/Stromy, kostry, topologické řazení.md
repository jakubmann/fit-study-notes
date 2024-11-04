TARGET DECK: FIT::AG1::Stromy, kostry, topologické řazení

START
Basic

Co je kostra grafu?

Back:
Podgraf $K$ grafu $G$ nazveme kostrou grafu $G$, pokud $V(K) = V$ a $K$ je strom.
<!--ID: 1729870806055-->
END

START
Basic

Jaké grafy mají kostru?

Back:
Kostru má každý souvislý graf. Nesouvislé grafy kostru nemají, kostru má každá souvislá komponenta.
<!--ID: 1729870806061-->
END


START
Basic

Co je kostra souvislého grafu?

Back:
Kostra souvislého grafu je souvislý podgraf nad stejnou množinou vrcholů s nejmenším počtem hran.
<!--ID: 1729870806065-->
END

START
Basic

Jak lze modifikovat BFS pro nalezení kostry grafu?

Back:
Pro nalezení kostry grafu pomocí BFS je třeba sledovat hrany vedoucí k předchůdcům v BFS stromu. Tyto hrany tvoří kostru grafu, protože každý vrchol má právě jednoho předchůdce, což zajišťuje souvislost a počet hran $n - 1$.
<!--ID: 1729870806071-->
END

START
Basic

Co je topologické uspořádání orientovaného grafu?

Back:
Topologické uspořádání orientovaného grafu $G = (V, E)$ je takové seřazení vrcholů $V = \{v_1, \dots, v_n\}$, že pro každou orientovanou hranu $(v_i, v_j) \in E$ platí $i < j$.
<!--ID: 1729870806076-->
END

START
Basic

Kdy se používá topologické uspořádání?

Back:
Topologické uspořádání se používá především pro plánování pořadí provedení navzájem závislých úloh nebo výpočtů.
<!--ID: 1729870806080-->
END

START
Basic

Co je orientovaná kružnice?

Back:
Nechť $n \geq 1$. Orientovaná kružnice délky $n$ (s $n$ vrcholy) je orientovaný graf $({1, \dots, n}, \{(i, i + 1) \mid i \in \{1, \dots, n - 1\}\} \cup \{(n, 1)\})$.
<!--ID: 1729870806085-->
END

START
Basic

Co je acyklický orientovaný graf?

Back:
Orientovaný graf $G$ nazveme acyklický, pokud neobsahuje jako podgraf orientovanou kružnici.
<!--ID: 1729870806090-->
END

START
Basic

Co je zdroj v orientovaném grafu?

Back:
Zdroj je takový vrchol orientovaného grafu, do kterého nevede žádná hrana.
<!--ID: 1729870806095-->
END

START
Basic

Co je stok v orientovaném grafu?

Back:
Stok je takový vrchol orientovaného grafu, ze kterého nevede žádná hrana.
<!--ID: 1729870806100-->
END

START
Basic

Co říká věta o existenci zdroje a stoku?

Back:
Věta o existenci zdroje a stoku tvrdí, že každý orientovaný acyklický graf $G = (V, E)$ obsahuje alespoň jeden zdroj a alespoň jeden stok.
<!--ID: 1729870806105-->
END

START
Basic

Jak vypadá pseudokód algoritmu TopSort?

Back:
$$
\begin{array}{rl}
    (1) & Q \text{ je prázdná fronta} \\
    (2) & \delta[] = \text{pole vstupních stupňů vrcholů } G, \text{ na počátku vynulované} \\
    (3) & \text{Pro každou hranu } (u, v) \in E(G): \\
    (4) & \quad \delta[v] + + \\
    (5) & \text{Vlož do } Q \text{ všechny vrcholy } z \text{ s } \delta[z] = 0 \\
    (6) & \text{Dokud fronta } Q \text{ není prázdná:} \\
    (7) & \quad \text{Odeber prvek } z \text{ ze začátku fronty } Q \\
    (8) & \quad \text{Vypiš } z \\
    (9) & \quad \text{Pro každou hranu } (z, w) \text{ vedoucí ze } z: \\
    (10) & \quad\quad \delta[w] - - \\
    (11) & \quad\quad \text{Pokud } \delta[w] = 0: \text{ zařaď } w \text{ do } Q \\
    (12) & \text{Pokud nebyly zpracovány všechny vrcholy:} \\
    (13) & \quad \text{graf } G \text{ obsahuje orientovaný cyklus} \\
\end{array}
$$
<!--ID: 1729870806110-->
END

START
Basic

Jaká je časová a paměťová složitost algoritmu TopSort?

Back:
Algoritmus TopSort($G$), kde $G = (V, E)$ je orientovaný graf reprezentovaný pomocí pole následníků, má časovou i paměťovou složitost $O(|V| + |E|)$.
<!--ID: 1729870806117-->
END

START
Basic

Jaké jsou základní operace pro algoritmy řazení?

Back:
1. Řazení založené na binární operaci porovnání-a-prohození (Compare-And-Exchange).
2. Řazení založené na jiné operaci.
<!--ID: 1729870806123-->
END

START
Basic

Jaké jsou kategorie algoritmů řazení podle paměťové náročnosti?

Back:
1. In-place algoritmy (potřebují $n + \text{polylog}(n)$ paměti).
2. Out-of-place algoritmy.
<!--ID: 1729870806127-->
END

START
Basic

Jaké jsou kategorie algoritmů řazení podle stability?

Back:
1. Stabilní algoritmy (stejně velké prvky se nikdy neprohodí).
2. Nestabilní algoritmy (stejně velké prvky se mohou prohodit).
<!--ID: 1729870806132-->
END

START
Basic

Jak funguje algoritmus SelectSort?

Back:
Algoritmus SelectSort dělí vstupní posloupnost na levou seřazenou a pravou neseřazenou část. Z neseřazené části vybírá minimum a prohodí jej s prvním prvkem této části. Tento postup se opakuje, dokud není celá posloupnost seřazena.
<!--ID: 1729870806137-->
END

START
Basic

Jak funguje algoritmus InsertSort?

Back:
Algoritmus InsertSort dělí vstupní posloupnost na levou seřazenou a pravou neseřazenou část. Z neseřazené části vezme první prvek a vloží ho zprava na správnou pozici v levé seřazené části. Proces pokračuje, dokud není celá posloupnost seřazena.
<!--ID: 1729870806143-->
END

START
Basic

Jak funguje algoritmus BubbleSort?

Back:
Algoritmus BubbleSort postupně porovnává a prohazuje sousední prvky v posloupnosti, pokud jsou ve špatném pořadí. Tento proces opakuje, dokud největší prvky neprobublají na konec a celá posloupnost není seřazena.
<!--ID: 1729870806147-->
END

START
Basic

Jaká je složitost algoritmu SelectSort?

Back:
Algoritmus SelectSort má časovou složitost $\Theta(n^2)$, je in-place, nestabilní a datově necitlivý.
<!--ID: 1729870806152-->
END

START
Basic

Jaká je složitost algoritmu InsertSort?

Back:
Algoritmus InsertSort má časovou složitost $O(n^2)$, je in-place, stabilní a datově citlivý.
<!--ID: 1729870806158-->
END

START
Basic

Jaká je složitost algoritmu BubbleSort?

Back:
Algoritmus BubbleSort má časovou složitost $O(n^2)$, je in-place, stabilní a datově citlivý.
<!--ID: 1729870806163-->
END

