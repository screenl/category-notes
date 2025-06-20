## Definition
Let $\mathscr{A} \overset{F}{\underset{G}{\rightleftarrows}} \mathscr{B}$ be categories and functors. We say that $F$ is **left adjoint** to $G$, and $G$ is **right adjoint** to $F$, and write $F \dashv G$, if
$$
\mathscr{B}(F(A), B) \cong \mathscr{A}(A, G(B))
$$
**naturally** in $A \in \mathscr{A}$ and $B \in \mathscr{B}$: where
- Given objects $A \in \mathscr{A}$ and $B \in \mathscr{B}$, there is a bijective correspondence between maps $F(A) \to B$ and maps $A \to G(B)$, denoted by a horizontal bar, in both directions:$$\begin{align}
\left( F(A) \overset{g}{\longrightarrow} B \right) \mapsto \left( A \overset{\bar{g}}{\longrightarrow} G(B) \right), \\
\left( A \overset{f}{\longrightarrow} G(B) \right) \mapsto\left( F(A) \overset{\bar{f}}{\longrightarrow} B \right) . \end{align}
$$So $\bar {\bar {f}} = f$ and $\bar{\bar g} = g$. We call $\bar{f}$ the **transpose** of $f$, and similarly for $g$.
- The **naturality axiom** is satisfied:$$
\overline{\left( F(A) \overset{g}{\longrightarrow} B \overset{q}{\longrightarrow} B' \right)} = \left( A \overset{\bar{g}}{\longrightarrow} G(B) \overset{G(q)}{\longrightarrow} G(B') \right)
$$(that is, $\overline {q \circ g} = G(q) \circ \bar{g}$) for all $g$ and $q$, and$$
\overline{\left( A' \overset{p}{\longrightarrow} A \overset{f}{\longrightarrow} G(B) \right)} = \left( F(A') \overset{F(p)}{\longrightarrow} F(A) \overset{\bar{f}}{\longrightarrow} B \right) 
$$for all $p$ and $f$. 

$F$ is said to be left adjoint to $G$ if, whenever $A ∈ \mathscr A$ and $B ∈ \mathscr B$, maps $F(A) → B$ are *essentially the same thing* as maps $A → G(B)$.

An **adjunction** between $F$ and $G$ is a choice of natural isomorphism (the transpose operation).

Adjunctions can be composed.

### Algebraic Theories
- A collection of operations (functions with a specified arity) **defined everywhere**.$$·: X^2 → X, \ \ \ \ \ ( )^{−1} : X^1 → X, \ \ \ \ \  e: X^0 → X,$$
- A collection of equations (axioms).
### Examples
- **free ⊣ forgetful**: $\mathbf{Vect} \overset{U}{\underset{F}{\rightleftarrows}} \mathbf{Set}$, $\mathbf{Grp} \overset{U}{\underset{F}{\rightleftarrows}} \mathbf{Set}$ (the free group functor is hard to construct), $\mathbf{Ab} \overset{U}{\underset{F}{\rightleftarrows}} \mathbf{Grp}$. $\mathbf{Field} \overset{U}{\rightarrow} \mathbf{Set}$ (does not have a left adjoint)
- For a given set $B$, there is a functor defined by $$\begin{align}F(A)  &\mapsto A\times B \\ F(f)(a,b) & \mapsto (f(a),b)\end{align}$$ and a functor defined by $$\begin {align} G(C) & \mapsto C^B \\ G(g)(h) & \mapsto h \circ g \end{align}$$There is a canonical bijection $\mathbf{Set}(A × B,C) \cong \mathbf{Set}(A,C^B)$ (*Currying*). Therefore $F$ and $G$ are adjunct.
## Units/Counits

For each $A \in \mathscr{A}$, we have a map
$$
\left( A \xrightarrow{\eta_A} GF(A) \right) = \overline {\left( F(A) \xrightarrow{1} F(A) \right)}
$$
Dually, for each $B \in \mathscr{B}$, we have a map
$$
\left( FG(B) \xrightarrow{\varepsilon_B} B \right) = \overline {\left( G(B) \xrightarrow{1} G(B) \right)}
$$
They therefore are natural transformations
$$
\eta: 1_{\mathscr{A}} \rightarrow G \circ F, \quad \varepsilon: F \circ G \rightarrow 1_{\mathscr{B}},
$$
defined by $\eta_A = \overline{1_{F(A)}}$ and $\epsilon_B = \overline{1_{G(B)}}$ called the unit and counit of the adjunction, respectively.

- **Proof of naturality**:
$$
GF(f)\circ\overline{1_{F(A)}} = 
\overline{F(f)\circ1_{F(A)}} = \overline{F(f)} = \overline{1_{F(A')}\circ F(f)} = \overline{1_{F(A')}}\circ f$$
$$
\overline{1_{G(B')}} \circ FG(g) = \overline{1_{G(B')} \circ G(g)} = \overline{G(g)}= \overline{G(g)\circ 1_{G(B)}} = g \circ \overline{1_{G(B)}}$$

- It follows that $\overline{g}  = G( g ) \circ \eta_A$ and $\overline{f}  = \epsilon_B  \circ F( f )$

### Triangle Identities
The triangles 

```tikz
\usepackage{tikz-cd}

\begin{document}
    \begin{tikzcd} F \arrow[r, "F\eta"] \arrow[rd, "1_F"'] & FGF \arrow[d, "\varepsilon F"] \\ & F \end{tikzcd} \quad \begin{tikzcd} G \arrow[r, "\eta G"] \arrow[rd, "1_G"'] & GFG \arrow[d, "G\varepsilon"] \\ & G \end{tikzcd}
\end{document}
```

in the functor category $[\mathscr A, \mathscr B]$ and $[\mathscr B, \mathscr A]$ commute, that is
- $\epsilon_{F(A)} \circ F(\eta_A) = 1_{F(A)}$ for all $A \in \mathscr A$
	- $\epsilon_{F(A)} \circ F(\eta_A) = \overline{1_{GF(A)}} \circ F(\eta_A) = \overline{1_{GF(A)} \circ \eta_A} = \overline {\eta_A} = 1_{F(A)}$ 
- $G(\epsilon_B) \circ \eta_{G(B)} = 1_{G(B)}$ for all $B \in \mathscr B$
### Equivalence of Definitions
If $F\dashv G$, there is an one-to-one correspondence between:
- Adjunctions between $F$ and $G$
- Pairs of natural transformations $(\eta: 1_{\mathscr A} \to GF, \epsilon: FG \to 1_{\mathscr B})$ that satisfies the triangle identity

**Proof**
- Indeed, a pair $(\eta,\epsilon)$ follows an adjunction. 
- On the other hand, given a pair $(\eta,\epsilon)$, we can define the unique adjunction via $\overline{g}  = G( g ) \circ \eta_A$ and $\overline{f}  = \epsilon_B  \circ F( f )$. 
	- $\overline{\overline{f}} = G(\epsilon_B  \circ F( f )) \circ \eta_{A} = G(\epsilon_B) \circ GF(f) \circ \eta_{A} = G(\epsilon_B) \circ \eta_{G(B)} \circ f = f$ (Triangle identity), and the adjunction is well-defined.
Therefore, $F\dashv G$ iff there exists pairs of natural transformations $(\eta: 1_{\mathscr A} \to GF, \epsilon: FG \to 1_{\mathscr B})$ that satisfies the triangle identity.

## Initial Objects
### Initial/Terminal
- Initial objects: For every $A \in ob(\mathscr A)$, there is exactly one map $I \to A$.
- Terminal objects: For every $A \in ob(\mathscr A)$, there is exactly one map $A \to T$.
- Initial objects forms an isomorphism class. (also true for terminal objects)
- A left adjoint to $\mathscr A → \mathbf 1$ is exactly an initial object of $\mathscr A$, while the right adjoint is a terminal object.
### Comma Category
Given $P: \mathscr A \to \mathscr C$ and $Q: \mathscr B \to \mathscr C$, the comma category ($P ⇒ Q$) (often written as ($P ↓ Q$)) is the category defined as follows:
- Objects are triples $(A,h,B)$ with $A\in \mathscr A$, $B\in \mathscr B$, and $h\in \mathscr C(P(A),Q(B))$;
- Maps $(A,h,B) → (A',h',B')$ are pairs $(f: A → A', g: B → B')$ of maps such that the square$$\begin{array}{ccc}

P(A) & \xrightarrow{P(f)} & P(A') \\

h \downarrow & & \downarrow h' \\

Q(A) & \xrightarrow{Q(g)} & Q(A')

\end{array}$$ commutes ($h' \circ P(f) = Q(g) \circ h$).

**Slice Category**: An object $(X,h)$ in the slice category $\mathscr A / A$ consists of $X \in \mathscr A$ and $h \in \mathscr A(X,A)$; a morphism $(X,h)→(X',h')$ is a map $f : \mathscr A(X,X')$ making the triangle
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
X \arrow[rr, "f"] \arrow[rd, "h"'] &   & X' \arrow[ld, "h'"] \\
                                   & A &                    
\end{tikzcd}
\end{document}
```
commute. It is the same as $1_{\mathscr A} \Rightarrow A$, where $A$ is the functor $\mathbf 1\to \mathscr A$. 

**Comma category on an object**: In $A \Rightarrow G$, the objects are pairs $(B ∈ \mathscr B, f:A → G(B))$. A morphism $(B,f) → (B',f')$ in $(A ⇒ G)$ is a map $q : B → B'$ in $\mathscr B$ making the triangle
```tikz
\usepackage{tikz-cd}

\begin{document}
    \begin{tikzcd} A \arrow[r, "f"] \arrow[rd, "f'"'] & G(B) \arrow[d, "G(q)"] \\ & G(B') \end{tikzcd}
\end{document}
```

**Unit is initial in the comma category**: Take an adjunction $F \dashv G$ and an object $A ∈ \mathscr A$ . The unit map $(F(A),η_A: A→GF(A))$ is an initial object of ($A⇒G$). 
- In other words, for all $(B, f: A\to G(B))$ in $A\Rightarrow G$, there is exactly one $q: F(A) \to B$ such that $G(q) \circ \eta_A = f$. It follows the property of the unit that $G(q) \circ \eta_A = \overline{q}$, and $q = \overline{f}$ is unique.
### Equivalence of definitions
If $F\dashv G$, there is an one-to-one correspondence between:
- Adjunctions between $F$ and $G$
- Natural transformations $\eta: 1_{\mathscr A} \to GF$ such that the unit $(F(A),η_A: A→GF(A))$ is initial in $A⇒G$ for all $A \in \mathscr A$. 

**Proof**
- Indeed, the unit $\eta$ follows an adjunction and satisfies the initial requirement. 
- For an $\eta: 1_{\mathscr A} \to GF$ that satisfies the initial requirement, there is an one-to-one correspondence between $f: A \to G(B)$ and $g: F(A) \to B$ defined by $G(g) \circ \eta_A = f$.