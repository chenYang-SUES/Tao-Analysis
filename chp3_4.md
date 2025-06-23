## 3.4 Images and Inverse Images

We know that a function $f: X \to Y$ from a set $X$ to a set $Y$ can take individual elements $x \in X$ to elements $f(x) \in Y$. Functions can also take subsets in $X$ to subsets in $Y$:

> Definition 3.4.1 (*Images of sets*) if $f: X \to Y$ is a function from $X \to Y$, and $S$ is a subset of $X$, we define[^4] $f(S)$ to be the set
> $$
f(S):=\{f(x): x\in S\};
$$
this set is a subset of $Y$ and is sometimes called the *image* of $S$ under the map $f$. We sometimes call $f(S)$ the *forward image* of $S$ to distinguish it from the concept of *inverse image* $f^{-1}(S)$ of $S$, which is defined below.

Note that the set $f(S)$ is well-defined thanks to the axiom of replacement (Axiom 3.7). One can also define $f(S)$ using the axiom of specification (Axiom 3.6) instead of replacement, but we have leave this as an exercise to reader. The image $f(X)$ of the domain is also known as the *range* of the function $f: X \to Y$; it is a subset of the codmain $Y$.

!!! Note If $f(S)$ is defined by axiom of replacement, what is the statement $P(x,y)$?
    Let $P(x,y)$ be the statement that $y=f(x)$ and $x \in S$. Since the definition of functions follows the vertical line test, for every $x \in S$ there is exactly one $y \in Y$ such that $P(x,y)$ holds and $y=f(x)$ as per this definition. So there exists a set $\{y: y=f(x), x \in S\}$, i.e., $\{f(x):x\in S\}$.

***Example 3.4.2*** If $f: \mathbf{N} \to \mathbf{N}$ is the map $f(x)=2x$, then the forward image of $\{1, 2, 3\}$ is $\{2, 4, 6\}$:
$$
f(\{1, 2, 3\}) = \{2, 4, 6\}.
$$

More informally, to compute $f(S)$, we take every element $x$ of $S$ and apply $f$ to each element individually, and then put all the resulting objects together to form a new set.

In the above example, the image had the same size as the original set. But sometimes the image can be smaller, because $f$ is not one-to-one (see Defintion 3.3.17).

***Example 3.4.3*** (Informal) let $\mathbf{Z}$ be the set of integers (which we will define rigorously in the next section) and let $f: \mathbf{Z} \to \mathbf{Z}$ be the map $f(x) = x^2$, then
$$
f(\{-1,0,1,2\}) = \{0,1,4\}.
$$
Note that $f$ is not one-to-one because $f(-1) = f(1)$.

Note that
$$
x \in S \implies f(x) \in f(S)
$$
but in general
$$
f(x) \in f(S) \not \Rightarrow x\in S;
$$
for instance in the above informal example, $f(-2)$ lies in the set $f(\{-1,0,1,2\})$ but $-2$ is not in $\{-1,0,1,2\}$. the correct statement is 
$$
y \in f(S) \Leftrightarrow y = f(x) \text{ for some } x \in S
$$
(why?).

!!! note Why $y \in f(S) \Leftrightarrow y = f(x) \text{ for some } x \in S$?
    Let $P(x,y)$ be the statement that $y=f(x)$ and $x \in X$. By Definition 3.3.1, $f(x)\in Y$ is the unique object for which $P(x,f(x))$ is true. By Axiom 3.7, there exists a set $\{y:y=f(x) \text{ is true for some }x \in X\}$ such that for any object $y$, $\{y:y=f(x) \text{ is true for some }x \in X\}$ iff $y=f(x)$ for some $x \in S$. By Definition 3.4.1, $f(S):=\{f(x): x\in S\} = \{y:y=f(x) \text{ is true for some }x \in X\}$. So $y \in f(S) \Leftrightarrow y = f(x) \text{ for some } x \in S$.<span style="float: right">□</span>

***Example 3.4.4*** From Definition 3.3.20 we see that a function $f: X \to Y$ is onto if and only if $f(X) = Y$.

!!! Note Why a function $f: X \to Y$ is onto if and only if $f(X) = Y$?
    First we show that $f$ is onto $\implies$ $f(X)=Y$. We prove by contradiction. Suppose $f(X) \neq Y$. Since $f(X) \subseteq Y$, we have $Y \not \subseteq f(X)$ otherwise $f(X) = Y$ as per Proposition 3.1.17. This means that there exist some $y \in Y$ for which $y \neq f(x)$ for all $x \in X$, which is contradictory to the fact that $f$ is onto. So $f \text{ is onto } \implies f(X) = Y$. Next we show that $f(X)=Y \implies f \text{ is onto}$. Suppose $y$ is an arbitrary element of $Y$. Since $f(X) = Y$, we have $y \in f(X)$ by Axiom 3.2, which is equivalent to $y=f(x)$ for some $x \in X$. So for every element of $Y$ there exists $x \in X$ such that $f(x)=y$ and by hence $f$ is onto by the definition of onto functions.

> **Definition 3.4.5** (Inverse images) If $U$ is a subset of $Y$, we define the set $f^{-1}(U)$ to be the set
$$
f^{-1}(U):= \{x\in X: f(x) \in U\}.
$$
In other words, $f^{-1}(U)$ consists of all the elements of $X$ which map into $U$:
$$
f(x) \in U \Leftrightarrow x \in f^{-1}(U).
$$
We call $f^{-1}(U)$ the *inverse image* of $U$.

***Example 3.4.6*** If $f: \mathbf{N} \to \mathbf{N}$ is the map $f(x)=2x$, then $f(\{1,2,3\})=\{2,4,,6\}$ but $f^{-1}(\{1,2,3\})= \{1\}$. Thus the forward image of $\{1,2,3\}$ and the backwards image of $\{1,2,3\}$ are quite different sets. Also not that
$$
f(f^{-1}(\{1,2,3\})) \neq \{1,2,3\}
$$
(why?).

!!! Note Why $f(f^{-1}(\{1,2,3\})) \neq \{1,2,3\}$?
    Since $f^{-1}(\{1,2,3\}) = \{1\}$, we have $f(f^{-1}(\{1,2,3\}))=f(\{1\})=\{2\}$.<span style="float: right">□</span>

***Example 3.4.7*** (Informal) If $f: \mathbf{Z} \to \mathbf{Z}$ is the map $f(x)=x^2$, then
$$
f^{-1}(\{0,1,4\}) = \{-2,-1,0,1,2\}.
$$
Note that $f$ does not have to be invertible in order for $f^{-1}(U)$ to make sense. Also note that images and inverse images do not quite invert each other, for instance we have
$$
f^{-1}(f(\{-1,0,1,2\})) \neq \{-1,0,1,2\}
$$
(why?).

!!! note Why $f^{-1}(f(\{-1,0,1,2\})) \neq \{-1,0,1,2\}$?
    $f(\{-1,0,1,2\}) = \{0, 1, 4\}$, so $f^{-1}(f(\{-1,0,1,2\}))=f^{-1}(\{0,1,4\})=\{-2,-1,0,1,2\}$<span style="float: right">□</span>

***Remark 3.4.8*** If $f$ is a bijective function, then we have defined $f^{-1}$ in two slightly differently ways, but this is not an issue because the two defintions agree in this case (Exercise 3.4.1).

As remarked earlier, functions are not necessarily sets. However, we do consider functions to be a type of object, and in particular we should be able to consider sets of functions. In particular, we should be able to consider the set of *all* functions from a set $X$ to a set $Y$. To do this we need to introduce another axiom to set theory.

> **Axiom 3.11** (*Power set axiom*). Let $X$ and $Y$ be sets. Then there exists a set, denoted $Y^X$, which consists of all the functions from $X$ to $Y$, thus
$$
f \in Y^X \Leftrightarrow (f \text{ is a function with domain } X \text{ and codomain } Y).
$$

***Example 3.4.9*** Let $X = \{4, 7\}$ and $Y=\{0, 1\}$. Then the set $Y^X$ consists of four functions: the function that maps $4 \mapsto 0$ and $7 \mapsto 0$; the function that maps $4 \mapsto 0$ and $7 \mapsto 1$; the function that maps $4 \mapsto 1$ and $7 \mapsto 0$; and the function that maps $4 \mapsto 1$ and $7 \mapsto 1$. The reason we use the notation $Y^X$ to denote this set is that if $Y$ has $n$ elements and $X$ has $m$ elements, then one can show that $Y^X$ has $n^m$ elements; see Proposition 3.6.14(f).

One consequence of this axiom is

>**Lemma 3.4.10** *Let $X$ be a set. Then the set*
$$
\{Y: Y \text{ is a subset of } X\}
$$
*is a set. That is to say, there exists a set $Z$ such that*
$$
Y\in Z \Leftrightarrow Y \subseteq X
$$
for all objects $Y$.

***Proof*** See Exercise 3.4.6 <span style="float: right">□</span>

***Remark 3.4.11*** The set $\{Y: Y \text{ is a subset of } X\}$ is known as the *power set* of $X$ and is denoted  $2^X$. For instance, if $a, b, c$ are distinct objects, we have
$$
2^{\{a, b, c\}} = \{\emptyset, \{a\}, \{b\}, \{c\}, \{a, b\}, \{a, c\}, \{b, c\}, \{a, b, c\}\}.
$$

Note that while \{a, b, c\} has 3 elements, $2^{\{a, b, c\}}$ has $2^3=8$ elements. This gives a hint as to why we refer to the power set of $X$ as $2^X$; we return to this issue in Chap. 8.

For sake of completeness, let us now add one further axiom to our set theory, in which we enhance the axiom of pairwise union to allow unions of much larger collections of set.

> **Axiom 3.12** (*Union*). Let $A$ be a set, all of whose elements are themselves set. Then there exists a set $\bigcup A$ whose elements are precisely those objects which are elements of the elements of $A$, thus for all objects $x$
$$
x \in \bigcup A \Leftrightarrow (x \in S \text{ for some } S \in A).
$$

***Example 3.4.12*** If $A=\{\{2,3\},\{3,4\},\{4,5\}\}$, then $\bigcup A = \{2,3,4,5\}$ (why?).

!!! Note Why If $A=\{\{2,3\},\{3,4\},\{4,5\}\}$, then $\bigcup A = \{2,3,4,5\}$?
    Suppose $x$ is an arbitrary object. By the axiom of union, $x \in \bigcup A$ iff $x \in \{2, 3\}$ or $x \in \{3,4\}$ or $x \in \{4,5\}$. By axiom of pair sets $x \in \{2, 3\}$ iff $x=2$ or $x=3$; $x \in \{3,4\}$ iff $x=3 \text{ or } x=4$; and $x \in \{4,5\}$ iff $x = 4 \text{ or } x=5$. Thus $x \in \bigcup A \Leftrightarrow (x=2 \text{ or } x=3) \text{ or } (x=3 \text{ or } x=4) \text{ or } (x=4 \text{ or } x=5) \Leftrightarrow x=2 \text{ or } x=3 \text{ or } x=4 \text{ or } x=5$. By the axiom of singleton sets, $x=2 \text{ or } x=3 \text{ or } x=4 \text{ or } x=5 \Leftrightarrow x\in \{2\} \text{ or } x\in \{3\} \text{ or } x \in \{4\} \text{ or } x\in \{5\}$. By consecutive applications of Axiom 3.5, we have $x \in \bigcup A \Leftrightarrow x \in \{2\} \cup \{3\} \cup \{4\} \cup \{5\} \Leftrightarrow x \in\{2,3,4,5\}$. By Axiom 3.2 $\bigcup A = \{2,3,4,5\}$ as desire.<span style="float: right">□</span>

The axiom of union, combined with the axiom of pair set, implies the axiom of pairwise union (Exercise 3.4.8). Another important consequence of this axiom is that if one has some set $I$, and for every element $\alpha \in I$ we have some set $A_{\alpha}$, then we can form the union set $\bigcup_{\alpha \in I}A_{\alpha}$ by defining
$$
\bigcup_{\alpha \in I}A_{\alpha}:=\bigcup\{A_{\alpha}: \alpha \in I\},
$$
which is a set thanks to the axiom of replacement and the axiom of union. Thus for instance, if $I=\{1, 2,3\}$, $A_1:=\{2,3\}$, $A_2=\{3,4\}$, and $A_3:\{4,5\}$, then $\bigcup_{\alpha\in\{1,2,3\}}A_\alpha=\{2,3,4,5\}$. More generally, we see that for any object $y$,
$$
\begin{equation}
y \in \bigcup_{\alpha \in I}A_\alpha \Leftrightarrow (y \in A_\alpha \text{ for some } \alpha \in I). \tag{3.2}
\end{equation}
$$
In situations like this, we often refer to $I$ as an *index set*, and the elements $\alpha$ of this index set as *labels*; the sets $A_\alpha$ then called a *family of sets* and are *indexed* by the labels $\alpha \in I$. Note that if $I$ was empty, then $\bigcup_{\alpha \in I}A_\alpha$ would automatically also be empty (why?)

!!! Note Why $I = \emptyset \implies \bigcup_{\alpha \in I}A_\alpha = \emptyset$ 
    We prove this statement by contradiction. If $\bigcup_{\alpha \in I}A_\alpha \neq \emptyset$, by the lemma of single choice there exist an object $y \in \bigcup_{\alpha \in I}A_\alpha$. By equation 3.2 there exists some $\alpha \in I$ for which $y \in A_\alpha$. However, by the axiom of empty set, we have $\alpha \not \in I$, which leads to a contradiction. So $I = \emptyset \implies \bigcup_{\alpha \in I}A_\alpha = \emptyset$ as desired.<span style="float: right">□</span>

We can similarly form intersections of families of sets, as long as the index set is non-empty. More specifically, given any non-empty set $I$, and given an assignment of a set $A_\alpha$ to each $\alpha \in I$, we can define the intersection $\bigcap_{\alpha \in I}A_\alpha$ by first choosing some element $\beta$ of $I$ (which we can do since $I$ is non-empty), and setting
$$
\bigcap_{\alpha \in I}A_\alpha:=\{x \in A_\beta: x \in A_\alpha \text{ for all } \alpha \in I\} \tag{3.3}
$$

which is a set by the axiom of specification. This definition may look like it depends on the choice of $\beta$, but it does not (Exercise 3.4.9). Observe that for any object $y$,
$$
y \in \bigcup_{\alpha \in I}A_\alpha \Longleftrightarrow (y \in A_\alpha \text{ for all } \alpha \in I) \tag{3.4}
$$
(compare with (3.2))

***Remark 3.4.13*** The axioms of set theory that we have introduced (Axioms 3.1 and 3.12, excluding the dangerous Axiom 3.9) are known as the *Zermelo-Fraenkel axioms of set theory*,[^5] after Ernest Zermelo (1871-1953) and Abraham Fraenkel (1891-1965). There is one further axiom we wil eventually need, the famous axiom of choice (see Sect. 8.4), giving rise to the *Zermelo-Fraenkel-Choice (ZFC) axioms of set theory*, but we will not need this axiom for some time.

## Exercises

*Exercise 3.4.1* Let $f:X \to Y$ be a bijective function, and let $f^{-1}: Y \to X$ be its inverse. Let $V$ be any subset of $Y$. Prove that the forward image of $V$ under $f^{-1}$ is the same set as the inverse image of $V$ under $f$; thus the fact that both sets are denoted by $f^{-1}(V)$ will not lead to any inconsistency.

!!! success
    By Definition 3.4.1, the forward image of $V$ under $f^{-1}$ is defined as $f^{-1}(V):=\{f^{-1}(y): y\in V\}$. By Definition 3.4.5, the inverse image of $V$ under f is defined as $f^{-1}(V)=\{x \in X: f(x) \in V\}$. To show that $\{f^{-1}(y): y\in V\} = \{x \in X: f(x) \in V\}$, we need to show that every element of $\{f^{-1}(y): y\in V\}$ is an element of $\{x \in X: f(x) \in V\}$ and vice versa by Axiom 3.2. Let $x$ be an arbitrary object. By the axiom of replacement, $x \in \{f^{-1}(y): y\in V\}$ iff $x=f^{-1}(y)$ and $y \in V$. By the defintion of inverse function, $x=f^{-1}(y) \Leftrightarrow y = f(x)$. So $x \in \{f^{-1}(y): y\in V\}$ iff $y=f(x)$ and $y \in V$, i.e, iff $f(x) \in V$. However, by Definition 3.4.5, $f(x) \in V$ iff $x \in \{x \in X: f(x) \in V\}$. Thus $x \in \{f^{-1}(y): y\in V\}$ iff $x \in \{x \in X: f(x) \in V\}$ and hence $\{f^{-1}(y): y\in V\} = \{x \in X: f(x) \in V\}$.<span style="float: right">□</span>

!!! Success Model solution
    Since "$f^{-1}(V)$" may refer to two different things here, let's first introduce some notations to avoid any confusion:
    - Let $F$ be the *forward image* of $V$ under $f^{-1}$, i.e., $F:=\{f^{-1}(y):y \in V\}$.
    - Let $I$ be the *inverse image* of $V$ under $f$, i.e., $I:=\{x \in X: f(x) \in V\}$.
    In this exercise we must show that $F = I$, so as to ensure that the two definitions of $f^{-1}$ are equivalent. So, we will prove that $F \subseteq I$ and $I \subseteq F$.
    1. Let be $x \in F$, there exists $y \in V$ such that $x = f^{-1}(y)$. By definition, this is equivalent to $f(x) = y$. But since $y \in V$, we can say that $f(x) \in V$. Thus, we have both $x \in X$ (because $F \subseteq X$) and $f(x) \in V$, which means that $x \in I$.
    2. Conversely, let be $x \in I$. By definition, this means that $x \in X$ and that $f(x) \in V$, i.e., there exists a certain element $y \in V$ such that $y = f(x)$ and $x = f^{-1}(y)$ for a certain $y \in V$ which means that $x \in F$

*Exercise 3.4.2* Let $f: X \to Y$ be a function from one set $X$ to another set $Y$, let $S$ be a subset of $X$ and let $U$ be a subset of Y.
- (i) What, in general, can one say about $f^{-1}(f(S))$ and $S$?
- (ii) What about $f(f^{-1}(U))$ and $U$?
- (iii) What about $f^{-1}(f(f^{-1}(U)))$ and $f^{-1}(U)$?

!!! Fail False solution
    1. In general, $f^{-1}(f(S)) \not \subseteq S$. For instance, Let $f: \mathbf{Z} \to \mathbf{Z}$ be the map $f(x)=x^2$. Let $S = \{-1, 0, 1, 2\}$ and hence $S \subseteq \mathbf{Z}$. Then we have $f(S)=f(\{-1,0,1,2\})=\{0,1,4\}$ and hence $f^{-1}(f(S))=f^{-1}(\{0,1,4\})=\{-2,-1,0,1,2\}$. It is clear that $f^{-1}(f(S)) \not \subseteq S$. Instead we can see that $S \subseteq f^{-1}(f(S))$. Moreover, $S \subseteq f^{-1}(f(S))$ is indeed a true statement. Suppose $x$ is an object. If $x \in S$, then $f(x) \in f(S)$ by the definition of forward image. Then we further have $x \in f^{-1}(f(S))$ as $f(x) \in f(S) \Longleftrightarrow x \in f^{-1}(f(S))$ by the definition of inverse image. In conclusion, we can say $S \subseteq f^{-1}(f(S))$ in general.
    2. If $f(x) \in f(f^{-1}(U))$ then $x \in f^{-1}(U)$ by the definition of forward image. However, $x \in f^{-1}(U) \Longleftrightarrow f(x) \in U$ by the definition of inverse image. So $f(x) \in f(f^{-1}(U))$ implies $f(x) \in U$ and hence $f(f^{-1}(U)) \subseteq U$. On the other hand, suppose $f(x)$ is an arbitrary object. If $f(x) \in U$ then we have $x\in f^{-1}(U)$ by the definition of inverse image, which further means that $f(x) \in f(f^{-1}(U))$ by the definition of forward image, so $U \subseteq f(f^{-1}(U))$. Since $f(f^{-1}(U)) \subseteq U$ and $U \subseteq f(f^{-1}(U))$, we have $U = f(f^{-1}(U))$.
    3. As we proved in 2, $f(f^{-1}(U)) = U$, so $f^{-1}(f(f^{-1}(U)))=f(U)$.
!!! Success Model solution
    This exercise gives a first taste of Exercise 3.4.5 below.
    1. First consider $f^{-1}(f(S))$ and $S$.
        - Do we have $f^{-1}(f(S)) \subseteq S$? Generally, no. As a counterexample, let's consider $f(x)=x^2$ with $X=Y=\mathbf{R}$ and $S= \{0,2\}$. We have $f^{-1}(f(S))=f^{-1}(\{0,4\})=\{-2,0,2\}$. In this set, we have an element, $-2$, which is not an element of $S$.
        - Do we have $S \subseteq f^{-1}(f(S))$? Yes. Let be $x \in S$. Then, by definition, $f(x) \in f(S)$. So, $x \in X$ and is such that $f(x) \in f(S)$: this is precisely the defintion of $x \in f^{-1}(f(S))$.
        - Conclusion: generally speaking, $S$ and $f^{-1}(f(S))$ are not equal, but $S \subseteq f^{-1}(f(S))$.
    2. Now consider $f(f^{-1}(U))$ and $U$.
        - Do we have $U \subseteq f(f^{-1}(U))$? Generally, no. As a counterexample, let's consider $f(x)=\sqrt{x}$ with $X = \mathbf{R}^+, Y= \mathbf{R}$ and $U=[-1, 1]$. We have $f(f^{-1}(U))=[0，1]$，which clearly shows that $U \not \subseteq f(f^{-1}(U))$.
        - Do we have $f(f^{-1}(U)) \subseteq U$? Yes. Let be $y \in f(f^{-1}(U))$. By definition, there exists $x \in f^{-1}(U)$ such that $y=f(x)$. But if $x \in f^{-1}(U)$, we have $f(x) \in U$. And since $y=f(x)$, this means that $y \in U$.
        - Conclusion: generally speaking, $U \neq f(f^{-1}(U))$, but $f(f^{-1}(U)) \subseteq U$.
    3. Finally, consider $f^{-1}(f(f^{-1}(U)))$ and $f^{-1}(U)$.
        - Do we have $f^{-1}(f(f^{-1}(U))) \subseteq f^{-1}(U)$? Yes. Let be $x \in f^{-1}(f(f^{-1}(U)))$. By definition, we have $x \in X$ and $f(x) \in f(f^{-1}(U))$. But if $f(x) \in f(f^{-1}(U))$, then $f(x) \in U$ by what we proved in 2. And since $x \in X$, by definition we have $x \in f^{-1}(U)$.
        - Do we have $f^{-1}(U) \subseteq f^{-1}(f(f^{-1}(U)))$? Yes. By definition, $f^{-1}(U)$ is a subset of $X$. By what we proved in 1, we have $f^{-1}(U) \subseteq f^{-1}(f(f^{-1}(U)))$.
        - Conclusion: $f^{-1}(f(f^{-1}(U)))= f^{-1}(U)$.

*Exercise 3.4.3* Let $A$, $B$ be two subsets of a set $X$, and let $f: X \to Y$ be a function. Show that $f(A \cap B) \subseteq f(A) \cap f(B)$, that $f(A) \setminus f(B) \subseteq f(A \setminus B)$, $f(A \cup B) = f(A) \cup f(B)$. For the first two statements, is it true that the $\subseteq$ relation can be improved to $=$?

!!! Success
    1. $f(A \cap B) \subseteq f(A) \cap f(B)$
       - By definition, $A \cap B \subseteq A$, and since $A \subseteq X$ we have $A \cap B \subseteq X$ by Proposition 3.1.17. Let be $y \in f(A \cap B)$, then there exists $x \in A \cap B$ such that $y=f(x)$. Since $A \cap B \subseteq A$ and $y=f(x)$, we have $y \in f(A)$. Similarly, $A \cap B \subseteq B$ leads to $y \in f(B)$. So we have $y \in f(A)$ and $y \in f(B)$, and hence $y \in f(A) \cap f(B)$ by definition. As $y$ is arbitrary, we have $f(A \cap B) \subseteq f(A) \cap f(B)$ as desired.
    2. $f(A) \setminus f(B) \subseteq f(A \setminus B)$
        - Let be $y \in f(A)\setminus f(B)$. By the definition of difference sets, we have $y \in f(A)$ and $y \not \in f(B)$. This means there exists $x \in A$ such that $y=f(x)$ and we must also have $x \not \in B$. Otherwise, we would have $y \in f(B)$ by definition. So there exists $x \in A$ and $x \not \in B$, namely $x \in A \setminus B$, such that $y=f(x)$ and hence $y \in f(A \setminus B)$. Since $y$ is arbitrary, we have $f(A)\setminus f(B) \subseteq f(A\setminus B)$ as desired.
    3. $f(A \cup B) = f(A) \cup f(B)$
        - We first show that $f(A \cup B) \subseteq f(A) \cup f(B)$. Let be $y \in f(A \cup B)$. By definition, there exists $x \in A \cup B$ such that $y=f(x)$. By the axiom of pairwise union, $x \in A \cup B$ iff $x \in A$ or $x \in B$. So either $y=f(x), x \in A$ or $y=f(x), x\in B$ is true. This means $y \in f(A)$ or $y \in f(B)$ and hence $y \in f(A) \cup f(B)$. Since $y$ is arbitrary, we have $f(A \cup B) \subseteq f(A) \cup f(B)$.
        - Next we show that $f(A) \cup f(B) \subseteq f(A \cup B)$. Let be $y \in f(A) \cup f(B)$. By the axiom of pairwise union, we have $y \in f(A)$ or $y \in f(B)$. This means there exists $x \in A$ or $x \in B$ such that $y=f(x)$, which also means $y \in f(A \cup B)$. Since $y$ is arbitrary, we have $f(A) \cup f(B) \subseteq f(A \cup B)$.
    4. Is it true that the $\subseteq$ relation can be improved to $=$?
        - For the first statement, $f(A \cap B) = f(A) \cap f(B)$ is false. As a counterexample, let be $f: \{0, 1\} \to \{1\}$ be the map $f(0)=f(1)=1$. Let $A=\{0\}$ and $B=\{1\}$.We have $A \subseteq \{0,1\}$ and $B \subseteq \{0,1\}$ and $f(A) \cap f(B)=\{1\} \cap \{1\}=\{1\}$. However, $f(A \cap B)=f(\emptyset)=\emptyset$. It is clear that $\{1\} \neq \emptyset$, so $f(A \cap B) \neq f(A) \cap f(B)$.
        - For the second statement, $f(A) \setminus f(B) = f(A \setminus B)$ is also false. As a counterexample,  let be $f: \{0, 1, 2\} \to \{1, 2\}$ be the map $f(0)=f(1)=1, f(2)=2$.Let $A=\{0,1\}$ and $B=\{1,2\}$. We have $A \subseteq \{0,1,2\}$ and $B \subseteq \{0,1,2\}$. $f(A) \setminus f(B) = f(\{0,1\}) \setminus f(\{1,2\})=\{1\} \setminus \{1, 2\} = \emptyset$ while $f(A\setminus B) = f(\{0\})=\{1\}$. It is clear that $\emptyset \neq \{1\}$, so $f(A) \setminus f(B)\neq f(A \setminus B)$.

!!! Success Model solution
    1. If $y \in f(A \cap B)$, then there exists $x \in A \cap B$ such that $f(x)=y$. Since $x \in A \cap B$, we have both $x \in A$ and $x \in B$, which implies $y=f(x) \in f(A)$ and $y=f(x) \in B$ respectively. Thus, $y\in f(A) \cap f(B)$, and we have proved that $f(A \cap B) \subseteq f(A) \cap f(B)$.
    However, the converse inclusion false in general. For instance, let's consider the two sets $A=\{1,2\}$, $B=\{2,3\}$ and the (non injective) function $f$ defined as the mapping $f(1)=1,f(2)=2,f(3)=1$. We have $f(A)=\{1,2\}, f(B)=\{1,2\}$, thus $f(A) \cap f(B)=\{1,2\}$. This is not a subset of $f(A \cap B)=f(\{2\})=\{2\}$.

    2. If $y \in f(A) \setminus f(B)$, then there exists $x_0 \in A$ such that $y=f(x_0)$, but we have $f(b) \neq y$ for all $b \in B$. Suppose that $x_0 \in B$: in this case, $f(x_0)\neq y$, a contradiction. Thus, $y=f(x_0)$ with $x_0 \in A \setminus B$, which proves that $f(A) \setminus f(B) \subseteq f(A \setminus B)$.
    However, the converse inclusion is false in general. For instance, let's consider the two sets $A=\{1,2,3\}, B=\{3\}$ and the function $f$ defined as the mapping $f(1)=1,f(2)=2,f(3)=1$. We have $f(A\setminus B)=\{1, 2\}$, but $f(A) \setminus f(B) = \{2\}$.
    
    3. if $y \in f(A \cup B)$, then there exists $x \in A \cup B$ such that $y = f(x)$. If $x \in A$, then $f(x) \in f(A)$, which implies $x \in f(A) \cup f(B)$. There is an identical result if $x \in B$. Thus, $f(A \cup B)\subseteq f(A) \cup f(B)$.
    Conversely, if $y \in f(A) \cup f(B)$, then we have either $y \in f(A)$ or $y \in f(B)$ (or both). In the first case, there exists $x \in A$ such that $y=f(x)$. But since $x \in A$, we also have $x \in A \cup B$, so that $y \in f(A \cup B)$. the same result holds if $y \in B$. Thus, in both cases, $y \in f(A \cup B)$.

*Exercise 3.4.4* Let $f: X \to Y$ be a function from one set $X$ to another set $Y$, and let $U$, $V$ be subsets of $Y$. Show that $f^{-1}(U \cup V)=f^{-1}(U)\cup f^{-1}(V)$, that $f^{-1}(U\cap V)=f^{-1}(U) \cap f^{-1}(V)$, and that $f^{-1}(U\setminus V)=f^{-1}(U)\setminus f^{-1}(V)$.

!!! Success
    1. $f^{-1}(U \cup V) = f^{-1}(U) \cup f^{-1}(V)$
        - Let be $x \in f^{-1}(U \cup V)$. By definition, we have $x \in X$ and $f(x) \in U \cup V$, which further means $f(x) \in X$ and ($f(x)\in U$ or f(x) \in V). If $f(x) \in U$, by definition we have $x \in f^{-1}(U) $ and hence $x \in f^{-1}(U) \cup f^{-1}(V)$. Similarly, if $f(x) \in V$, then we have $x \in f^{-1}(V)$ and hence $x \in f^{-1}(U) \cup f^{-1}(V)$. In both cases, we have $x \in f^{-1}(U) \cup f^{-1}(V)$, so $f^{-1}(U \cup V) \subseteq f^{-1}(U) \cup f^{-1}(V)$.
        - Let be $x \in f^{-1}(U) \cup f^{-1}(V)$. By definition, we have $x \in f^{-1}(U) $ or $x \in f^{-1}(V)$. If $x \in f^{-1}(U)$, then by definition we have $x \in X$ and $f(x) \in U$. But $f(x) \in U$ also means $f(x) \in U \cup V$. So by definition, we have $x \in f^{-1}(U \cup V)$. Similarly, if $x \in f^{-1}(V)$, then we have $x \in V$ and $f(x) \in V$, which further means $f(x) \in U \cup V$. And then we have $x \in f^{-1}(U \cup V)$. In both cases, we have $x \in f^{-1}(U \cup V)$, so $f^{-1}(U) \cup f^{-1}(V) \subseteq f^{-1}(U \cup V)$.
        - Finally, since $f^{-1}(U \cup V) \subseteq f^{-1}(U) \cup f^{-1}(V)$ and $f^{-1}(U) \cup f^{-1}(V) \subseteq f^{-1}(U \cup V)$, we have $f^{-1}(U \cup V) = f^{-1}(U) \cup f^{-1}(V)$.
    2. $f^{-1}(U \cap V)=f^{-1}(U) \cap f^{-1}(V)$
        - Let be $x \in f^{-1}(U \cap V)$. By definition, $f(x) \in U \cap V$, so that we have both $f(x) \in U$ and $f(x) \in V$. By definition we have both $x \in f^{-1}(U)$ and $x \in f^{-1}(V)$, implying that $x \in f^{-1}(U) \cap f^{-1}(V)$. thus, we have demonstrated that $f^{-1}(U \cap V) \subseteq f^{-1}(U) \cap f^{-1}(V)$.
        - For the converse inclusion, let be $x \in f^{-1}(U) \cup f^{-1}(V)$, then we have both $x \in f^{-1}(U)$ and $x \in f^{-1}(V)$. By definition, we have both $f(x) \in U$ and $f(x) \in V$, which means $f(x) \in U \cap V$. So we have $x \in f^{-1}(U \cap V)$ by definition. Thus, we have proved that $^{-1}(U \cap V)\subseteq f^{-1}(U) \cap f^{-1}(V)$.
        - This proves the equality $f^{-1}(U \cap V)=f^{-1}(U) \cap f^{-1}(V)$.
    3. $f^{-1}(U \setminus V)=f^{-1}(U) \setminus f^{-1}(V)$.
        - Let be $x \in f^{-1}(U \setminus V)$. By definition, $f(x) \in U \setminus V$, so that we have both $f(x) \in U$ and $f(x) \notin V$ for all $x \in X$. On one hand, $f(x) \in U$ implies $x \in f^{-1}(U)$. On the other hand, $f(x) \notin V$ implies $x \notin f^{-1}(V)$. Since if $x\in f^{-1}(V)$, then there exists $x \in X$ such that $f(x) \in V$ which leads to a contradiction. So we have both $x \in f^{-1}(U)$ and $x \notin f^{-1}(V)$, meaning that $x \in f^{-1}(U) \setminus f^{-1}(V)$. Thus, we have demonstrated that $f^{-1}(U \setminus V)\subseteq f^{-1}(U) \setminus f^{-1}(V)$.
        - For the converse inclusion, let be $x \in f^{-1}(U) \setminus f^{-1}(V)$. Then we have both $x \in f^{-1}(U)$ and $x \notin f^{-1}(V)$. By definition, $x \in f^{-1}(U)$ iff $f(x) \in U$, and $x \notin f^{-1}(V)$ implies $f(x) \notin V$ for all $x \in X$. So $f(x) \in U \setminus V$ and hence $x \in f^{-1}(U \setminus V)$ by definition. Thus, we have proved that $f^{-1}(U) \setminus f^{-1}(V) \subseteq f^{-1}(U \setminus V)$.
        - This proves the equality $f^{-1}(U \setminus V)=f^{-1}(U) \setminus f^{-1}(V)$.

!!! Success Model solution
    We prove only the first statement here, since only very small adjustments are required in its proof to prove the last two ones.
    - Let be $x \in f^{-1}(A \cup B)$. By definition, $f(x)\in A \cup B$, so that we have either $f(x) \in A$ or $f(x) \in B$. If $f(x)\in A$, then $x \in f^{-1}(A)$ by defintion. This implies that $x \in f^{-1}(A) \cup f^{-1}(B)$. The same conclusion holds if $f(x) \in B$. Thus, we have demonstrated that $f^{-1}(A \cup B)\subseteq f^{-1}(A) \cup f^{-1}(B)$.
    - For the converse inclusion, let be $x \in f^{-1}(A) \cup f^{-1}(B)$. We have either $x \in f^{-1}(A)$ or $x \in f^{-1}(B)$. If $x \in f^{-1}(A)$, then $f(x) \in A$, and since $A \subseteq A \cup B$, we have $f(x) \in A \cup B$. This implies $x \in f^{-1}(A \cup B)$. The same conclusion holds if $x \in f^{-1}(B)$. Thus, $f^{-1}(A) \cup f^{-1}(B) \subseteq f^{-1}(A \cup B)$.
    - This proves the equality $f^{-1}(A \cup B)=f^{-1}(A)\cap f^{-1}(B)$.

*Exercise 3.4.5* Let $f: X \to Y$ be a function from one set $X$ to another set $Y$. Show that $f(f^{-1}(S))=S$ for every $S \subseteq Y$ if and only if $f$ is surjective. Show that $f^{-1}(f(S))=S$ for every $S \subseteq X$ if and only if $f$ is injective.

!!! Note
    1. $f(f^{-1}(S))=S$ for every $S \subseteq Y$ iff $f$ is surjective
        - First we show that $f(f^{-1}(S))=S$ for every $S \subseteq Y$ implies $f$ is surjective. Since $Y \subseteq Y$, we have $f(f^{-1}(Y))=Y$. Let be $y \in Y$, so that we have $y \in f(f^{-1}(Y))$. By definition, there exists $x \in f^{-1}(Y)$ such that $y=f(x)$. By definition, $f^{-1}(Y) \subseteq X$, and since the arbitrary of $y$, there exists $x \in X$ such that $y=f(x)$ for every $y \in Y$. So $f$ is surjective.
        - Next we show that the oppsite direction of the statement also holds. Let $y \in f(f^{-1}(S))$, so that there exists $x \in f^{-1}(S)$ such that $y=f(x)$ by definition. By definition, $x \in f^{-1}(S)$ implies $f(x) \in S$ which means $y \in S$. Thus, $f(f^{-1}(S))\subseteq S$. On the other hand, let $y \in S$. Since $S \subseteq Y$, we have $y \in Y$. As $f$ is surjective, there exists $x \in X$ that $f(x)=y$. By definition we have $x \in f^{-1}(S)$ since $f(x) \in S$ and hence $f(x) \in f(f^{-1}(S))$, i.e., $y \in f(f^{-1}(S))$. Thus we have proved $f(f^{-1}(S))=S$. Since $S$ is arbitrary, we have proved that $f(f^{-1}(S))=S$ for every $S \subseteq Y$.
        - Therefore, $f(f^{-1}(S))=S$ for every $S \subseteq Y$ iff $f$ is surjective.
    2. $f^{-1}(f(S))=S$ for every $S \subseteq X$ if and only if $f$ is injective
        - First we show that $f^{-1}(f(S))=S$ for every $S \subseteq X$ implies $f$ is injective. Since $X \subseteq X$, we have $f^{-1}(f(X))=X$. Let be $x_1 \in X, x_2 \in X, x_1 \neq x_2$ and $X_1:=X \setminus \{x_1\}$. It is clear that $X_1 \subsetneq X$. Suppose $f(x_1)=f(x_2)$. Let $x \in X_1$ and then we have $f(x) \in f(X_1)$. Since $X_1 \subseteq X$, we also have $x \in X$ and hence $f(x) \in f(X)$. So we have $f(X_1) \subseteq f(X)$. Let $x \in X$. By definition, we have $f(x) \in f(X)$. Since $X = X_1 \cup \{x_1\}$, we can divide into two cases. If $x \in X_1$, then we have $f(x) \in f(X_1)$. If $x\in \{x_1\}$, then $x = x_1$. Since $f(x_1) = f(x_2)$ and $f(x_2) \in f(X_1)$, we have $f(x_1)\in f(X_1)$ and hence $f(x) \in f(X_1)$. In both cases we have $f(x) \in f(X_1)$, so $f(X) \subseteq f(X_1)$. Thus, we have $f(X) = f(X_1)$ and hence $f^{-1}(f(X))=f^{-1}(f(X_1))$. Thus, we have $X = X_1$ which is a contradiction. So $x_1 \neq x_2$ implies $f(x_1) \neq f(x_2)$. Thus, $f$ is injective. 
        - Next we show the oppsite direction of the statement also holds. Let be $x \in f^{-1}(f(S))$. By definition, we have $f(x) \in f(S)$, which further means that there exists $x_0 \in S$ such that $f(x) = f(x_0)$. Since $f$ is injective, we have $x=x_0$, so $x \in S$. Thus, we have demonstrated that $f^{-1}(f(S)) \subseteq S$. Let be $x \in S$. By definition, we have $f(x) \in f(S)$, which further means $x \in f^{-1}(f(S))$. Thus, we have proved that $S \subseteq f^{-1}(f(S))$. Since $S$ is an arbitrary subset of $X$, we have proved that $f$ is injective implies $f^{-1}(f(S))=S$ for every $S \subseteq X$.
        - Therefore, $f^{-1}(f(S))=S$ for every $S \subseteq X$ if and only if $f$ is injective.

!!! Success Improvements on the proving $f^{-1}(f(S))=S$ for every $S \subseteq X$ implies $f$ is injective
    Let be $x_0 \in X$. By the axiom of singleton, there exists a set $\{x_0\}$ such that $x \in \{x_0\}$ iff $x=x_0$. So $\{x_0\} \subseteq X$ and hence $f^{-1}(f(\{x_0\}))=\{x_0\}$. Since $x_0 \in \{x_0\}$, we have $f(x_0) \in f(\{x_0\})$. Let be $x_1 \in X$. If $f(x_1)=f(x_0)$, then $f(x_1) \in f(\{x_0\})$, thus $x_1 \in f^{-1}(f(\{x_0\}))$ by definition, and hence $x_1 \in \{x_0\}$, so we have $x_1 = x_0$. Since $x_0$ and $x_1$ are arbitrary, $f$ is injective.
    
*Exercise 3.4.6*
(i) Prove Lemma 3.4.10. (*Hint:* start with the set $\{0, 1\}^X $ and apply the replacement axiom, replacing each function $f$ with the object $f^{-1}(\{1\})$.) See also Exercise 3.5.11.

!!! Note
    By the power set axiom, $f \in \{1, 2\}^X$ iff $f: X \to \{1, 2\}$. Since $\{1\} \subseteq \{1, 2\}$, $f^{-1}(\{1\})$ is inverse image of $\{1\}$ which is unique by the definition of inverse images. So for each $f \in \{1,2\}^X$ there is at most one $Y$ such that $Y=f^{-1}(\{1\})$. By the replacement axiom, we can construct a set $Z:=\{f^{-1}(\{1\}):f \in \{1, 2\}^X \}$ such that for any object $Y$, $Y\in Z \Longleftrightarrow Y=f^{-1}(\{1\})$ for some $f \in \{1, 2\}^X$.

    First we show that $Y \in Z \implies Y \subseteq X$. Since $Y \in Z \Longleftrightarrow Y=f^{-1}(\{1\})$ and $f^{-1}(\{1\}) \subseteq X$ by definition, we have $Y \subseteq X$. Next we show that $Y \subseteq X \implies Y \in Z$. Let $f_A: X \to \{1,2\}$ defined by $f_A(x)=1$ for $x \in Y$ and $f_A(x)=0$ otherwise. Obviously, we have $f_A \in \{0,1\}^X$ and $Y = f_A^{-1}(\{1\})$. So we have $Y \in Z$. Thus $Y \in Z \Longleftrightarrow Y \subseteq X$ for all objects $Y$.

!!! Success Model solution
    First, let's recall the main propositions involved in this exercise:
    - **Replacement axiom**. Let $A$ be a set. For any object $x \in A$, and any object $y$, suppose we have a statement $P(x,y)$ pertaining to $x$ and $y$, such that for each $x \in A$ there is at most one $y$ for which $P(x,y)$ is true. Then there exists a set $\{y: P(x, y) \text{ is true for some } x \in A\}$, such that for any object $z$,$$z \in \{y: P(x, y) \text{ is true for some } x \in A\} \Longleftrightarrow P(x, z) \text{ is true for some } x \in A$$
    - **Power set axiom** Let $X$ and $Y$ be sets. Then there exists a set, denoted $Y^X$, which consists of all the functions from $X$ to $Y$, thus $$f \in Y^x \Longleftrightarrow (f \text{ is a function with domain} X \text{ and codomain } Y).$$
    - **Lemma 3.4.10** Let $X$ be a set. Then the set $$\{Y: Y \text{ is a subset of } X\}$$ is a set. That is to say, there exists a set $Z$ such that $$Y \in Z \Longleftrightarrow Y \subseteq X$$.

    The aim is to prove this lemma using the two axioms recalled here.

    1. Let $X$ be a set, and $Y=\{0,1\}$. As per the power axiom, $\{0,1\}^X$ is set, and it contains all functions $f:X \to \{0,1\}$.
    2. Let $A$ be a subset of $X$. One can define the function $f_A:X \to \{0,1\}$, such that for all $x \in X$, $f(x)=1$ if $x \in A$, and $f(x)=0$ otherwise. We can even say more:
        - If $A$ is a subset of $X$, then there exists an element $f \in \{0,1\}^X$ such that $A=f^{-1}(\{1\})$: this is precisely $f_A$ as defined above.
        - Conversely, if $f \in \{0,1\}^X$, then $A=f^{-1}(\{1\})$ is by definition a subset of $X$.
    
        Thus, the two statements "$A$ is a subset of $X$" and "there exists $f \in \{0,1\}^X$ such that $A=f^{-1}(\{1\})$" are equivalent.
    3. Finally, let be $A \subseteq X$ and $f \in \{0,1\}^X$. Let's define $P(f, A)$ the statement "$A=f^{-1}(\{1\})$". For each $f$, there is at most one $A$ (in fact, *exactly* one $A$) such that $P(f, A)$ is true. Thus, as per the axiom of replacement, there exists a set: $$P=\{A:A=f^{-1}(\{1\}) \text{ for some } f \in \{0,1\}^X\}$$
    And, thanks to the equivalence demonstrated in 2:
    $$P = \{A: A \text{ is a subset of } X\}$$ is a well-defined set, which we wanted to prove.
    
(ii) Conversely, show that Axiom 3.11 can be deduced the preceding axioms of set theory if one accepts Lemma 3.4.10 as an axiom. (This may help explain why we refer to Axiom 3.11 as the "power set axiom")

*Exercise 3.4.7* Let $X$, $Y$ be sets. Define a *partial function* from $X$ to $Y$ to be any function $f: X' \to Y'$ whose domain $X'$ is subset of $X$, and whose codomain $Y'$ is a subset of $Y$. Show that the collection of all partial functions from $X$ to $Y$ is itself a set. (*Hint*: use Exercise 3.4.6, the power set axiom, the replacement axiom, and the union axiom.)

!!! Note 
    By Lemma 3.4.10, there exists two set $A:=\{X':X'\subseteq X\}$ and $B:=\{Y':Y' \subseteq Y\}$. Let be $Y' \in B$. Let $P(X',C)$ be the statement that "for every $X' \in X$ there is a set $C$, which contains all functions from $X'$ to $Y'$". By the power set axiom, there is exactly one $C$ (i.e., $Y'^{X'}$) for which $P(X',C)$ is true. And by the replacement axiom and the specification axiom, there exists a set $D:=\{Y'^{X'}| Y' \in B, X' \in A\}$. By the union axiom, there exists a set $\bigcup D$ such that for every object $f$, $f\in \bigcup D$ iff $f \in S$ for some $S \in D$, which is precisely the collection of all partial functions from $X$ to $Y$.

!!! Success Model solution
    - Let be $X' \subseteq X$ and $Y' \subseteq Y$. If both $X'$ and $Y'$ are fixed, then as per the power set axiom, there exists a set $Y'^{X'}$ which consists all the functions from $X'$ to $Y'$ and hence is unique.
    - By Lemma 3.4.10, there exists a set $2^X$ which consists of all the subsets of $X$, and a set $2^Y$ which consists of all the subsets $Y$.
    - Now we fix an element $X'$ of $2^X$. Let be $Y'$ an element of $2^Y$, $A$ a set, and $P$ the property "$P(Y', A): A=Y'^{X'}$". For each $Y' \in 2^Y$, there exists exactly one $A$, namely $A=Y'^{X'}$, for which $P(Y',A)$ is true. By the replacement axiom, there exists a set $B:=\{Y'^{X'}:Y' \in 2^Y\}$.
    - Each element of this set is itself a set. Thus by the union axiom, there exists a set $\bigcup \{Y'^{X'}:Y' \in 2^Y\}$ whose element are those objects which are elements of the elements of $\{Y'^{X'}:Y' \in 2^Y\}$, i.e.:
    $$
    \bigcup \{Y'^{X'}:Y' \in 2^Y\} = \{f|f:X' \to Y' \text{ for some } Y' \in Y\}
    $$  
    This set is obtained for one given fixed subset $X' \subseteq X$, so let's denote this set:
    $$
    S_{X'}=\{f|f:X' \to Y' \text{ for some } Y' \in Y\}
    $$
    - Now we apply once again the union axiom, especially in its second formulation. If we denote $I=2^X$, then for each element $X' \in I$ we do have one set $S_{X'}$, which is denoted above. Thus there exists a set $\bigcup_{X' \in 2^X}S_{X'}:=\bigcup\{S_{X'}|X'\in 2^X\}$. And, for every function $f$, we have $f \in \bigcup \{S_{X'}|X'\in 2^X\}$ iff there exists $X' \in 2^X$ such that $f \in S_{X'}$, i.e., iff there exists $X' \subseteq X$ and $Y' \subseteq Y$ such that $f:X' \to Y'$, which is equivalent to $f$ is a partial function from $X$ to $Y$ by definition.
    - Consequently, we have proved that there exists a set which consists of the collection of all partial functions from $X \to Y$.

*Exercise 3.4.8* Show that Axiom 3.5 can be deduced from Axiom 3.1, Axiom 3.4, and Axiom 3.12.

!!! Success
    - Let $A, B$ be two distinct sets. By Axiom 3.1, $A$ and $B$ are object and hence, by Axiom 3.4, there exists a set $\{A, B\}$ whose only elements are $A$ and $B$. As $\{A, B\}$ is a set, all of whose elements are themselves set, there exists a set $\bigcup \{A, B\}$ whose elements are those objects which are element of the elements of $\{A, B\}$, i.e.:
    $$
    \bigcup \{A, B\} = \{x: x \in S \text{ for some } S \in \{A, B\}\} = \{x: x\in A \text{ or } x \in B\}.
    $$
    - Consequently, we have proved that there exists a set whose elements are either the elements of $A$ or the elements of $B$. This is precisely Axiom 3.5.

*Exercise 3.4.9* Show that if $\beta$ and $\beta'$ are two elements of a set $I$, and to each $\alpha \in I$ we assign a set $A_\alpha$, then
$$
\{x\in A_\beta: x \in A_\alpha \text{ for all } \alpha \in I\}=\{x\in A_{\beta'}: x \in A_\alpha \text{ for all } \alpha \in I\}
$$
and so the definition of $\bigcap_{\alpha \in I}A_\alpha$ defined in $(3.3)$ does not depend on $\beta$. Also explain why $(3.4)$ is true.

[^4]: In principle this notation could collide with the existing notation f(x) for the evaluation of $f$ at $x$, if $S$ turns out to both be a subset of $X$ and an element of $X$. However, we will ignore this potential collision as it rarely occurs in practice.