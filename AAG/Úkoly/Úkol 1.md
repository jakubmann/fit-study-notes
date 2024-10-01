1.
$$
\begin{flalign*}
	S &\rightarrow A \mid B \mid \varepsilon \\
	A &\rightarrow aA \mid aAb \mid a \\
	B &\rightarrow Bb \mid aBb \mid b
\end{flalign*}
$$
2.
Gramatika $G_1$ musí nutně generovat prázdný jazyk, jelikož pravá strana žádného z pravidel nikdy nebude obsahovat terminální symbol. Nehledě na konkrétní pravidla gramatiky proto můžeme prohlásit, že takový jazyk musí jít generovat pomocí gramatiky, jež má pravidla ve tvaru $\gamma N \delta \rightarrow \gamma (N \cup T)^+ \delta$ - prostě zkonstruujeme libovolnou gramatiku generující prázdný jazyk.  

3.
Veškeré jazyky, které můžeme pomocí takové gramatiky generovat, budou nutně podmnožinou $\{a^i \mid i \in \mathbb{N_0}\}$. Musí být možné pro danou množinu řetězců obsahující pouze symbol $a$ sestrojit regulární gramatiku, která jí generuje. Například $G = (\{S\}, \{a\}, \{S \rightarrow \varepsilon \mid a \mid aa \mid aaa \mid aaaa \mid \ldots \}, S)$, kde řetězce na pravé straně pravidla upravíme dle pravidel zdrojové bezkontextové gramatiky (pravidla $G$ splňují podmínky pro pravidla regulární gramatiky - jsou ve tvaru $A \rightarrow a$).