# Limits
## Definition
 Let $\mathscr A$ be a category and $\mathbf I$ a small category.
- A functor $D : \mathbf I \to \mathscr A$ is called a **diagram** in $\mathscr A$ of shape $\mathbf I$
- A **cone** on $D$ is an object $A \in \mathscr A$ (the **vertex** of the cone) together with the family $(A\overset{f_I}\longrightarrow D(I))_{I\in\mathbf I}$ of maps in $\mathscr A$ such that for all maps $I \overset {u}\rightarrow J$ in $\mathbf I$, the triangle commutes:
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
                                        &  & D(I) \arrow[dd, "Du"] \\
A \arrow[rru, "f_I"] \arrow[rrd, "f_J"] &  &                       \\
                                        &  & D(J)                 
\end{tikzcd}
\end{document}
```
- A **limit** of $D$ is a cone $(L\overset{f_I}\longrightarrow D(I))_{I\in\mathbf I}$ with the property that for any cone on $D$, there exists a unique map $\bar f: A \to L$ such that $p_I \circ \bar f = f_I$ for all $I \in \mathbf{I}$. The maps $p_I$ are called the **projections** of the limit.
	- For any $A\in \mathscr A$  map $A \to L$ corresponds one-to-one with cones on $D$ with vertex $A$.  -> Limits are unique up to canonical isomorphism
	- A *map into* $L = \underset {\leftarrow I} \lim D$  is a cone of $D$.
### Diagrams
![[Pasted image 20241019154314.png]]
- **Products**: A diagram of shape $\mathbf T$ is a pair of objects of $\mathscr A$. A cone on $D$ is an object $A$ together with maps $f_1: A \to X$ and $f_2 : A \to Y$. 
- **Equalizers**: A diagram of shape $\mathbf E$ is a fork of $\mathscr A$. A cone on $D$ is a fork.
- **Pullbacks**: A diagram of shape $\mathbf P$ is a commutative sqaure of $\mathscr A$. A cone on $D$ is a commutative square.
- Let $\mathbf I = (\mathbb N, \le)^{\text {op}}$. A diagram $D :\mathbf I \to \mathscr A$ consists of objects and maps $$\cdots \overset {s_3} \longrightarrow X_2 \overset {s_2} \longrightarrow X_1 \overset {s_1} \longrightarrow X_0$$A limit of this is called an **inverse limit**.
### Existence of limits
- Let $D: \mathbf I \to \mathbf {Set}$, 
     $\lim_{\leftarrow \mathbf I} D \cong \mathbf{Set} (1, \lim_{\leftarrow \mathbf I} D) \cong \{\text{cones on } D\text{ with vertex 1}\}$
		   $\cong \{x_I \mid \forall I \in \mathbf I, u \in \mathbf I(I, J), \  x_I \in D(I), (Du)(x_I) = x_J\}$
- A category $\mathscr A$ **has limits of shape** $\mathbf I$ if for every diagram $D$ of shape $\mathbf I$ in $\mathscr A$, a limit of $D$ exists.
- A category **has all (small) limits** if it has limits of shape $\mathbf I$ for all small categories $\mathbf I$.
- A category is **finite** if it contains finitely many maps. A finite limit is a limit of shape $\mathbf I$ for some finite category $\mathbf I$. 
- If $\mathscr A$ has all products and equalizers then $\mathscr A$ has all limits.
	- Let $D : \mathbf I \to \mathscr A$ be a diagram in $\mathscr A$. Define maps $$\prod_{I\in \mathbf I}D(I) \overset s {\underset t \rightrightarrows} \prod_{u\in \mathbf I(J,K)}D(K)$$as follows: $$s = \prod_{u\in \mathbf I(J,K)}Du \circ \pi_J, \ t = \prod_{u\in \mathbf I(J,K)} \pi_{K}$$Then for all cone $(A,(f_I)_{I\in \mathbf I})$ on $D$, $A$ is a fork of $s$ and $t$ (check), which means that there exists a unique map $\bar f: A \to L$ such that $f_I \circ \bar f = p_I$ for all $I \in \mathbf{I}$.
- If $\mathscr A$ has binary products, a terminal object and equalizers then $\mathscr A$ has finite limits.
	- If $\mathscr A$ has binary products and a terminal object, $\mathscr A$ has all finite products.
		- The empty product is the terminal object $0$, which is the limit of the empty diagram.
## Products
#### Binary Products
A product of $X, Y \in \mathscr A$ consists of an object $P$ and maps
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
  & P \arrow[ld, "p_1"'] \arrow[rd, "p_2"] &   \\
X &                                        & Y
\end{tikzcd}
\end{document}
```
such that for all $f_1: A \to X, f_2: A \to Y$, exists unique $\bar f: A \to P$ such that $p_1 \circ \bar f = f_1$, $p_2 \circ \bar f = f_2$.
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
  & A \arrow[ldd, "f_1"'] \arrow[rdd, "f_2"] \arrow[d, "\exists ! \bar f" description] &   \\
  & P \arrow[ld, "p_1"'] \arrow[rd, "p_2"]                                             &   \\
X &                                                                                    & Y
\end{tikzcd}
\end{document}
```
$p_1$ and $p_2$ are called projections.
#### General Products
Let $\mathscr A$ be a category, $I$ be a set, and $(X_i)|_{i\in I}$ is a family of objects of $\mathscr A$. A product of $(X_i)|_{i\in I}$  consists of an object $P$ and a family of maps
$$\left( P \overset{p_i}{\longrightarrow} X_i \right)_{i \in I}$$
with the property that for all objects $A$ and families of linear maps
$$\left( A \overset{f_i}{\longrightarrow} X_i \right)_{i \in I}
$$
there exists a unique map $\bar f: A \to P$ sucht that $p_i \circ \bar f = f_i$ for all $i \in I$.
### Examples
- For all $X, Y \in \mathbf{Set}$, $X \times Y$ is a product of $X$ and $Y$.
- In a poset, the greatest lower bound of $x$ and $y$ is a product.
	- In $(\mathbb R, \le)$, $\min(x,y)$ is a product of $x$ and $y$, since for all $a$ s.t. $a \le x$ and $a \le y$, $a \le \min(x,y)$.
	- In $(\mathscr P(S), \subseteq)$,  $X\cup Y$ is a product of $X$ and $Y$. 
## Equalizers
- A **fork** in a category consists of objects and maps such that $sf = tf$.
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
A \arrow[r, "f"] & X \arrow[r, "s", shift left] \arrow[r, "t"', shift right] & Y
\end{tikzcd}
\end{document}
```
Let $\mathscr{A}$ be a category and let $X\underset{s}{\overset{t}{\rightrightarrows}}Y$ be objects and maps in $\mathscr A$, An **equalizer** of $s$ and $t$ is an object $E$ together with a map $i: E \to X$ such that 
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
E \arrow[r, "f"] & X \arrow[r, "s", shift left] \arrow[r, "t"', shift right] & Y
\end{tikzcd}
\end{document}
```
is a fork and for any fork $A \overset{f} \rightarrow X\underset{s}{\overset{t}{\rightrightarrows}}Y$, there exists a unique $\bar f: A \to E$ such that
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
A \arrow[d, "\tilde{f}"'] \arrow[r, "f"] & X \\
E \arrow[ru, "i"'] 
\end{tikzcd}
\end{document}
```
commutes.
### General Equalizers
Take a set $\Lambda$ and a family of pairs of map $(X\underset{s_\lambda}{\overset{t_\lambda}{\rightrightarrows}}Y_\lambda)_{\lambda \in \Lambda}$. The solution set $\{x \in X \mid s_{\lambda}(x) = t_{\lambda}(x)\  \forall \lambda \in \Lambda \}$ is the equalizer of the functions
$$
(X\underset{s_\lambda|\lambda\in\Lambda}{\xrightarrow{t_\lambda|\lambda\in\Lambda}}\prod_{\lambda \in \Lambda} Y_\lambda)
$$
### Examples
- An equalizer in $\mathbf{Set}$ is $E = \{x \in X \mid s(x) = t(x)\}$ for $X\underset{s}{\overset{t}{\rightrightarrows}}Y$, with $i$ being the inclusion map.
- Group homomorphism $\theta: G \to H$ induces a fork $\ker \theta \overset{\iota} \hookrightarrow G\underset{\epsilon}{\overset{\theta}{\rightrightarrows}}H$ where $\iota$ is the inclusion and $\epsilon$ is the trivial homomorphism ($\epsilon (g) = 1$) which is an equalizer in $\mathbf{Grp}$.
- Given linear maps $V\underset{t}{\overset{s}{\rightrightarrows}}W$, an equalizer in $\text{Vect}_k$ is $\ker (t-s) \overset{i} \hookrightarrow V\underset{t}{\overset{s}{\rightrightarrows}}W$, with $i$ being the inclusion map.
## Pullbacks
Let $\mathscr A$ be a category, and take objects and maps in $\mathscr A$:
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
                  & Y \arrow[d, "t"] \\
X \arrow[r, "s"'] & Z               
\end{tikzcd}
\end{document}
```
A **pullback** (fibred product) of this diagram is an object $P \in \mathscr A$ together with maps $p_1: P \to X, p_2: P \to Y$ such that
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
P \arrow[r, "p_2"] \arrow[d, "p_1"] & Y \arrow[d, "t"] \\
X \arrow[r, "s"] & Z
\end{tikzcd}
\end{document}
```
commutes, and that for any commutative square
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
A \arrow[r, "f_2"] \arrow[d, "f_1"] & Y \arrow[d, "t"] \\
X \arrow[r, "s"] & Z
\end{tikzcd}
\end{document}
```
in $\mathscr A$, there is a unique map $\bar f: A \to P$ such that
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
A \arrow[rdd, "f_1", bend right] \arrow[rrd, "f_2", bend left] \arrow[rd, "\exists!\bar f", dotted] &                                     &                  \\
                                                                                                    & P \arrow[r, "p_2"] \arrow[d, "p_1"] & Y \arrow[d, "t"] \\
                                                                                                    & X \arrow[r, "s"]                    & Z               
\end{tikzcd}
\end{document}
```
commutes.
### Examples
- One pullback in $\mathbf{Set}$ is $P = \{ (x,y) \mid s(x) = t(y)\}$  
	- Given $f: X \to Y$ and $Y' \subseteq Y$, the inverse image is defined as $f^{-1}Y' \mapsto \{x| f(x) \in Y'\}$; along with the inclusion maps $i: f^{-1}Y \hookrightarrow X$  and  $j: Y' \hookrightarrow Y$ the following square is a pullback:
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
f^{-1}Y' \arrow[d, "i"', hook] \arrow[r, "f|_{f^{-1}Y'}"] & Y' \arrow[d, "j", hook] \\
X \arrow[r, "f"]                                          & Y                      
\end{tikzcd}
\end{document}
```
- Intersections of subsets are another example of pullbacks. Let $Y \subseteq Z$ and $X \subseteq Z$, the following square is a pullback, with all the map being inclusions:
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
X\cap Y \arrow[d, hook] \arrow[r, hook] & Y \arrow[d, hook] \\
X \arrow[r, hook]                       & Z                
\end{tikzcd}
\end{document}
```
## Monics
A map $f : \mathscr A (X,Y)$ is a **monic** (or **monomorphism**) if for all objects $A$ and maps $A\overset x{\underset {x'}\rightrightarrows} X$, $$f\circ x = f\circ x' \implies x = x'$$
- A map $f : \mathscr A (X,Y)$ is a monic if and only if the square
```tikz
\usepackage{tikz-cd}

\begin{document}
\begin{tikzcd}
X \arrow[r, "1"] \arrow[d, "1"] & X \arrow[d, "f"] \\
X \arrow[r, "f"] & Z
\end{tikzcd}
\end{document}
```
is a pullback