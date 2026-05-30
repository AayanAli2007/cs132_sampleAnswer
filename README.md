# Logic, Automata, and Computation Solutions

---

## 1a

$$
A(r,p,q) =
\neg\Big(
((\neg r \rightarrow (p \lor q)) \rightarrow (r \land \neg q))
\rightarrow (r \rightarrow q)
\Big)
$$

Satisfiable means:
$$
\exists r,p,q : A(r,p,q) = \text{True}
$$

Let:
$$
A = \neg B
$$

$$
B = C \rightarrow (r \rightarrow q)
$$

$$
C = D \rightarrow (r \land \neg q)
$$

$$
D = (\neg r \rightarrow (p \lor q))
$$

We want:
$$
B = \text{False}
$$

So:
$$
B = \text{False} \Leftrightarrow C = \text{True} \land (r \rightarrow q) = \text{False}
$$

Thus:
$$
r = \text{True}, \quad q = \text{False}
$$

Substituting shows $C$ holds, hence:
$$
A = \text{True}
$$

---

## 1b

$$
\forall x [\exists y\, S(x,y)] \models \exists y [\forall x\, S(x,y)]
$$

Countermodel:
- Domain: $A = \{T, F\}$
- $S(x,y) = x \oplus y$

---

## 1c

$$
((q \rightarrow (p \lor (q \rightarrow p))) \lor \neg(p \rightarrow q)) \rightarrow p
$$

Take $p = 0$:

Then:
$$
\neg(p \rightarrow q) = 0
$$

So we need:
$$
q \rightarrow (0 \lor (q \rightarrow 0))
$$

Choose $q = 1$:

This evaluates to false, so:
$$
\text{formula is not a tautology}
$$

---

## 1d

$$
p \rightarrow (q \lor r),\ \neg q,\ \neg p \vdash \neg r
$$

---

## 1e

$$
P(v,w) \Leftrightarrow \exists x \; (E(v,x) \land E(x,w))
$$

---

## 2a

Regular expression idea:
$$
\Sigma \mid \Sigma\Sigma \mid 01\Sigma \mid 0\Sigma1 \mid 10\Sigma \mid 1\Sigma0 \mid \Sigma^4 \Sigma^*
$$

Alternative form:
$$
\Sigma_\epsilon 0 \Sigma_\epsilon 1 \Sigma_\epsilon
\;\mid\;
\Sigma_\epsilon 1 \Sigma_\epsilon 0 \Sigma_\epsilon
$$

---

## 2b

```
S → aSa | bSb | aXb | bXa
X → XX | a | b | ε
```

Alternative:

```
S → XSX | R
R → aTb | bTa
T → XTX | X | ε
X → a | b
```

---

## 2c

Let:
$$
w = a^{p+1} b^p c^p
$$

Pumping:
$$
y = a^j,\quad 1 \le j \le p
$$

After pumping down:
$$
a^{p+1-j} b^p c^p
$$

This leaves the language ⇒ contradiction.

---

## 2d

Construct:
$$
G = (Q_L \cup Q_R \cup \{S\}, \Sigma_L \cup \Sigma_R, R_L \cup R_R \cup \{S \rightarrow S_L \mid S_R\})
$$

Hence CFL ∪ REG is CFL.

---

## 2e

Steps:
- Remove unreachable states
- Remove dead states
- Run DFS for cycles

If a cycle exists on a path to accept ⇒ infinite language.

---

## 3a

$$
\forall x[\exists y (P(x) \rightarrow Q(y))]
$$

Equivalent:
$$
\exists y [\forall x (P(x) \rightarrow Q(y))]
$$

---

## 3b

Construct product DFA:
- Check $A \cap \overline{B}$
- If empty ⇒ $A \subseteq B$

---

## 3c

Using DFA loop structure:
- Decompose $w = xyz$
- Pump loop

Produces:
$$
x(yy)^iz,\quad xy(yy)^iz
$$

Distinct ⇒ structure proven.

---

## 4a

Assume:
$$
LOOPS_{TM} = \overline{HALT_{TM}}
$$

Both RE ⇒ HALT decidable ⇒ contradiction.

---

## 4b

Derivation:
$$
\forall x \exists y (P(x) \lor Q(y))
\Rightarrow
\exists y \forall x (P(x) \lor Q(y))
$$

---

## 4c

Complement grammar:

```
S → S1 | S2

S1 → S1ab | S1ba | bS1a | aS1b | abS1 | baS1 | X
X → A+ | B+

S2 → aS2 | bΣ*
```

---
