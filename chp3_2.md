## 3.2 Russell's Paradox (Optional)

Many of the axioms introduced in the previous section have a similar flavor: they allow us to form a set consisting of all the elements which have a certain property. These axioms are plausible, but one might think that they could be unified, for instance by introducing the following axiom:

> **Axiom 3.9** (*Universal specification*) (Dangerous!) Suppose for every object $x$ we have a property $P(x)$ pertaining to $x$ (so that for every $x$, $P(x)$ is either a true statement or a false statement). Then there exists a set $\{x: P(x) \text{ is true}\}$ such that for every object $y$,
> $$ y \in \{x: P(x) \text{ is true}\} \Longleftrightarrow P(y) \text{ is true.}$$

This axioms is also known as the *axiom of comprehension*. It asserts that every property corresponds to a set; if we assumed that axiom, we could talk about the set of all blue objects, the set of all natural numbers, the set of all sets, and so forth. This axiom also implies most of the axioms in the previous section (Excercise 3.2.1). Unfortunately, this axiom cannot be introduced into set theory, because it creates a logical contradiction known as *Russell's paradox*, discovered by the philosopher and logician Bertrand Russell (1872-1970) in 1901. The paradox runs as follows. Let $P(x)$ be the statement
$$
P(x) \Longleftrightarrow "x \text{ is a set, and } x \notin x";
$$
i.e., $P(x)$ is true only when $x$ is a set which does not contain itself. For instance, $P(\{2,3,4\})$ is true, since the set $\{2,3,4\}$ is not one of the three elements $2,3,4$ of $\{2,3,4\}$. On the other hand, if we let $S$ be the set of all sets (which we could know to exist from the axiom of universal specification), then since $S$ itself is a set, it is an element of $S$, and so $P(S)$ is false. Now use the axiom of universal specification to create the set
$$
\Omega:=\{x:P(x) \text{ is true}\} = \{x: x \text{ is a set and } x \notin x\},
$$
i.e., the set of all sets which do not contain themeselves. Now ask the question: does $\Omega$ contain itself, i.e., is $\Omega \in \Omega$? If $\Omega$ did contain itself, then by the definition of $\Omega$ this means that $P(\Omega)$ is true, i.e., $\Omega$ is a set and $\Omega \notin \Omega$. On the other hand, if $\Omega$ did not contain itself, then by the defnition of $P$ $P(\Omega)$ would be true, and hence by the definition of $\Omega$ we have $\Omega \in \Omega$. Thus in either case we have both $\Omega \in \Omega$ and $\Omega \notin \Omega$, which is absurd.

The problem with the above axiom is that it creates sets which are far too "large" — for instance, we can use that axiom to talk about the set of all objects (a so-called universal set). Since sets are themselves objects (Axiom 3.1), this means that sets are allowed to contain themselves, which is a somewhat silly state of affairs. One way to informally resolve this issue is to think of objects as being arranged in a hierarchy. At the bottom of the hierarchy are the *primitive objects* — the objects that are not sets[^1], such as the natural number $37$. Then on the next rung of the hierarchy there are sets whose elements consist only of primitive objects, such as $\{3,4,7\}$ or the empty set $\emptyset$; let's cll these "primitive sets" for now. Then there are sets whose elements consist only of primitive objects and primitive sets, such as $\{3,4,7,\{3,4,7\}\}$. Then we can form sets out of these objects, and so forth. The point is that at each stage of the hierarchy we only see sets whose elements consist of objects at lower stages of the hierarchy, and so at not stage do we ever construct a set which contains itself.

To actually formalize the above intuition of a hierarchy of objects is actually rather complicated, and we will not do so here. Insdead, we shall simply postulate an axiom which ensures that absurdities such as Russell's paradox do not occur.

> **Axiom 3.10** (*Regularity*) If $A$ is non-empty set, then there is at least one element $x$ of $A$ which is either not a set, or is  disjoint from $A$.

The point of this axiom (which is also known as the *axiom of foundation*) is that it is asserting that at least one of the elements of $A$ is so low on the hierarchy of objects that it does not contain any of the other elements of $A$. For instance, if $A=\{\{3,4\}, \{3,4,\{3,4\}\}\}$, then the element $\{3,4\} \in A$ does not contain any of the elements of $A$ (neither $3$ nor $4$ lies in $A$), although the element $\{3,4,\{3,4\}\}$, being somewhat higher in the hierarchy, does contain an element of $A$, namely $\{3,4\}$. One particular consequence of this axiom is that sets are no longer allowered to contain themselves (Exercise 3.2.2).

One can legitimately ask whether we really need this axiom in our set theory, as it is certainly less intuitive than our other axioms. For the purposes of doing analysis, it turns out in fact that this axiom is never needed; all the sets we consisder in analysis are typically very low on the hierarchy of objects, or at worst sets of sets of sets of primitive objects. However it is necessary to include this axiom in order to perform more advanced set theory, and so we included this axiom in the text (but in tan optional section) for sake of completeness.

## Exercises
*Exercise 3.2.1* Show that the universal specification axiom, Axiom 3.9, if assumed to be true, would imply Axioms 3.3, 3.4, 3.5, 3.6, and 3.7. (If we assume that all natural numbers are objects, we also obtain Axiom 3.8). Thus, this axiom, if permitted, would satisfy the foundations of set theory tremendously (and can be viewed as one basis for an intuitive model of set theory known as "naive set theory). Unfortunately, as we have seen, Axiom 3.9 is "too good to be true"!

!!! Note
    1. Axiom 3.3
        - Let $P(x)$ be the statement $$
            P(x) \Longleftrightarrow 
        $$

[^1]: In pure set theory, there will be no primitive objects, but there will be one primitive set $\emptyset$ on the next rung of the hierarchy.