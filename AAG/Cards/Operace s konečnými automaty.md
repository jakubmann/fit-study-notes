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


