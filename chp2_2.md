## Addition

The natural number system is very bare right now: we have only one operation—incrementation—and a handful axioms. But now we can build up more complex operations, such as addition.

The way it works is the following. To add three to five should be the same as incrementing five three times—this is one increment more than adding two to five, which is one increment more than adding one to five, which is one increment more than adding zero to five, which should just give five. So we give a recursive definition for addition as follows.

> **Definition 2.2.1** (*Addition of natural numbers*). Let $m$ be a natural number. To add zero to $m$, we define $0+m:=m$. Now suppose inductively that we have defined how to add $n$ to $m$. Then we add $n++$ to $m$ by defining $(n++)+m:=(n+m)++$.

Thus $0+m$ is $m$, $1+m=(0++)+m$ is $m++$; $2+m=(1++)+m=(m++)++$; and so forth; for instance we have $2+3=(3++)++=4++=5$. From our discussion of recursion in the previous section we see that we have defined $n+m$ for every natural number $n$. Here we are specializing the previous general discussion to the setting where $a_n=n+m$ and $f_n=a_n++$. Note that this definition is asymmetric: $3+5$ is incrementing $5$ three times, while $5+3$ is incrementing $3$ five times. Of course, they both yield the same value of $8$. More generally, it is a fact (which we shall prove shortly) that $a+b=b+a$ for all natural numbers $a$, $b$, although this is not immediately clear from the definition.

Notice that we can prove easily, using Axioms 2.1, 2.2, and induction (Axiom 2.5), that the sum of two natural numbers is again a natural number (why?)

!!! Note Why the sum of two natural numbers is again a natural number?
    Let $m$ and $n$ be two natural numbers, then we wish to show that $n+m$ is also a natural number. We induct on $n$. The base case $0+m=m$ follows by the definition of addition. Now suppose inductively that $n+m$ is a natural number. We wish to show that $(n++)+m$ is also a natural number. But by definition of addition, $(n++)+m=(n+m)++$, and hence $(n+m)++$ is a natural number by Axiom 2.2. This closes the induction.

Right now we only have two facts about addition: that $0+m=m$, and that $(n++)+m=(n+m)++$. Remarkably, this turns out to be enough to deduce every thing else we know about addition. We begin with some basic lemmas.[^6]

**Lemma 2.2.2** *For any natural number $n$, $n+0=n$*

Note that we cannot deduce this immediately from $0+m=m$ because we have not yet established the commutative property $a+b=b+a$ of addition.

***Proof*** We use induction. The base case $n=0$ follows since we know that $0+m=m$ for every natural number, and $0$ is a natural number. Now suppose inductively that $n+0=n$. We wish to show that $(n++)+0=n++$. But by definition of addition, $(n++)+0$ is equal to $(n+0)++$, which is equal to $n++$ since $n+0=n$. This closes induction.

**Lemmar 2.2.3** *For any natural numbers $n$ and $m$, $n+(m++)=(n+m)++$*.

Again, we cannot deduce this yet from $(n++)+m=(n+m)++$ because we do not know yet that $a+b=b+a$.

***Proof*** We induct on $n$ (keeping $m$ fixed). We first consider the base case $n=0$. In this case we have to prove $0+(m++)=(0+m)++$. but by definition of addition, $0+(m++)=m++$ and $0+m=m$, so both sides are equal to $m++$ and are thus equal to each other. Now we assume inductively that $n+(m++)=(n+m)++$; we now have to show that $(n++)+(m++)=((n++)+m)++$. The left-hand side is $(n+(m++))++$ by definition of addition, which is equal to $((n+m)++)++$ by the inductive hypothesis. Similarly, we have $(n++)+m=(n+m)++$ by the definition of addition, and so the right-hand side is also equal to $((n+m)++)++$. Thus both sides ere equal to each other, and we have closed the induction.

As a particular corollary of Lemma 2.2.2 and lemma 2.2.3 we see that $(n++)=n+1$ (why?)

!!! Note
    By lemma 2.2.3, the right-hand side is $(n+0)++$ since $1=0++$, which is equal to $n++$ by lemma 2.2.2. So both sides are equal to each other and hence we have $(n++)=n++$.

As promised earlier, we can now prove that $a+b=b+a$.

**Proposition 2.2.4** (Addition is commutative). *For any natural numbers $n$ and $m$, $n+m=m+n$*.

***Proof*** We shall use induction on $n$ (keeping $m$ fixed). First we do the base case $n=0$, i.e., we show $0+m=m+0$. By definition of addition, $0+m=m$, while by lemma 2.2.2, $m+0=m$. Thus the base case is done. Now suppose inductively that $n+m=m+n$. By the definition of addition, $(n++)+m=(n+m)++$. By lemma 2.2.3, $m+(n++)=(m+n)++$, but this is equal to $(n+m)++$ by the inductive hypothesis $n+m=m+n$. Thus $(n++)+m=m+(n++)$ and we have closed the induction.

**Proposition 2.2.5** (Addition is associative). *For any natural numbers $a$, $b$, $c$, we have $(a+b)+c=a+(b+c)$*

***Proof*** See Exercise 2.2.1

Because of this associativity we can write sums such as $a+b+c$ without having to worry about which order the numbers are being added together.

Now we develop a cancellation law.

**Proposition 2.2.6** (Cancellation law). *Let $a$, $b$, $c$ be natural numbers such that $a+b=a+c$. Then we have $b=c$*.

Note that we cannot use substraction or negative numbers yet to prove this proposition, because we have not developed these concepts yet. In fact, this cancellation law is crucial in letting us define substraction (and the integers) later on in this text, because it allows for a sort of "virtual substraction" even before substraction is officially defined.

***Proof*** We prove this by indcution on $a$. First consider the base case $a=0$. Then we have $0+b=0+c$, which by definition of addition implies that $b=c$ as desired. Now suppose inductively that we have the cancellation law for $a$ (so that $a+b=a+c$ implies $b=c$); we now have to prove the cancellation law for $a++$. In other words, we assume that $(a++)+b=(a++)+c$ and need to show that $b=c$. By the definition of addition, $(a++)+b=(a+b)++$ and $(a++)+c=(a+c)++$ and so we have $(a+b)++=(a+c)++$. By Axiom 2.4, we have $a+b=a+c$. Since we already have the cancellation law for $a$, we thus have $b=c$ as desired. This closes the induction.

We now discuss how addition interacts with positivity.

> **Definition 2.2.7** (*Positive natural numbers*). A natural number $n$ is said to be *positive* iff it is not equal to $0$. ("iff" is shorthand for "if and only if"; see Sect. A.1)

**Proposition 2.2.8** *If $a$ is a positive natural number, and $b$ is a natural number, then $a+b$ is positive (and hence $b+a$ is also, by Proposition 2.2.4).*

***Proof*** We use induction on $b$. If $b=0$, then $a+b=a+0=a$, which is positive, so this proves the base case. Now suppose inductively that $a+b$ is positive. Then $a+(b++)=(a+b)++$, which cannot be $0$ by Axiom 2.3, and is hence positive. This closes the induction.

**Corollary 2.2.9** If $a$ and $b$ are natural numbers such that $a+b=0$, then $a=0$ and $b=0$.

***Proof*** Suppose for sake of contradiction that $a \neq 0$ or $b \neq 0$. If $a\neq 0$ then $a$ is positive, and hence $a+b=0$ is positive by Proposition 2.2.8, a contradiction. Similarly if $b\neq 0$ then $b$ is positive, and again $a+b=0$ is positive by Proposition 2.2.8, a contradiction. Thus $a$ and $b$ must both be zero.

**Lemma 2.2.10** *Let $a$ be a positive number. Then there exists exactly one natural number $b$ such that b++=a*.

***Proof*** See Exercise 2.2.2

Once we have a notion of addition, we can begin define a notion of *order*.

> **Definition 2.2.11** (*Ordering of the natural numbers*) Let $n$ and $m$ be natural numbers. We say that $n$ is *greater than or equal to $m$*, and write $n \ge m$ or $m \le n$. iff we have $n=m+a$ for some natural number $a$. We say that $n$ is *strictly greater than* $m$, and write $n > m$ or $m < n$, iff $n \ge m$ and $n \neq m$.

Thus for instance $8>5$, because $8=5+3$ and $8 \neq 5$. Also note that $n++ > n$ for any $n$; thus there is no largest natural number $n$, because the next number $n++$ is always larger still.

**Proposition 2.2.12** (Basic properties of order for natural numbers). *Let $a$, $b$, $c$ be natural numbers* Then
- *(a) (Order is relexive) $a \ge a$*.
- *(b) (Order is transitive) If $a \ge b$ and $b \ge c$, then $a \ge c$*.
- *(c) (Order is antisymmetric) If $a \ge b$  and $b \ge a$, then $a=b$*.
- *(d) (Addition preserves order) $a \ge b$ if and only if $a+c \ge b+c$*.
- *(e) $a < b$ if and only if $a++ le b$*.
- *(f) $a<b$ if and only if $b=a+d$ for some* positive *number $d$*.

***Proof*** See Exercise 2.2.3

**Proposition 2.2.13** (Trichotomy of order for natural numbers). *Let $a$ and $b$ be natural numbers. Then exactly one of the following statements is true: $a<b$, $a=b$, or $a>b$*.

***Proof*** This is only a sketch of the proof; the gaps will be filled in Exercise 2.2.4.

First we show that we cannot have more than one of the statements $a<b$, $a=b$, $a>b$ holding at the same time. If $a<b$ then $a\neq b$ by definition, and if $a>b$ then $a \neq b$ by definition. If $a > b$ and $a < b$ then by Proposition 2.2.12 we have $a=b$, a contradiction. Thus no more than one of the statements is true.

Now we show that at least one of the statements is true. We keep $b$ fixed and induct on $a$. When $a=0$ we have $0 \le b$ for all $b$ (why?), so we have either $0=b$ or $0 < b>$, which proves the base case. Now suppose we have proven the proposition for $a$, and now we prove the proposition for $a++$. From the trichotomy for $a$, there are three cases: $a<b$, $a=b$, and $a>b$. If $a>b$, then $a++>b$ (why?). Now suppose that $a < b$. Then by Proposition 2.2.12, we have $a++ \le b$. Thus either $a++=b$ or $a++ < b$, and in either case we are done. This closes the induction.

!!! Note Why when $a=0$ we have $0 \le b$ for all $b$?
    By the definition of addition, we have $b=0+b$. And by the the definition of ordering of the natural numbers, we have $0 \le b$. Since $b$ is arbitrary, we have $0 \le b$ for all natural number $b$.

!!! Note Why if $a>b$, then $a++>b$?
    Suppose for sake of contradiction that $a=b$, then $a++=b++$. The right-hand side is equal to $b + 1$ by the particular corollary of Lemma 2.2.2 and 2.2.3. So we have $a++=b+1$. By the definition of ordering of the natural numbers we have $a++ \ge b$. Suppose for sake of contradiction that $a++=b$, then $b=b++=b+1$. By Lemma 2.2.2 we have $b+0=b+1$, and by the cancellation law we have $0=1=0++$, a contradiction by Axiom 2.3. So $a++ \neq b$ and hence $a++>b$ by the definition of ordering of the natural numbers.

!!! Note Why if $a=b$ then $a++>b$?
    Since $a=b$ we have $a++=b++$. By the particular corollary of Lemma 2.2.2 and Lemma 2.2.3 we have $a++=b+1$ and hence $a++ \ge b$ by the definition of ordering of the natural numbers. Suppose for sake of contradiction that $a++=b$.
    By the particular corollary of Lemma 2.2.2 and Lemma 2.2.3, the left-hand side is equal to $b+1$, while the right-hand side is equal to $b+0$ by Lemma 2.2.2, so we have $b+1=b+$ and thus by the cancellation $1=0++=0$, a contradiction by Axiom 2.3. So we have $a++ \neq b$ and hence $a++ > b$ by the definition of ordering of the natural numbers.

The properties of order allow one to obtain a stronger version of the principle of induction:

**Proposition 2.2.14** (Strong principle of induction). *Let $m_0$ be a natural number, and let $P(m)$ be a property pertaining to an arbitrary natural number $m$. Suppose that for each $m \ge m_0$, we have the following implication: if $P(m')$ is true for all natural numbers $m_0 \le m' < m$, then $P(m)$ is also true. (In particular, this means that $P(m_0)$ is true, since in this case the hypothesis is vacuous.) Then we can conclude that $P(m)$ is true for all natural numbers $m \ge m_0$* 

***Remark 2.2.15*** In applications we usually use this principle with $m_0=0$ or $m_0=1$.

***Proof*** See Exercise 2.2.5.

## Exercises

*Exercise 2.2.1* Prove Proposition 2.2.5. (*Hint*: fix two of the variables and induct on the third)

!!! Note
    We induct on $b$ (keeping $a$ and $c$ fixed). We first consider the base case $b=0$. In this case we have to prove $(a+0)+c=a+(0+c)$. By Lemma 2.2.2, the left-hand side is equal to $a+c$; and by the definition of addition, the right-hand side is also equal to $a+c$. So both sides are equal to $a+c$ and are thus equal to each other. Now we assume inductively that $(a+b)+c=a+(b+c)$; we now have to show that $(a+(b++))+c=a+((b++)+c)$. The left-hand side is $((a+b)++)+c$ by Lemma 2.2.3, which is equal to $((a+b)+c)++$ by the definition of addition, which is equal to $(a+(b+c))++$ by the inductive hypothesis. The right-hand is equal to $a+((b+c)++)$ by the definition of addition, which is equal to $(a+(b+c))++$ by Lemma 2.2.3. Thus both sides are equal to each other, and we have closed the induction.

*Exercise 2.2.2* Prove Lemma 2.2.10. (*Hint*: use induction. The induction here is somewhat degenerate, in that the induction hypothesis is not actually used, but this does not prevent the argument from remaining valid: cf. the disscussion on implication and causality in Appendix A.2.).

!!! Note
    We shall use induction on $a$. First we do the base case $a=0$. The claim is vacuously true since this hypothesis is false. Thus the base case is done. Now suppose inductively that there is exactly one natural number $b$ such that $b++=a$, now we have to prove that there is exactly one natural number $c$ such that $c++=a++$. First we show that there is at least one natural number $c$ such that $c++=a++$. Let $c:=a$ then we have $c++=a++$ as desired. Now we show that we cannot have more than one natural number $c$ such that $c++=a++$. By Axiom 2.2 we see that both $c++$ and $a++$ are natural numbers, and by Axiom 2.3 we have $c=a$ since $c++=a++$. So there is exactly one natural number $c$ ($c=a$) such that $c++=a++$. This closes the induction.

*Exercise 2.2.3* Prove Proposition 2.2.12. (*Hint*: you will need many of the preceding propositions, collaries, and lemmas.)

!!! Note
    1. *(a)* (*Order is reflexive*) $a \ge a$.
        - We have $a=a+0$ by Lemma 2.2.2 and hence $a \ge a$ by definition of ordering of the natural numbers.
    2. *(b)*(*Order is transitive*) *If $a \ge b$ and $b \ge c$, then $a \ge c$*.
        - By definition of ordering of the natural numbers we have $a=b+m$ for some natural number $m$. Similarly, by this definition again, we have $b=c+n$ for some natural number $n$. So we have $a = (c+n)+m=c+(n+m)$ by Propostion 2.2.5. Since we have previously proved that $n+m$ is also a natural number if both $n$ and $m$ are natural numbers, we have $a \ge c$ by definition of ordering of the natural numbers again.
    3. *(c)* (*Order is antisymmetric*) *If $a \ge b$ and $b \ge a$, then $a=b$*. 
        - By definition of ordering of the natural numbers, we have $a=b+m$ for some natural number $m$ and $b=a+n$ for some natural number $n$. So we have $a=(a+n)+m=a+(n+m)$ by Proposition 2.2.5, which also implies $a+0=a+(n+m)$ by Lemma 2.2.2. Then by the cancellation law, we have $0=n+m$. Since both $n$ and $m$ are natural numbers, we must have $n=0$ and $=0$ by Corollary 2.2.9, indicating $a=b+0=b$ by Lemma 2.2.2. Thus $a$ must equal $b$.
    4. *(d)* (*Addition preserves order*) *$a \ge b$ if and only if $a+c \ge b+c$*.
        - First we show that $a \ge b$ implies $a+c\ge b+c$. Since $a \ge b$, by the definition of odering of the natural numbers, we have $a=b+m$ for some natural number $m$. So $a+c=(b+m)+c=(b+c)+m$ By Lemma 2.2.2 and Lemma 2.2.3. Since $m$ is a natural number, we have $a+c \ge b+c$ by the definition of odering of the natural numbers again. Thus $a \ge b$ implies $a+c \ge b+c$.
        - Now we show the reverse direction of the statement also holds. Since $a+c \ge b+c$, we have $a+c=(b+c)+n$ for some natural number $n$ by the definition of odering of the natural numbers, which means $c+a=c+(b+n)$ by Lemma 2.2.2 and 2.2.3. By the cancellation law, we have $a=b+n$, indicating $a \ge b$ since $n$ is a natural number. Thus $a+c \ge b+c$ implies $a\ge b$.
        - Therefore we can conclude that $a \ge b$ iff $a+c \ge b+c$.
    5. *(e)* *$a<b$ if and only if $a++ \le b$*.
        - First we show that $a<b \implies a++ \le b$. Since $a<b$, we have $a+m=b$ by the definition of odering of the natural numbers. If $m=0$ then $a+0=a=b$, a contradiction. So $m \neq 0$ and hence $m$ is positive by definition of positive natural numbers. Then by Lemma 2.2.10, there exists exactly one natural number $n$ such that $n++=m$, and then $a+m=a+(n++)=b$. By Lemma 2.2.3, we have $a+(n++)=(a+n)++$, and by definition of addition, we have $(a+n)++=(a++)+n$. So $(a++)+n=b$ and hence $a++ \le b$ by definition of odering of the natural numbers again.
        - Now we show that the reverse direction of the statement also holds. Since we have proved that $n++=n+1$ for any natural number $n$, we have $a+1 \le b$ as $a++ \le b$. By definition of odering of the natural numbers, we have $(a+1)+m=b$ for some natural number $m$, which also means $b=a+(1+m)$ by Proposition 2.2.5 and $a \le b$ by definition of odering of the natural numbers. Since $1=0++$, we have $1 \neq 0$ by Axiom 2.3 and hence $1$ is positive. So $1+m$ is also positive by Proposition 2.2.8. Suppose for sake of contracition that $a=b$, by the cancellation law we have $1+m=0$, a contradiction. Thus we have $a<b$.
        - Therefore we can conclude that $a<b$ iff $a++\le b$.
    6. *(f)* *$a<b$ if and only if $b=a+d$ for some positive number $d$.*
        - cf. the discussion in the proof of property (e) of Proposition 2.2.12

*Exercise 2.2.4* Justify the three statements marked (why?) in the proof of Proposition 2.2.13.

!!! Note
    cf. the discussion from Line 95 to Line 103.

*Exercise 2.2.5* Prove Proposition 2.2.14. (*Hint*: define $Q(n)$ to be the property that $P(m)$ is true for all $m_0\le m <n$; note that $Q(n)$ is vacuously true when $n \le m_0$.)

!!! Success
    Let $Q(n)$ to be the property that $P(m)$ is true for all $m_0 \le m <n$. Then we can restate Proposion 2.2.14 as follows:
    - Let $m_0$ be a natural number, and let $P(m)$ be a property pertaining to an arbitrary natural number $m$. Suppose that for each natural number $n$, we have the following implication: if $n \ge m_0$ and $Q(n)$ is true, then $P(n)$ is also true. Then $P(n)$ is true for all natural numbers $n \ge m_0$.

    If we can prove that $Q(n)$ is true for all natural numbers $n$, then the bullet point is thus verified. We use indcution on $n$.

    First consider the base case that $n=0$. Then we need to show that if $m_0 \le m <0$ then $P(m)$ is true. By Proposition 2.2.12(b) we have $m_0 \le 0$. Since $m_0=0+m_0$ by the definition of addition, we have $m_0 \ge 0$ by the definition of ordering of the natural numbers. Then by Proposition 2.2.12(c) we have $m_0=n=0$ and hence $m \ge 0$ and $m < 0$, which is a contradiction by Proposition 2.2.13. So the hypothesis is false and $P(m)$ is thus vacuously true.

    Now suppose inductively that $Q(n)$ is true, now we have to prove that $Q(n++)$ is true i.e., to prove that if $m_0 \le m <n++$ then $P(m)$ is true. But $m<n++$ iff $m++ \le n++$ by Propostion 2.2.12(e), and $m++\le n++$ iff $m \le n$ by Propostion 2.2.12(d). So $m_0 \le m < n++$ iff $m_0\le m \le n$, and we need to show that if $m_0\le m \le n$ then $P(m)$ is true. By Proposition 2.2.13, we have either $n<m_0$ or $n \ge m_0$. if $n < m_0$, then the hypothesis "$n \ge m_0$ and $Q(n)$ is true" of the bullet point is false and hence $P(n)$ is vacuously true. Thus $P(m)$ is true for all $m_0 \le m \le n$. If $n \ge m_0$, then by the inductive hypothesis that $Q(n)$ is true we have $P(n)$ is true, which also leads to result that $P(m)$ is true for all $m_0 \le m \le n$. So both case leads to $P(m)$ is true if $m_0\le m \le n$ and this closes the induction.


*Exercise 2.2.6* Let $n$ be a natural number, and let $P(m)$ be a property pertaining to the natural numbers such that whenever $P(m++)$ is true, then $P(m)$ is true. Suppose that $P(n)$ is also true. Prove that $P(m)$ is true for all natural numbers $m \le n$; this is known as the *principle of backwards induction*. (*Hint*: apply induction to the variable $n$.)

!!! Note
    We first introduce a small lemma as follow:
    - let $m$ and $n$ be two natural numbers, then $m \le n$ iff either $m=n$ or $m<n$.

    ***Proof*** We first show that $m \le n \implies (m=n \text{ or } m<n)$. By definition of ordering of the natural numbers, $n=m+a$ for some natural numbers. By Proposition 2.2.13, we have either $a=0$ or $a \neq 0$. If $a=0$ then $n=m+0=m$; otherwise if $a \neq 0$ then $a$ is positive and hence $m<n$ by Proposition 2.2.12(f). Thus $m \le n \implies (m=n \text{ or } m<n)$. Now we show that the reverse direction of the statement also holds. If $m<n$ then $m \le n$ by definition of ordering of the natural numbers; otherwise if $m=n$ then we have $n=m+0$ and hence $m \le n$ by definition of ordering of the natural numbers again. In both cases we have $(m \le n$ so $m=n \text{ or } m<n) \implies m \le n$. Therefore we have proved the lemma.

    We use induction on $n$. First we do the base case $n=0$, i.e., we show $P(0)$ is true for all natural numbers $m \le 0$. By Lemma 2.2.2, $m=m+0$, and then we have $m \ge 0$ by the definition of ordering of the natural numbers. By Proposition 2.2.12(c) we have $m=0=n$ since $0 \le m \le 0$. So $P(m)$ is equivalent to $P(n)$ which known to be true. Thus the base case is done. Now suppose inductively that we have proved that if $P(n)$ is true then $P(m)$ is also true for all natural numbers $m \le n$, now we have to prove that if $P(n++)$ is true then $P(m)$ is true for all natural numbers $m \le n++$. Since $P(n++)$ is true, we have $P(n)$ is true by the property of $P$. Then $P(m)$ is true for all natural numbers $m \le n$ by the inductive hypothesis. By Proposition 2.2.12(d) we have $m \le n$ iff $1+m\le 1+n$ which means $m++ \le n++$, and by Proposition 2.2.12(e) we have $m++ \le n++$ iff $m < n++$. So $m \le n$ iff $m < n++$. Thus $P(m)$ is true for all natural numbers $m<n++$. Since $P(m)$ is also true when $m=n++$ by the hypothesis, by the lemma we introduced in at the begining, we actually have showed that $P(m)$ is true for all $m \le n++$ and thus completed the induction.

!!! Success Model solution
    Let $P$ be a property pertaining to the natural numbers such that whenever $P(m++)$ is true, $P(m)$ is true.

    Let $Q(n)$ be the following statement: if $P(n)$ is true, then $P(m)$ is true for all $m \le n$.

    We shall show that $Q(n)$ is true for all $n$ using induction. For the base case, we must show $Q(0)$. So suppose that $P(0)$ is true. We want to show that $P(m)$ is true for all $m \le 0$. By definition of inequality (definition 2.2.11), $m \le 0$ means that $0=m+a$ for some natural number $a$. By Corollary 2.2.9, we have $m=0$. In other words, $m \le 0$ implies $m=0$, so showing that $P(m)$ for all $m \le 0$ is equivalent to showing $P(0)$, which we already know. This completes the base case.

    Now suppose $Q(n)$ is true. We must show that $Q(n++)$ is true. By definition of $Q$, $Q(n++)$ is the statement "if $P(n++)$ is true, then $P(m)$ is true for all $m \le n++$", so suppose that $P(n++)$ is true. We need to show that $P(m)$ is true for all $m \le n++$. We know that whenever $P(m++)$ is true, $P(m)$ is true, so for $m=n$ in particular this means that if $P(n++)$ is true then $P(n)$ is true. Since $P(n++)$ is true, we see that $P(n)$ is true. By the induction hypothesis we thus have $P(m)$ for all $m \le n$. Now let $m \le n++$. We want to show $P(m)$ is true. If we can show that $m \le n$ or $m=n++$, then we will be done, because in either case we have already shown that $P(m)$ is true. To show that $m \le n$ or $m=n++$, we will show that $m \neq n++$ implies $m \le n$. Suppose $m \neq n++$. This means $m < n++$ by definition 2.2.11. By proposition 2.2.12(e), we have $m++ \le n++$, i.e., $m+1 \le n+1$. By proposition 2.2.12(d) this means $m \le n$ as required. This closes the induction.

    Now let $n$ be a natural number, and suppose $P(n)$ is true. By our work above, we know that $Q(n)$ is true. This means that $P(m)$ is true for all natural numbers $m \le n$ as required.

*Exercise 2.2.7* Let $n$ be a natural number, and let $P(m)$ be a property pertaining to the natural numbers such that whenever $P(m)$ is true, $P(m++)$ is true. Show that if $P(n)$ is true, then $P(m)$ is true for all $m \ge n$. (This principle is sometimes referred to as the *principle of induction starting from the base case $n$*)

!!! Note
    - Let $Q(n)$ be a property that if $P(n)$ is true then $P(m)$ is true for all $m \ge n$. Then we shall prove that $Q(n)$ is true for every natural number $n$. 
    - We induct on $n$. First consider the base case $n=0$. In this case we have to show that if $P(0)$ is true then $P(m)$ is true for all $m \ge 0$. So suppose $P(0)$ is true and we need to show $P(m)$ is true for all $m \ge 0$ .We induct on $m$. The base case $m=0$ follows since we already know that $P(0)$ is true. Now supppose inductively that $P(m)$ is true, we have to show $P(m++)$ is true. But by the given property of $P$ we have $P(m++)$ is true since $P(m)$ is true by the inductive hypothesis. This closes the induction. Thus $Q(0)$ is true. 
    - Now suppose inductively that $Q(n)$ is true, we now have to show $Q(n++)$ is also true. In other words, we need to show that if $P(n++)$ is true then $P(m)$ is true for all $m \ge n++$. So suppose $P(n++)$ is true, we need to show that $P(m)$ is true for all $m \ge n++$. We induct on $m$. First consider the base case $m=0$. Since $n++ =0+(n++)$ by definition of addition, we have $n++ \ge 0$ by definition of ordering of the natural numbers. By Axiom 2.3, $n++ \neq 0$ thus $n++ > 0$ by definition of ordering of the natural numbers again. By Proposition 2.2.13, $0\ge n++$ is false and hence $P(0)$ is true for all $0 \ge n++$ is vacuously true. Now suppose inductively $P(m)$ is true for all $m \ge n++$, we now have to show $P(m++)$ is true for all $m \ge n++$. Since $m++=m+1$ by Lemma 2.2.3, we have $m++ \ge m$ by definition of ordering of the natural numbers. If $m \ge n++$, by Proposition 2.2.12(b) we have $m++ \ge n++$. By the inductive hypothesis $P(m++)$ is true for all $m++ \ge n++$. This closes the induction.
     
 
[^6]: From a logic point of view, there is not difference between a lemma, proposition, theorem or corollary—they are all claims waiting to be proved. However, we use these terms to suggest different levels of importance and difficulty. A lemma is an easily proved claim which is helpful for proving other propositions and theorems, but is usually not particularly interesting in its own right. A proposition is a statement which is interesting in its own right, while a theorem is a more important statement than a proposition which says something definitive on the subject, and often takes more effort to prove than a proposition or lemma. A collary is a quick consequence of a proposition or theorem that was proved recently.
