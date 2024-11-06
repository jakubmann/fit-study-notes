TARGET DECK: FIT::AAG::Operace s konečnými automaty

START  
Basic  

Kdy jsou dva konečné automaty ekvivalentní?  

Back:  
Konečné automaty $M_1$ a $M_2$ nazýváme ekvivalentní, jestliže přijímají stejný jazyk, tj. $L(M_1) = L(M_2)$.  

END  

START  
Basic  

Jaký je algoritmus pro převod NKA na DKA?  

Back:  
**Algoritmus Převod NKA na DKA (podmnožinová konstrukce):**  
Vstup: $ \text{NKA } M = (Q, \Sigma, \delta, q_0, F) $.  
Výstup: $ \text{DKA } M' $ takový, že $ L(M) = L(M') $.  

1. $ Q' \leftarrow \{ \{q_0\} \} $ ⊲ Stavy DKA = množiny stavů NKA.  
2. $ q'_0 \leftarrow \{q_0\} $ ⊲ Počáteční stav $ q'_0 $ DKA je množina $ \{q_0\} $.  
3. Pro $ \forall q' \in Q' $:  
    a. $ \delta'(q', a) \leftarrow \bigcup_{p \in q'} \delta(p, a), \forall a \in \Sigma $ ⊲ Vyhodnoť všechny přechody z $ q' $.  
    b. $ Q' \leftarrow Q' \cup \{ \delta'(q', a) : a \in \Sigma \} $ ⊲ Přidej nové stavy.  
4. $ F' \leftarrow \{ q' : q' \in Q', q' \cap F \neq \emptyset \} $.  
5. $ M' \leftarrow (Q', \Sigma, \delta', q'_0, F') $.  
6. Vrátíme $ M' $.  

END  

START  
Basic  

Jak velký může být výsledný DKA po převodu z NKA (ve vztahu k původnímu NKA)?  

Back:  
Počet stavů výsledného DKA může být až $2^{|Q|}$, kde $|Q|$ je počet stavů původního NKA.  

END  

START  
Basic  

Jak vypadá NKA pro sjednocení jazyků?  

Back:  
**Algoritmus NKA pro sjednocení jazyků – $\varepsilon$-přechody:**  
Vstup: $\text{NKA } M_1 = (Q_1, \Sigma, \delta_1, q_{01}, F_1)$, $M_2 = (Q_2, \Sigma, \delta_2, q_{02}, F_2)$, kde $Q_1 \cap Q_2 = \emptyset$.  
Výstup: $\text{NKA } M$, kde $L(M) = L(M_1) \cup L(M_2)$.  

1. $Q \leftarrow Q_1 \cup Q_2 \cup \{q_0\}$, kde $q_0 \notin Q_1 \cup Q_2$ ⊲ nový počáteční stav $q_0$.  
2. $\delta(q_0, \varepsilon) \leftarrow \{q_{01}, q_{02}\}$ ⊲ $\varepsilon$-přechody z $q_0$ do původních počátečních stavů.  
3. $\delta(q, a) \leftarrow \delta_1(q, a), \forall q \in Q_1, \forall a \in \Sigma$.  
4. $\delta(q, a) \leftarrow \delta_2(q, a), \forall q \in Q_2, \forall a \in \Sigma$.  
5. $F \leftarrow F_1 \cup F_2$ ⊲ koncové stavy jsou sjednocení $F_1$ a $F_2$.  
6. $M \leftarrow (Q, \Sigma, \delta, q_0, F)$.  
7. Vrátíme $M$.  

END  


START  
Basic  

Jak vypadá KA pro průnik jazyků?  

Back:  
**Algoritmus NKA pro průnik jazyků – paralelní činnost:**  
Vstup: $\text{NKA } M_1 = (Q_1, \Sigma, \delta_1, q_{01}, F_1)$, $\text{NKA } M_2 = (Q_2, \Sigma, \delta_2, q_{02}, F_2)$.  
Výstup: $\text{NKA } M$, kde $L(M) = L(M_1) \cap L(M_2)$.  

1. $M \leftarrow (Q_1 \times Q_2, \Sigma, \delta, (q_{01}, q_{02}), F_1 \times F_2)$, kde:  
    a. $\delta((q_1, q_2), a) \leftarrow \{(q'_1, q'_2) : q'_1 \in \delta_1(q_1, a), q'_2 \in \delta_2(q_2, a)\}, \forall (q_1, q_2) \in Q_1 \times Q_2, \forall a \in \Sigma$.  

Poznámka: Na vstupu není požadován úplně určený NKA.  

END  

START  
Basic  

Jak vypadá KA pro doplněk jazyka?  

Back:  
**Algoritmus DKA pro doplněk jazyka:**  
Vstup: Úplně určený $\text{DKA } M = (Q, \Sigma, \delta, q_0, F)$.  
Výstup: $\text{DKA } M'$, kde $L(M') = \Sigma^* \setminus L(M)$.  

1. $M' \leftarrow (Q, \Sigma, \delta, q_0, Q \setminus F)$ ⊲ Prohodíme koncové a nekoncové stavy.  
2. Vrátíme $M'$.  

END  

START  
Basic  

Jak vypadá KA pro součin jazyků?  

Back:  
**Algoritmus NKA pro součin jazyků – $\varepsilon$-přechody:**  
Vstup: $\text{NKA } M_1 = (Q_1, \Sigma, \delta_1, q_{01}, F_1)$, $\text{NKA } M_2 = (Q_2, \Sigma, \delta_2, q_{02}, F_2)$, kde $Q_1 \cap Q_2 = \emptyset$.  
Výstup: $\text{NKA } M$, kde $L(M) = L(M_1) \cdot L(M_2)$.  

1. $Q \leftarrow Q_1 \cup Q_2$.  
2. $\delta(q, a) \leftarrow \delta_1(q, a), \forall q \in Q_1, \forall a \in \Sigma$.  
3. $\delta(q, a) \leftarrow \delta_2(q, a), \forall q \in Q_2, \forall a \in \Sigma$.  
4. $\delta(q, \varepsilon) \leftarrow \{q_{02}\}, \forall q \in F_1$ ⊲ $\varepsilon$-přechody z koncových stavů $M_1$ do počátečního stavu $M_2$.  
5. $M \leftarrow (Q, \Sigma, \delta, q_{01}, F_2)$.  
6. Vrátíme $M$.  

END  


START  
Basic  

Jak vypadá KA pro iteraci jazyka?  

Back:  
**Algoritmus NKA pro iteraci jazyka – s $\varepsilon$-přechody:**  
Vstup: $\text{NKA } M = (Q, \Sigma, \delta, q_0, F)$, který přijímá jazyk $L$.  
Výstup: $\text{NKA } M^*$, který přijímá jazyk $L^*$.  

1. $\delta'(q, a) \leftarrow \delta(q, a), \forall q \in Q, \forall a \in \Sigma$.  
2. $\delta'(q, \varepsilon) \leftarrow \{q_0\}, \forall q \in F$.  
3. $\delta'(q'_0, \varepsilon) \leftarrow \{q_0\}$.  
4. $M^* \leftarrow (Q \cup \{q'_0\}, \Sigma, \delta', q'_0, F \cup \{q'_0\})$.  
5. Vrátíme $M^*$.  

END  

START  
Basic  

Co je minimální DKA?  

Back:  
Nechť $M = (Q, \Sigma, \delta, q_0, F)$ je DKA. $M$ nazveme (stavově) minimální DKA, pokud $\nexists M' = (Q', \Sigma, \delta', q'_0, F')$ takový, že $L(M) = L(M')$ a $|Q| > |Q'|$.  

END  

START  
Basic  

Jak se minimalizuje DKA?  

Back:  
**Algoritmus Minimalizace DKA (Hopcroft):**  
Vstup: $\text{DKA } M = (Q, \Sigma, \delta, q_0, F)$ bez zbytečných a nedosažitelných stavů.  
Výstup: Minimální $\text{DKA } M' = (Q_m, \Sigma, \delta_m, q_{0m}, F_m)$, kde $L(M) = L(M')$.  

1. Rozděl množinu $Q$ na dvě podmnožiny $Q_I \leftarrow Q \setminus F$, $Q_{II} \leftarrow F$.  
2. repeat  
3. Vytvoř tabulku $\delta'$ indexovanou stavy $Q$ (řádky) a symboly abecedy $\Sigma$ (sloupce) tak, že $\delta'(q, a) = Q_j, \delta(q, a) \in Q_j$.  
   ⊲ V tabulce přechodů nahraď každý stav identifikátorem podmnožiny, do které náleží.  
4. Jestliže $\exists$ podmnožina $Q_i$, ve které nejsou všechny příslušné řádky stejné, rozděl $Q_i$ tak, aby každá její podmnožina měla shodné řádky pro všechny své prvky.  
5. until Podmnožiny se dále dělí  
6. $Q_m \leftarrow$ množina všech výsledných podmnožin.  
7. $\delta_m(Q_i, a) \leftarrow Q_j, \forall Q_i \in Q_m, \forall a \in \Sigma, \exists q \in Q_i, \delta(q, a) \in Q_j$.  
8. $q_{0m}$ je podmnožina obsahující $q_0$.  
9. $F_m$ jsou všechny vytvořené podmnožiny množiny $F$.  
10. return $M'$.  

Na konci algoritmu musí platit, že $\delta_m(Q_i, a) = Q_j \iff \forall q \in Q_i, \delta(q, a) \in Q_j$.  

END  
