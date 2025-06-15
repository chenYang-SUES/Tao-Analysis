## 3.4 Images and Inverse Images

We know that a function $f: X \to Y$ from a set $X$ to a set $Y$ can take individual elements $x \in X$ to elements $f(x) \in Y$. Functions can also take subsets in $X$ to subsets in $Y$:

> Definition 3.4.1 (*Images of sets*) if $f: X \to Y$ is a function from $X \to Y$, and $S$ is a subset of $X$, we define[^4] $f(S)$ to be the set
> $$
f(S):=\{f(x): x\in S\};
$$
this set is a subset of $Y$ and is sometimes called the *image* of $S$ under the map $f$. We sometimes call $f(S)$ the *forward image* of $S$ to distinguish it from the concept of *inverse image* $f^{-1}(S)$ of $S$, which is defined below.

Note that the set $f(S)$ is well-defined thanks to the axiom of replacement (Axiom 3.7). One can also define $f(S)$ using the axiom of specification (Axiom 3.6) instead of replacement, but we have leave this as an exercise to reader. The image $f(X)$ of the domain is also known as the *range* of the function $f: X \to Y$; it is a subset of the codmain $Y$.

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
    Let $P(x,y)$ be the statement that $y=f(x)$ and $x \in X$. By Definition 3.3.1, $f(x)\in Y$ is the unique object for which $P(x,f(x))$ is true. By Axiom 3.7, there exists a set $\{y:y=f(x) \text{ is true for some }x \in X\}$ such that for any object $y$, $\{y:y=f(x) \text{ is true for some }x \in X\}$ iff $y=f(x)$ for some $x \in S$. By Definition 3.4.1, $f(s):=\{f(x): x\in S\} = \{y:y=f(x) \text{ is true for some }x \in X\}$. So $y \in f(S) \Leftrightarrow y = f(x) \text{ for some } x \in S$.<span style="float: right">□</span>

***Example 3.4.4*** From Definition 3.3.20 we see that a function $f: X \to Y$ is onto if and only if $f(X) = Y$.

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

As remarked earlier, functions are not necessarily sets. However, we do consider functions to be a type of object, and in particular we should be able to consider sets as functions. In particular, we should be able to consider the set of *all* functions from a set $X$ to a set $Y$. To do this we need to introduce another axiom to set theory.

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

Note that while \{a, b, c\} has 3 elements, $2^{a, b, c}$ has $2^3=8$ elements. This gives a hint as to why we refer to the power set of $X$ as $2^X$; we return to this issue in Chap. 8.

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
y \in \bigcup_{\alpha \in I}A_\alpha \Leftrightarrow (y \in A_\alpha \text{ for some } \alpha \in I). \tag{3.2}
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
    Since "f^{-1}(V)" may refer to two different things here, let's first introduce some notations to avoid any confusion:
    - Let $F$ be the *forward image* of $V$ under $f^{-1}$, i.e., $F:=\{f^{-1}(y):y \in V\}$.
    - Let $I$ be the *inverse image* of $V$ under $f$, i.e., $I:=\{x \in X: f(x) \in V\}$.
    In this exercise we must show that $F = I$, so as to ensure that the two definitions of $f^{-1}$ are equivalent. So, we will prove that $F \subseteq I$ and $I \subseteq F$.
    1. Let be $x \in F$, there exists $y \in V$ such that $x = f^{-1}(y)$. By definition, this is equivalent to $f(x) = y$. But since $y \in V$, we can say that $f(x) \in V$. Thus, we have both $x \in X$ (because $F \subseteq X$) and $f(x) \in V$, which means that $x \in I$.
    2. Conversely, let be $x \in I$. By definition, this means that $x \in X$ and that $f(x) \in V$, i.e., there exists a certain element $y \in V$ such that $y = f(x)$ and $x = f^{-1}(y)$ for a certain $y \in V$ which means that $x \in F$

[^4]: In principle this notation could collide with the existing notation f(x) for the evaluation of $f$ at $x$, if $S$ turns out to both be a subset of $X$ and an element of $X$. However, we will ignore this potential collision as it rarely occurs in practice.