## Definition
Let $\mathscr A$ be a **locally small** category. A functor $X: \mathscr A \rightarrow \mathbf{Set}$ is **representable** by $A \in \mathscr A$ if $X \cong H^A$, where $H^A = \mathscr A(A,-) : \mathscr A \rightarrow \mathbf{Set}$ is a functor defined by 
- $H^A(B) = \mathscr A(A,B)$
- $H^A(g)= g \circ -$ (or less formally, $\lambda p. g\circ p$)
### Dual Definition
Let $\mathscr A$ be a **locally small** category. A contravariant functor $X: \mathscr A^\text{op} \rightarrow \mathbf{Set}$ is **representable** by $A \in \mathscr A$ if $X \cong H_A$, where $H_A = \mathscr A(-,A) : \mathscr A^\text{op} \to \mathbf{Set}$ is a contravariant functor defined as:
- $H_A(B) = \mathscr A(B, A)$
- $H_A(g) = - \circ g$
### Yoneda Embedding
- *Observation*: map $A' \xrightarrow{f} A$ induces a natural transformation $H^f : H^A(\mathscr B) \to H^{A'}(\mathscr B) = \mathscr A(A,B) \to \mathscr A(A',B)$  
- Let $\mathscr A$ be a **locally small** category. The **contravariant** functor $H^\bullet: \mathscr A ^ \text{op} \rightarrow [\mathscr A, \mathbf{Set}]$ is defined by $H^\bullet(A) = H^A$ and $H^\bullet(f) = H^f = - \circ f$
- The **Yoneda embedding** of $\mathscr A$ is the functor $H_\bullet: \mathscr A \to [\mathscr A^\text{op},\mathbf{Set}]$ defined by $H_\bullet(A) = H_A$ and $H_\bullet(f) = H_f = f \circ -$. 
- The Hom-functor $\text{Hom}_\mathscr A : \mathscr A ^\text{op} \times \mathscr A \to \mathbf{Set}$ is defined by 
	- $\text{Hom}_\mathscr A(A,B) = \mathscr A(A,B)$
	- $\text{Hom}_\mathscr A (f,g) = g \circ -\circ f$
- Naturality of adjunct functors:
	![[Pasted image 20241001110551.png]]
### Generalized Element
Let $A$ be an object of a category. A generalized element of $A$ is a map with codomain $A$. A map $S \to A$ is a generalized element of $A$ of shape $S$ .
### Example
- $1_{\mathbf{Set}}$ (the identity functor) is representable by $1$(the singleton set), since $H^1(A) \cong A$
- $\text{ob}: \mathbf{Cat} \rightarrow \mathbf{Set}$ (sending small categories to their set of objects) is representable by $\mathbf{1}$(the terminal category). $H^{\mathbf{1}}(\mathscr A) \cong \text{ob}(\mathscr A)$ 
- $H: \mathbf{Cat} \rightarrow \mathbf{Set}$ (sending small categories to their set of maps) is representable by the category $\mathbf 2$ consisting of two objects and one nonidentity map.
- The left-$M$-set is only one representable functor $M \rightarrow \mathbf{Set}$ up to isomorphism, where $M$ is the one-object monoid category. The unique representable is called the **left regular representation** of $M$.
- Every set-valued functor with a left adjoint is representable by $F(1)$ 
	- $G(B) \cong \mathbf{Set}(1,G(B)) \cong \mathscr B(F(1),B)$
	- Example: $U(V) \cong \mathbf{Vect}_k(k,V)$, where $U$ is the forgetful functor
- There is a functor $\mathscr P: \mathbf{Set}^\text{op} \to \mathbf{Set}$ defined by $\mathscr P(B) = 2^B$ and $\mathscr P(g)(U) = g^{-1}U$ (inverse image of $U$) is representable by $H_2$.
## Yoneda Lemma
- A natural transformation in the presheaf category $H_A → X$ is an element of $X(A)$. $[\mathscr A^\text{op}, \mathbf {Set} ] (H_A,X) \cong X(A)$ **naturally in** $A\in \mathscr A$ and $X \in [\mathscr A^\text{op}, \mathbf {Set} ]$
$$[\mathscr{A}^{\text{op}}, \mathbf{Set}](H_A, X) \overset{(\hat{\,})}{\underset{(\tilde{\,})}{\rightleftharpoons}} X(A)$$
- Given $\alpha : H_A\to X$ define $\hat \alpha = \alpha_A(1_A)$ 
- Given $x \in X(A)$, define $\tilde x: H_A \to X$ as
$$ \tilde x_B : H_A(B)=\mathscr A(B,A) \to X(B)$$
$$\tilde{x}_B(f) \mapsto (X(f))(x)$$
	- Proof of naturality: Given $h \in \mathscr A(B,A), g \in \mathscr A(B,A) \to \mathscr A(B',A) = \mathscr A(B',B)$, $X(g)(\tilde{x}_B(f)) = X(g)(X(h)(x)) = X(h\circ g)(x) = \tilde{x}_{B'}(h \circ g) = \tilde{x}_{B'}(H_A(g)(h))$ 
- Proof of isomorphism: 
	- Given $x$, $X(1_A)(x) = 1_{X(A)}(x) = x$
	- Given $\alpha : H_A \to X$, define $a'_B(h) \mapsto X(h)(\alpha_A(id_A)) = \alpha_B(id_A \circ h) = \alpha_B(h)$ 
- Proof of naturality in $A$ ( $(\hat{\,})$  is a natural transformation $[\mathscr A^\text{op},\mathbf{Set}](H_\bullet,X) \to X$): 
![[Pasted image 20241011164345.png]]
	- $(\alpha \circ H_f)_B(1_B) = \alpha_B(H_f(1_B))= \alpha_B(f\circ 1_B) = \alpha_B(f) = X(f)(\alpha_A(1_A))$   
- Proof of naturality in $X$ ($(\hat{\,})$  is a natural transformation $[\mathscr A^\text{op},\mathbf{Set}](H_A,\bullet) \to \bullet(A)$):
![[Pasted image 20241011164415.png]]
	- $(\theta \circ \alpha)_A = \theta_A \circ \alpha_A$ 
## Corollaries of Yoneda
### Representation is Universal Element
A representation of $X : \mathscr A^\text{op} \to \mathbf{Set}$ corresponds to an object $A \in \mathscr A$ together with an element $u \in X(A)$ such that *for each $B \in \mathscr A$ and $x \in X(B)$, there is a unique map $\bar x: B \to A$ such that $X(\bar x)(u) = x$.*
	- $X(\bar x)(u) = \tilde u_B(\bar x) \iff x$ (the bijectivity of $\tilde u$) 
	- $u$ is called a **universal element** of $X$
	- Presheaf $X$ $\iff$ A universal element of $X$
- For every adjunction $\mathscr{A} \overset{F}{\underset{G}{\rightleftarrows}} \mathscr{B}$, the functor $X = \mathscr A(A,G(-)): \mathscr B \to \mathbf{Set}$ is representable. This can be expressed by:
	1. $\mathscr{A}(A, G(B)) \cong \mathscr{B}(F(A), B)$ naturally in $B$, i.e. $X \cong H^{F(A)}$
	2. The unit $\eta_A: A \to G(F(A))$ is an initial object of the comma category $A\Rightarrow G$, i.e. $\eta_A \in X(F(A))$ satisfies the condition above.
- $-1$ and $1$ in $U(\mathbb Z)$ are universal elements of the forgetful functor $U: \mathbf{Grp} \to \mathbf{Set}$, since for every $x \in U(G)$ there is a unique homomorphism $\phi$ such that $U(\phi)(1) = x$ (the same is for $-1$)
### Yoneda Embedding is Full & Faithful
The Yoneda embedding $H_\bullet: \mathscr A \to [\mathscr A^\text{op},\mathbf{Set}]$ is full and faithful, i.e. $f \mapsto H_f$ is bijective 
	- By the Yoneda lemma, $(\tilde{\ }): H_{A'}(A) = \mathscr A(A,A')   \to [\mathscr A^\text{op},\mathbf{Set}](H_A,H_{A'})$ is bijective; $\tilde f(g) = H_{A'}(g)(f) = H_f(g)$.
	- Map of presheaves $\iff$ Map in $\mathscr A$
- $\mathscr A$ is equivalent to the full subcategory of $[\mathscr A^\text{op},\mathbf{Set}]$ whose objects are representables. 
- There are as many isomorphisms $A\leftrightarrows A'$  as there are isomorphisms $H_A \leftrightarrows H_{A'}$; if $H_{A'} \cong X$, there are as many of these as isomorphisms $H_A \leftrightarrows X$, which is the number of universal elements of $X(A)$ 
## Isomorphisms of Representables
$H_A \cong H_{A'} \iff A \cong A' \iff H^A \cong H^{A'}$  
