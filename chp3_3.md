## 3.3 Functions

In order to do analysis, it is not particularly useful to just have the notion of a set; we also need the notion of a _function_ from one set to another. Informally, a function $f: X \rightarrow Y$ from one set $X$ to another set $Y$ is an operation which assigns to each element (or "input") $x$ in $X$, a single element (or "output") $f(x)$ in $Y$; we have already used this informal concept in the previous chapter when we discussed the natural numbers. The formal definition is as follows.

> **Definition 3.3.1** (*Functions*) Let $X$, $Y$ be sets, and let $P(x, y)$ be a property pertaining to an object $x \in X$ and an object $y \in Y$, such that for every $x \in X$, there is exactly one $y \in Y$ for which $P(x, y)$ is true (this is sometimes known as the *vertical line test*). Then we define the *function* $f: X \rightarrow Y$ *defined by $P$ on the domain $X$ and codomain[^2]* to be the object which, given any input $x \in X$, assigns an output $f(x) \in Y$, defined to be the unique object $f(x) \in Y$ for which $P(x,f(x))$ is true. Thus, for any $x \in X$ and $y \in Y$,
> $$
y = f(x) \Leftrightarrow P(x,y) \text{ is true}.
$$

Functions are also referred to as *maps* or *transformations*, depending on the context. They are also sometimes called *morphisms*, although to be more precise, a morphism refers to a more general class of object, which may or may not correspond to actual functions, depending on the context.

**_Remark 3.3.2_** Implicit in the above definition is an assumption that whenever one is given two sets $X$, $Y$ and a property $P$ obeying the vertical line test, one can form a function object $f$. Strictly speaking, the assumption of the existence of such a function object $f$ should be stated as an explicit axiom. However, we will not do so here, as it turns out to be redundant. (More precisely, in view of Exercise 3.5.10, it is always possible to encode a function $f$ as an ordered triple $(X, Y, \{(x, f(x)): x\in X\})$ consisting of the domain, codomain and graph of the function, which gives a way to build functions as objects using the operations provided by the preceding axioms of set theory.) Also implicit in the above definition is the understanding that every function $f$ is automatically associated with a domain $X$, a codomain $Y$, and a defining property $P$.

**_Example 3.3.3_** Let $X = \mathbf{N}$, $Y = \mathbf{N}$, and let $P(x,y)$ be the property that $y = x++$. Then for each $x \in \mathbf{N}$ there is exactly one $y \in \mathbf{N}$ for which $P(x, y)$ is true, namely $y = x++$. Thus we can define a function $f: \mathbf{N} \to \mathbf{N}$ associated to this property, so that $f(x) = x++$ for all $x$; this is the *increment* function on $\mathbf{N}$, which takes a natural number as input and returns its increment as output. Thus for instance $f(4)=5$, $f(2n+3) = 2n + 4$ and so forth. One might also hope to define a *decrement* function $g: \mathbf{N} \to \mathbf{N}$ associated to the property $P(x, y)$ defined by $y++ = x$, i.e., $g(x)$ would be the number whose increment is $x$. Unfortunately this does not define a function, because when $x=0$ there is no natural number $y$ whose increment is equal to $x$ (Axiom 2.3). On the other hand, we can legitimately define a decrement function $h: \mathbf{N}\setminus\{0\} \to \mathbf{N}$ associated to the property $P(x, y)$ defined by $y++=x$, because when $x \in \mathbf{N} \setminus \{0\}$ there is indeed exactly one natural number $y$ such that $y++=x$, thanks to Lemma 2.2.10. Thus for instance $h(4)=4$ and $h(2n+3) = 2n+2$, but $h(0)$ is undefined since $0$ is not in the domain $\mathbf{N} \setminus \{0\}$.

**_Example 3.3.4_** (Informal) This example requires the real numbers $\mathbf{R}$, which we will define in Chap. 5. One could try to define a square root function $\sqrt{}: \mathbf{R} \to \mathbf{R}$ by associating it to the property $P(x, y)$ defined by $y^2=x$, i.e.,A we would want $\sqrt{x}$ to be the number $y$ such that $y^2 = x$. Unfortunately there are two problems which prohibit this definition from actually creating a function. The first is that there exist real numbers $x$ for which $P(x, y)$ is never true, for instance if $x = -1$ then there is no real number $y$ such that $y^2=x$. This problem however can be solved by restricting the domain from $\mathbf{R}$ to the right half-line $[0,+\infty)$. The second problem is that even when $x \in [0,+\infty)$, it is possible for there to be more than one $y$ in the codomain $\mathbf{R}$ for which $y^2=x$, for instance if $x=4$ then both $y=2$ and $y=-2$ obey the property $P(x, y)$, i.e., both $+2$ and $-2$ are square roots of $4$. This problem can however be solved by restricting the codomain of $\mathbf{R}$ to $[0,+\infty)$. Once one does this, then one can correctly define a square root function $\sqrt{}: [0,+\infty) \to [0,+\infty)$ using the relation $y^2=x$; thus $\sqrt{x}$ is the unique number $y \in [0,+\infty)$ such that $y^2=x$.

One common way to define a function is simply to specify its domain, its codomain, and how one generates the output $f(x)$ from each input; this is known as an *explicit* definition of a function. For instance, the function $f$ in Example 3.3.3 could be defined explicitly by saying that $f$ has domain and codomain equal to $\mathbf{N}$, and $f(x):=x++$ for all $x \in \mathbf{N}$. In other cases we only define a function $f$ by specifying what property $P(x,y)$ links the input $x$ with the output $f(x)$; this is an *implicit* definition of a function. For instance, the square root function $\sqrt{x}$ in Example 3.3.4 was defined implicitly by the relation $(\sqrt{x}^2 = x)$. Note that an implicit defnition is only valid if we know that for every input there is exactly one output which obeys the implicit relation. In many cases we omit specifying the domain and codomain of a function for brevity, and thus for instance we could refer to the function $f$ in Example 3.3.3 as "the function $f(x):=x++$,", "the function $x \mapsto x++$", "the function $x++$", or even the extremely abbreviated $++$. However, too much of this abbreviation can be dangerous; sometimes it is important to know what the domain and codomain if the function is.

We observe that functions obey the axiom of substitution: if $x = x'$, then $f(x) = f(x')$ (why?). In other words, equal inputs imply equal outputs. On the other hand, unequal inputs do not necessarily ensure unequal outputs, as the following example show:

!!! note Why $f(x) = f(x')$ if $x = x'$?


**_Example 3.3.5_** Let $X = \mathbf{N}$, $Y = \mathbf{N}$, and let $P(x, y)$ be the property that $y = 7$. Then certainly for every $x \in \mathbf{N}$ there is exactly one $y$ for which $P(x,y )$ is true, namely the number $7$. Thus we can create a function $f: \mathbf{N} \to \mathbf{N}$ associated to this property; it is simply the *constant function* which assigns the output of $f(x)=7$ to each input $x \in \mathbf{N}$. Thus it is certainly possible for different inputs to generate the same output.

**_Remark 3.3.6_** We are now using parentheses $()$ to denote several different things in mathematics; on one hand, we are using them to clarify the order of operations (compare for instance $2 + (3 \times 4)= 14$ with $(2 + 3) \times 4 = 20$), but on the other hand we also use parentheses to enclose the argument $x$ of a function $f(x)$ or of a property such as $P(x)$. However, the two usages of parentheses usually are unambiguous from context. For instance, if $a$ is a number, then $a(b+c)$ denotes the expression $a \times (b + c)$, whereas if $f$ is a function, then $f(b + c)$ denotes the output of $f$ when the input is $b+c$. Sometimes the argument of a function is denoted by subscripting instead of parentheses; for instance, a sequence of natural numbers $a_0, a_1, a_2, a_3, ...$ is, strictly speaking, a function from $\mathbf{N}$ to $\mathbf{N}$, but is denoted by $n \mapsto a_n$ rather than $n \mapsto a(n)$.

**_Remark 3.3.7_** We do not necessarily require functions to be sets, nor do we require sets to be functions. Thus, it does not necessarily make sense to ask whether an object $x$ is an element of a function $f$, and it does not necessarily make sense to apply a set $A$ to an input $x$ to create an output $A(x)$. On the other hand, it is permissible to start with a function $f: X \to Y$ and construct its *graph* $\{(x, f(x)): x \in X\}$, which describes the function completely once the domain $X$ and codomain $Y$ are specified: See Sect. 3.5.

We now define some basic concepts and notions for functions. the first notion is that of equality.

> **Definition 3.3.8** (*Equality of functions*). Two functions $f: X \to Y$, $g: X' \to Y'$ are said to be equal if their domains and codomains agree (i.e., X = X' and Y = Y'), and furthermore that $f(x) = g(x)$ for *all* $x \in X$. If $f(x)$ and $g(x)$ agree for some values of $x$ in the domain, but not others, then we do not consider $f$ and $g$ to be equal[^3]. If two functions $f$, $g$ have different domains, or different ranges, we also do not consider them to be equal.

**_Remark 3.3.9_** According to this definition, two functions that have different domains or different codomains are, strictly speaking, distinct functions. However, when it is safe to do so without causing confusion, it is sometimes useful to "abuse notation" by identifying together functions of different domains or codomains if their values agree on their common domain of definition; this is analogous to the practice of "overloading" an operator in software engineering. See the discussion after Definition 9.4.1 for one instance of this.

**_Example 3.3.10_** (Informal) The functions $x \mapsto x^2 + 2x + 1$ and $x \mapsto (x+1)^2$ are equal on the domain $\mathbf{R}$. The functions $x \mapsto x$ and $x \mapsto |x|$ are equal on the positive real axis, but are not equal on $\mathbf{R}$; thus the concept of equality of functions can depend on the choice of domain.

**_Example 3.3.11_** A rather boring example of a function is the *empty function* $f: \emptyset \to X$ from the empty set to a given set $X$. Since the empty set has not elements, we do not need to specify what $f$ does to any input. Nevertheless, just as the empty set is a set, the empty function is a function, albeit not a particularly interesting one. Note that for each set $X$, there is only one function from $\emptyset$ to $X$, since Definition 3.3.8 asserts that all functions from $\emptyset$ to $X$ are equal (why?).

!!! note Why all functions from $\emptyset$ to $X$ are equal?
    Let $f: \empty \to X$, $g: \emptyset \to X$ be any two functions from $\emptyset$ to $X$. We need to show that $f = g$. Since they have the same domain $\emptyset$ and the same codomain $X$, we only need to show that $f(x) = g(x)$ for all $x \in \emptyset$, which is equivalent to prove the statement that, for any object $x$, if $x \in \emptyset$, then $f(x) = g(x)$. This statement is vacuously true since the hypothesis is false. Thus we can conclude that all functions from $\emptyset$ to $X$ are equal. <span style="float: right">□</span>

**_Remark 3.3.12_** It is not immediately apparent that Definition 3.3.8 is compatible with the axioms of equality in Appendix A.7, although Exercise 3.3.1 provides evidence toward this compatibility. There are at least three ways to address this issue. One is to regard Definition 3.3.8 as an *axiom* about equality of functions rather than a definition. Another is to provide a more explicit definition of a function in which Definition 3.3.8 becomes a theorem; for instance, one can define a function $f: X \to Y$ to be an ordered triple $(X, Y, G)$ consisting of a domain set $X$, a codomain set $Y$, and a graph $G = \{(x, f(x)): x \in X\}$ that obeys the vertical line test and use this latter graph to define the value of $f(x) \in Y$ for each element $x$ of the domain; see Exercise 3.5.10. A third way is to start with a mathematical universe $\mathcal{U}$ without any functions in it and use Definition 3.3.8 to create a larger extention of this universe that contains function objects that behave as specified as in Definition 3.3.8. This final procedure however requires a bit more of the formalism of logic and model theory than is provided by this text, and so will not be detailed here.

A fundamental operation available for functions is *composition*.

> **Defintion 3.3.13** (*Composition*). Let $f: X \to Y$ and $g: Y \to Z$ be two functions, such that the codomain of $f$ is the same set as the domain of $g$. We then define the *composition* $g \circ f: X \to Z$ of the two functions $g$ and $f$ to be the function defined explicitly by the formula
$$
(g \circ f)(x) = g(f(x)).
$$
If the codomain of $f$ does not match the domain of $g$, we leave the composition $g \circ f$ undefined.

It is easy to check that composition obeys the axiom of substitution (Exercise 3.3.1).

**_Example 3.3.14_** Let $f: \mathbf{N} \to \mathbf{N}$ be the function $f(n):=2n$, and let $g: \mathbf{N} \to \mathbf{N}$ be the function $g(n):= n + 3$. Then $g \circ f$ the function
$$
g \circ f(n) = g(f(n)) = g(2n) = 2n + 3,
$$
thus for instance $g \circ f(1) = 5$, $g \circ f(2) = 7$, and so forth. Meanwhile, $f \circ g$ is the function
$$
f \circ g(n) = f(g(n))=f(n+3) = 2(n+3) = 2n +6,
$$
thus for instance $f \circ g(1) = 8$, $f \circ g(2) = 10$, and so forth.

The above example shows that composition is not commutative: $f \circ g$ and $g \circ f$ are not necessarily the same function. However, composition is still associative:

> **Lemma 3.3.15** (Composition is associative). *Let $f: Z \to W$, $g: Y \to Z$*, and $h: X \to Y$ be functions. Then $f \circ (g \circ h) = (f \circ g) \circ h$.

**_Proof_** Since $g \circ h$ is a function from $X$ to $Z$, $f \circ (g \circ h)$ is a function from $X$ to $W$. Similarly $f \circ g$ is a function from $Y$ to $W$, and hence $(f \circ g) \circ h$ is a function from $X$ to $W$. Thus $f \circ (g \circ h)$ and $(f \circ g) \circ h$ have the same domain and codomain. In order to check that they are equal, we see from Definition 3.3.8 that we have to verify that $(f \circ (g\circ h))(x) = ((f\circ g) \circ h)(x)$ for all $x \in X$. But by Definition 3.3.13
$$
\begin{align*}
(f \circ (g \circ h))(x) &= f((g\circ h)(x)) \\
&= f(g(h(x))) \\
&=(f \circ g)(h(x)) \\
&=((f \circ g) \circ h)(x)
\end{align*}
$$
as desired.

**_Remark 3.3.16_** Note that while $g$ appears to the left of $f$ in the expression $g \circ f$, the function $g \circ f$ applies the right-most function $f$ first, before applying $g$. This is often confusing at first; it arises because we traditionally place a function $f$ to the left of its input $x$ rather than to the right. (There are some alternate mathematical notations in which the function is placed to the right of the input; thus we would write $xf$ instead of $f(x)$, but this notation has often proven to be more confusing than clarifying and has not as yet become partially popular.)

We now describe certain special types of functions: *one-to-one* functions, *onto* functions, and *invertible* functions.

> **Definition 3.3.17** (*One-to-one functions*). A function $f$ is *one-to-one* (or injective) if different elements map to different elements:
$$
x \neq x' \implies f(x) \neq f(x')
$$
Equivalently, a function is one-to-one if
$$
f(x) = f(x') \implies x = x'
$$

**_Example 3.3.18_** (Informal) The function $f: \mathbf{Z} \to \mathbf{Z}$ defined by $f(n):=n^2$ is not one-to-one because the distinct elements $-1$, $1$ map to the same element $1$. On the other hand, if we restrict this function to the natural numbers, defining the function $g: \mathbf{N} \to \mathbf{Z}$ by $g(n):=n^2$, then $g$ is now a one-to-one function. Thus the notion of a one-to-one function depends not just on what the function does, but also what its domain is.

**_Remark 3.3.19_** If a function $f: X \to Y$ is not one-to-one, then one can find distinct $x$ and $x'$ in the domain $X$ such that $f(x) = f(x')$, thus one can find two inputs which map to one output. Because of this, we say that $f$ is *two-to-one* instead of *one-to-one*.

> **_Definition 3.3.20_** (*Onto functions*). A function $f$ is *onto* (or *surjective*) if every element in Y comes from applying $f$ to some element in $X$:
> $$
\text{For every } y \in Y, \text{ there exists } x \in X \text{ such that } f(x) =y.
$$

**_Example 3.3.21_** (Informal) The function $f: \mathbf{Z} \to \mathbf{Z}$ defined by $f(n):=n^2$ is not onto because the negative numbers are not in the image of $f$. However, if we restrict the codomain $Z$ to the set $A:=\{n^2: n\in \mathbf{Z}\}$ of square numbers, then the function $g: \mathbf{Z} \to A$ defined by $g(n):=n^2$ is now onto. Thus the notion of an onto function depends not just on what the function does, but also what its range is.

**_Remark 3.3.22_** The concepts of injectivity and surjectivity are in many ways dual to each other; see Exercises 3.3.2, 3.3.4, 3.3.5 for some evidence of this.

> **_Definition 3.3.23_** (*Bijective functions*). Functions $f: X \to Y$ which are both one-to-one and onto are also called *bijective* or *invertible*.

**_Example 3.3.24_** Let $f: \{1, 2, 4\} \to \{3, 4\}$ be the function $f(0):=3$, $f(1):=3$, $f(2):=4$. This function is not bijective because if we set $y=3$, then there is more than one $x$ in $\{1, 2, 4\}$ such that $f(x) = y$ (this is a failure of injectivity). Now let $g: \{0,1\} \to \{2, 3, 4\}$ be the function $g(0):=2, g(1):=3$; then $g$ is not bijective because if we set $y=4$, then there is no $x$ for which $g(x)=y$ (this is a failure of surjectivity). Now let $h: \{0, 1, 2\} \to \{3, 4, 5\}$ be the function $h(0):=3$, $h(1):=4$, $h(2):=5$. Then $h$ is bijective, because each of the elements $3, 4, 5$ comes from exactly one element from $0,1,2$.

**_Example 3.3.25_** The function $f: \mathbf{N} \to \mathbf{N} \setminus \{0\}$ defined by $f(n):= n++$ is a bijection (in fact, this fact is simply restating Lemma 2.2.10). On the other hand, the function $g: \mathbf{N} \to \mathbf{N}$ defined by the same defintion $g(n):=n++$ is not a bijection. thus the notion of a bijective function depends not just on what the function does, but also what its domain and codomain are.

**_Remark 3.3.26_** If a function $x \mapsto f(x)$ is bijective, then we sometimes call $f$ a *perfect matching* or *one-to-one correspondence* (not to be confused with the notion of a one-to-one function) and denote the action of $f$ using the notion $x \leftrightarrow f(x)$ instead of $x \mapsto f(x)$. Thus for instance the function $h$ in the above example is the one-to-one correspondence $0 \leftrightarrow 3$, $1 \leftrightarrow 4$, $2 \leftrightarrow 5$.

**_Remark 3.3.27_** A common error is to say that a function $f: X \to Y$ is bijective iff "for every $x$ in $X$, there is exactly one $y$ in $Y$ such that $y = f(x)$". This is not what it means for $f$ to be bijective; rather, this is merely stating what it means for $f$ to be a *function*. A function cannot map one element to two different elements, for instance one cannot have a function $f$ for which $f(0) = 1$ and also $f(0) = 2$. The functions $f$, $g$ given in Example $3.3.25$ are not bijective, but they are still functions, since each input still gives exactly one output.

If $f$ is bijective, then for every $y \in Y$, there is exactly one $x$ such that $f(x) = y$ (there is at least one because of surjectivity, and at most one because of injectivity). This value of $x$ is denoted by $f^{-1}(y)$; thus $f^{-1}$ is a function from $Y$ to $X$. We call $f^{-1}$ the *inverse* of $f$.

## Exercises

*Exercise 3.3.1* Show that the definition of equality in Definition 3.3.8 is reflexive, symmetric, and transitive. Also verify the substitution property: if $f$, $\tilde{f}$: $X \to Y$ and $g$, $\tilde{g}$: $Y \to Z$ are functions such that $f = \tilde{f}$ and $g = \tilde{g}$, then $g \circ f = \tilde{g} \circ \tilde{f}$.(Of course, these statements are immediate from the axioms of equality in Appendix A.7 applied directly to the functions in question, but the point of the exercise is to show that they can also be established by instead applying the axioms of equality to elements of the domain and codomain of these functions, rather than to the functions itself).

!!! success
    To show the definition is reflexive, let $f: X \to Y$ be a function. We must to show $f=f$. Let $x \in X$. Then $f(x) = f(x)$ by reflexivity of equality on elements of $Y$. Since $x$ was arbitrary, this shows that $f=f$.

    To show the defintion is symmetric, let $f: X \to Y$ and $g: X \to Y$ be two functions with the same domain and codomain. Suppose $f=g$. This means that $f(x) = g(x)$ for all $x \in X$. To show that $g = f$, we must show that $g(x) = f(x)$ for all $x \in X$. So let $x \in X$. Then since $f = g$ we have $f(x)=g(x)$. By symmetry of equality on the elements of $Y$, we have $g(x) = f(x)$. Since $x$ was arbitrary, this shows that $g = f$.

    To show the defintion is transitive, let $f:X \to Y$, $g: X \to Y$ and $h: X \to Y$ be three functions with the same domain and codomain. Suppose $f = g$ and $g = h$. We must show $f = h$. So let $x \in X$. Then we have $f(x)=g(x)$ since $f=g$. We also have $g(x)=h(x)$ since $g=h$. By transitivity of equality on elements of $Y$, we have $f(x)=h(x)$. Since $x$ was arbitrary, this shows that $f = h$.

    Now let $f,\tilde{f}: X \to Y$ and $g,\tilde{g}: Y \to Z$ be functions such that $f = \tilde{f}$ and $g = \tilde{g}$. We want to show $g \circ f = \tilde{g} \circ \tilde{f}$. Let $x \in X$. Then since $f = \tilde{f}$ we have $f(x) = \tilde{f}(x)$. By the substitution axiom of equality for elements of $Y$, we have $g(f(x)) = g(\tilde{f}(x))$. Since $g = \tilde{g}$, we have $g(\tilde{f}(x)) = \tilde{g}(\tilde{f}(x))$. Now we have $(g \circ f)(x) = g(f(x)) = g(\tilde{f}(x)) = \tilde{g}(\tilde{f}(x)) = (\tilde{g} \circ \tilde{f})(x)$ using symmetry and transitivity of equality on elements of $Z$. Since $x \in X$ was arbitrary, this shows that $g \circ f = \tilde{g} \circ \tilde{f}$ as required. <span style="float: right">□</span>

*Exercise 3.3.2* Let $f: X \to Y$ and $g: Y \to Z$ be functions. Show that if $f$ and $g$ are both injective, then so is $g \circ f$; similarly, show that if $f$ and $g$ are both surjective, then so is $g \circ f$.

!!! success
    - To show $g \circ f$ is injective if both $f$ and $g$ are injective, let $x$ and $x'$ be elements of $X$, we want to show that $(g \circ f)(x) = (g \circ f) (x')$ implies $x = x'$ by Definition 3.3.17. By Definition 3.3.13, $(g \circ f)(x) = g(f(x))$ and $(g \circ f)(x') = g(f(x'))$, so we need to show that $g(f(x))=g(f(x')) \implies x = x'$. By consecutive applications of Definition 3.3.17, we have $f(x) = f(x')$ and hence $x = x'$ as desired.

    - To show $g \circ f$ is surjective if both $f$ and $g$ are surjective, let $z \in Z$. By Definition 3.3.20, there exists $y \in Y$ such that $z = g(y)$ since $g: Y \to Z$ is surjective. Also by Definition 3.3.20, there exists $x \in X$ such that $y = f(x)$ since $f: X \to Y$ is surjective. By the substitution axiom of equality $z = g(f(x))$ and hence $z = (g \circ f)(x)$ by Definition 3.1.13. Since $z$ was arbitrary, there exists $x \in X$ such that $(g \circ f)(x)$ for every $z \in Z$. So $g \circ f$ is surjective. <span style="float: right">□</span>

*Exercise 3.3.3* When is the empty function into a given set $X$ injective? surjective? bijective?

!!! Success
    - For any two distinct objects $x$ and $x'$, if $x \in \emptyset$ and $x' \in \emptyset$, then $f(x) \neq f(x')$ is vacuously true since the hypothesis is false. So empty function is always injective.

    - Suppose $f: \emptyset \to X$ is the empty function and $x$ be any object. If $X = \emptyset$ then $x \in X$ implies there is $a \in \emptyset$ such that $f(a) = x$ since $x \in X$ is false and hence $f$ is surjective by Defintion 3.3.20. On the other hand, if $X \neq \emptyset$ then $f$ is by no means surjective. Since if $f$ is surjective, then there exists $a \in empty$ such that $x = f(a)$. However such $a$ does not exist by Axiom 3.3, leading to a contradiction. Thus the empty function into a given set $X$ is surjective iff $X = \emptyset$.

    - Since the empty function is always injective but surjective iff $X = \emptyset$, it is bijective iff $X = \emptyset$ by Definition 3.3.23.<span style="float: right">□</span>

*Exercise 3.3.4* In this section we give some cancellation laws for compostion. Let $f: X \to Y$, $\tilde{f}: X \to Y$, $g: Y \to Z$ and $\tilde{g}: Y \to Z$ be functions. Show that if $g \circ f = g \circ \tilde{f}$ and $g$ is injective, then $f = \tilde{f}$. Is the same statement true if $g$ is not injective? Show that if $g \circ f = \tilde{g} \circ f$ and $f$ is surjective, then $g = \tilde{g}$. Is the same statement true if $f$ is not surjective?

!!! Success
    - To show $f = \tilde{f}$, we need to show $f(x) = \tilde{f}(x)$ for all $x \in X$. Obviously, $g \circ f$ and $g \circ \tilde{f}$ are all functions from $X \to Z$. Now we prove by contradiction. Suppose $x \in X$ then $f(x) \in Y$ and $\tilde{f}(x) \in Y$. If $f(x) \neq \tilde{f}(x)$ then we have $g(f(x)) \neq g(\tilde{f}(x))$ since $g$ is injective. This means $(g \circ f)(x) \neq (g \circ \tilde{f})(x)$ and hence $g \circ f \neq g \circ \tilde{f}$, which is a contradiction. Since $x$ was arbitrary, $f(x) = \tilde{f}(x)$ for all $x \in X$. So $f = \tilde{f}$ as desired. If $g$ is not injective, then the same statement is not true. For instance, let $g: Y \to Z$ defined by $g(x):=1$, $f:X \to Y$ defined by$f(x):=2$, $\tilde{f}: X \to Y$ defined by $\tilde{f}(x) := 3$. Although $g \circ f = g \circ \tilde{f}$, $f \neq \tilde{f}$.

    - To show $g = \tilde{g}$, we need to show $g(y) = \tilde{g}(y)$ for all $y \in Y$. Suppose $y \in Y$, then there exists $x \in X$ such that $y=f(x)$. Since $g \circ f = \tilde{g} \circ f$, we have $(g \circ f)(x) = (\tilde{g} \circ f)(x)$ for all $x \in X$. This means $g(f(x))=\tilde{g}(f(x))$, so $g(y) = \tilde{g}(y)$. Since $y$ is arbitrary, $g = \tilde{g}$ as desired. If $x$ is not surjective, then the same statement is not true. For instance let $f: \{1, 2, 3\} \to \{1, 2, 3\}$ defined by $f(x):=1$, $g: \{1, 2, 3\} \to \{1, 2, 3\}$ defined by $g(1):=1, g(2):=2, g(3):=3$, $\tilde{g}: \{1, 2, 3\} \to \{1, 2, 3\}$ defined by $\tilde{g}(1):=1, \tilde{g}(2):=3, \tilde{g}(3):=2$. Obviously, $(g \circ f)(x)=(\tilde{g} \circ f)(x)=1$ for all $x \in \{1, 2,3\}$, but $g \neq \tilde{g}$ since $g(2) \neq \tilde{g}(2)$.<span style="float: right">□</span>

*Exercise 3.3.5* Let $f: X \to Y$ and $g: Y \to Z$ be functions. Show that if $g \circ f$ is injective, then $f$ must be injective. Is it true that $g$ must also be injective? Show that if $g \circ f$ is surjective, then $g$ must be surjective. Is it true that $f$ must also be surjective?

!!! Success
    - To show $f$ is injective, we need to show that if $x$ and $x'$ are any two distinct elements of $X$ then $f(x) \neq f(x')$. We prove this statement by contradiction. If $f(x) = f(x')$, then we have $g(f(x)) = g(f(x'))$ by the substitution axiom of equality. This means $(g \circ f)(x) = (g \circ f) (x')$ by the definition of composition. However, $(g \circ f)(x) \neq (g \circ f)(x')$ since $g \circ f$ is injective and $x \neq x'$. So $f(x) \neq f(x')$ and hence $f$ is injective. Moreover, $g$ does not need to be injective. For instance, let $f: \{1, 2\} \to \{1, 2, 3\}$ be a function defined by $f(1):=1, f(2):=2$ and $g: \{1, 2, 3\} \to \{1, 2\}$ be a function defined by $g(1):= 1, g(2):=2, g(3):=2$. Then $g \circ f: \{1, 2\} \to \{1, 2\}$ is a function defined by $g \circ f(1) = 1, g \circ f(2)=2$, which is injective, while $g$ itself is not injective since $g(2)=g(3)=2$.
    - To show $g$ is surjective, we need to show that for any $z \in Z$ there exists $y \in Y$ such that $z = g(y)$. Let $z \in Z$. Since $g \circ f: X \to Z$ is surjective, there exists $x \in X$ such that $z = g \circ f(x)$. By the definition of composition, $g \circ f(x) = g(f(x))$, so $z = g(f(x))$. As $f(x) \in Y$, $f(x)$ is then one such $y$ that satisfies $z = g(y)$. Since $z$ was arbitrary, $g$ is surjective as desired. Moreover, $f$ does not have to be surjective. For instance, let $f: \{1, 2\} \to \{1, 2, 3\}$ be a function defined by $f(1):=1, f(2):=2$ and $g: \{1, 2, 3\} \to \{1, 2\}$ be a function defined by $g(1):= 1, g(2):=2, g(3):=2$. Then $g \circ f: \{1, 2\} \to \{1, 2\}$ is a function defined by $g \circ f(1) = 1, g \circ f(2)=2$, which is surjective, while $f$ itself is not surjective since there does not exist $x \in \{1, 2\}$ such that $3 = f(x)$.<span style="float: right">□</span>

*Exercise 3.3.6* Let $f: X \to Y$ be a bijective function, and let $f^{-1}: Y \to X$ be its inverse. Verify the cancellation laws $f^{-1}(f(x)) = x$ for all $x \in X$ and $f(f^{-1}(y))=y$ for all $y \in Y$. Conclude that $f^{-1}$ is also invertible and has $f$ as its inverse (thus $(f^{-1})^{-1}=f$).

!!! success
    - To prove $f^{-1}(f(x)) = x$ for all $x \in X$, let $x \in X$, then $f(x) \in Y$. Since $f$ is surjective, there exists $x' \in X$ such that $f(x') = f(x)$. Since $f$ is injective, $f(x') = f(x)$ implies $x' = x$. Thus there is exactly one $x$ such that $f(x) = f(x)$ and hence $f^{-1}(f(x))=x$. Since $x$ was arbitrary, $f^{-1}(f(x)) = x$ holds for all $x \in X$.
    - To prove $f(f^{-1}(y)) = y$ for all $y \in Y$, let $y \in Y$. Since $f$ is surjective, there is exactly one $x \in X$ such that $f(x) = y$ and we denote this $x$ by $f^{-1}(y)$. So $f(x) = f(f^{-1}(y)) = y$. Since $y$ was arbitrary, $f(f^{-1}(y)) = y$ holds for all $y \in Y$.
    - To prove $f^{-1}$ is invertible, we need to show that $f^{-1}: Y \to X$ is both injective and surjective. To prove that $f^{-1}$ is injective, let $y$ and $y'$ be any two element of $Y$, we need to show that if $f^{-1}(y) = f^{-1}(y')$ then $y = y'$. By applying $f$ to both sides of $f^{-1}(y) = f^{-1}(y')$, we get $f(f^{-1}y)=f(f^{-1}(y'))$. By the second cancellation law we just proved, this means $y = y'$. So $f^{-1}$ is injective. To prove that $f^{-1}$ is surjective, let $x$ be any element of $X$, we need to show that there exists $y \in Y$ such that $x = f^{-1}(y)$. Let $y:=f(x)$, then by the first cancellation law we just proved, we have $f^{-1}(y)=f^{-1}(f(x)) = x$. So $f^{-1}$ is surjective. Therefore, $f^{-1}$ is invertible.
    - Finally we need to show that $f^{-1}$ has $f$ as its inverse. To prove this statement, we need to show that for any $x \in X$ we have $(f^{-1})^{-1}(x) = f(x)$. Since we already showed $f^{-1}$ is bijective, then there exists exactly one $y \in Y$ such that $x = f^{-1}(y)$ and we denote this $y$ as $(f^{-1})^{-1}(x)$. On the other hand, by applying f to both sides of the equation $x = f^{-1}(y)$ we have $f(x) = f(f^{-1}(y))$. By the second cancellation law, we have $f(f^{-1}(y))=y$. So $(f^{-1})^{-1}(x) = y = f(x)$, and hence $f^{-1}$ has $f$ as its inverse as desired.<span style="float: right">□</span>

*Exercise 3.3.7* Let $f: X \to Y$ and $g: Y \to Z$ be functions. Show that if $f$ and $g$ are bijective, then so is $g \circ f$, and we have $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$.

!!! success
    We first show that $g \circ f$ is bijective. On one hand, we need to prove that $g \circ f$ is surjective, so we need to show that for any $z \in Z$, there exists $x \in X$ such that $z=(g \circ f)(x)$. Suppose now $z$ is an arbitrary element of $X$. Since $g$ is surjective, there exists $y \in Y$ such that $z=g(y)$. Similarly, since $f$ is surjective, there exists $x \in X$ such that $y=f(x)$. Thus $z = g(y)=g(f(x))=(g\circ f)(x)$. This means that for any $z \in Z$ there exists $x \in X$ such that $z = (g \circ f)(x)$ and hence $g \circ f$ is surjective. On the other hand, we need to show that $g \circ f$ is injective, so we need to show that for any two distinct elements $x$ and $x'$ of X, $g \circ f(x') \neq g \circ f(x)$. Suppose $x$ and $x'$ are any two distinct elements of $A$. Since $f$ is injective, we have $f(x) \neq f(x')$. Since $f(x) \in Y$, $f(x')\in Y$, and $g$ s injective,  we have $g(f(x)) \neq g(f(x'))$ which means $(g \circ f)(x) \neq (g \circ f)(x')$. Thus $g \circ f$ is injective. So $g \circ f$ is bijective as desired.

    Next we show that $(g \circ f)^{-1}=f^{-1}\circ g^{-1}$. Since the two functions have the same domain $X$ and codomain $Z$, we just need to show that $(g \circ f)^{-1}(z)=f^{-1} \circ g^{-1}(z)$ for any $z \in Z$. Let $x=(g\circ f)^{-1}(z)$, by the definition of inverse function, we have $(g \circ f)(x)=g(f(x))=z)$. By applying $g^{-1}$ on both sides of the equation, we have $f(x)=g^{-1}(z)$. By applying $f^{-1}$ on both sides of the equation, we have $x = f^{-1}(g^{-1}(z))= (f^{-1} \circ g^{-1})(z)$. So $(g\circ f)^{-1}(z)=(f^{-1} \circ g^{-1})(z)$ and hence $(g \circ f)^{-1}=f^{-1}\circ g^{-1}$ as desired.

*Exercise 3.3.8* If $X$ is a subset of $Y$, let $\iota_{X \to Y}: X \to Y$ be the *inclusion map from $X$ to $Y$*, defined by mapping $x \mapsto x$ for all $x \in X$, i.e., $\iota_{X \to Y(x)}:=x$ for all $x \in X$. The map $\iota_{X \to X}$ is in particular called the *identity map* on $X$.
- (a) Show that if $X \subseteq Y \subseteq Z$ then $\iota_{Y \to Z} = \iota_{X \to Z}$.
- (b) Show that if $f: A \to B$ is any function, then $f = f \circ \iota_{A \to A} = \iota_{B \to B} \circ f$.
- (c) Show that, if $f: A \to B$ is a bijective function, then $f \circ f^{-1} = \iota_{B \to B}$ and $f^{-1} \circ f = \iota_{A \to A}$.
- (d) Show that if $X$ and $Y$ are disjoint sets, and $f: X \to Z$ and $g: Y \to Z$ are functions, then there is a unique function $h: X \cup Y \to Z$ such that $h \circ \iota_{X \to X \cup Y} = g$.
- (e) Show that the hypothesis that $X$ and $Y$ are disjoint can be dropped in (d) if one adds the additional hypothesis that $f(x) = g(x)$ for $x \in X \cap Y$.



[^2]: In some texts the codmain is referred to as the *range*; however we will use the term range to refer instead to the image $f(X)$ of the domain, defined after Definition 3.4.1. 
[^3]: In Chap. 8 of *Analysis II*, we shall introduce da weaker notion of equality, that of two functions being *equal almost everywhere*.
