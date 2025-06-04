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
> $$ \text{For any object } x, x \in A \Rightarrow x \in B. $$
> We say that $A$ is a proper _subset_ of $B$, denoted $A \subsetneq B$, if $A \subseteq B$ and $A \neq B$.

**_Remark 3.1.15_** Because these definitions involve only the notions of equality and the "is an element of" relation, both of which already obey the axiom of substitution, the notion of subset also automatically obeys the axiom of substitution. Thus for instance if $A \subseteq B$ and $A = A'$, then $A' \subseteq B$\dots

**_Examples 3.1.16_** We have $\{1, 2, 4\} \subseteq \{1,2,3,4,5\}$, because every element of $\{1,2,4\}$ is also an element of $\{1,2,3,4,5\}$. In fact we also have $\{1,2,4\} \subsetneq \{1,2,3,4,5\}$, since the two sets $\{1,2,4\}$ and $\{1,2,3,4,5\}$ are not equal. Given any set $A$, we always have $A \subseteq A$ (why?) and $\emptyset \subseteq A$ (why?).

!!! note Why $A \subseteq A$ and $\emptyset \subseteq A$?
    (1) By the reflexive axiom of equalitiy, we have $A = A$. By Axiom 3.2, for any object $x$, $x \in A \Leftrightarrow x \in A$. Thus by the definition of subsets, we have $A \subseteq A$.

    (2) We need to show that for any object $x$, $x \in \emptyset \Rightarrow x \in A$. This statement is vacuously true since the hypothesis is false by Axiom 3.3.

The notion of subset in set theory is similar to the notion of "less than or equal to" for numbers, as the following proposition demonstrates (for a more precise statement, see Definition 8.5.1):

**Proposition 3.1.17** (Sets are partially ordered by set inclusion). _Let $A$, $B$, $C$ be sets. If $A \subseteq B$ and $B \subseteq C$ then $A \subseteq C$. If $A \subseteq B$ and $B \subseteq A$, then $A = B$. Finally, if $A \subsetneq B$ and $B \subsetneq C$ then $A \subsetneq C$_.

**_Proof_** We shall just prove the first claim. Supppose that $A \subseteq B$ and $B \subseteq C$. To prove that $A \subseteq C$, we have to provce that every element of $A$ is an element of $C$. So, let us pick an arbitary element $x$ of $A$. Then, since $A \subseteq B$, $x$ must then be an element of $B$. But then since $B \subseteq C$, $x$ is an element of $C$. Thus every element of $A$ is indeed an element of $C$, as claimed.<span style="float: right">□</span>

**_Remark 3.1.18_** The subset relation and the union operation are related to each other: seed for instance Exercice 3.1.7.

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
    Let $B :=\{4, 6, 10\}$ and $C:=\{y: y = x++ \text{ for some } x \in \{3,5,9\}\}$. To prove that in this case the set is \{4,6,10\}, we need to show that every element $z$ of $B$ is an element of $C$, and vice versa. Obviously, for $4 \in B$ and $3 \in A$, we have $4 = 3++$, i.e., $P(3, 4)$ is true, and hence $4 \in C\} $. Similarly, we can show that $6 \in C$ and $10 \in C$. Therefore $C$ at least contains $4$, $6$ and $10$ as its elements. Suppose that contains any element other than these three elements, say $a$, then at least one of $P(3,a)$, $P(5, a)$ or $P(9,a)$ is true. By Axiom 3.7 again, at least one of $a = 4$ or $a = 6$ or $a = 10$ is true, which leads to a contradiction. Therefore, C only contains $4$, $6$ and $10$, all of which belong to B. Therefore, the set is $\{4, 6, 10\}$.

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

Formally, we can refer to $\mathbf{N}$ as "the set of naturall numbers", but we shall often abbreviate this to simply "the natural numbers". Similarly for some otehr sets that we will introduce later in this text; for instance $Z$ will be "the set of integers" but also the "integers", $\mathbf{R}$ will be the "set of real numbers" but also "the real numbers" or even just "the reals", and so forth.

## Exercises

_Exercise 3.1.1_ Let $a$, $b$, $c$, $d$ be objects such that $\{a, b\} = \{c, d\}$. Show that at least one of the two statements "$a=c$ and $b=d$" and "$a=d$ and $b=c$" hold.