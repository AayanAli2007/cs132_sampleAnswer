# 1a.
$$ A(r,p,q) = 
\neg\Bigl(  
\bigl(  
(\neg r \rightarrow (p \lor q))  
\rightarrow  
(r \land \neg q)  
\bigr)  
\rightarrow  
(r \rightarrow q)  
\Bigr)  
$$

Satisfiability means $\exists r,p,q : A(r,p,q) = True$
$$A(r,p,q) = \neg\Bigl( B(r,p,q)\Bigr)$$
$$ B(r,p,q) =  
C(r,p,q) 
\rightarrow  
(r \rightarrow q)  
$$
$$C(r,p,q)=(D(r,p,q)  
\rightarrow  
(r \land \neg q)  
\bigr) $$
$$D(r,p,q)=(\neg r \rightarrow (p \lor q))$$

$\exists r,p,q : A(r,p,q) = True$
$\exists r,p,q : \neg( B(r,p,q)) = True$
$\exists r,p,q : B(r,p,q) = False$
$B(r,p,q) = False \Leftrightarrow C(r,p,q) = True \wedge (r \rightarrow q) = False$
$(r \rightarrow q) = False$ implies $r = True, q = False$

$C(r,p,q) = True \Leftrightarrow \neg D(r,p,q) \lor (r \land \neg q)$
$C(r,p,q) = True \rightarrow (True \land \neg False)$ if $r = True, q = False$
$C(r,p,q) = True$ because $r = True, q = False$ 
Hence $B(r,p,q) = False$ hence $A(r,p,q) = True$

# 1b.
$$
\forall x \bigl[\exists y \, S(x,y)\bigr]
\models
\exists y \bigl[\forall x \, S(x,y)\bigr]
$$

Contradiction is $A = \{T,F\}$ and $S(x,y) = x \oplus y$

# 1c.
$$
\Bigl(
    \bigl(
        q \rightarrow (p \lor (q \rightarrow p))
    \bigr)
    \lor
    \neg(p \rightarrow q)
\Bigr)
\rightarrow p
$$
Assume it is a tautology. We would need to find a model in which the entire things evaluates to 0. With would be when
then $p=0$ and $A = 1$
$$A = B
    \lor
    \neg(p \rightarrow q)
$$
$$B = q \rightarrow (p \lor (q \rightarrow p))$$
For $A = 1$ when $p=0$. Either $B = 1$ or $\neg(p \rightarrow q) = 1$
$\neg(0 \rightarrow q) \Rightarrow \neg(1) \Rightarrow 0$
So $B = 1$ when $p=0$.
$1 = q \rightarrow (0 \lor (q \rightarrow 0))$
If $q=0$ it would be $=1$ and when $q=1$ then $0 \lor (1 \rightarrow 0)$ must equal 1. Which it doesn't.
$\therefore$ when $q=1$ and $p=0$ then statement is false, so it isn't a tautology.

# 1d.
He meant to write $p → (q ∨ r), ¬q, ¬p ⊢ ¬r$
But ill do both
1di = $p → (q ∨ r), ¬q, ¬p ⊢ ¬p$
1dii = $p → (q ∨ r), ¬q, ¬p ⊢ ¬r$
### 1di.



# 1e.

![[Pasted image 20260529180448.png]]

$P(v,w) \Leftrightarrow \exists x : E(v,x) \land E(x,w)$

# 2a
Normal
$\{\Sigma \mid \Sigma\Sigma \mid 01\Sigma \mid 0\Sigma1 \mid 10\Sigma \mid 1\Sigma0 \mid \Sigma \Sigma \Sigma \Sigma (\Sigma^*)\}$

Alt
$\{\Sigma \mid \Sigma_{\epsilon}0\Sigma_{\epsilon}1\Sigma_{\epsilon} \mid \Sigma_{\epsilon}1\Sigma_{\epsilon}0\Sigma_{\epsilon} \mid \Sigma \Sigma \Sigma \Sigma (\Sigma^*)\}$

Similar to W3,E5,P5
# 2b.

$S \rightarrow aSa \mid bSb \mid aXb \mid bXa$
$X \rightarrow XX \mid a \mid b \mid \epsilon$

Idea is 
If the ends start of as a palindrome then consume them until the edges are different. Then in between that put whatever you like


Similar to W6,E1
ALT solution:
$S \rightarrow XSX \mid R$
$R \rightarrow aT b \mid bT a$ 
$T \rightarrow XT X \mid X \mid ε$
$X \rightarrow a \mid b$

# 2c.
For language to be regular it must follow the pumping lemma
the word $a^{p+1}b^pc^p \in L$ 
First $p$ letters are $a \therefore y = a^j$ where $1 \leq j \leq p$  
Pumping down to $i=0$ would lead to $a^{p+1-j}b^pc^p$
For it to be in the language $p+1-j\gt p \Rightarrow j \gt 1$. CONTRADICTION
$j$ must be $\ge 1$.

# 2d.
If $L \in CFL$ then it must have a minimal CFG $G_{L}$ and if $L_2 \in REG$ it must have a minimal RLG $G_{R}$
$G_{L} = (Q_L, \Sigma_L, R_L, S_L)$ s.t. $L = [\![G_L]\!]$
$G_{R} = (Q_R, \Sigma_R, R_R, S_R)$ s.t. $R = [\![G_R]\!]$

Produce a grammar  
$G=(Q, \Sigma, R, S)$ s.t.
$Q=Q_L \cup Q_R \cup \{S\}$
$\Sigma=\Sigma_L\cup \Sigma_R$
$R = R_L \cup R_R \cup \{S \rightarrow S_L, S \rightarrow S_R\}$

This grammar is a CFG because
- $Q$ is finite as $Q_R$ and $Q_L$ are finite
- $\Sigma$ is finite as $\Sigma_R$ and $\Sigma_L$ are finite
- $R$ is finite as $R_R$ and $R_L$ are finite
- $R$ is in the form $X \times (V \cup \Sigma)^*$
	- $R_L$ is already in this form
	- $R_R$ is in the form $V \times (\Sigma^*V \cup \Sigma^*)$
		- $\Sigma^*V \cup \Sigma^* \subseteq (V \cup \Sigma)^*$
	- Extra $S$ rules are in such a format as well


# 2e.
First turn the DFA into a DFA with no unnecessary states.
This would be done by traversing the graph, and after that, removing all unreachable states (with their corresponding transitions).

Flip all transition in the DFA and from each accept state traverse the graph whilst keeping track of the unreachable states from each run, and after that, removing all states that cant be reached by any of the accepting states (with their corresponding transitions).

Now every state is both reachable by the start state and can reach one of the accepting states

Turn the DFA into a directed weightless graph G. Test if the graph is acyclic. If the graph has no cycles then there is no way to loop that edge / path to produce a string that can be repeated indefinably.

The way you would test for cycles is through DFS.
First just find a random path (doesn't need to be to an accept state) and keep going until you reach either a state you cannot move from or a state you have already been too $(q)$.
- If you have found a state you have already been too then test if there is an accepting state $(p)$ in the path you just took.
	- If there is then
	- $S \rightarrow ... \rightarrow q \rightarrow ... \rightarrow p \rightarrow ... \rightarrow q$
	- So there must exists paths that need words words
		- $S \rightarrow ... \rightarrow q = x$
		- $q \rightarrow ... \rightarrow q = y$
		- $q \rightarrow ... \rightarrow p = z$
	- These form the values in the pumping lemma $xy^iz$
- If you cannot move then in memory save that (current path - final state, final state) lead to nothing special. Go back an edge and repeat the process skipping any instance of the saved pair again. You will keep repeating this until either a loop is found or every possible path is existed

If a loop is found the language is infinite
If loop is not found them language is finite
If there are $p$ states then the longest path without loops is $p-1$.
The number of paths without loops that start a S is finite.
- $O(q!)$

#### **Simple ALT answer**
Turn DFA into minimal DFA. With start state $s$ and possible end state $f_0$ with a node $v$ somewhere

Since the language is **regular** and **infinite** it must follow pumping lemma. Take a word $|w| \gt p$. Then is must be in the form $w = xyz$. 
Therefore $\exists v:\hat{\delta}(s,x) =v \land \hat{\delta}(v,y) = v \land\hat{\delta}(v,z) =f_0$
Take the minimal DFA and remove all edges and states that weren't using in these transitions $\hat{\delta}(s,x),\hat{\delta}(v,y),\hat{\delta}(v,z)$.

Now there exists only one simple path from $s$ to $f_0$ and only one loop which contains state $v$.

Make two DFA's
First one what will have have a state $w$ s.t. the DFA will have only the transitions necessary for these paths. 
$\hat{\delta}(s,x)=v$
$\hat{\delta}(v,y)=w$
$\hat{\delta}(w,y)=v$
$\hat{\delta}(v,z) = f_0$
So overall the accepted words are in the form $x(yy)^iz$.

Second one what will have have a states $w,z$ s.t. the DFA will have only the transitions necessary for these paths. 
$\hat{\delta}(s,x)=z$
$\hat{\delta}(z,y)=v$
$\hat{\delta}(v,y)=w$
$\hat{\delta}(w,y)=v$
$\hat{\delta}(v,z) = f_0$

So overall the accepted words are in the form $xy(yy)^iz$
And $\nexists i$ s.t. $xy(yy)^iz = x(yy)^iz$ if $|y|\gt0$
# 3a.
$\forall x \big[ \; \exists y [\; P(x) \rightarrow Q(y)\;] \; \big]$
$\forall x \big[\; \exists y [\; \neg P(x) \lor Q(y) \;]\; \big]$
- $y$ isn't bounded in $\neg P(x)$ so we can bring it out
$\forall x \big[\; \neg P(x) \lor \exists y [\; Q(y) \;] \; \big]$
- $x$ isn't bounded in $\exists y [\; Q(y) \;]$ so we can bring it out
$\forall x [\; \neg P(x) \;] \lor \exists y [\; Q(y) \;]$
- Expand $\exists y$ over $\forall x [\; \neg P(x) \;]$
$\exists y [\; \forall x [\; \neg P(x) \;] \lor Q(y) \;]$
- Expand $\forall x$ over $Q(y)$
$\exists y [\; \forall x [\; \neg P(x) \lor Q(y) \;] \;]$
$\exists y [\; \forall x [\; P(x) \rightarrow Q(y) \;] \;]$

# 3b.
Non-deterministic finite automata A and B can be written as minimal deterministic finite automata A' and B' which will recognise the same languages.

Note that regular languages are closed under intersection and compliment
if $\mathcal{L}(A') \subseteq \mathcal{L}(B')$ then $\mathcal{L}(\overline{B'}) \; \cap \; \mathcal{L}(A') = \emptyset$

Since $B'$ is a DFA. Then filliping all accepting state to non-accepting ones and vice verse will get you $\overline{B'}$

Define $\overline{B'} =(Q_1,\Sigma,q_1,F_1,\delta_1)$  
Define $\overline{A} =(Q_2,\Sigma,q_2,F_2,\delta_2)$  
Then make a new DFA $M = (Q,\Sigma,q_0,F,\delta)$ 
$Q = (Q_1 \times Q_2)$
$q_0 = (q_1,q_2)$
$F = (F_1 \times F_2)$
$\delta((q_n,q_m),l) \rightarrow (\delta_1(q_n,l),\delta_2(q_m,l))$

Then test is this machine accepting only the empty language
- Use BFS and save all the state you can traverse to from the start.
- If amongst these states, one of them is an accept state. Then $\mathcal{L}(A) \nsubseteq \mathcal{L}(B)$
- Else then $\mathcal{L}(A) \subseteq \mathcal{L}(B)$


# 3c
The an infinite regular language must follow the pumping lemma for some $w=xy^iz$ . Now in the minimal DFA of of this language just image removing all states and transition that aren't needed for the construction of this specially chosen $x$, $y$ and $z$. So now your DFA will only have a simple path between $S$ and $A$, two distinct (using different edges) paths between $A$ and $B$ (and no others) and finally a simple path between $B$ and $E$. These 4 simple path should share no-edges.

Now construct machines that accept $x(yy)^iz$ and $xy(yy)^iz$.
These languages will be distinct

# 4a
Suppose $LOOPS_{TM}$ is recognizable
$HALT_{TM}$ is recognizable and not decidable
$⟨M,w⟩∈LOOPS_{TM}​⟺⟨M,w⟩ \notin HALT_{TM}​$
Because something that doesn't loop halts and vice versa
$\therefore \overline{HALT_{TM}} = LOOPS_{TM}$
Theorem: $L,\overline{L} \in RE \Leftrightarrow L,\overline{L} \in R$
If $\overline{HALT_{TM}} = LOOPS_{TM}$ and $LOOP_{TM}, HALT_{TM} \in RE$ 
then $LOOP_{TM}, HALT_{TM} \in R$

CONTRADICTION $HALT_{TM} \notin R$.

# 4b
1) $\forall x \big[ \; \exists y [\; P(x) \lor Q(y)\;] \; \big]$
2) $\exists y [\; P(c) \lor Q(y)\;]$         $\forall e (1)$, $c$ is arbitrary
3) $P(c) \lor Q(d)$                 $\exists e (2)$, $c$ is arbitrary, $d$ is a witness for $Q$
4) Assume $P(c)$                         $c$ is arbitrary
5)      $\exists y [P(c)\lor Q(y)]$               $∨i_1(4)$, $c$ is arbitrary 
6) Assume $Q(d)$                        $d$ is a witness for $Q$
7)      $P(c)\lor y\,Q(y)$                   $\vee i_2(6)$, $c$ is arbitrary
8)      $\exists y [P(c)\lor Q(y)]$               $∨i_1(4)$, $c$ is arbitrary 
9) $\exists y (P(c)\lor Q(y))$        $\vee e(3,4\text{-}5,6\text{-}8)$, $c$ is arbitrary
10) $\forall x\exists y [P(c)\lor Q(y)]$             $\forall i(9)$

# 4c
$\overline{L} = \{a^nb^n:n\gt0\}$
Then $L$ can either
- have different amount of $a$'s and $b$'s
- have an $a$ after a $b$


Suppose
$A^+ = a \mid aA^+$
$B^+ = b \mid bB^+$
$\Sigma = a \mid b$
$\Sigma^* = \Sigma^*\Sigma \mid \epsilon$

$G_1$: Different amount of $a$'s and $b$'s
$S_1 = S_1ab \mid S_1ba \mid bS_1a \mid aS_1b \mid abS_1\mid baS_1 \mid X_1$
$X_1 = A^+ \mid B ^+$
Ideas: Remove every pair of $a,b$ (then get to $X_1$)and then fill up with the rest that you need

$G_2$: An $a$ occurs after a $b$
$S_2 = aS_2 \mid b\Sigma^*$
Idea: Remove all $a$'s from the front and then when $b$ is found fill up the rest of the word with whatever you want

So overall
$S = S_1\mid S_2$

$S_1 = S_1ab \mid S_1ba \mid bS_1a \mid aS_1b \mid abS_1\mid baS_1 \mid X$
$X = A^+ \mid B ^+$

$S_2 = aS_2 \mid b\Sigma^*$

Similar W6,E1

