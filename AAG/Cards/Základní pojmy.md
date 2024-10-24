TARGET DECK: FIT::AAG::Základní pojmy

START
Basic

Jak zní definice abecedy?

Back:
Abeceda ($\Sigma$, nebo $T$) je konečná množina symbolů.

END

START
Basic

Jak definujeme řetězec nad abecedou?

Back:
*Řetězec* nad abecedou je konečná posloupnost symbolů abecedy.

END

START
Basic

Jak značíme množinu všech řetězců nad abecedou?

Back:
$\Sigma^*$

END

START
Basic

Jak značíme množinu všech neprázdných řetězců nad abecedou?

Back:
$\Sigma^+$.
Platí $\Sigma^* = \Sigma^+ \cup \{\varepsilon\}$.

END


START
Basic

Jaké vlastnosti má operace zřetězení?

Back:
- $\forall x, y \in \Sigma^*$ připojením řetězce $y$ za řetězec $x$ vznikne řetězec $x.y$ ($xy$).
- Je asociativní
- Není komutativní
- $\varepsilon$ se chová vzhledem k operaci zřetězení jako neutrální prvek.

END

START
Basic

Jak funguje reverze řetězce? ($x^R$)

Back:
- $x = a_1 a_2 a_3 \ldots a_n$, $x^R = a_n a_{n-1} \ldots a_1$

END

START
Basic

Jak vypadá řetězec s délkou $0$?

Back:

$|x| = 0 \Leftrightarrow x = \varepsilon$

END

START
Basic

Jaká je definice formálního jazyku?

Back:
Formální jazyk $L$ nad $\Sigma$: $L \subseteq \Sigma^*$.


END

START
Basic

Jaké operace můžeme provést nad formálním jazykem?

Back:
- Množinové operace (průnik, sjednocení, rozdíl)
- Doplněk jazyka $L_1$ : $\overline{L_1} = \Sigma^* \setminus L_1$
- Součin (zřetězení) jazyků: $L = L_1 . L_2 = \{xy : x \in L_1, y \in L_2\}$ nad abecedou $\Sigma = \Sigma_1 \cup \Sigma_2$.
- $n$-tá mocnina jazyka $L$ : $L^n = L.L^{n-1}, L^0 = \{ \varepsilon \}$
	- Iterace $L^*$ jazyka $L$: $L^* = \bigcup_{n=0}^{\infty} L^n$
	- $L^* = L^+ \cup \{ \varepsilon \}$
	- $L^+ = L.L^* = \bigcup_{n=1}^{\infty} L^n$

END

START
Basic

Jak zní definice gramatiky?

Back:

Gramatika je uspořádaná čtveřice $G = (N, \Sigma, P, S)$, kde
- $N$ je konečná množina neterminálních symbolů,
- $\Sigma$ je konečná množina terminálních symbolů ($\Sigma \cap N = \emptyset$)
- $P$ je množina (přepisovacích) pravidel. Je to konečná podmnožina množiny $(N \cup \Sigma)^*.N.(N \cup \Sigma)^* \times (N \cup \Sigma)^*$.
- $S \in N$ je počáteční symbol gramatiky.

END

START
Basic

Co znamená, že $x$ přímo derivuje $y$ ($x \Rightarrow y$)?

Back:
Existuje ($\alpha \rightarrow \beta \in P$ a $\gamma, \delta \in (N \cup \Sigma)^*$ takové, že $x = \gamma \alpha \delta, y = \gamma \beta \delta$)


END

START
Basic

Co znamená $\alpha \Rightarrow^k \beta$?
Back:
$\alpha \Rightarrow^k \beta$, jestliže existuje posloupnost $\alpha_0 \alpha_1, \ldots, \alpha_k$ pro $k \geq 0, k+1$  řetězců takových, že $\alpha = \alpha_0, \alpha_{i-1} \Rightarrow \alpha_i$ pro $1 \leq i \leq k$ a $\alpha_k = \beta$. Tuto posloupnost nazveme derivací řetězce $\beta$ z řetězce $\alpha$, která má délku $k$ (v gramatice $G$).

END

START
Basic

Jak definujeme tranzitivní uzávěr relace $\Rightarrow$?

Back:
$\alpha \Rightarrow^+ \beta$, když $\alpha \Rightarrow^i$ pro nějaké $i \geq 1$.

END

START
Basic

Jak vypadá tranzitivní a reflexivní uzávěr relace $\Rightarrow$?

Back:
$\alpha \Rightarrow^* \beta$, když $\alpha \Rightarrow^i \beta$ pro nějaké $i \geq 0$.

END

START
Basic

Co znamená pojem větná forma v gramatice?

Back:
Řetězec $\alpha$ nazveme větnou formou v gramatice $G$, jestliže $S \Rightarrow^* \alpha, \alpha \in (N \cup \Sigma)^*$.

END

START
Basic
Jak definujeme větu generovanou gramatikou?

Back:
Větná forma v $G = (\ldots)$, která neobsahuje žádné neterminální symboly, se nazývá *větou generovanou gramatikou $G$*.

END

START
Basic

Jaká je definice jazyka generovaného gramatikou $G = (\ldots)$?

Back:
$L(G) = \{ w : w \in \Sigma^*, \exists S \Rightarrow^* w \}$

END

START
Basic

Kdy jsou dvě gramatiky ekvivalentní?

Back:
Když generují stejný jazyk.

END

START
Basic

Jak vypadá neomezená gramatika?

Back:
Když odpovídá obecné definici gramatiky.

END



START
Basic

Jak vypadá kontextová gramatika?

Back:
Každé pravidlo z $P$ má tvar $\gamma A \delta \rightarrow \gamma \alpha \delta$, kde $\gamma, \delta \in (N \cup \Sigma)^*, \alpha in (N \cup \Sigma)^+, A \in N$, nebo tvar $S \rightarrow \varepsilon$ v případě, že S se nevyskytuje na pravé straně žádného pravidla.

END

START
Basic

Jak vypadá bezkontextová gramatika?

Back:
Každé pravidlo má tvar $A \rightarrow \alpha$, kde $A \in N, \alpha \in (N \cup \Sigma)^*$.

END

START
Basic

Jak vypadá regulární gramatika?

Back:
Každé pravidlo má tvar $A \rightarrow aB$ nebo $A \rightarrow a$, kde $A, B \in N, a \in \Sigma$, nebo tvar $S \rightarrow \varepsilon$ v případě, že $S$ se nevyskytuje na pravé straně žádného pravidla.

END

START
Basic

Jaká je definice rekurzivně spočetného jazyka?

Back:
Jazyk je *rekurzivně spočetný*, pokud $\exists$ neomezená gramatika, která ho generuje.
- Jsou rozpoznatelné turignovým strojem.

END


START
Basic

Jaká je definice kontextového jazyka?

Back:
Jazyk je kontextový, pokud $\exists$  kontextová gramatika, která ho generuje.
- Jsou rozpoznatelné lineárně omezeným automatem.

END


START
Basic

Jaká je definice bezkontextového jazyka?

Back:
Jazyk je bezkontextový, pokud $\exists$  bezkontextová gramatika, která ho generuje.
- Jsou rozpoznatelné zásobníkovým automatem.

END

START
Basic

Jaká je definice regulárního jazyka?

Back:
Jazyk je regulární, pokud $\exists$  regulární gramatika, která ho generuje.
- Jsou rozpoznatelné konečným automatem.

END

START
Basic

Na jakých operacích je uzavřena třída bezkontextových jazyků?

Back:
Třída bezkontextových jazyků je uzavřena na operacích *sjednocení, součin a iterace*.

END