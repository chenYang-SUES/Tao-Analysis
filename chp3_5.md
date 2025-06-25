## 3.5 Cartesian Products

In addition to the basic operations of union, intersection, and differencing, another fundamental operation on sets is that of the *Cartesian product*. To define this notion, we first need the concept of an *ordered pair*.

> **Definition 3.5.1** *(Ordered pair)*. If $x$ and $y$ are any objects (possible equal), we define the *ordered pair* $(x,y)$ to be new object, consisting of $x$ as its first component and $y$ as its second component. Two ordered pairs $(x,y)$ and $(x',y')$ are considered equal if and only if both their components match, i.e.,
> $$
(x,y) = (x',y') \Longleftrightarrow (x=x' \text{ and } y=y'). \tag{3.5}
$$
This notion of equality is consistent with the usual axioms of equality (Exercise 3.5.3). Thus for instance, the pair $(3,5)$ is equal to the pair $(2+1,4+1)$, but is distinct from the pair $(5,3)$, $(3,3)$, and $(2,5)$. (This is contrast to sets, where $\{3, 5\}$ and $\{5, 3\}$ are equal).

***Remark 3.5.2*** Strictly speaking, this definition is partly an axiom, because we have simply postulated that given any two objects $x$ and $y$, that an object of the form $(x,y)$ exists. However, it is possible to define an ordered pair using the axioms of set theory in such a way that we do not need further postulates (see Exercise 3.5.1).

!!! note What's the difference between an axiom and a definition?

***Remark 3.5.3*** We have now "overloaded" the parenthesis symbols $()$ once again; they now are not only used to denote grouping of operators and arguments of functions, but also to enclose ordered pairs. This is usually not a problem in practice as one can still determine what usage the symbols $()$ were intended for from context.

> **Definition 3.5.4** (*Cartesian product*). If $X$ and $Y$ are sets, then we define the *Cartesian product* $X \times Y$ to be collection of ordered pairs, whose first component lies in $X$ and second component lies in $Y$, thus
> $$
> X \times Y = \{(x,y): x\in X, y \in Y\}
> $$
> or equivalently
$$
a\in (X \times Y) \Longleftrightarrow (a=(x,y) \text{ for some } x \in X \text{ and } y \in Y)
$$.

One can show that the Cartesian product $X \times Y$ is in fact a set; see Exercise 3.5.1.

***Example 3.5.5*** If $X:=\{1,2\}$ and $Y:=\{3,4,5\}$,then
$$
X \times Y = \{(1,3),(1,4),(1,5),(2,3),(2,4),(2,5)\}
$$
and 
$$
Y \times X = \{(3,1),(4,1),(5,1),(3,2),(4,2),(5,2)\}.
$$
Thus, strictly speaking, $X \times Y$ and $Y \times X$ are different sets, although they are very similar. For instance, they always have the same number of elements (Exercise 3.6.5).

Let $f:X \times Y \to Z$ be a function whose domain $X \times Y$ is a Cartesian product of two other sets $X$ and $Y$. Then $f$ can either be thought of as a function of one variable, mapping the single input of an ordered pair $(x,y)$ in $X \times Y$ to an output[^6] $f(x,y)$ in $Z$, or as a functions of two variables, mapping an input $x \in X$ and another input $y \in Y$ to a single output $f(x,y) \in Z$. While the two notions are technically different, we wil not bother to distinguish the two, and think of $f$ simultaneously as a function of one varible with domaim $X \times Y$ and as a function of two variables with domains $X$ and $Y$. Thus for instance the addition operation $+$ on the natural numbers can now be re-interpreted as a function $+$: $\mathbf{N} \times \mathbf{N} \to \mathbf{N}$, defined by $(x,y) \mapsto x+y$.

Once one has the notion of an ordered pair, one can also define an ordered triple $(x,y,z)$ of three objects $(x,y,z)$ be the formula $(x,y,z):=((x,y),z)$. One could continue in this fashion and define ordered quadruples, etc., but we shall instead use a different construction to build ordered $n$-tuples.

> **Definition 3.5.6** (*Ordered n-tuple and n-fold Cartesian product*). Let $n$ be a natural number. An *ordered n-tuple* $(x_i)_{1\le i\le n}$ (also denoted $(x_1,...,x_n)$) is a collection of objects $x_i$, one for every natural number $i$ between $1$ and $n$; we refer to $x_i$ as the $i^{th}$ component of the ordered $n$-tuple. Two ordered $n$-tuples $(x_i)_{1\le i \le n}$ and $(y_i)_{1\le i \le n}$ are said to be equal iff $x_i = y_i$ for all $1 \le i \le n$. If $(X_i)_{1\le i \le n}$ is an ordered $n$-tuple of sets, we define their Cartesian product $\prod_{1\le i \le n}X_i$ (also denoted $\prod_{i=1}^nX_i$ or $X_1 \times...\times X_n$) by 
> $$
\prod_{1\le i \le n} X_i :=\{(x_i)_{1\le i \le n}: x_i \in X_i \text{ for all } 1 \le i \le n\}.
$$

Again, this definition simply postulates that an ordered $n$-tuple and a Cartesian product always exist when needed, but using the axioms of set theory one can explicitly construct these objects; see Exercise 3.5.2.

***Remark 3.5.7*** One can generalize this construction to infinite Cartesian products; see Definition 8.4.1.

***Example 3.5.8*** Let $a_1, b_1, a_2, b_2, a_3, b_3$ be objects, and let $X_1:=\{a_1,b_1\}$ $X_2:=\{a_2, b_2\}$, and $X_3:=\{a_3, b_3\}$. Then we have
$$
X_1 \times X_2 \times X_3 = \{(a_1,a_2,a_3), (a_1,a_2,b_3), (a_1,b_2,a_3),(a_1,b_2,b_3),\\(b_1,a_2,a_3),(b_1,a_2,b_3),(b_1,b_2,a_3),(b_1,b_2,b_3)\} \\
(X_1 \times X_2) \times X_3 = \{((a_1,a_2),a_3), ((a_1,a_2),b_3), ((a_1,b_2),a_3),((a_1,b_2),b_3),\\((b_1,a_2),a_3),((b_1,a_2),b_3),((b_1,b_2),a_3),((b_1,b_2),b_3)\}\\
X_1 \times (X_2 \times X_3) = \{(a_1,(a_2,a_3)), (a_1,(a_2,b_3)), (a_1,(b_2,a_3)),(a_1,(b_2,b_3)),\\(b_1,(a_2,a_3)),(b_1,(a_2,b_3)),(b_1,(b_2,a_3)),(b_1,(b_2,b_3))\}.
$$
Thus, strictly speaking, the sets $X_1 \times X_2 \times X_3$, $X_1 \times X_2 \times X_3$, and $X_1 \times (X_2 \times X_3)$ are distinct. However, they are clearly very related to each other (for instance, there are obvious bijections between any two of the three sets), and it is common in practice to neglect the minor distinctions between these sets and pretend that they are in fact equal. Thus a function $f: X_1 \times X_2 \times X_3 \to Y$ can be thought of as a function of one variable $(x_1, x_2, x_3) \in X_1 \times X_2 \times X_3$, or as a function of three variables $x_1 \in X_1$, $x_2 \in X_2$, $x_3 \in X_3$, or a function of two variables $x_1 \in X_1$, $(x_2,x_3) \in X_2 \times X_3$, and so forth; we will not bother to distinguish between these different perspectives.

***Remark 3.5.9*** An ordered $n$-tuple $(x_1,...x_n)$ of objects is also called an *ordered sequence* of $n$ elements, or a *finite sequence* for short. In Chap. 5 we shall also introduce the very useful concept of an *infinite sequence*.

***Example 3.5.10*** If $x$ is an object, then $(x)$ is a 1-tuple, which we shall identify with $x$ itself (even though the two are, strictly speaking, not the same object). Then if $X_1$ is any set, then the Cartesian product $\prod_{1 \le i \le 1}X_i$ is just $X_1$ (why?). Also, the *empty Cartesian product* $\prod_{1 \le i \le 0}X_i$ gives, not the empty set $\{\}$, but rather the singleton set $\{()\}$ whose only element is the $0$-*tuple* $()$, also known as the *empty tuple*.

!!! Note Why $\prod_{1 \le i \le 1}X_i$ is just $X_1$？
    Since $i$ is natural number and $1\le i \le 1$, by the antisymmetry of order, we have $i=1$. By definition, we have
    $$
        \begin{align*}
             \prod_{1\le i \le 1}X_i 
             &= \{(x_i)_{1 \le i \le 1}:x_i \in X_i \text{ for all } 1 \le i \le 1\} \\ 
             &= \{(x_1):x_1\in X_1\} \\
             &= \{x_1:x_1 \in X_1\} \\
             &= X_1
        \end{align*} 
    $$
!!! Note Why $\prod_{1 \le i \le 0}X_i = \{()\}$?

We can now generalize the single choice lemma (Lemma 3.1.5) to allow for multiple (but finite) number of choices.

> **Lemma 3.5.11** (Finite choice). *Let $n \ge 1$ be a natural number, and for each natural number $1\le i \le n$, let $X_i$ be a non-empty set. Then there exists an $n$-tuple $(x_i)_{1\le i \le n}$ such that $x_i \in X_i$ for all $1 \le i \le n$. In other words, if each $X_i$ is non-empty, then the set $\prod_{1 \le i \le n}X_i$ is also non-empty*.

***Proof*** we induct on $n$ (starting with the base case $n=1$; the claim is also vacuously true with $n=0$ but is not particularly interesting in that case). When $n=1$ the claim follows from Lemma 3.1.5 (why?). Now suppose inductively that the claim has already been proven for some $n$; we will now prove it for $n++$. Let $X_1,...X_{n++}$ be a collection of non-empty sets. By induction hypothesis, we can find an $n$-tuple $(x_i)_{1\le i \le n}$ such that $x_i \in X_i$ for all $1 \le i \le n$. Also, since $X_{n++}$ is non-empty, by Lemma 3.1.5 we may find an object $a$ such that $a \in X_{n++}$. If we thus define the $n++$-tuple $(y_i)_{1\le i \le n++}$ by setting $y_i:=x_i$ when $1 \le i \le n$ and $y_i:=a$ when $i=n++$ it is clear that $y_i \in X_i$ for all $1 \le i \le n++$, thus closing the induction.<span style="float: right">□</span>

!!! note Why when $n=1$ the claim follows from Lemma 3.1.5?
    Since $i$ is a natural number for which $1 \le i \le 1$, by the antisymmetry of order we have $i=1$. As $X_1$ is non-empty, by the single choice lemma (Lemma 3.1.5), there exists an object $a$ such that $a \in X_1$. If we define the $1$-tuple $(y_1)$ by setting $y_1:=a$, it is clear $y_i \in X_i$ for all $1 \le i \le 1$.
    
***Remark 3.5.12*** It is intuitively plausible that this lemma should be extended to allow or an infinite number of choices, but this cannot be done automatically; it requires an additional axiom, the *axiom of choice*. See Section 8.4



[^6]: Here (and in the rest of this text) we adopt the very common practice of abbreviating $f((x,y))$ as $f(x,y)$