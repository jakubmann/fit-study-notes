TARGET DECK: FIT::AAG::Základní pojmy

START
Basic

Jak zní definice abecedy?

Back:
Abeceda ($\Sigma$, nebo $T$) je konečná množina symbolů.
<!--ID: 1729776183493-->
END

START
Basic

Jak definujeme řetězec nad abecedou?

Back:
*Řetězec* nad abecedou je konečná posloupnost symbolů abecedy.
<!--ID: 1729776183498-->
END

START
Basic

Jak značíme množinu všech řetězců nad abecedou?

Back:
$\Sigma^*$
<!--ID: 1729776183502-->
END

START
Basic

Jak značíme množinu všech neprázdných řetězců nad abecedou?

Back:
$\Sigma^+$.
Platí $\Sigma^* = \Sigma^+ \cup \{\varepsilon\}$.
<!--ID: 1729776183507-->
END


START
Basic

Jaké vlastnosti má operace zřetězení?

Back:
- $\forall x, y \in \Sigma^*$ připojením řetězce $y$ za řetězec $x$ vznikne řetězec $x.y$ ($xy$).
- Je asociativní
- Není komutativní
- $\varepsilon$ se chová vzhledem k operaci zřetězení jako neutrální prvek.
<!--ID: 1729776183511-->
END

START
Basic

Jak funguje reverze řetězce? ($x^R$)

Back:
- $x = a_1 a_2 a_3 \ldots a_n$, $x^R = a_n a_{n-1} \ldots a_1$
<!--ID: 1729776183516-->
END

START
Basic

Jak vypadá řetězec s délkou $0$?

Back:

$|x| = 0 \Leftrightarrow x = \varepsilon$
<!--ID: 1729776183520-->
END

START
Basic

Jaká je definice formálního jazyku?

Back:
Formální jazyk $L$ nad $\Sigma$: $L \subseteq \Sigma^*$.
<!--ID: 1729776183525-->
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
<!--ID: 1729776183530-->
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
<!--ID: 1729776183535-->
END

START
Basic

Co znamená, že $x$ přímo derivuje $y$ ($x \Rightarrow y$)?

Back:
Existuje ($\alpha \rightarrow \beta \in P$ a $\gamma, \delta \in (N \cup \Sigma)^*$ takové, že $x = \gamma \alpha \delta, y = \gamma \beta \delta$)
<!--ID: 1729776183539-->
END

START
Basic

Co znamená $\alpha \Rightarrow^k \beta$?
Back:
$\alpha \Rightarrow^k \beta$, jestliže existuje posloupnost $\alpha_0 \alpha_1, \ldots, \alpha_k$ pro $k \geq 0, k+1$  řetězců takových, že $\alpha = \alpha_0, \alpha_{i-1} \Rightarrow \alpha_i$ pro $1 \leq i \leq k$ a $\alpha_k = \beta$. Tuto posloupnost nazveme derivací řetězce $\beta$ z řetězce $\alpha$, která má délku $k$ (v gramatice $G$).
<!--ID: 1729776183544-->
END

START
Basic

Jak definujeme tranzitivní uzávěr relace $\Rightarrow$?

Back:
$\alpha \Rightarrow^+ \beta$, když $\alpha \Rightarrow^i$ pro nějaké $i \geq 1$.
<!--ID: 1729776183549-->
END

START
Basic

Jak vypadá tranzitivní a reflexivní uzávěr relace $\Rightarrow$?

Back:
$\alpha \Rightarrow^* \beta$, když $\alpha \Rightarrow^i \beta$ pro nějaké $i \geq 0$.
<!--ID: 1729776183554-->
END

START
Basic

Co znamená pojem větná forma v gramatice?

Back:
Řetězec $\alpha$ nazveme větnou formou v gramatice $G$, jestliže $S \Rightarrow^* \alpha, \alpha \in (N \cup \Sigma)^*$.
<!--ID: 1729776183559-->
END

START
Basic
Jak definujeme větu generovanou gramatikou?

Back:
Větná forma v $G = (\ldots)$, která neobsahuje žádné neterminální symboly, se nazývá *větou generovanou gramatikou $G$*.
<!--ID: 1729776183564-->
END

START
Basic

Jaká je definice jazyka generovaného gramatikou $G = (\ldots)$?

Back:
$L(G) = \{ w : w \in \Sigma^*, \exists S \Rightarrow^* w \}$
<!--ID: 1729776183569-->
END

START
Basic

Kdy jsou dvě gramatiky ekvivalentní?

Back:
Když generují stejný jazyk.
<!--ID: 1729776183573-->
END

START
Basic

Jak vypadá neomezená gramatika?

Back:
Když odpovídá obecné definici gramatiky.
<!--ID: 1729776183579-->
END



START
Basic

Jak vypadá kontextová gramatika?

Back:
Každé pravidlo z $P$ má tvar $\gamma A \delta \rightarrow \gamma \alpha \delta$, kde $\gamma, \delta \in (N \cup \Sigma)^*, \alpha in (N \cup \Sigma)^+, A \in N$, nebo tvar $S \rightarrow \varepsilon$ v případě, že S se nevyskytuje na pravé straně žádného pravidla.
<!--ID: 1729776183583-->
END

START
Basic

Jak vypadá bezkontextová gramatika?

Back:
Každé pravidlo má tvar $A \rightarrow \alpha$, kde $A \in N, \alpha \in (N \cup \Sigma)^*$.
<!--ID: 1729776183588-->
END

START
Basic

Jak vypadá regulární gramatika?

Back:
Každé pravidlo má tvar $A \rightarrow aB$ nebo $A \rightarrow a$, kde $A, B \in N, a \in \Sigma$, nebo tvar $S \rightarrow \varepsilon$ v případě, že $S$ se nevyskytuje na pravé straně žádného pravidla.
<!--ID: 1729776183593-->
END

START
Basic

Jaká je definice rekurzivně spočetného jazyka?

Back:
Jazyk je *rekurzivně spočetný*, pokud $\exists$ neomezená gramatika, která ho generuje.
- Jsou rozpoznatelné turignovým strojem.
<!--ID: 1729776183598-->
END


START
Basic

Jaká je definice kontextového jazyka?

Back:
Jazyk je kontextový, pokud $\exists$  kontextová gramatika, která ho generuje.
- Jsou rozpoznatelné lineárně omezeným automatem.
<!--ID: 1729776183603-->
END


START
Basic

Jaká je definice bezkontextového jazyka?

Back:
Jazyk je bezkontextový, pokud $\exists$  bezkontextová gramatika, která ho generuje.
- Jsou rozpoznatelné zásobníkovým automatem.
<!--ID: 1729776183608-->
END

START
Basic

Jaká je definice regulárního jazyka?

Back:
Jazyk je regulární, pokud $\exists$  regulární gramatika, která ho generuje.
- Jsou rozpoznatelné konečným automatem.
<!--ID: 1729776183614-->
END

START
Basic

Na jakých operacích je uzavřena třída bezkontextových jazyků?

Back:
Třída bezkontextových jazyků je uzavřena na operacích *sjednocení, součin a iterace*.
<!--ID: 1729776183619-->
END

START
Basic

Jak vytvoříme gramatiku pro sjednocení jazyků?

Back:
Vstup: Bezkontextové gramatiky $G_1 = (N_1, \Sigma_1, P_1, S_1)$ a $G_2 = (N_2, \Sigma_2, P_2, S_2)$ generující jazyky $L_1$ a $L_2$, $N_1 \cap N_2 = \emptyset$.
Výstup: bezkontextová gramatika $G$, $L(G) = L_1 \cup L_2$.
$G \leftarrow (N_1 \cup N_2 \cup \{ S \}, \Sigma, P_1 \cup P_2 \cup \{ S \rightarrow S_1 \mid S_2\}, S)$, kde $S \notin N_1 \cup N_2$.
<!--ID: 1729776183623-->
END


START
Basic

Jak vytvoříme gramatiku pro součin jazyků?

Back:
Vstup: Bezkontextové gramatiky $G_1 = (N_1, \Sigma_1, P_1, S_1)$ a $G_2 = (N_2, \Sigma_2, P_2, S_2)$ generující jazyky $L_1$ a $L_2$, $N_1 \cap N_2 = \emptyset$.
Výstup: bezkontextová gramatika $G$, $L(G) = L_1 . L_2$.
$G \leftarrow (N_1 \cup N_2 \cup \{ S \}, \Sigma, P_1 \cup P_2 \cup \{ S \rightarrow S_1 S_2 \}, S)$, kde $S \notin N_1 \cup N_2$.
<!--ID: 1729776930156-->
END

START
Basic

Jak vytvoříme gramatiku pro iteraci jazyka?

Back:
Vstup: Bezkontextová gramatika $G = (N, \Sigma, P, S)$ generující jazyk $L$.
Výstup: Bezkontextová gramatika $G'$, $L(G') = L^*$.
$G' \leftarrow (N \cup {S'}, \Sigma, P \cup \{ S' \rightarrow S S', S' \rightarrow \varepsilon \}, S')$, kde $S' \notin N$.
<!--ID: 1729776930172-->
END

START
Basic

Co je konečný jazyk?

Back:
Jazyk $L \subset \Sigma^*$ je  nazván konečný, pokud $\exists n \in \mathbb{N} : |L| < n$.
<!--ID: 1729776930176-->
END

START
Basic

Co je to derivační strom pro bezkontextové jazyky?

Back:
Derivační strom je grafickým vyjádřením syntaktické struktury větné formy.

Mějme gramatiku $G = (N, \Sigma, P, S)$. **Derivační strom** je strom, který má následující vlastnosti:

1. Uzly derivačního stromu jsou ohodnoceny terminálními a neterminálními symboly a symbolem $\varepsilon$ (pak je to jediný syn svého otcovského uzlu).
2. Kořen stromu je ohodnocen počátečním symbolem $S$.
3. Jestliže uzel má alespoň jednoho následovníka, je ohodnocen neterminálním symbolem.
4. Jestliže $n_1, n_2, \dots, n_k$ jsou bezprostřední následovníci uzlu $n$, který je ohodnocen symbolem $A$, a tyto uzly jsou zleva doprava ohodnoceny symboly $A_1, A_2, \dots, A_k$, pak $A \rightarrow A_1 A_2 \dots A_k$ je pravidlo v $P$.
5. Koncové uzly derivačního stromu tvoří zleva doprava větnou formu nebo větu v gramatice $G$, která je **výsledkem derivačního stromu**.
<!--ID: 1729776930181-->
END
