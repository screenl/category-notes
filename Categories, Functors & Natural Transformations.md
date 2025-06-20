## Categories

A **category** $\mathscr A$ consists of:
- A collection $\text {ob}(\mathscr A )$ of **objects**;
- For each $A, B ∈ \text {ob} (\mathscr A)$, a collection $\mathscr A (A, B)$ of **maps** or **arrows** or **morphisms** from A to B; 
- For each $A, B,C ∈ \text {ob}(\mathscr A )$, a function  
$$\begin{align}
\mathscr A(B,C)× \mathscr A(A,B) & → \mathscr A(A,C) \\
(g, f ) & \mapsto g \circ f
\end{align}
$$
	,called composition;
- For each $A ∈ \text {ob} (\mathscr A)$, an element $1_A$ of $\mathscr A(A, A)$, called the **identity** on $A$,

satisfying the following axioms:
- **Associativity**: For each $f ∈ \mathscr A(A,B), g ∈ \mathscr A(B,C)$ and $h ∈ \mathscr A(C,D)$, we have $(h\circ g) \circ f =h \circ (g \circ f)$;
- **Identity laws**: For each $f ∈ \mathscr A(A,B)$, we have $f\circ 1_A = f = 1_B \circ f$.

**Discrete Categories**: Categories whose only morphisms are identity morphisms.
**Dual Category**: $\mathscr A^{op}$ is the dual category of $\mathscr A$ formed by:
- $\text{ob}(\mathscr A^{op}) = \text{ob}(\mathscr A)$
- $\mathscr A(A,B) = \mathscr A^{op}(B,A)$
## Functors
Let $\mathscr{A}$ and $\mathscr{B}$ be categories. A functor $F : \mathscr{A} \to \mathscr{B}$ consists of:
- A function $\text{ob}(\mathscr{A}) \to \text{ob}(\mathscr{B})$, written as $A \mapsto F(A)$;
- For each $A, A' \in \mathscr{A}$, a function $\mathscr{A}(A, A') \to \mathscr{B}(F(A), F(A'))$, written as $f \mapsto F(f)$,

satisfying the following axioms:
- $F(f' \circ f) = F(f') \circ F(f)$ whenever $A \xrightarrow{f} A' \xrightarrow{f'} A''$ in $\mathscr{A}$;
- $F(1_A) = 1_{F(A)}$ whenever $A \in \mathscr{A}$.

### Free/Forgetful

**Forgetful functors**: Takes the underlying object and does nothing on morphisms. (*forgets* some structure or properties) 
- Example: $U : \textbf {Grp} → \textbf {Set}$ defined as follows: if $G$ is a group then $U(G)$ is the elements of $G$; if $f : G → H$ is a group homomorphism then $U(f)$ is the $f$itself. 

**Free functors**: The only equations that hold between elements of the free object are those that follow from the defining axioms of the algebraic structure. 
Examples:
 - Free monoids
	 - $\{x,y\} \mapsto (\{x^ay^b\ | \ a,b \in N\},\cdot)$ *(monomials of a set)*
 - Free rings
	 -  $\{x,y\} \mapsto (\{ k_1 x^{a_1} y^{b_1} + ... +  k_n x^{a_n} y^{b_n} \ | \ n \in N, a_i,b_i \in N \},+,\cdot)$ *(polynomials of a set)*
 - Free vector spaces
	 - $\{x,y\} \mapsto (F, \{ax+by\ | \ a,b \in F \})$ *(linear combinations of a set)*

**Schemes**: ...

### Contravariant functors:
$F: \mathscr A^{op}  → \mathscr B$ is a contravariant functor if it maps $A\rightarrow A'$ to $F(A')\rightarrow F(A)$
- reverse the arrows
- $\mathscr C → \mathscr D$ correspond one-to-one with functors $\mathscr C ^{op} → \mathscr D^{op}$;
- $(\mathscr A ^{op})^{op} = \mathscr A$
- $\mathscr A^{op}  → \mathscr B =\mathscr A  → \mathscr B^{op}$

**Presheafs**: A presheaf on $\mathscr A$ is a functor $\mathscr A ^{op} → \textbf{Set}$. 

### Faithful/Full/Surjective
- A functor $F: \mathscr A \rightarrow \mathscr B$ is **faithful** if $F$ is injective for morphisms from $A$ to $A'$, **full** if $F$ is surjective for morphisms from $A$ to $A'$.
- A functor $F : \mathscr A → \mathscr B$ is **essentially surjective** on objects if for all $B∈ \mathscr B$, there exists $A∈\mathscr A$ such that $F(A) \cong B$.

### Subcategory
A subcategory $\mathscr S$ of $\mathscr A$ consists of a subclass $ob(\mathscr S)$ of $ob(\mathscr A)$, for each pair of objects $S,S'∈ob(\mathscr S)$, a subclass $\mathscr S(S,S')⊆\mathscr A(S,S')$ of morphisms between these objects in $\mathscr A$, which satisfy
- Closure under composition: If $f \in \mathscr S(S, S')$ and $g \in \mathscr S(S', S'')$, then $g \circ f \in \mathscr S(S, S'')$.
- Closure under identity: For every object $S \in \text{ob}(\mathscr S)$, the identity morphism $\text{id}_S \in \mathscr S(S, S)$.
A **full** subcategory is a special kind of subcategory where the set of morphisms between every pair of objects remains same:
- The objects are a subclass $\text{ob}(\mathscr F) \subseteq \text{ob}(\mathscr A)$.
- For every pair of objects $F, F' \in \text{ob}(\mathscr F)$, $F(F, F') = A(F, F')$.
### Categories as algebraic structures
- A **monoid** is essentially the same thing as a category that has only one object and in which all the maps are **isomorphisms**. $$\begin{align} 
\textit{category } \mathscr A \textit{ with single object A} 
&& \textit{corresponding monoid } G \\
\text{maps in   } \mathscr A && \text{elements of }G\\
\circ\  \text{in } \mathscr A && \cdot \text{in } G \\
1_A\ && 1 \in G
 \end{align}$$
	 - A functor $F: \mathscr G \rightarrow \mathscr H$ is a homomorphism $G\rightarrow H$.
	 - A functor $F: \mathscr G \rightarrow \textbf{Set}$ consists of a set $F(A) \mapsto S$ (the underlying set of the monoid), and the monoid action $$\begin{align} G\to S & \to S\\F(g)(s) &\mapsto g\cdot s \end{align}$$such that the operation satisfies associativity and identity laws. (called a **left-G-set**, since the expression is like $g_0\cdot g_1 \dots  g_n \cdot s$)
 - A preordered set $(S,\lesssim)$ can be regarded as a category $A$ in which, for each $A, B ∈ \mathscr A$ , there is at most one map from $A$ to $B$ ($A \lesssim B$).
	 - Functors between preordered-set-categories: Order-preserving maps.

## Natural Transformations
A natural transformation $\alpha: F \to G$ is a collection of morphisms in $\mathscr{B}$ indexed by the objects of $\mathscr{A}$. For each object $A \in \mathscr{A}$, there is a morphism $\alpha_A: F(A) \xrightarrow{\alpha_A} G(A)$ in $\mathscr{B}$ such that
$$\begin{array}{ccc}

F(A) & \xrightarrow{F(f)} & F(A') \\

\alpha_A \downarrow & & \downarrow \alpha_{A'} \\

G(A) & \xrightarrow{G(f)} & G(A')

\end{array}$$
commutes, that is, $\alpha_{A'} \circ F(f) = G(f) \circ \alpha_A$. 
- $\alpha_A$ are called **components** of $\alpha$.
- From each map $A \xrightarrow{f} A'$ in $\mathscr A$ , it is possible to construct exactly one map $F(A)→G(A')$ in $\mathscr B$.

### Functor categories 
The functor category from $[\mathscr A, \mathscr B]$ (or, $\mathscr B ^{\mathscr A}$) consists of the functors from $\mathscr A$ to $\mathscr B$ as objects and the natural transformations between them as maps.
- Composition of natural transformations: $(\beta \circ \alpha)_A := \beta_A \circ \alpha_A$
- Identity: $(1_F)_A = 1_{F(A)}$ 

### Natural isomorphism
A natural isomorphism is an isomorphism in the functor category, or, $α$ is a natural isomorphism if and only if $α_A : F(A) → G(A)$ is an isomorphism for all $A∈\mathscr A$.
 - Natural isomorphism means that there is a one-to-one correspondence between objects mapped with $F$ and objects mapped with $G$. We can also deduce a one-to-one-correspondence between mapped morphisms (via the commute rules).
 - Natural isomorphism is an equivalence relation.

### Equivalence of categories
An equivalence between categories $\mathscr A$ and $\mathscr B$ ($\mathscr A \simeq \mathscr B$) consists of a pair of functors together with natural isomorphisms: $η:1_{\mathscr A} →G\circ F, ε:F\circ G→1_{\mathscr B}$.
- A functor is an equivalence if and only if it is **full, faithful and essentially surjective** on objects.

**Dual categories**: $\mathscr A$ is dual to $\mathscr B$ if $\mathscr A^{op} \simeq \mathscr B$

### Examples
- **G-equivariant maps**: In a monoid category $\mathscr G$ with single object $A$. There is a natural transformation $\alpha: S(A)\to T(A)$ between two left-$G$-sets $S,T: \mathscr G \to \textbf{Set}$, which satisfies $\alpha(g\cdot s) = g \cdot \alpha(s)$.
- **Determinants**: For every commutative ring $R$, $n \times n$ matrices with entries in $R$ is a functor $M_n(R): \textbf{CRing} \to \textbf{Mon}$. There is also the forgetful functor $U(R) = (R,\cdot)$. The determinant function is a monoid homomorphism as well as a natural transformation. 

