# Set Theory

Modern analysis, like most other subfields of modern mathematics, is concerned with numbers, sets, and geometry.We have already introduced one type of number system, the natural numbers. We will introduce the other number systems shortly, but for now we pause to introduce the concepts and notation of set theory, as they will be used increasingly heavily in later chapters. (We will not pursue a rigorous description of Euclidean geometry in this text, preferring instead to describe that geometry in terms of real number system by means of Cartesian co-ordinate system.)

While set theory is not the main focus of this text, almost every other branch of mathematics relies on set theory as part of its foundation, so it is important to get at least some grounding in set theory before doing other advanced areas of mathematics. In this chapter we present the more elementary aspects of axiomatic set theory, leaving more advanced topics such as discussion of infinite sets and the axiom of choice to Chap. 8. A full treatment of the finer subtleties of set theory (of which there are many!) is unfortunately well beyond the scope of this text.

## 3.1 Fundamentals

In this section we shall set out some axioms for sets, just as we did for the natural numbers. For pedagogical reasons, we will use a somewhat overcomplete list of axioms for set theory, in the sense that some of the axioms can be used to deduce others, but there is no real harm in doing this. We begin with an informal description of what sets should be.

> **Definition 3.1.1** (*Informal*) We define a *set* $A$ to be any unordered colleciton of objects, e.g., $\{3,8,5,2\}$ is set. If $x$ is an object, we say that $x$ is *an element of* $A$ or $x \in A$ if $x$ lies in the collection; otherwise we say that $x \notin A$. For instance $3 \in \left \{1,2,3,4,5 \right \}$ but $7 \notin \left \{1,2,3,4,5  \right \}$.

This definition is intuitive enough, but it doesn't answer a number of questions, such as which collections of objects are considered to be sets, which sets are equal to other sets, and how one defines operations on sets (e.g., unions, intersections, etc.). Also, we have not axioms yet on what sets do, or what their elements do. Obtaining these axioms and defining these operations will be the purpose of the remainder of this section.

We first clarify one point: we consider sets themselves to be a type of object.

> **Axiom 3.1** (*Sets are objects*). If $A$ is a set, then $A$ is also an object. In particular, given two sets $A$ and $B$, it is meaningful to ask whether $A$ is also an element of $B$.

**_Example 3.1.2_** (Informal) The set $\left \{ 3, \left \{ 3,4 \right \},4  \right \}$ is a set of three distinct elements, one of which happens to itself to be a set of two elements. See Example 3.1.9 for a more formal version of this example.

**_Remark 3.1.3_** There is a special case of set theory, called "pure set theory", in which _all_ objects are sets; for instance the number $0$ might be identified with the empty set $\emptyset = \left \{  \right \}$, the number $1$ might be identified with $\left \{  0\right \}=\left \{  \left \{  \right \} \right \}$, the number $2$ might be identified with $\left \{0,1\right \}=\left \{\left \{  \right \} ,\left \{\left \{  \right \}   \right \}   \right \}$, and so forth. From a logical point of view, pure set theory is a simpler theory, since one only has to deal with sets and not with objects; however, from a conceptual point of view it is often easier to deal with impure set theories in which some objects are not considered to be sets. The two types of theories are more or less equivalent for the purposes of doing mathematics, an so we shall take an agnostic position as to whether all objects are sets or nots. For instance, we do not insist that a natural number such as $3$ be identified with a set as indicated above. (The more accurate and mathematically useful statement is that natural numbers can be cardinalities of sets, rather than necessarily being sets themselves. See Sect. 3.6.)

To summarize so far, among all the objects studied in mathematics, some of the objects happen to be sets; and if $x$ is an object and $A$ is a set, then either $x \in A$ true or $x \in A$ is false. (If $A$ is not a set, we leave the statement $x \in A$ undefined; for instance, we consider the statement $3 \in 4$ to neither be true or false, but simply meaningless, since $4$ is not a set.)

Next, we try to capture the notion of equality: when are two sets considered to be equal? We do not consider the order of the elements inside a set to be important; thus we think of $\left \{3,8,5,2\right \}$ and $\left \{2,3,5,8\right \}$ as the same set. On the other hand, $\left \{3,8,5,2\right \}$ and $\left \{3,8,5,2,1 \right \}$ are different sets because the latter set contains an element that the former one does not, namely the element $1$. For similar reasons $\left \{3,8,5,2\right \}$ and $\left \{3,8,5\right \}$ are different sets. We formalize this by a further axiom:

> **Axiom 3.2** (_Equality of sets_). Two sets $A$ and $B$ are _equal_, $A=B$, iff every element of $A$ is an element of $B$ and vice versa. To put it another weay, $A = B$ if and only if every element of $x$ of $A$ belongs also to $B$, and every element $y$ of $B$ belongs also to $A$.

**_Example 3.1.4_** Thus, for instance, $\left \{1,2,3,4,5\right \}$ and $\left \{3,4,2,1,5\right \}$ are the same set, since they contain exactly the same elements. (The set $\left \{3,3,1,5,2,4,2\right \}$ is also equal to $\left \{1,2,3,4,5\right \}$; the repetition of $3$ and $2$ is irrelevant as it does not further change the status of $2$ and $3$ being elements of the sets.)

The "is an element of" relation $\in$ obeys the axiom of substitution (see Section A.7). Because of this, any new operation we define on sets will also obey the axiom of substitution, as long as we can define that operation purely in terms of the relation $\in$. This is for instance the case for the remaining definitions in this section. (on the other hand, we cannot use the notion of the "first" or "last" element in a set in a well-defined manner, because this would not respect the axiom of substitution; for instance the sets $\left \{1,2,3,4,5\right \}$ and $\left \{3,4,2,1,5\right \}$ are the same set, but have different first elements.)

Next, we turn to the issue of exactly which objects are sets and which objects are not. The situation is analogous to how we defined the natural numbers in the previous chapter; we started with a single natural number, $0$, and started building more numbers out of $0$ using increment operation. We will try something similar here, starting wiht a single set, the _empty set_, and building more sets out of the empty set by various operations. We begin by postulatiing the existence of the empty set.

> **Axiom 3.3** (_Empty set_). There exists a set $\emptyset$, known as the _empty set_, which contains no elements, i.e., for every object $x$ we have $x \notin \emptyset$.

The empty set is also denoted $\left \{ \right \}$. Note that there can only be one empty set; if there were two sets $\emptyset$ and $\emptyset'$ which were both empy, then by Axiom 3.2 they would be equal to each other (why?).

!!! Note why there can only be one empty set?
    We need to show that $\emptyset = \emptyset'$.Therefore, for an object $x$, we need to check the following two statements:(1) if $x \in \emptyset$, then $x \in \emptyset'$; (2) if $x \in \emptyset'$,then $x \in \emptyset$. Obviously both statements are vacuously true because their hypothethes are false. According to Axiom 3.2, $\emptyset = \emptyset'$. <span style="float: right">□</span>

If a set is not equal to the empty set, we call it _non-empty_. The following statement is very simple, but worth stating nevertheless:

**Lemma 3.1.5** (Single choice). _Let $A$ be a non-empty set. Then there exists an object $x$ such that $x \in A.$_

**_Proof_** we prove by contradiction. Suppose there does not exist any object $x$ such that $x \in A$. Then for all objects $x$, we have $x \notin A$. Also, by Axiom 3.3 we have $x \notin \emptyset$. Thus $x \in A \Leftrightarrow x \in \emptyset$ (both statements are equally false), and so $A = \emptyset$ by Axiom 3.2, a contradiction. <span style="float: right">□</span>

!!! note why both statements are equally false?
    Let $X$ be the statement that for all objects $x$, we have $x \notin A$, and let $Y$ be the statement that for all objects $x$, we have $x \notin \emptyset$. Under the condition that there does not exist any object $x$ such that $x \in A$, whenever X is false, Y has to be false, and whenever $Y$ is false, $X$ has to be false. So $X$ and $Y$ are equally false which means they are equivalent statements.

**_Remark 3.1.6_** The above Lemma asserts that given any non-empty set $A$, we are allowed to "choose" an element $x$ of $A$ which demonstrates this non-emptyness. Later on (in Lemma 3.5.11) we will show that given any finite number of non-empty sets, say $A_1,...A_n$, it is possible to choose one element $x_1,...,x_n$ from each set $A_1,...A_n$ this is known as "finite choice". However, in order to choose elements from an infinite number of sets, we need an additional axiom, the _axiom of choice_ which we will discuss in Sect. 8.4.

**_Remark 3.1.7_** Note that the empty set is _not_ necessarily the same thing as the natural number $0$. One is a set; the other is a number. However, it is true that the _cardinality_ of the empty set is $0$; see Sect. 3.6.

If Axiom 3.3 was the only axiom that set theory had, then set theory could be quite boring, as there might be just a single set in existence, the empty set. We now present further axioms to enrich the class of sets available.

> **Axiom 3.4** (_Singleton sets and pair sets_). If $a$ is an object, then there exists a set $\left \{ a\right \}$ whose only element is $a$, i.e., for every object $y$, we have $y \in \left \{ a\right \}$ if and only if $y = a$; we refer to $\left \{ a\right \}$ as the _singleton set_ whose element is $a$. Furthermore, if $a$ and $b$ are objects, then there exists a set $\left \{ a, b\right \}$ whose only elements are $a$ and $b$; i.e., for every object $y$, we have $y \in \left \{ a, b\right \}$ if and only if $y=a$ or $y=b$; we refer to this set as the _pair set_ formed by $a$ and $b$.

**_Examples 3.1.9_** Since $\emptyset$ is a set (and hence an object), the singleton set $\left \{ \emptyset\right \}$, i.e., the set whose only element is $\emptyset$, is also a set. Similarly, the singleton set $\left \{ \left \{ \emptyset\right \}\right \}$ and the pair set $\left \{ \emptyset, \left \{ \emptyset\right \}\right \}$ are also sets. These four sets are not equal to each other (Exercies 3.1.2)

As the above examples show, we can now create quite a few sets; however, the sets we make are still fairly small (each set that we can build consists of no more than two elements, so far). The next axiom allows us to build somewhat larger sets than before.

> **Axiom 3.5** (_Pairwise union_).Given any two sets $A$, $B$, there exists a set $A \cup B$, called the _union_ of $A$ and $B$, which consists of all the elements which belong to $A$ or $B$ or both. In other words, for any object $x$,
> $$
    x \in A \cup B \Leftrightarrow (x \in A \text{ or } x \in B)
$$

Recall that "or" refers by default in mathematics to _inclusive_ or:"$X$ or $Y$ is true" means that "either $X$ is true, or $Y$ is true, or both are true". See Sect. A.1.

**_Example 3.1.10_** The set $\{1, 2\} \cup \{2, 3\}$ consists of those elements which either lie on $\{1, 2\}$ or in $\{2, 3\}$ or in both, or in other words the elements of this set are simply $1$, $2$ and 3. Because of this, we denote this set as $\{1, 2\} \cup \{2, 3\} = \{1, 2, 3\}$.

**_Remark 3.1.11_** If $A$, $B$, $A'$ are sets, and $A$ is equal to $A'$, then $A \cup B$ is equal to $A' \cup B$ (why? One needs to use Axiom 3.5 and Axiom 3.2). Similarly if $B'$ is a set which is equal to $B$, then $A \cup B$ is equal to $A \cup B'$. Thus the operation of union obeys the axiom of substitution and is thus well-defined on sets.

!!! note Why $A \cup B$ is equal to $A' \cup B$?
    For any object $x \in A \cup B$, we have $x \in A$ or $x \in B$. If $x \in A$, then $x \in A'$ according to Axiom 3.2 and thus $x \in A' \cup B$ according to Axiom 3.5; if $x \in B$, then $x \in A' \cup B$ according to Axiom 3.5. Both situations lead to the result that $x \in A \cup B'$. Similarly, for any object $y \in A' \cup B$, we can show that $y \in A \cup B$. Hence, according to Axiom 3.2, $A \cup B$ is equal to $A' \cup B$. <span style="float: right">□</span>

We now give some basic properties of unions.

> **Lemma 3.1.12** _If $a$ and $b$ are objects, then $\{a, b\} = \{a\} \cup \{b\}$. If $A$, $B$, $C$ are sets, then the union operation is commutative (i.e., $A \cup B = B \cup A$) and associative (i.e., (A \cup B) \cup C = A \cup (B \cup C)). Also, we have $A \cup A = A \cup \emptyset = \emptyset \cup A = A$._

**_Proof_** We prove just the associativity identity $(A \cup B) \cup C = A \cup (B \cup C)$ and leave the remaining claims to Exercise 3.1.3. By Axiom 3.2, we need to show that every element $x$ of $(A \cup B) \cup C$ is an element of $A \cup (B \cup C)$, and vice versa. So suppose first that $x$ is an element of $(A \cup B) \cup C$. By Axiom 3.5, this means that at least one of $x \in A \cup B$ or $x \in C$ is true. We now divide into two cases. If $x \in C$, then by Axiom 3.5 again $x \in B \cup C$, and so by Axiom 3.5 again we have $x \in A \cup (B \cup C)$. Now suppose instead $x \in A \cup B$, then by Axiom 3.5 again $x \in A$ or $x \in B$. If $x \in A$ then $x \in A \cup (B \cup C)$ by Axiom 3.5, while if $x \in B$ then by consecutive applications of Axiom 3.5 we have $x \in B \cup C$ and hence $x \in A \cup (B \cup C)$. Thus in all cases we see that every element of $(A \cup B) \cup C$ lies in $A \cup (B \cup C)$. A similar argument shows that every element of $A \cup (B \cup C)$ lies in $(A \cup B) \cup C$, and so $(A \cup B) \cup C = A \cup (B \cup C)$ as desired.<span style="float: right">□</span>

Because of the above lemma, we do not need to use parentheses to denote multiple unions, thus of instance we can write $A \cup B \cup C$ insdead of $(A \cup B) \cup C$ or $A \cup (B \cup C)$. Similarly for unions of four seets, $A \cup B \cup C \cup D$, etc.

**_Remark 3.1.13_** While the operation of union has some similarities with addition, the two operations are _not_ identical. For instance, $\{2\} \cup \{3\} = \{2,3\}$ and $2+3=5$, whereas \{2\} + \{3\}  is meaningless (addition pertains to numbers, not sets) and $2 \cup 3$ is also meaningless (union pertains to sets, not numbers).

This axiom allows us to define triplet sets, quadruplet set, and so forth: if $a$, $b$, $c$ are three objects, we define $\{a, b, c, d\}:= \{a\} \cup \{b\} \cup \{c\}$; if $a$, $b$, $c$, $d$ are four objects, then we define $\{a, b, c, d\}:= \{a\} \cup \{b\} \cup \{c\} \cup \{d\}$, and so forth. On the other hand, we are not yet in a position to define sets consisting of $n$ objects for any given natural number $n$, this would require iterating the above construction "$n$ times", but the concept of $n$-fold iteration has not yet been rigorously defined. For similar reasons, we cannot yet define sets consisting of inifinitely many objects, because that would require iterating the axiom of pairwise union infinitely often, and it is not clear at this stage that one can do this rigorously. Later on, we wil introduce other axioms of set theory which allow one to construct arbitarily large, and even infinite, sets.

Clearly, some sets seem to be larger than others. One way to formalize this concept is through the notion of a _subset_.

> **Definition 3.1.14** (_Subsets_). Let $A$, $B$ be sets. We say that $A$ is a _subset_ of $B$, denoted $A \subseteq B$, iff every element of $A$ is also an element of $B$, i.e.,
> $$
\text{For any object } x, x \in A \Rightarrow x \in B.
$$

We say that $A$ is a proper _subset_ of $B$, denoted $A \subsetneq B$, if $A \subseteq B$ and $A \neq B$.

