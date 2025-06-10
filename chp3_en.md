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

> **Lemma 3.1.12** _If $a$ and $b$ are objects, then $\{a, b\} = \{a\} \cup \{b\}$. If $A$, $B$, $C$ are sets, then the union operation is commutative (i.e., $A \cup B = B \cup A$) and associative (i.e., $(A \cup B) \cup C = A \cup (B \cup C))$. Also, we have $A \cup A = A \cup \emptyset = \emptyset \cup A = A$._

**_Proof_** We prove just the associativity identity $(A \cup B) \cup C = A \cup (B \cup C)$ and leave the remaining claims to Exercise 3.1.3. By Axiom 3.2, we need to show that every element $x$ of $(A \cup B) \cup C$ is an element of $A \cup (B \cup C)$, and vice versa. So suppose first that $x$ is an element of $(A \cup B) \cup C$. By Axiom 3.5, this means that at least one of $x \in A \cup B$ or $x \in C$ is true. We now divide into two cases. If $x \in C$, then by Axiom 3.5 again $x \in B \cup C$, and so by Axiom 3.5 again we have $x \in A \cup (B \cup C)$. Now suppose instead $x \in A \cup B$, then by Axiom 3.5 again $x \in A$ or $x \in B$. If $x \in A$ then $x \in A \cup (B \cup C)$ by Axiom 3.5, while if $x \in B$ then by consecutive applications of Axiom 3.5 we have $x \in B \cup C$ and hence $x \in A \cup (B \cup C)$. Thus in all cases we see that every element of $(A \cup B) \cup C$ lies in $A \cup (B \cup C)$. A similar argument shows that every element of $A \cup (B \cup C)$ lies in $(A \cup B) \cup C$, and so $(A \cup B) \cup C = A \cup (B \cup C)$ as desired.<span style="float: right">□</span>

Because of the above lemma, we do not need to use parentheses to denote multiple unions, thus of instance we can write $A \cup B \cup C$ instead of $(A \cup B) \cup C$ or $A \cup (B \cup C)$. Similarly for unions of four seets, $A \cup B \cup C \cup D$, etc.

**_Remark 3.1.13_** While the operation of union has some similarities with addition, the two operations are _not_ identical. For instance, $\{2\} \cup \{3\} = \{2,3\}$ and $2+3=5$, whereas \{2\} + \{3\}  is meaningless (addition pertains to numbers, not sets) and $2 \cup 3$ is also meaningless (union pertains to sets, not numbers).

This axiom allows us to define triplet sets, quadruplet set, and so forth: if $a$, $b$, $c$ are three objects, we define $\{a, b, c, d\}:= \{a\} \cup \{b\} \cup \{c\}$; if $a$, $b$, $c$, $d$ are four objects, then we define $\{a, b, c, d\}:= \{a\} \cup \{b\} \cup \{c\} \cup \{d\}$, and so forth. On the other hand, we are not yet in a position to define sets consisting of $n$ objects for any given natural number $n$, this would require iterating the above construction "$n$ times", but the concept of $n$-fold iteration has not yet been rigorously defined. For similar reasons, we cannot yet define sets consisting of inifinitely many objects, because that would require iterating the axiom of pairwise union infinitely often, and it is not clear at this stage that one can do this rigorously. Later on, we wil introduce other axioms of set theory which allow one to construct arbitarily large, and even infinite, sets.

Clearly, some sets seem to be larger than others. One way to formalize this concept is through the notion of a _subset_.

> **Definition 3.1.14** (_Subsets_). Let $A$, $B$ be sets. We say that $A$ is a _subset_ of $B$, denoted $A \subseteq B$, iff every element of $A$ is also an element of $B$, i.e.,
> $$ \text{For any object } x, x \in A \Rightarrow x \in B. $$
> We say that $A$ is a proper _subset_ of $B$, denoted $A \subsetneq B$, if $A \subseteq B$ and $A \neq B$.

**_Remark 3.1.15_** Because these definitions involve only the notions of equality and the "is an element of" relation, both of which already obey the axiom of substitution, the notion of subset also automatically obeys the axiom of substitution. Thus for instance if $A \subseteq B$ and $A = A'$, then $A' \subseteq B$.

**_Examples 3.1.16_** We have $\{1, 2, 4\} \subseteq \{1,2,3,4,5\}$, because every element of $\{1,2,4\}$ is also an element of $\{1,2,3,4,5\}$. In fact we also have $\{1,2,4\} \subsetneq \{1,2,3,4,5\}$, since the two sets $\{1,2,4\}$ and $\{1,2,3,4,5\}$ are not equal. Given any set $A$, we always have $A \subseteq A$ (why?) and $\emptyset \subseteq A$ (why?).

!!! note Why $A \subseteq A$ and $\emptyset \subseteq A$?
    (1) By the reflexive axiom of equalitiy, we have $A = A$. By Axiom 3.2, for any object $x$, $x \in A \Leftrightarrow x \in A$. Thus by the definition of subsets, we have $A \subseteq A$.

    (2) We need to show that for any object $x$, $x \in \emptyset \Rightarrow x \in A$. This statement is vacuously true since the hypothesis is false by Axiom 3.3.

The notion of subset in set theory is similar to the notion of "less than or equal to" for numbers, as the following proposition demonstrates (for a more precise statement, see Definition 8.5.1):

**Proposition 3.1.17** (Sets are partially ordered by set inclusion). _Let $A$, $B$, $C$ be sets. If $A \subseteq B$ and $B \subseteq C$ then $A \subseteq C$. If $A \subseteq B$ and $B \subseteq A$, then $A = B$. Finally, if $A \subsetneq B$ and $B \subsetneq C$ then $A \subsetneq C$_.

**_Proof_** We shall just prove the first claim. Supppose that $A \subseteq B$ and $B \subseteq C$. To prove that $A \subseteq C$, we have to provce that every element of $A$ is an element of $C$. So, let us pick an arbitary element $x$ of $A$. Then, since $A \subseteq B$, $x$ must then be an element of $B$. But then since $B \subseteq C$, $x$ is an element of $C$. Thus every element of $A$ is indeed an element of $C$, as claimed.<span style="float: right">□</span>

**_Remark 3.1.18_** The subset relation and the union operation are related to each other: seek for instance Exercice 3.1.7.

**_Remark 3.1.19_** There is one important difference between the subset relation $\subsetneq$ and the less than relation $<$. Given any two distinct natural numbers $n$, $m$, we know that one of them is smaller than the other (Proposition 2.2.13); however, given two distinct sets, it is not in general true that one of them is a subset of the other. For instance, take $A:=\{2n: n \in \mathbf{N}\}$ to the set of even natural numbers, and $B:= \{2n+1: n \in \mathbf{N}\}$ to be the set of odd natural numbers. Then neither set is a subset of the other. This is why we say that sets are only partially ordered, whereas the natural numbers are totally ordered (see Definitions 8.5.1, 8.5.3).

**_Remark 3.1.20_** We should also caution that the subset relation $\subseteq$ is _not_ the same as the element relation $\in$. The number $2$ is an element of $\{1,2,3\}$ but not a subset; thus $2 \in \{1,2,3\}$, but $2 \not\subseteq \{1,2,3\}$. Indeed, $2$ is not even a set. Conversely, while $\{2\}$ dis a subset of $\{1,2,3\}$, it is not an element; thus $\{2\} \subseteq \{1,2,3\}$ but $\{2\} \notin \{1,2,3\}$. The point is that the number $2$ and the set $\{2\}$ are distinct objects. It is important to distinguish sets from their elements, as they can have different properties. For instance, it is possible to have an infinitie set consisting of finite numbers (the set $\mathbf{N}$ of natural numbers is one such example), and it is also possible to have a finite set consisting of infinite objects (consider for instance the finite set $\{\mathbf{N}, \mathbf{Z}, \mathbf{Q}, \mathbf{R}\}$, which has four elements, all of which are infinite).

We now give an axiom which easily allows us to create subsets out of larger sets.

> **Axiom 3.6** (_Axiom of specification_). Let $A$ be a set, and for each $x \in A$, let $P(x)$ be a property pertaining to $x$ (i.e., for each $x \in A$, $P(x)$ is either a true statement or a false statement). Then there exists a set, called $\{x \in A: P(x) \text{ is true}\}$ (or simply $\{x \in A: P(x)\}$ for short), whose elements are precisely the elements $x$ in $A$ for which $P(x)$ is true. In other words, for any object $y$,
$$
y \in \{x \in A: P(x) \text{ is true}\} \Leftrightarrow (y \in A \text{ and } P(y) \text{ is true}).
$$

This axiom is also known as the _axiom of seperation_. Note that $\{x \in A: P(x) \text{ is true} \}$ is always a subset of $A$ (why?), though it could be as large as $A$ or as small as the empty set. One can verify that the axiom of substitution works for specification, thus if $A = A'$ then $\{x \in A: P(x)\} = \{x \in A': P(x)\}$ (why?).

!!! note Why $\{x \in A: P(x) \text{ is true} \}$ is always a subset of $A$
    We have to prove that every element of $\{x \in A: P(x) \text{ is true} \}$ is an element of $A$. So let us pick an arbitary element $x$ of $\{x \in A: P(x) \text{ is true} \}$. By Axiom 3.6, we have $x \in A$. Thus $\{x \in A: P(x) \text{ is true} \}$ is always a subset of $A$.

!!! note why if $A = A'$ then $\{x \in A: P(x)\} = \{x \in A': P(x)\}$ ?
    We have to prove that every element of $\{x \in A: P(x)\}$ is an element of $\{x \in A': P(x)\}$, and vice versa. So let us pick an arbitary element $x$ of $\{x \in A: P(x)\}$. By Axiom 3.6, we have ($x \in A$ and $P(x)$ is true). Since $A = A'$, we have ($x \in A'$ and $P(x)$ is true) by the substitution axiom. By Axiom 3.6 again, we have $x \in \{x \in A': P(x)\}$. Thus every element of $\{x \in A: P(x)\}$ is an element of $\{x \in A': P(x)\}$. Similarly, we can prove that every element of $\{x \in A': P(x)\}$ is an element of $\{x \in A: P(x)\}$.

**_Example 3.1.21_** Let $S:=\{1,2,3,4,5\}$. Then the set $\{n \in S: n<4\}$ is the set of those elements $n$ in $S$ for which $n < 4$ is true, i.e., $\{n\in S: n < 4\} = \{1,2,3\}$. Similarly, the set $\{n \in S: n < 7\}$ is the same as $S$ itself, while $\{n \in S: n<1\}$ is the empty set.

We sometimes write $\{x \in A | P(x)\}$ instead of $\{x \in A: P(x)\}$; this is useful when we are using the colon ":" to denote something else, for instance to denote the domain and codomain of a function $f: X \rightarrow Y$. We can also describe $\{x \in A: P(x)\}$ in words as "the set of all $x$ in $A$ such that $P(x)$ is true".

We can use this axiom of specification to define some further operations on sets, namely intersections and difference sets.

> **Definition 3.1.22** (_Intersections_). The _intersection_ $S_1 \cap S_2$ of two sets is defined to be the set
> $$ S_1 \cap S_2 := \{x \in S_1: x \in S_2\}.  $$
> In other words, $S_1 \cap S_2$ consists of all the elements which belong to both $S_1$ and $S_2$. Thus, for all objects $x$,
> $$ x \in S_1 \cap S_2 \Leftrightarrow x \in S_1 \text{ and } x \in S_2.$$

**_Remark 3.1.23_** Note that this definition is well-defined (i.e., it obeys the axiom of substitution, see Sect. A.7) because it is defined in terms of more primitive operations which were already known to obey the axiom fo substitution. Similar remarks apply to future definitions in this chapter and will usually not be mentioned explicitly again.

**_Examples 3.1.24_** We have $\{1,2,4\} \cap \{2, 3, 4\} = \{2, 4\}$, $\{1, 2\} \cap \{3, 4\} = \emptyset$, $\{2,3\} \cup \emptyset = \{2, 3\}$, and $\{2, 3\} \cap \emptyset = \emptyset$.

**_Remark 3.1.25_** By the way, one should be careful with the English word "and": rather confusingly, it can mean either union or intersection, depending on context. For instance, if one talks about a set of "boys and girls", one means _union_ of a set of boys with a set of girls, but if one talks about the set of people who are single and male, then one means the _intersection_ of the set of single people wiht the set of male people. (Can you work out the rule of grammar that determines when "and" means union and when "and" means intersection?) Another problem is that "and" is also used in English to denote addition, thus for instance one could say that "$2$ and $3$ is $5$", while also saying that "the elements of $\{2\}$ and the elements of $\{3\}$ form the set $\{2, 3\}$" and "the elements in $\{2\}$ and $\{3\}$ form the set $\emptyset$". This can certainly get confusing! One reason we resort to mathematical symbols instead of English words such as "and" is that mathematical symbols always have a precise and unambiguous meaning, whereas one must often look very carefully at the contex in order to work out what an English word means.

Two sets $A$, $B$ are said to be _disjoint_ if $A \cap B = \emptyset$. Note that this is not the same concept as being _distinct_, $A \neq B$. For instance, the sets $\{1,2,3\}$ and $\{2,3,4\}$ are distinct (there are elements of one set which are not elements of the other) but not disjoint (because their intersection is non-empty). Meanwhile, the sets $\emptyset$ and $\emptyset$ are disjoint but not distinct (why?)

!!! note Why $\emptyset$ and $\emptyset$ are disjoint but not distinct?
    By the definition, for all objects $x$, $x \in \emptyset \cap \emptyset \Leftrightarrow x \in \emptyset \text{ and } x \in \emptyset$. By Axiom 3.3 $x \in \emptyset$ is false, thus $x \in \emptyset \text{ and } x \in \emptyset$ is false. Therefore, $x \in \emptyset \cap \emptyset$ is false, i.e., $x \notin \emptyset \cap \emptyset$. By the Axiom 3.3 again, $\emptyset \cap \emptyset = \empty$, i.e., $\emptyset$ and $\emptyset$ are disjoint. On the other hand, $\emptyset = \emptyset$, so $\emptyset$ and $\emptyset$ are not distinct.

There is an operation on sets that is somewhat analogous to substraction:

> **Definition 3.1.26** (_Difference sets_). Given two sets $A$ and $B$, we define the set $A - B$ or $A \setminus B$ to be the set $A$ with any elements of $B$ removed:
> $$ A \setminus B := \{x \in A: x \notin B\}; $$
> for instance, $\{1,2,3,4\} \setminus \{2,4,6\} = \{1,3\}$. In many cases $B$ will be a subset of $A$, but not necessarily.

We now give some basic properties of unions, intersections, and difference sets.

**Proposition 3.1.27** (Sets form a boolean algebra). _Let $A$, $B$, $C$ be sets, and let $X$ be a set containing $A$, $B$, $C$ as subsets._
- (a) _(Minimal element) We have $A \cup \emptyset = A$ and $A \cap \emptyset = \emptyset$._
- (b) _(Maximal element) We have $A \cup X = A$ and $A \cap X = A$._
- (c) _(Identity) We have $A \cap A = A$ and $A \cup A = A$._
- (d) _(Commutativity) We have $A \cup B = B \cup A$ and $A \cap B = B \cap A$._
- (e) _(Associativity) We have $(A \cup B) \cup C = A \cup (B \cup C)$ and $(A \cap B) \cap C = A \cap (B \cap C)$._
- (f) _(Distributivity) We have $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ and $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$._
- (g) _(Partition) We have $A \cup (X \setminus A) = X$ and $A \cap (X \setminus A) = \emptyset$._
- (h) _(De Morgan laws) We have $X \setminus (A \cup B) = (X \setminus A) \cap (X \setminus B)$ and $X \setminus (A \cap B) = (X \setminus A) \cup (X \setminus B)$._ 

**_Remark 3.1.28_** The de Morgan laws are named after the logician Augustus De Morgan (1806-1871), who identified them as one of the basic laws of set theory.

**_Proof_** See Exercise 3.1.6.<span style="float: right">□</span>

**_Remark 3.1.29_** The reader may observe a certain symmetry in the above laws between $\cup$ and $\cap$, and between $X$ and $\emptyset$. This is an example of _duality_ -- two distinct properties or objects being dual to each other. In this case, the duality is manifested by the complementation $A \mapsto X \setminus A$; the de Morgan laws assert that this relation converts unions into intersections and vice versa. (It also interchanges $X$  and the empty set.) The above laws are collectively known as the _laws of Boolean algebra_, after the mathematician George Boole (1815-1864), and are also applicable to a number of other objects other than sets; they play a particularly important role in mathematical logic.

We have now accumulated a number of axioms and results about sets, but there are still many things we are not able to do yet. One of the basic things we wish to do with a set is take each of the objects of that set, and somehow transform each such object into a new object; for instance we may wish to start with a set of numbers, say $\{3, 5, 9\}$, and increment each one, creating a new set $\{4,6,10\}$. This is not something we can do directly using only the axioms we already have, so we need a new axiom:

> **Axiom 3.7** (_Replacement_). Let $A$ be a set. For any object $x \in A$, and any object $y$, suppose we have a statement $P(x, y)$ pertaining to $x$ and $y$, such that for each $x \in A$ there is at most one $y$ for which $P(x,y)$ is true. Then there exists a set $\{y: P(x,y) \text{ is true for some } x \in A\}$, such that for any object $z$,
> $$
z \in \{y: P(x,y) \text{ is true for some } x \in A\} \Leftrightarrow P(x, z) \text{ is true for some } x \in A.
$$

**_Example 3.1.30_** Let $A:=\{3,5,9\}$ and let $P(x,y)$ be the statement $y = x++$, i.e., $y$ is the successor of $x$. Observe that for every $x \in A$, there is exactly one $y$ for which $P(x,y)$ is true -- specifically, the successor of $x$. Thus the above axiom asserts that the set $\{y:y=x++ \text{ for some } x \in \{3,5,9\}\}$ exists; in this case, it is clearly the same set as $\{4, 6, 10\}$ (why?)

!!! note Why in this case the set is $\{4, 6, 10\}$?
    Let $B :=\{4, 6, 10\}$ and $C:=\{y: y = x++ \text{ for some } x \in \{3,5,9\}\}$. To prove that in this case the set is \{4,6,10\}, we need to show that every element $z$ of $B$ is an element of $C$, and vice versa. Obviously, for $4 \in B$ and $3 \in A$, we have $4 = 3++$, i.e., $P(3, 4)$ is true, and hence $4 \in C$. Similarly, we can show that $6 \in C$ and $10 \in C$. Therefore $C$ at least contains $4$, $6$ and $10$ as its elements. Suppose that contains any element other than these three elements, say $a$, then at least one of $P(3,a)$, $P(5, a)$ or $P(9,a)$ is true. By Axiom 3.7 again, at least one of $a = 4$ or $a = 6$ or $a = 10$ is true, which leads to a contradiction. Therefore, C only contains $4$, $6$ and $10$, all of which belong to B. Therefore, the set is $\{4, 6, 10\}$.

**_Example 3.1.31_** Let $A = \{3,5,9\}$, and let $P(x,y)$ be the statement $y = 1$. Then again for every $x \in A$, there is exactly one $y$ for which $P(x,y)$ is true -- specifically, the number $1$. In this case $\{y: y=1 \text{ for some } x \in \{3,5,9\} \}$ is just the singleton set $\{1\}$; we have replaced each element $3$, $5$, $9$ of the original set $A$ by the same object, namely $1$. Thus this rather silly example shows that the set obtained by the above axiom can be "smaller" than the original set.

we often abbreviate a set of the form
$$
\{y: y = f(x) \text{ for some } x \in A\}
$$
as $\{f(x): x \in A\}$ or $\{f(x)| x \in A\}$. Thus for instance, if $A = \{3,5,9\}$, then $\{x++: x\in A\}$ is the set $\{4, 6, 10\}$. We can of course combine the axiom of replacement with the axiom of specification, thus for instance we can create sets such as $\{f(x): x \in A; P(x) \text{ is true}\}$ by starting with the set $A$, using the axiom of specification to create $\{x \in A: P(x) \text{ is true}\}$, and then applying the axiom of replacement to create $\{f(x): x \in A; P(x) \text{ is true}\}$. Thus for instance $\{n++: n \in \{3, 5, 9\}; n < 6\} = \{4, 6\}$.<span style="float: right">□</span>

In many of our examples we have implicitly assumed that natural numbers are in fact objects. Let us formalize this as follows.

> **Axiom 3.8** (_Infinity_). Thre exists a set $\mathbf{N}$, whose elements are called natural numbers, as well as an object $0$ in $\mathbf{N}$, and an object $n++$ assigned to every natural number $n \in \mathbf{N}$, such that Peano axioms (Axioms 2.1-2.5) hold.

This is the more formal version of Assumption 2.6. It is called the axiom of infinity because it introduces the most basic example of an infinite set, namely the set of natural numbers $\mathbf{N}$. (We will formalize what finite and infinite mean in Sect. 3.6.) From the axiom of infinity we see what numbers such as $3$, $5$, and $7$ are indeed objects in set theory, and so (from the pair set axiom and pairwise union axiom) we can indeed legitimately construct sets such as $\{3, 5, 9\}$ as we have been doing in our examples.

One has to keep the concept of a set distinct from the elements of that set; for instance, the set $\{n+3, n \in \mathbf{N}, 0 \le n \le 5\}$ is not the same thing as the expression or function $n+3$. We emphasize this with an example:

**_Example 3.1.32_** (Informal) This example requires the notion of subtraction, which has not yet been formally introduced. The following two sets are equal,
$$
\{n+3: n \in \mathbf{N}, 0\le n \le 5\} = \{8-n:n\in \mathbf{N}, 0 \le n \le 5\}, \tag{3.1}
$$
(see below), even though the expressions $n+3$ and $8-n$ are never equal to each other for any natural number $n$. Thus, it is a good idea to remember to use those curly braces $\{\}$ when you talk about sets, lest you accidentally confuse a set with its elements. One reason for this counterintuitive situation is that the letter $n$ is being used in two different ways on the two sides of (3.1). To clarify the situation, let us rewrite the set $\{8-n: n \in \mathbf{N}, 0 \le n \le 5\}$ by replacing the letter $n$ by the letter $m$, thus giving $\{8-m: m \in \mathbf{N}, 0 \le m \le 5\}$. This is exactly the same set as before (why?), so we can rewrite (3.1)
$$
\{n+3: n \in \mathbf{N}, 0\le n \le 5\} = \{8-m:m\in \mathbf{N}, 0 \le m \le 5\}. 
$$
Now it is easy to se (using Axiom 3.2) why this identity is true, every number of the form $n+3$, where $n$ is a natural number between $0$ and $5$, is also of the form $8-m$ where $m:=5-n$ (note that $m$ is therefore also a natural number between $0$ and $5$); conversely, every number of the form $8-m$, where $m$ is a natural number between $0$ and $5$, is also of the form $n+3$, where $n:=5-m$ (note that $n$ is therefore a natural number between $0$ and $5$). Observe how much more confusing the above explanation of (3.1) would have been if we had not changed one of the $n$'s to an $m$ first!

!!! note Why $\{8-n: n \in \mathbf{N}, 0 \le n \le 5\} = \{8-m: m \in \mathbf{N}, 0 \le m \le 5\}$?
    Let $A := \{8-n: n \in \mathbf{N}, 0 \le n \le 5\}$ and $B := \{8-m: m \in \mathbf{N}, 0 \le m \le 5\}$.  For any $x \in A$, there exists $n \in \mathbf{N}$ with $0 \le n \le 5$ such that $x = 8-n$. Let $m = n$, then $m \in \mathbf{N}$ and $0 \le m \le 5$, and $x = 8-m$. Therefore $x \in B$.  Similarly, for any $y \in B$, there exists $m \in \mathbf{N}$ with $0 \le m \le 5$ such that $y = 8-m$. Let $n = m$, then $n \in \mathbf{N}$ and $0 \le n \le 5$, and $y = 8-n$. Therefore $y \in A$.  By Axiom 3.2, $A = B$. <span style="float: right">□</span>

Formally, we can refer to $\mathbf{N}$ as "the set of natural numbers", but we shall often abbreviate this to simply "the natural numbers". Similarly for some otehr sets that we will introduce later in this text; for instance $Z$ will be "the set of integers" but also the "integers", $\mathbf{R}$ will be the "set of real numbers" but also "the real numbers" or even just "the reals", and so forth.

## Exercises

_Exercise 3.1.1_ Let $a$, $b$, $c$, $d$ be objects such that $\{a, b\} = \{c, d\}$. Show that at least one of the two statements "$a=c$ and $b=d$" and "$a=d$ and $b=c$" hold.

!!! success
    _Proof_ It is obvious that $a \neq b$ and by Axiom 3.2 we have $a \in \{c, d\}$ and $b \in \{c, d\}$. By Axiom 3.4, We have ($a = c$ or $a =d$) and ($b = c$ or $b=d$). We now divide into two cases. If $a = c$, then we have $b = d$ since $b = c$ will lead to $a = b$. If $a = d$, then we have $b = c$ since if $b = d$ will lead to $a = b$. Thus at least one of the two statements hold.<span style="float: right">□</span>

_Exercises 3.1.2_ Using only Axiom 3.2, Axiom 3.1, Axiom 3.3, and Axiom 3.4, prove that the sets $\emptyset$, $\{\emptyset\}$, $\{\{\emptyset\}\}$, and $\{\emptyset,\{\emptyset\}\}$ are all distinct (i.e., no two of them are equal to each other).

!!! failure 
    Firstly, we shall prove that $\emptyset$ is distinct from the others. By Axiom 3.3, we have $\emptyset \notin \emptyset$ and $\{\emptyset\} \notin \emptyset$, while we also have $\emptyset \in \{\emptyset\}$, $\emptyset \in \{\emptyset, \{\emptyset\}\}$ and $\{\emptyset\} \in \{\{\emptyset\}\}$ by Axiom 3.4. So We have $\emptyset \neq \{\emptyset\}$, $\emptyset \neq \{\{\emptyset\}\}$ and $\emptyset \neq \{\emptyset,\{\emptyset\}\}$. Secondly, we shall prove that $\{\emptyset\} \neq \{\{\emptyset\}\}$ and $\{\emptyset\} \neq \{\emptyset, \{\emptyset\}\}$. It is obvious that $\{\empty\} \notin \{\emptyset\}$ while $\{\emptyset\} \in \{\{\emptyset\}\}$ and hence we have $\{\emptyset\} \neq \{\{\emptyset\}\}$. Similarly we can prove that $\{\emptyset\} \neq \{\emptyset,\{\emptyset\}\}$. Finally, we shall prove that $\{\{\emptyset\}\} \neq \{\emptyset,\{\emptyset\}\}$. Obviously, we have $\emptyset \notin \{\{\emptyset\}\}$ while $\emptyset \in \{\emptyset,\{\emptyset\}\}$. Therefore we have $\{\{\emptyset\}\} \neq \{\emptyset,\{\emptyset\}\}$.<span style="float: right">□</span>

!!! success
    We first show that the empty set is distinct from all the other sets. By Axiom 3.4, $\emptyset \in \{\emptyset\}$. However, $\emptyset \notin \emptyset$ by Axiom 3.3. Thus not every element of $\{\emptyset\}$ is an element of $\emptyset$, so we conclude that $\emptyset \neq \{\emptyset\}$. Similarly, $\{\emptyset\} \in \{\{\emptyset\}\}$ but $\emptyset \notin \emptyset$, so $\emptyset \neq \{\{\emptyset\}\}$. Also, $\emptyset \in \{\emptyset,\{\emptyset\}\}$ but $\emptyset \notin \emptyset$, so $\emptyset \neq \{\emptyset,\{\emptyset\}\}$. 

    Next we show that $\{\emptyset\}$ and $\{\{\emptyset\}\}$ are distint. By Axiom 3.4, we see that $\emptyset \in \{\emptyset\}$. Also by Axiom 3.4, we see that $y \in \{\{\emptyset\}\}$ iff $y=\{\emptyset\}$. Considering the case $y = \emptyset$, it follows that if we can show that $\emptyset \neq \{\emptyset\}$, this will mean $\emptyset \notin \{\emptyset\}$. But we already showed in the previous paragraph that $\emptyset \neq \{\emptyset\}$. Thus $\emptyset \notin \{\{\emptyset\}\}$, and it follows that not every element of $\{\emptyset\}$ is an element of $\{\{\emptyset\}\}$, so $\{\emptyset\} \neq \{\{\emptyset\}\}$.

    Now we show that $\{\emptyset\}$ and $\{\emptyset,\{\emptyset\}\}$ are distinct. By Axiom 3.4, we see that $\{\emptyset\} \in \{\emptyset,\{\emptyset\}\}$. Also by Axiom 3.4, we see that $\{\emptyset\} \in \{\emptyset\}$ iff $\{\emptyset\} = \emptyset$. But by the first paragraph of this proof, $\emptyset \neq \{\emptyset\}$. Thus $\{\emptyset\} \notin \{\emptyset\}$, which means that we have found an element which is in $\{\emptyset,\{\emptyset\}\}$ but not in $\{\emptyset\}$, so the two sets are distinct by Axiom 3.2.

    Finally we show that $\{\{\emptyset\}\}$ and $\{\emptyset,\{\emptyset\}\}$ are distinct. By Axiom 3.4, we have $\emptyset \in \{\emptyset,\{\emptyset\}\}$. Also by Axiom 3.4, we see that $\emptyset \in \{\{\emptyset\}\}$ iff $\emptyset = \{\emptyset\}$. Since we showed in the first paragraph that $\emptyset \neq \{\emptyset\}$, it follows that $\emptyset \notin \{\emptyset\}$. Thus we have found an element, namely $\emptyset$, which is in $\{\emptyset, \{\emptyset\}\}$ but not in $\{\emptyset\}$, so the two sets are distinct.<span style="float: right">□</span>

_Exercise 3.1.3_ Prove the remaining claims in Lemma 3.1.12.

!!! success
    We first show that $\{a,b\} = \{a\} \cup \{b\}$. By Axiom 3.4, for any object $y$, $y \in \{a, b\}$ iff $y=a$ or $y=b$. We now divide into two cases. Considering the case $y=a$, also by axiom 3.4, $a \in \{a\}$. By Axiom 3.5, we see that $a \in \{a\} \cup \{b\}$. Similarly, for the case $y=b$, we have $b \in \{b\}$ and $b \in \{a\} \cup \{b\}$. On the other hand, By Axiom 3.5, for any object $y$, $y \in \{a\} \cup \{b\}$ iff $y \in \{a\}$ or $y \in \{b\}$. Considering the case $y \in \{a\}$, by Axiom 3.4, we see that $y = a$ and $y \in \{a, b\}$. Similarly, for the case $y \in \{b\}$, we see that $y \in \{a, b\}$. By Axiom 3.2, we conclude that $\{a, b\} = \{a\} \cup \{b\}$.
    
    Next we show that $A \cup B = B \cup A$. By Axiom 3.5, for any object $y$, $y \in A \cup B$ iff $y \in A$ or $y \in B$, and in both cases we see that ($y \in B$ or $y \in A$) is true. So $y \in B \cup A$ by Axiom 3.5. Similarly, we can also show that for any object $y$, $y \in B \cup A$ also leads to $y \in A \cup B$, so we conclude that $A \cup B = B \cup A$ by Axiom 3.2.

    Finally we show that $A \cup A = A \cup \emptyset = \emptyset \cup A = A$. By Axiom 3.5, for any object $y$, $y \in A \cup A$ iff ($y \in A$ or $y \in A$) (i.e. $y \in A$), and hence $A \cup A = A$ by Axiom 3.2. By Axiom 3.5 again, for any object $y$, $y \in A \cup \emptyset$ iff ($y \in A$ or $y \in \emptyset$). By Axiom 3.3 $y \notin \emptyset$, so $(y \in A \text{ or } y \in \emptyset) \Leftrightarrow y \in A$ and hence $y \in A \cup \emptyset \Leftrightarrow y \in A$. Thus we conclude that $A = A \cup \emptyset$ by Axiom 3.2. By the axioms of equality and the commutativity identity proved in the second paragraph, we see that $A \cup A = A \cup \emptyset = \emptyset \cup A = A$.<span style="float: right">□</span>

*Exercise 3.1.4* Prove the remaining claims in Lemma 3.1.17

!!! success
    We first show that $A=B$. To prove that, we need to show that every element of $A$ is an element of $C$ and vice versa. By Definition 3.1.14, we see that every element of $A$ is an element of $B$ since $A \subseteq B$. A similar argument shows that every element of $B$ is an element of $A$. Thus, $A = B$.

    Next we show that $A \subsetneq C$. To prove that, we only need to show that $A \neq C$ while $A \subseteq C$ has been proved previously. By Axiom 3.2, there must be at least one element of B that is not an element of $A$. Suppose $x$ is such an element of $B$, it follows that $x$ is also an element of $C$ because $B \subsetneq C$ by Definition 3.1.14. So we find an element of $C$ that is not an element of A and hence $A \neq C$ by Axiom 3.2.<span style="float: right">□</span>

*Exercise 3.1.5* Let $A$, $B$ be sets. Show that the three statements $A \subseteq B$, $A \cup B = B$, $A \cap B=A$ are logically equivalent.

!!! success
    We first show that $A \subseteq B \Leftrightarrow A \cup B = B$. On one hand, suppose $A \subseteq B$, we need to show that $A \cup B = B$, which means that we need to prove that every element of $A \cup B$ is an element of $B$ and vice versa by Axiom 3.2. By Definition 3.1.14, for any object $x$, $x \in A \Rightarrow x \in B$. By Axiom 3.5, $x \in A \cup B \Leftrightarrow (x \in A \text{ or } x \in B)$. If $x \in A$ then $x \in B$, so we see that every element of $A \cup B$ is an element of $B$. Also by Axiom 3.5, if $x \in B$, then $x \in A \cup B$, which means that every element of $B$ is also an element of $A \cup B$. Therefore, $A \subseteq B \Rightarrow A \cup B = B$. On the other hand, given that $A \cup B = B$, we need to show that $A \subseteq B$. By Axiom 3.5, $x \in A \cup B \Leftrightarrow (x \in A \text{ or } x \in B)$. If $x \in A$, then $x \in A \cup B$, which also implies $A \in B$ by Axiom 3.2. So every element of $A$ is an element of $B$ and hence $A \cup B = B \Rightarrow A \subseteq B$.

    Next we show that $A \subset B \Leftrightarrow A \cap B = A$. On one hand, suppose $A \subseteq B$, we need to prove that $A \cap B = A$, which means that we need to show that every element of $A \cap B$ is an element of $A$ and vice versa. By Definition 3.1.14, for any object $x$, $x \in A \Rightarrow x\in B$, which leads to $x \in A \cap B$ by Definition 3.1.22, so every element of $A$ is an element of $A \cap B$. Meanwhile, $x \in A \cap B$ also implies $x \in A$ by Definition 3.1.14. Thus every element of $A \cup B$ is also an element of $A$.

    Finally, since $A \subseteq B \Leftrightarrow A \cup B = B$ and $A \subset B \Leftrightarrow A \cap B = A$, we can conclude that the three statements are logically equivalent.<span style="float: right">□</span>

*Exercise 3.1.6* Prove Proposition 3.1.27. (Hint: one can use some of these claims to prove others. Some of the claims have also appeared previously in Lemma 3.1.12.)

!!! success
    - (a) We just prove $A \cap \emptyset = \emptyset$ as the other claim was already proved in Lemma 3.1.12. To prove this statement, we have to show that every element of $A \cap \emptyset$ is an element of $\emptyset$ and vice versa. For any object $x$, $x \in \emptyset \Rightarrow x \in A \cap \emptyset$ is vacuously true since the hypothesis is false. On the other hand $x \in A \cap \emptyset \Rightarrow \emptyset$ is also true. This is because $x \in A \cup \emptyset \Leftrightarrow x \in A \text{ and } x \in B$ by Definition 3.1.22, but $x \notin \emptyset$ by Axiom 3.3.  This means that $x \notin A \cup$, so the hypothesis is false and such claim is vacuously true.
    - (b) We already proved this statement in Exercise 3.1.5
    - (c) We first show that $A \cup A = A$. By Axiom 3.2 we need to show that every element of $A$ is an element of $A \cup A$ and and vice versa. For any object $x$, $x \in A$ leads to $x \in A \text{ and } x \in A$ which means that $x \in A \cup A$ by Definition 3.1.22, while $x \in A \cup A$ requires $x \in A \text{ and } x \in A$ (i.e., $x \in A$), so $A \cup A = A$ as desired.  Next we show that $A \cup A = A$. $x \in A \Leftrightarrow x \in A \text{ or } x \in A$, which means $x \in A \Leftrightarrow x \in A \cup A$ by Axiom 3.5. So $A \cup A = A$ as desired.
    - (d) We just prove $A \cap B = B \cap A$ as the other claim was already proved in Lemma 3.1.12. To prove this claim, we need to show that every element of $A \cap B$ is also an element of $B \cap A$ and vice versa. For any object $x$, $x \in A \cap B \Leftrightarrow x\in A \text{ and } x \in B$ by Definition 3.1.22. $x \in A \text{ and } x \in B \Leftrightarrow x \in B \text{ and } x \in A$, while $x\in B \text{ and } x \in A \Leftrightarrow x \in B \cup A$ by Definition 3.1.22 again. So $x \in A \cap B \Leftrightarrow x \in B \cap A$, leading to $A \cap B = B \cap A$.
    - (e) We just prove that $(A \cap B) \cap C = A \cap (B \cap C)$ since the other claim was already proved in Lemma 3.1.12. By Axiom 3.2, for any object $x$, we need prove that $x \in (A \cap B) \cap C$ iff $ x\in A \cap (B \cap C)$. By consecutive applications of Definition 3.1.22, we see that $ x \in (A \cap B) \cap C \Leftrightarrow (x \in A \text{ and } x \in B) \text{ and } x \in C$. It is obvious that $(x \in A \text{ and } x \in B) \text{ and } x \in C \Leftrightarrow x \in A \text{ and } (x \in B \text{ and } x \in C)$, while $x \in A \text{ and } (x \in B \text{ and } x \in C) \Leftrightarrow x \in A \cap (B \cap C)$ by Definition 3.1.22. So $x \in (A \cap B) \cap C$ iff $ x\in A \cap (B \cap C)$ as desired.
    - (f) We first show that $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$. By Axiom 3.2, for any object $x$, we need show that $x \in A \cap (B \cup C) \Leftrightarrow x \in (A \cap B) \cup (A \cap C)$. By Definition 3.1.22, $x \in A \cap (B \cup C) \Leftrightarrow x \in A \text{ and } x \in (B \cup C)$, and by Axiom 3.5 $x \in A \text{ and } x \in (B \cup C) \Leftrightarrow x \in A \text{ and } (x \in B \text{ or } x \in C)$, which is equivalent to $(x \in A \text{ and } x \in B) \text{ or } (x \in A \text{ and } x \in C)$. By consecutive applications of Definition 3.1.22 and Axiom 3.5, we see that $(x \in A \text{ and } x \in B) \text{ or } (x \in A \text{ and } x \in C) \Leftrightarrow x \in A \cap B \text{ or } x \in A \cap C \Leftrightarrow x \in (A \cap B) \cup (A \cap C)$. So $x \in A \cap (B \cup C) \Leftrightarrow x \in (A \cap B) \cup (A \cap C)$ and hence $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ as desired.
    Next we show that $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$. By Axiom 3.2, for any object $x$, we need to show that $x \in A \cup (B \cap C) \Leftrightarrow x \in (A \cup B) \cap (A \cup C)$. By Axiom 3.5, $x \in A \cup (B \cap C) \Leftrightarrow x \in A \text{ or } x \in (B \cap C)$, which is equivalent to $x \in A \text{ or } (x \in B \text{ and } x \in C)$. It is apparent that $x \in A \text{ or } (x \in B \text{ and } x \in C) \Leftrightarrow (x \in A \text{ or } x \in B) \text{ and } (x \in A \text{ or } x \in C)$, and by Axiom 3.5 again $(x \in A \text{ or } x \in B) \text{ and } (x \in A \text{ or } x \in C) \Leftrightarrow (x \in A \cup B) \text{ and } (x \in A \cup C)$. By Definition 3.1.22, $(x \in A \cup B) \text{ and } (x \in A \cup C) \Leftrightarrow x \in (A \cup B) \cap (A \cup C)$. So $x \in A \cup (B \cap C) \Leftrightarrow x \in (A \cup B) \cap (A \cup C)$, and hence $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$.
    - (g) We first show that $A \cup (X \setminus A) = X$. By Axiom 3.2, we need to show that every element $x$ of $A \cup (X \setminus A)$ is an element of $X$ and vice versa. So suppose first $x$ is an element of $A \cup (X \setminus A)$. By Axiom 3.5, this means that at least one of $x \in A$ or $x \in X \setminus A$ is true. We now divide into two cases. If $x \in A$, then $x \in X$ since $A \subseteq X$. If instead $x \in X\setminus A$, then by Definition 3.1.26 $x \in X$. Thus in all cases we see that every element of $A \cup (X \setminus A)$ is an element of $X$. On the other hand, suppose $x$ is an element of $X$. We have two cases, i.e., either $x \in A$ or $x \notin A$. If $x \in A$, then $x \in A \cup (X \setminus A)$ by Axiom 3.5. if $x \notin A$, then $x \in X\setminus A$ by Definition 3.1.26. By Axiom 3.5 $x \in A \cup (X \setminus A)$. Both cases lead to $x \in A \cup (X \setminus A)$, So $A \cup (X \setminus A) = X$.
    Next we show that $A \cap (X \setminus A) = \emptyset$. By Axiom 3.2, we need to show that every element $x$ of $A \cap (X \setminus A)$ is an element of $\emptyset$ and vice versa. So suppose first that $x$ is an element of $A \cap (X\setminus A)$. By Definition 3.1.22, $x \in A \text{ and } \in X \setminus A$. By Definition 3.1.26, $x \in X \setminus A \Leftrightarrow x \in X \text{ and } x \notin A$. Thus $x \in A \text{ and } \in X \setminus A$ is false and hence $x \in A \cap (X \setminus A) \Rightarrow x \in \emptyset$ is vacuously true since the hypothesis is false. Now suppose instead $x \in \emptyset$. By Axiom 3.3, $x \notin \emptyset$, so $x \in \emptyset \Rightarrow x \in A \cap (X \setminus A)$ is vacuously true as the hypothesis is false. Thus $A \cap (X \setminus A) = \emptyset$ as desired.
    - (h) We first show that $X \setminus (A \cup B) = (X \setminus A) \cap (X \setminus B)$. By Axiom 3.2, we need to show that every element of $X \setminus (A \cup B)$ is an element of $(X \setminus A) \cap (X \setminus B)$ and vice versa. Suppose first $x \in X \setminus (A \cup B)$. By consecutive applications of Definition 3.1.26 and Axiom 3.5, this means $x \in X \text{ and } x\notin A \cup B$ and hence $x \in X \text{ and } x \notin A \text{ and } x \notin B$, which also implies that $(x \in X \text{ and } x \notin A) \text{ and } (x \in X \text{ and } x\notin B)$. By consecutive applications of Definition 3.1.26 and Definition 3.1.22, we see that $x \in X \setminus A \text{ and } x\in X \setminus B$ and hence $x \in (X \setminus A) \cap (X \setminus B)$. Now suppose instead, $x \in (X \setminus A) \cap (X \setminus B)$. By consecutive applications of Definition 3.1.26 and Definition 3.1.22, we see that $(x \in X \text{ and } x \notin A) \text{ and } (x \in X \text{ and } x \notin B)$, implying that $x \in X \text{ and } (x \notin A \text{ and } x \notin B)$. Since $x \notin A \text{ and } x \notin B$ iff ($x \in A \text{ or } x \in B$) is false. Then by Axiom 3.5, $x \notin A \cup B$, and combined with $x in X$, we have $x \in X \setminus (A \cup B)$ by Defintion 3.1.26. So $X \setminus (A \cup B) = (X \setminus A) \cap (X \setminus B)$ as desired.
    Next we show that $X \setminus (A \cap B) = (X \setminus A) \cup (X \setminus B)$. By Axiom 3.2 we need to prove that every element of $X \setminus (A \cap B)$ is an element of $(X \setminus A) \cup (X \setminus B)$ and vice versa. Suppose first that $x$ is an element of $X \setminus (A \cap B)$. By Definition 3.1.26, this means that $x \in X$ and $x \notin A \cap B$. The latter statement means that it is not the case that $x \in A \text{ and } x\in B$ by Definition 3.1.22; thus $x \notin A \text{ or } x \notin B$. Now we have both $x \in X \text{ not } x \notin A$ or $x \in X \text{ and } x \notin B$. By consecutive applications of Definition 3.1.26 and Axiom 3.5, we see that $x \in X \setminus A$ or $x \in X \setminus B$, and hence $x \in (X\setminus A) \cup (X \setminus B)$. Now suppose instead $x \in (X \setminus A) \cup (X \setminus B)$. By Axiom 3.5 this means that $x \in (X \setminus A)$ or $x \in (X \setminus B)$. In the first case, we have $x \in X \text{ and } x \notin A$. If $x \in A \cap B$ then $x \in A$ by Definition 3.1.22, which leads to a contradiction, so we must have $x \notin A \cap B$. Thus we have both $x \in X$ and $x \notin A \cup B$, which means $x \in X \setminus (A\cup B)$. in the second case, we can similarly show that $x \in X \setminus (A \cup B)$. So both cases imply $x \in X \setminus (A \cup B)$. Therefore,$X \setminus (A \cap B) = (X \setminus A) \cup (X \setminus B)$ as desired.<span style="float: right">□</span>

*Exercises 3.1.7* Let $A$, $B$, $C$ in sets. Show that $A \cap B \subseteq A$ and $A \cap B \subseteq B$. Furthermore, show that $C \subseteq A$ and $C \subseteq B$ if and only if $C \subseteq A \cap B$. In a similar spirit, show that $A \subseteq A \cup B$ and $B \subseteq A \cup B$, and furthermore that $A \subseteq C$ and $B \subseteq C$ if and only if $A \cup B \subseteq C$.

!!! success
    We first show that $A \cap B \subset A \text{ and } A \cap B \subset B$. To prove the first claim, by Defintion 3.1.14, we need to show that every element of $A \cap B$ is an element of $A$. Suppose that $x$ is an element of $A \cap B$. By Axiom 3.5 this means that $x \in A$ and $x \in B$. So $A \cap B \subseteq A$ as desired. A similar argument shows that every element of $A \cap B$ is an element of $B$, so $A \cap B \subseteq B$ as required.

    Secondly, we show that $C \subseteq A$ and $C \subseteq B$ iff $C \subseteq A \cap B$. On one hand, we need to show that $C \subseteq A \text{ and } C \subseteq B \implies C \subseteq A \cap B$. To prove this statement, by Defintion 3.1.14, we need to show that if every element of $C$ is both an element of $A$ and $C$, then it is also an element of $A \cap B$. Suppose $x$ is an element of $x$, then $x \in A$ and $x \in B$. By Axiom 3.5, we see that $x \in A \cap B$. So $C \subseteq A \text{ and } C \subseteq B \implies C \subseteq A \cap B$. On the other hand, we need to show that $C \subseteq A \cap B \implies C \subseteq A \text{ and } C \subseteq B$. By Definition 3.1.14 and Axiom 3.5, we need prove that if every element of $C$ is both an element of $A$ and $B$, then every element of $C$ is an element of $A$ and $B$. This statement is apparently true. So $C \subseteq A$ and $C \subseteq B$ iff $C \subseteq A \cap B$.

    Thirdly, we show that $A \subseteq A \cup B$ and $B \subseteq A \cup B$. We now prove the first claim. By defintion 3.1.14, we need to show that every element of $A$ is also an element of $A \cup B$. Suppose that $x \in A$, the $x \in A \text{ or } x \in B$ is true. By Axiom 3.5, we see that $x \in A \cup B$. So $A \subseteq A \cup B$ and $B \subseteq A \cup B$ . A similar argument shows that $B \subseteq A \cup B$.

    Finally, we show that $A \subseteq C$ and $B \subseteq C$ if and only if $A \cup B \subseteq C$. On one hand, We show that $A \subseteq C$ and $B \subseteq C \implies A\cup B \subseteq C$. To prove this statement, we need to show that if both every element of $A$ and every element of $B$ is an element of $C$, then every element of $A \cup B$ is an element of $C$. We prove this claim by contradiction. Suppose that $x$ is an element of $A \cup B$ but is not an element of $C$, which means $x \in A \cup B$ and $x \notin C$. By Axiom 3.5, $x \in A \cup B$ means that $x$ is either an element of $A$ or an element of $B$. If $x \in A$, then $A \not \subseteq C$ by Definition 3.1.14. Similarly, if $x \in B$, then $B \not \subseteq C$. Both cases lead to an contradiction and hence $A \cup B \subseteq C$. On the other hand, we show that $A \cup B \subseteq C \implies A \subseteq C$ and $B \subseteq C$. To prove this claim, we need to show that if every element of $A \cup B$ is an element of $C$, then every element of $A$ and every element of $B$ is an element of $C$. We also prove this claim by contradiction. If $A \subseteq C$ and $B \subseteq C$ is false. Then there exists an element of either A or B that is not an element of $C$. Suppose that $x \in A$ but $x \notin C$. By Axiom 3.5, we have $x \in A \cup B$. Together with $x \notin C$, We can conclude that $A \cup B \not \subseteq C$ by Definition 3.1.14. Similarly, $x \in B$ but $x\notin C$ also leads to $A\cup B \not \subseteq C$. So both cases lead to contradiction and hence $A \subseteq C$ and $B \subseteq C$. Therefore, $A \subseteq C$ and $B \subseteq C$ if and only if $A \cup B \subseteq C$ as desired. <span style="float: right">□</span>

*Exercise 3.1.8* Let $A$, $B$ be sets. Prove the *absorption laws* $A \cap (A \cup B) = A$ and $A \cup (A \cap B) = A$

!!! success
    We first show that $A \cap (A \cup B) = A$. By Axiom 3.2, we need to show that every element of $A \cap (A \cup B)$ is an element of $A$ and vice versa. Suppose now $x$ is an element of $A \cap (A \cup B)$. By Definition 3.1.22, $x \in A$. On the other hand, if $x$ is an element of $A$, then $x$ is also an element of $A \cup B$ by Axiom 3.5. Together with $x \in A$, we have $x \in A \cap (A \cup B)$. So $A \cap (A \cup B) = A$ as desired.

    Next we show that $A \cup (A \cap B) = A$. By Axiom 3.2, we need to show that every element of $A \cup (A \cap B)$ is also an element of $A$ and vice versa. Suppose now $x$ is an element of $A \cup (A \cap B)$. By Axiom 3.5, this means $x \in A$ or $x \in A \cap B$. If $x \in A$, then $x$ is an element of $A$, while if $x \in A \cap B$ then $x$ is also an element of $A$ by Definition 3.1.22. Both cases show that $x$ is an element of A. On the other hand, if $x$ is an element of $A$, then $x$ is an element of $A \cup A \cap B$ by Axiom 3.5. So $A \cup (A \cap B) = A$ as desired.<span style="float: right">□</span>

*Exercise 3.1.9* Let $A$, $B$, $X$ be sets such that $A \cup B = X$ and $A \cap B = \emptyset$. Show that $A = X \setminus B$ and $B = X \setminus A$.

!!! success
    We first show that $A = X \setminus B$. By Axiom 3.2, we need to show that every element of $A$ is an element of $X \setminus B$ and vice versa. Suppose now $x \in A$, then by Axiom 3.5 we have $x \in X$ since $A \cup B = X$. If $x$ is also an element of $B$, then $x \in A \cap B$ by Definition 3.1.22. By Axiom 3.3 $x \notin \emptyset$. So $A \cap B \neq \emptyset$ by Axiom 3.2, which leads to a contradiction. So $x\notin B$, and, together with $x \in X$, we have $x \in X\setminus B$ by Definition 3.1.26. On the other hand, if $x \in X \setminus B$, then $x \in X \text{ and } x\notin B$ by Definition 3.1.26. Since $A \cup B = X$, we have $x \in A \cup B$ which means at least one of $x \in A$ or $x \in B$ is true. While $x \notin B$, we see that $x \in A$. So $A = X \setminus B$. A similar argument can show that $B = X \setminus A$.<span style="float: right">□</span>

*Exercise 3.1.10* Let $A$ and $B$ be sets. Show that the three sets $A \setminus B$, $A \cap B$, and $B \setminus A$ are disjoint, and that theire union is $A \cup B$.

!!! success
    We first show that $(A \setminus B) \cap (A \cap B) = \emptyset$ and $(B \setminus A) \cap (A \cap B)=\emptyset$. By Axiom 3.2 we need to show that every element of $(A \setminus B) \cap (A \cup B)$ is an element of $\emptyset$ and vice versa. Suppose now $x$ is an element of $(A \setminus B) \cap (A \cap B)$. By Definition 3.1.22, $x \in A \setminus B$ and $x \in A \cap B$. By Definition 3.1.26, $x \in A \text{ and } x \notin B$, while by Definition 3.1.22 $x \in A \text{ and } x \in B$. Both requirements cannot be satisfied simultaneously, so $x \in (A \setminus B) \cap (A \cap B)$ is false. Thus $x \in (A \setminus B) \cap (A \cap B) \implies x \in \emptyset$ since the hypothesis is false. On the other hand, $x \in \emptyset \implies x\in (A \setminus B) \cap (A \cap B)$ since the hypothesis is also false by Axiom 3.3. Therefore, $(A \setminus B) \cap (A \cap B) = \emptyset$. A similar argument can show that $(B \setminus A) \cap (A \cap B) = \emptyset$. So $A \setminus B$ and $A \cap B$ are disjoint and $B \setminus A$ and $A \cap B$ are disjoint too.

    Next we show that $(A \setminus B) \cap (B \setminus A) = \emptyset$. By Axiom 3.2, we need to show that every element in $(A \setminus B) \cap (B \setminus A)$ is an element of $\emptyset$ and vice versa. Suppose now $x \in (A \setminus B) \cap (B \setminus A)$. By Definition 3.1.22, we have $x \in A \setminus B$ and $x \in B \setminus A$. By Definition 3.1.26, we further see that $(x \in A \text{ and } x \notin B)$ and $(x \in B \text{ and } x\notin A)$ must be met at the same time, which is impossible. So $(A \setminus B) \cap (B \setminus A) \implies x \in \emptyset$ since the hypothesis is false. In a similar spirit, $x \in \emptyset \implies x \in (A \setminus B) \cap (B \setminus A)$ since $x \in \emptyset$ is false by Axiom 3.3. So $A \setminus B$ and $B \setminus A$ are disjoint.

    Finally we show that $(A \setminus B) \cup (A \cap B) \cup (B \setminus A) = A \cup B$. By Axiom 3.2 we need to show that every element of $(A \setminus B) \cup (A \cap B) \cup (B \setminus A)$ is an element of $A \cup B$ and vice versa. Suppose $x$ is an element of $(A \setminus B) \cup (A \cap B) \cup (B \setminus A)$. By consecutive applications of Axiom 3.5, we have $x \in A \setminus B$ or $x \in A \cap B$ or $x \in B \setminus A$. If $x \in A \setminus B$ then $x \in A \cup B$ by Axiom 3.5 since $x \in A \setminus B \implies x \in A$ by Definition 3.1.26. A similar argument shows that $x \in B \setminus A \implies x \in A \cup B$. If $x \in A \cap B$, then by Definition 3.1.22 $x \in A$ and $x \in B$, and hence $x \in A \cup B$ by Axiom 3.5. All the three cases show that $x$ is an element of $A \cup B$. On the other hand, if $x \in A \cup B$, then at least one of $x \in A$ or $x \in B$ is true. If $x \in A \text{ and } x \notin B$, then $x \in A \setminus B$ by Definition 3.1.26 and hence $x \in (A \setminus B) \cup (A \cap B) \cup (B \setminus A)$ by consecutive applications of Axiom 3.5. Similarly, if $x \in B \text{ and } x \notin A$, then $x \in (A \setminus B) \cup (A \cap B) \cup (B \setminus A)$. Finally if $x \in A and x \in B$, then $x \in A\cap B$ by Definition 3.1.22 and hence $x \in (A \setminus B) \cup (A \cap B) \cup (B \setminus A)$ by consecutive applications of Definition 3.1.26. All three cases show that $x$ is an element of $(A \setminus B) \cup (A \cap B) \cup (B \setminus A)$. Thus $(A \setminus B) \cup (A \cap B) \cup (B \setminus A) = A \cup B$ as desired.<span style="float: right">□</span>

*Exercise 3.1.11* Show that the axiom of replacement implies the axiom of specification.

!!! success
    Let $A$ be a set, and let $P(x)$ be a statement pertaining to objects $x \in A$. To show that the axiom of replacement implies the axiom of specification, we will construct the set $\{x\in A: P(x) \text{ is true}\}$ using just the axiom of replacement. Let $Q(x,y)$ be the statement "$y=x$ and $P(x)$". To use the axiom of replacement, we must verify that for each $x \in A$, the statement $Q(x, y)$ is true for at most one $y$ satisfying the statement. But for each $x \in A$, there is exactly one $y$ such that $y = x$, so it follows that for the full statement of $Q(x,y)$ there is at most one $y$ satisfying the statement. The axiom of replacement thus allows us to construct the set $\{y: y=x \text{ and } P(x) \text{ for some } x\in A\}$. We claim that this is the same set as $\{x\in A: P(x) \text{ is true}\}$. We show the inclusion both ways:

    - Suppose $z \in \{x\in A: P(x) \text{ is true}\}$. Thus $z \in A$ and $P(z)$ is true. But this means that $z = x$ and $P(x)$ for some $x \in A$; specifically，there is $z \in A$ such that $z = z$ and $P(z)$. Thus $z \in \{y: y=x \text{ and } P(x) \text{ for some } x \in A\}$.
    - Suppose $z \in \text \{y: y=x \text{ and } P(x) \text{ for some } x\in A \}$. This means that for some $x \in A$, we have $z = x$ and $P(x)$. Since $z = x$ this means We have P(z) and $z \in A$ as well. Thus $z \in \{x\in A: P(x) \text{ is true}\}$.

    since both directions of the inclusion hold, this means that the two sets are equal.
    
*Exercise 3.1.12* Suppose that $A$, $B$, $A'$, $B'$ are sets such that $A' \subseteq A$ and $B' \subseteq B$.

- (i) Show that $A' \cup B' \subseteq A \cup B$ and $A' \cap B' \subseteq A \cap B$.

- (ii) Give a counterexample to show that the statement $A' \setminus B' \subseteq A \setminus B$ is false. Can you find a modification of this statement involving the set difference operation $\setminus$ which is true given the hypothesis? Justify your answer.

!!! success
    - (i) We first show that $A' \cup B' \subseteq A \cup B$. By Definition 3.1.14, we need to prove that every element of $A' \cup B'$ is an element of $A \cup B$. Suppose now $x$ is an element of $A' \cup B'$. By Axiom 3.5 we have $x \in A'$ or $x \in B'$. If $x \in A'$, then $x \in A$ by Definition 3.1.14, and hence $x \in A \cup B$ by Axiom 3.5. A similar argument shows that if $x \in B'$ then $x \in A \cup B$. Both cases show that every element of $A' \cup B'$ is an element of $A \cup B$.
    Next we show that $A' \cap B' \subseteq A \cap B$. By Definition 3.1.14, we need to prove that every element of $A' \cap B'$ is an element of $A \cap B$. Suppose now $x$ is an element of $A' \cap B'$. By Definition 3.1.22 we have $x \in A'$ and $x \in B'$. By Definition 3.1.14 $x \in A' \implies x \in A$ and $x \in B' \implies x\in B$, so $x \in A$ and $x \in B$, meaning that $x \in A \cap B$ by Definition 3.1.22.

    - (ii) A counterexample is that $A'=A=\{1, 2, 3, 4\}$, $B' = \{1, 2\}$, $B = \{1, 2, 3\}$. Then $A' \setminus B' = \{3, 4\}$ while $A \setminus B = \{ 4\}$. Obviously $A' \subseteq A$ and $B' \subset B$ but $A' \setminus B' \not \subseteq A \setminus B$.

*Exercise 3.1.13* Euclid famously defined a point to be "that which has no part". This exercise should be reminiscent of that definition. Define a *proper subset* of a set $A$ to be a subset $B$ of $A$ with $B \neq A$. Let $A$ be a non-empty set. Show that $A$ does not have any non-empty proper subsets if and only if $A$ is of the form $A = \{x\}$ for some object $x$.

!!! success
We first show that if $B = \emptyset$ for any $B \subsetneq A$, then $A$ is a singleton. We prove this statement by contradiction. If $A$ is not an singleton, then either there is no element in $A$ or there are at least two elements in $A$. In the former case, $A = \emptyset$ by Axiom 3.3, so $A = B$ and hence $B$ is not a proper subset of $A$. In the second case, suppose $a$ and $b$ are two distinct elements of $A$. By Axiom 3.4, $\{b\}$ is an set whose only element is $b$. It is obvious that every the element of $\{b\}$, namely $b$, is an element of $A$, so $\{b\} \subseteq A$. However $a \in A$ but $a \notin \{b\}$ by Axiom 3.4, so $\{b\} \neq A$. Thus we find a set $\{b\}$ that is a proper subset of $A$ but is not an emptyset, leading to a contradiction. Therefore, $A$ must be a singleton.

Next we show that if $A$ is an singleton, then an arbitrary proper subset $B$ of $A$ is an emptyset. We prove this statement by contradiction. Suppose $A = \{x\}$. If $B \neq \emptyset$, then there exists an object $y$ such that $y \in B$ by Lemma 3.1.5. By Definition 3.1.14, $y \in A$, and by Axiom 3.4 we have $y = x$. If there exists any object $z$ such that $z \neq y$ and $z \in B$, then $z \in A$ since $B \subsetneq A$. By Axiom 3.4 again we see that $z = x$. But we already showed $x = y$, so $z = y$, leading to a contradiction. Thus $x$ is the only element of $B$ and hence $B = A = \{x\}$. However $B \neq A$ since $B \subsetneq A$. Therefore $B = \emptyset$.<span style="float: right">□</span>



## 3.2 Russell's Paradox (Optional)

## 3.3 Functions

In order to do analysis, it is not particularly useful to just have the notion of a set; we also need the notion of a _function_ from one set to another. Informally, a function $f: X \rightarrow Y$ from one set $X$ to another set $Y$ is an operation which assigns to each element (or "input") $x$ in $X$, a single element (or "output") $f(x)$ in $Y$; we have already used this informal concept in the previous chapter when we discussed the natural numbers. The formal definition is as follows.

> **Definition 3.3.1** (*Functions*) Let $X$, $Y$ be sets, and let $P(x, y)$ be a property pertaining to an object $x \in X$ and an object $y \in Y$, such that for every $x \in X$, there is exactly one $y \in Y$ for which $P(x, y)$ is true (this is sometimes known as the *vertical line test*). Then we define the *function* $f: X \rightarrow Y$ *defined by $P$ on the domain $X$ and codomain[^2]* to be the object which, given any input $x \in X$, assigns an output $f(x) \in Y$, defined to be the unique object $f(x) \in Y$ for which $P(x,f(x))$ is true. Thus, for any $x \in X$ and $y \in Y$,
> $$
y = f(x) \Leftrightarrow P(x,y) \text{ is true}.
$$

Functions are also referred to as *maps* or *transformations*, depending on the context. They are also sometimes called *morphisms*, although to be mare precise, a morphism refers to a more general class of object, which may or may not correspond to actual functions, depending on the context.

**_Remark 3.3.2_** Implicit in the above definition is an assumption that whenever one is given two sets $X$, $Y$ and a property $P$ obeying the vertical line test, one can form a function object $f$. Strictly speaking, the assumption of the existence of such a function object $f$ should be stated as an explicit axiom. However, we will not do so here, as it turns out to be redundant. (More precisely, in view of Exercise 3.5.10, it is always possible to encode a function $f$ as an ordered triple $(X, Y, \{(x, f(x)): x\in X\})$ consisting of the domain, codomain and graph of the function, which gives a way to build functions as objects using the operations provided by the preceding axioms of set theory.) Also implicit in the above definition is the understanding that every function $f$ is automatically associated with a domain $X$, a codomain $Y$, and a defining property $P$.

**_Example 3.3.3_** Let $X = \mathbf{N}$, $Y = \mathbf{N}$, and let $P(x,y)$ be the property that $y = x++$. Then for each $x \in \mathbf{N}$ there is exactly one $y \in \mathbf{N}$ for which $P(x, y)$ is true, namely $y = x++$. Thus we can define a function $f: \mathbf{N} \to \mathbf{N}$ associated to this property, so that $f(x) = x++$ for all $x$; this is the *increment* function on $\mathbf{N}$, which takes a natural number as input and returns its increment as output. Thus for instance $f(4)=5$, $f(2n+3) = 2n + 4$ and so forth. One might also hope to define a *decrement* function $g: \mathbf{N} \to \mathbf{N}$ associated to the property $P(x, y)$ defined by $y++ = x$, i.e., $g(x)$ would be the number whose increment is $x$. Unfortunately this does not define a function, because when $x=0$ there is no natural number $y$ whose increment is equal to $x$ (Axiom 2.3). On the other hand, we can legitimately define a decrement function $h: \mathbf{N}\setminus\{0\} \to \mathbf{N}$ associated to the property $P(x, y)$ defined by $y++=x$, because when $x \in \mathbf{N} \setminus \{0\}$S there is indeed exactly one natural number $y$ such that $y++=x$, thanks to $Lemma 2.2.10$. Thus for instance $h(4)=4$ and $h(2n+3) = 2n+2$, but $h(0)$ is undefined since $0$ is not in the domain $\mathbf{N} \setminus \{0\}$.

**_Example 3.3.4_** (Informal) This example requires the real numbers $\mathbf{R}$, which we will define in Chap. 5. One could try to define a square root function $\sqrt{}: \mathbf{R} \to \mathbf{R}$ by associating it to the property $P(x, y)$ defined by $y^2=x$, i.e.,A we would want $\sqrt{x}$ to be the number $y$ such that $y^2 = x$. Unfortunately there are two problems which prohibit this definition from actually creating a function. The first is that there exist real numbers $x$ for which $P(x, y)$ is never true, for instance if $x = -1$ then there is no real number $y$ such that $y^2=x$. This problem however can be solved by restricting the domain from $\mathbf{R}$ to the right half-line $[0,+\infty)$, it is possible for there to be more than one $y$ in the codomain $\mathbf{R}$ for which $y^2=x$, for instance if $x=4$ then both $y=2$ and $y=-2$ obey the property $P(x, y)$, i.e., both $+2$ and $-2$ are square roots of $4$. This problem can however be solved by restricting the codomain of $\mathbf{R}$ to $[0,+\infty)$. Once one does this, then one can correctly define a square root function $\sqrt{}: [0,+\infty) \to [0,+\infty)$ using the relation $y^2=x$; thus $\sqrt{x}$ is the unique number $y \in [0,+\infty)$ such that $y^2=x$.

One common way to define a function is simply to specify its domain, its codomain, and how one generates the output $f(x)$ from each input; this is known as an *explicit* definition of a function. For instance, the function $f$ in Example 3.3.3 could be defined explicitly by saying that $f$ has domain and codomain equal $\mathbf{N}$, and $f(x):=x++$ for all $x \in \mathbf{N}$. In other cases we only define a function $f$ by specifying what property $P(x,y)$ links the input $x$ with the output $f(x)$; this is an *implicit* definition of a function. For instance, the square root function $\sqrt{x}$ in Example 3.3.4 was defined implicitly by the relation $(\sqrt{x}^2 = x)$. Note that an implicit defnition is only valid if we know that for every input there is exactly one output which obeys the implicit relation. In many cases we omit specifying the domain and codomain of a function for brevity, and thus for instance we could refer to the function $f$ in Example 3.3.3 as "the function $f(x):=x++$,", "the function $x \mapsto x++$", "the function $x++$", or even the extremely abbreviated $++$. However, too much of this abbreviation can be dangerous; sometimes it is important to know what the domain and codomain if the function is.

We observe that functions obey the axiom of substitution: if $x = x'$, then $f(x) = f(x')$ (why?). In other words, equal inputs imply equal outputs. On the other hand, unequal inputs do not necessarily ensure unequal outputs, as the following example show:

!!! note Why $f(x) = f(x')$ if $x = x'$?


**_Example 3.3.5_** Let $X = \mathbf{N}$, $Y = \mathbf{N}$, and let $P(x, y)$ be the property that $y = 7$. Then certainly for every $x \in \mathbf{N}$ there is exactly one $y$ for which $P(x,y )$ is true, namely the number $7$. Thus we can create a function $fL \mathbf{N} \to \mathbf{N}$ associated to this property; it is simply the *constant function* which assigns the output of $f(x)=7$ to each input $x \in \mathbf{N}$. Thus it is certainly possible for different inputs to generate the same output.

**_Remark 3.3.6_** We are now using parentheses $()$ to denote several different things in mathematics; on one hand, we are using them to clarify the order of operations (compare for instance $2 + (3 \times 4)= 14$ with $(2 + 3) \times 4 = 20$), but on the other hand we also use parentheses to enclose the argument $x$ of a function $f(x)$ or of a property such as $P(x)$. However, the two usages of parentheses usually are unambiguous from context. For instance, if $a$ is a number, then $a(b+c)$ denotes the expression $a \times (b + c)$, whereas if $f$ is a function, then $f(b + c)$ denotes the output of $f$ when the $input$ is $b+c$. Sometimes the argument of a function is denoted by subscripting instead of parentheses; for instance, a sequence of natural numbers $a_0, a_1, a_2, a_3, ...$ is, strictly speaking, a function from $\mathbf{N}$ to $\mathbf{N}$, but is denoted by $n \mapsto a_n$ rather than $n \mapsto a(n)$.

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

**_Example 3.3.14_** Let $f: \mathbf{N} \to \mathbf{N}$ be the function $f(n):=2n$, and let $g: \mathbf{N} \to \mathbf{N}$ be the function $g(n) = n + 3$. Then $g \circ f$ the function
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

> **_Definition 3.3.20_** (*Onto functions*). A function $f$ is *onto* (or *surjective*) if every element in Y comes from applying $f$ to some element $X$:
> $$
\text{For every } y \in Y, \text{ there exists } x \in X \text{ such that } f(x) =y.
$$

**_Example 3.3.21_** (Informal) The function $f: \mathbf{Z} \to \mathbf{Z}$ defined by $f(n):=n^2$ is not onto because the negative numbers are not in the image of $f$. However, if we restrict the codomain $Z$ to the set $A:=\{n^2: n\in \mathbf{Z}\}$ of square numbers, then the function $g: \mathbf{Z} \to A$ defined by $g(n):=n^2$ is now onto. Thus the notion of an onto function depends not just on what the function does, but also what its range is.

**_Remark 3.3.22_** The concepts of injectivity and surjectivity are in many ways dual to each other; see Exercises 3.3.2, 3.3.4, 3.3.5 for some evidence of this.

> **_Definition 3.3.23_** (*Bijective functions*). Functions $f: X \to Y$ which are both one-to-one and onto are also called *bijective* or *invertible*.

**_Example 3.3.24_** Let $f: \{1, 2, 4\} \to \{3, 4\}$ be the function $f(0):=3$, $f(1):=3$, $f(2):=4$. This function is not bijective because if we set $y=3$, then there is more than one $x$ in $\{1, 2, 4\}$ such that $f(x) = y$ (this is a failure of injectivity). Now let $g: \{0,1\} \to \{2, 3, 4\}$ be the function $g(0):=2, g(1):=3$; then $g$ is not bijective because if we set $y=4$, then there is no $x$ for which $g(x)=y$ (this is a failure of surjectivity). Now let $h: \{0, 1, 2\} \to \{3, 4, 5\}$ be the function $h(0):=3$, $h(1):=r$, $h(2):=5$. Then $h$ is bijective, because each of the elements $3, 4, 5$ comes from exactly one element from $0,1,2$.

**_Example 3.3.25_** The function $f: \mathbf{N} \to \mathbf{N} \setminus \{0\}$ defined by $f(n):= n++$ is a bijection (in fact, this fact is simply restating Lemma 2.2.10). On the other hand, the function $g: \mathbf{N} \to \mathbf{N}$ defined by the same defintion $g(n):=n++$ is not a bijection. thus the notion of a bijective function depends not just on what the function does, but also what its domain and codomain are.

**_Remark 3.3.26_** If a function $x \mapsto f(x)$ is bijective, then we sometimes call $f$ a *perfect matching* or *one-to-one correspondence* (not to be confused with the notion of a one-to-one function) and denote the action of $f$ using the notion $x \leftrightarrow f(x)$ instead of $x \mapsto f(x)$. Thus for instance the function $h$ in the above example is the one-to-one correspondence $0 \leftrightarrow 3$, $1 \Leftrightarrow 4$, $2 \leftrightarrow 5$.

**_Remark 3.3.27_** A common error is to say that a function $f: X \to Y$ is bijective iff "for every $x$ in $X$, there is exactly one $y$ in $Y$ such that $y = f(x)$". This is not what it means for $f$ to be bijective; rather, this is merely stating what it means for $f$ to be a *function*. A function cannot map one element to two different elements, for instance one cannot have a function $f$ for which $f(0) = 1$ and also $f(0) = 2$. The functions $f$, $g$ given in Example $3.3.25$ are not bijective, but they are still functions, since each input will gives exactly one output.

If $f$ is bijective, then for every $y \in Y$, there is exactly one $x$ such that $f(x) = y$ (there is at least one because of surjectivity, and at most one because of injectivity). This value of $x$ is denoted by $f^{-1}(y)$; thus $f^{-1}$ is a function from $Y$ to $X$. We call $f^{-1}$ the *inverse* of f.





[^2]: In some texts the codmain is referred to as the *range*; however we will use the term range to refer instead to the image $f(X)$ of the domain, defined after Definition 3.4.1. 
[^3]: In Chap. 8 of *Analysis II*, we shall introduce da weaker notion of equality, that of two functions being *equal almost everywhere*.