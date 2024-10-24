TARGET DECK: FIT::AAG::Deterministické a nedeterministické konečné automaty

START
Basic

Jak zní definice deterministického konečného automatu (DKA)?

Back:
Deterministický konečný automat $M$ je pětice $M = (Q, \Sigma, \delta, q_0, F)$, kde:
- $Q$ je konečná množina vnitřních stavů,
- $\Sigma$ je konečná vstupní abeceda,
- $\delta$ je zobrazení z $Q \times \Sigma$ do $Q$,
- $q_0 \in Q$ je počáteční stav,
- $F \subseteq Q$ je množina koncových stavů.
<!--ID: 1729778067028-->
END

START
Basic

Jak zní definice konfigurace konečného automatu?

Back:
Konfigurace konečného automatu $M$ je dvojice $(q, w) \in Q \times \Sigma^*$.
<!--ID: 1729778067033-->
END

START
Basic

START
Basic

Jak zní definice přechodu DKA?

Back:
Přechod DKA je relace $\vdash_M$ nad $Q \times \Sigma^*$, kde $(q, w) \vdash_M (p, w')$ právě tehdy, když $w = aw'$ a $\delta(q, a) = p$ pro nějaké $a \in \Sigma$ a $w \in \Sigma^*$.

<!--ID: 1729778067038-->
END

START
Basic

Jak zní definice jazyka přijímaného DKA?

Back:
Řetězec $w \in \Sigma^*$ je přijat deterministickým konečným automatem $M$, jestliže existuje $(q_0, w) \vdash_M^* (q, \varepsilon)$ pro nějaké $q \in F$. Jazyk přijatý automatem $M$ je $L(M) = \{ w : w \in \Sigma^*, \exists q \in F, (q_0, w) \vdash_M^* (q, \varepsilon) \}$.
<!--ID: 1729778067043-->
END

START
Basic

Jak zní definice úplně určeného deterministického konečného automatu (DKA)?

Back:
Deterministický konečný automat $M = (Q, \Sigma, \delta, q_0, F)$ nazveme úplně určený, když zobrazení $\delta(q, a)$ je definováno pro všechny dvojice stavů $q \in Q$ a vstupních symbolů $a \in \Sigma$.
<!--ID: 1729778067048-->
END

START
Basic

Jak zní definice nedeterministického konečného automatu (NKA)?

Back:
Nedeterministický konečný automat $M$ je pětice $M = (Q, \Sigma, \delta, q_0, F)$, kde:
- $Q$ je konečná množina vnitřních stavů,
- $\Sigma$ je konečná vstupní abeceda,
- $\delta$ je zobrazení z $Q \times \Sigma$ do množiny všech podmnožin $Q$,
- $q_0 \in Q$ je počáteční stav,
- $F \subseteq Q$ je množina koncových stavů.
<!--ID: 1729778067052-->
END

START
Basic

Jak zní definice přechodu NKA?

Back:
Přechod NKA je prvek relace $\vdash_M$ nad $Q \times \Sigma^*$, kde $(q, w) \vdash_M (p, w')$ právě tehdy, když $w = aw'$ a $p \in \delta(q, a)$ pro nějaké $a \in \Sigma$ a $w \in \Sigma^*$.
<!--ID: 1729778067058-->
END


START
Basic

Jak zní definice jazyka přijímaného nedeterministickým konečným automatem (NKA)?

Back:
Řetězec $w \in \Sigma^*$ je přijat nedeterministickým konečným automatem $M = (Q, \Sigma, \delta, q_0, F)$, jestliže existuje $(q_0, w) \vdash_M^* (q, \varepsilon)$ pro nějaké $q \in F$. Jazyk přijatý automatem $M$ je $L(M) = \{ w : w \in \Sigma^*, \exists q \in F, (q_0, w) \vdash_M^* (q, \varepsilon) \}$.
<!--ID: 1729778067062-->
END

START
Basic

Jak zní definice dosažitelného stavu?

Back:
Stav $q \in Q$ nazveme dosažitelný, pokud existuje řetězec $w \in \Sigma^*$ takový, že $(q_0, w) \vdash_M^* (q, \varepsilon)$.
<!--ID: 1729778067067-->
END

START
Basic

Jak zní definice užitečného stavu?

Back:
Stav $q \in Q$ nazveme užitečný, pokud existuje řetězec $w \in \Sigma^*$ takový, že existuje posloupnost přechodů, která vede ze stavu $q$ do nějakého koncového stavu $p \in F$.
<!--ID: 1729778067072-->
END

START
Basic

Jak zní definice nedeterministického konečného automatu s ε-přechody?

Back:
Nedeterministický konečný automat s ε-přechody je pětice $M = (Q, \Sigma, \delta, q_0, F)$, kde $Q$, $\Sigma$, $q_0$, a $F$ jsou stejné jako v definici NKA.

Zobrazení $\delta$ je definováno takto:
$\delta$ je zobrazení z $Q \times (\Sigma \cup \{ε\})$ do množiny všech podmnožin $Q$.
<!--ID: 1729778067077-->
END

START
Basic

Co je $\varepsilon$-Closure?

Back:
Funkce $\varepsilon$-Closure: $Q \to 2^Q$ pro konečný automat $M = (Q, \Sigma, \delta, q_0, F)$ je definována takto:
$\varepsilon$-Closure$(q) = \{p \mid (q, \varepsilon) \vdash_M^* (p, \varepsilon), p \in Q\}$.
<!--ID: 1729778067086-->
END



START
Basic

Jak z automatu odstraníme $\varepsilon$-přechody?

Back:
**Vstup:** NKA $M = (Q, \Sigma, \delta, q_0, F)$ s $\varepsilon$-přechody.

**Výstup:** NKA $M' = (Q, \Sigma, \delta', q_0, F')$ bez $\varepsilon$-přechodů, takový, že $L(M) = L(M')$.

Algoritmus:

1. $M' \leftarrow (Q, \Sigma, \delta', q_0, F')$
2. $\delta'(q, a) \leftarrow \bigcup_{p \in \varepsilon\text{-Closure}(q)} \delta(p, a)$, $\forall a \in \Sigma$
3. $F' \leftarrow \{q \mid \varepsilon\text{-Closure}(q) \cap F \neq \emptyset, q \in Q\}$
4. return $M'$
<!--ID: 1729778067091-->
END

START
Basic

Co je NKA s více počátečními stavy?

Back:
Jedná se o pětici $M = (Q, \Sigma, \delta, I, F)$.
Místo jednoho počátečního stavu může začít v libovolném stavu z množiny počátečních stavů $I \subseteq Q$.
<!--ID: 1729778067096-->
END

START
Basic

Jak zní definice algoritmu pro převod NKA s více počátečními stavy na NKA s jedním počátečním stavem?

Back:
**Vstup:** NKA $M = (Q, \Sigma, \delta, I, F)$, kde $|I| > 1$ (více počátečních stavů).

**Výstup:** NKA $M' = (Q', \Sigma, \delta', q_0, F')$ s jedním počátečním stavem, takový, že $L(M) = L(M')$.

Algoritmus:

1. $M' \leftarrow (Q', \Sigma, \delta', q_0, F')$
2. $Q' \leftarrow Q \cup \{q_0\}$, kde $q_0 \notin Q$
3. $\delta'(q_0, a) \leftarrow \bigcup_{q \in I} \delta(q, a)$, $\forall a \in \Sigma$
4. $\delta'(q, a) \leftarrow \delta(q, a)$, $\forall a \in \Sigma, \forall q \in Q$
5. Pokud $F \cap I = \emptyset$, potom $F' \leftarrow F$, jinak $F' \leftarrow F \cup \{q_0\}$
6. return $M'$
<!--ID: 1729778067101-->
END
