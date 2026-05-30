# Logic, Automata, and Computation Solutions

---

## 1a

\[
A(r,p,q) = 
\neg\Bigl(  
\bigl(  
(\neg r \rightarrow (p \lor q))  
\rightarrow  
(r \land \neg q)  
\bigr)  
\rightarrow  
(r \rightarrow q)  
\Bigr)
\]

Satisfiability means:
\[
\exists r,p,q : A(r,p,q) = \text{True}
\]

Let:
\[
A(r,p,q) = \neg B(r,p,q)
\]

\[
B(r,p,q) = C(r,p,q) \rightarrow (r \rightarrow q)
\]

\[
C(r,p,q) = D(r,p,q) \rightarrow (r \land \neg q)
\]

\[
D(r,p,q) = (\neg r \rightarrow (p \lor q))
\]

We want:
\[
\exists r,p,q : B(r,p,q) = \text{False}
\]

So:
\[
B = \text{False} \Leftrightarrow C = \text{True} \land (r \rightarrow q) = \text{False}
\]

\[
(r \rightarrow q) = \text{False} \Rightarrow r = \text{True}, q = \text{False}
\]

Substituting:
- \(C = \text{True}\) holds
- Hence \(B = \text{False}\)
- Therefore \(A = \text{True}\)

---

## 1b

\[
\forall x [\exists y\, S(x,y)] \models \exists y [\forall x\, S(x,y)]
\]

Countermodel:
- Domain: \(A = \{T,F\}\)
- \(S(x,y) = x \oplus y\)

---

## 1c

\[
\Bigl(
(q \rightarrow (p \lor (q \rightarrow p))) \lor \neg(p \rightarrow q)
\Bigr) \rightarrow p
\]

Take \(p = 0\):

\[
A = B \lor \neg(p \rightarrow q)
\]

Since:
\[
\neg(p \rightarrow q) = 0
\]

We need \(B = 1\).

But for \(q = 1\), \(B = 0\).

So:
\[
p = 0, q = 1 \Rightarrow \text{formula is false}
\]

Therefore it is **not a tautology**.

---

## 1d

Correct sequent:
\[
p \rightarrow (q \lor r),\ \neg q,\ \neg p \vdash \neg r
\]

---

## 1e

\[
P(v,w) \Leftrightarrow \exists x : E(v,x) \land E(x,w)
\]

---

## 2a

\[
\Sigma \mid \Sigma\Sigma \mid 01\Sigma \mid 0\Sigma1 \mid 10\Sigma \mid 1\Sigma0 \mid \Sigma\Sigma\Sigma\Sigma\Sigma^*
\]

Alternative:
\[
\Sigma_\epsilon 0 \Sigma_\epsilon 1 \Sigma_\epsilon \mid \Sigma_\epsilon 1 \Sigma_\epsilon 0 \Sigma_\epsilon
\]

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
\[
w = a^{p+1} b^p c^p
\]

Then:
- \(y = a^j,\ 1 \le j \le p\)

Pumping down:
\[
a^{p+1-j} b^p c^p
\]

Contradiction since string leaves language.

---

## 2d

Construct CFG:
\[
G = (Q_L \cup Q_R \cup \{S\}, \Sigma_L \cup \Sigma_R, R_L \cup R_R \cup \{S \rightarrow S_L \mid S_R\})
\]

Thus CFLs are closed under union with REG.

---

## 2e

Algorithm:
1. Remove unreachable states
2. Remove dead states (cannot reach accept)
3. DFS to detect cycles

- Cycle reachable to accept ⇒ infinite language
- No cycle ⇒ finite language

---

## 3a

\[
\forall x[\exists y (P(x) \rightarrow Q(y))]
\]

Equivalent:
\[
\exists y [\forall x (P(x) \rightarrow Q(y))]
\]

---

## 3b

Construct product DFA:
- Check \(A \cap \overline{B}\)
- If empty ⇒ \(A \subseteq B\)

---

## 3c

Using pumping lemma decomposition:
- Identify loop in DFA
- Split \(w = xyz\)

Construct:
- \(x(yy)^iz\)
- \(xy(yy)^iz\)

Distinct ⇒ structure proven.

---

## 4a

Assume:
\[
LOOPS_{TM} = \overline{HALT_{TM}}
\]

Both RE ⇒ both decidable ⇒ contradiction since HALT is undecidable.

---

## 4b

Derivation shows:
\[
\forall x \exists y (P(x) \lor Q(y))
\Rightarrow \exists y \forall x (P(x) \lor Q(y))
\]

---

## 4c

Complement of \(a^n b^n\):

```
S → S1 | S2

S1 → S1ab | S1ba | bS1a | aS1b | abS1 | baS1 | X
X → A+ | B+

S2 → aS2 | bΣ*
```

---

## End of solutions
