# 1.
Automat generující $L_1$
$M = (\{0, 1, 2, 3, 4\}, \{a, b, c\}, \delta, 0, \{4\})$
$\delta=$
![[hw01_automat1.png]]

# 2.
Automat generující $L_2$
$M = (\{0, 1, 2, 3, 4\}, \{a, b, c\}, \delta, 0, \{1, 2, 3\})$
$\delta=$
![[hw01_automat2.png]]

# 3.
Gramatika generující $L_1$
$G = (\{S, A, B, C, D\}, \{a, b, c\}, P, S)$ 
$P=$
$$
\begin{aligned}
S &\rightarrow aA \mid bS \mid cS \\
A &\rightarrow aA \mid bB \mid cS \\
B &\rightarrow aC \mid bS \mid cS \\
C &\rightarrow aA \mid bB \mid cD \mid c\\
D &\rightarrow aD \mid bD \mid cD \mid a \mid b \mid c \\
\end{aligned}$$



Gramatika generující $L_2$
$G = (\{S, A, B, C, D\}, \{a, b, c\}, P, S)$ 
$P=$
$$
\begin{aligned}
S &\rightarrow aA \mid bS \mid cS \mid a \mid b \mid c\\
A &\rightarrow aA \mid bB \mid cS \mid a \mid b \mid c\\
B &\rightarrow aC \mid cS \mid bS \mid a \mid b \mid c\\
C &\rightarrow aA \mid bB \mid a \mid b\\
\end{aligned}$$
