## Addition

The natural number system is very bare right now: we have only one operation—incrementation—and a handful axioms. But now we can build up more complex operations, such as addition.

The way it works is the following. To add three to five should be the same as incrementing five three times—this is one increment more than adding two to five, which is one increment more than adding one to five, which is one increment more than adding zero to five, which should just give five. So we give a recursive definition for addition as follows.

> **Definition 2.2.1** (*Addition of natural numbers*). Let $m$ be a natural number. To add zero to $m$, we define $0+m:=m$. Now suppose inductively that we have defined how to add $n$ to $m$. Then we add $n++$ to $m$ by defining $(n++)+m:=(n+m)++$.

Thus $0+m$ is $m$, $1+m=(0++)+m$ is $m++$; $2+m=(1++)+m=(m++)++$; and so forth; for instance we have $2+3=(3++)++=4++=5$. From our discussion of recursion in the previous section we see that we have defined $n+m$ for every natural number $n$. Here we are specializing the previous general discussion to the setting where $a_n=n+m$ and $f_n=a_n++$. Note that this definition is asymmetric: $3+5$ is incrementing $5$ three times, while $5+3$ is incrementing $3$ five times. Of course, they both yield the same value of $8$. More generally, it is a fact (which we shall prove shortly) that $a+b=b+a$ for all natural numbers $a$, $b$, although this is not immediately clear from the definition.

Notice that we can prove easily, using Axioms 2.1, 2.2, and induction (Axiom 2.5), that the sum of two natural numbers is again a natural number (why?)

!!! Note

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

**Corollary 2.2.9** If $a$ and $b$ are natural numbers such that $a+b=0$, then $a=0$ and $b=0$. Suppose for sake of contradiction that $a \neq 0$ or $b \neq 0$. If $a\neq 0$ then $a$ is positive, and hence $a+b=0$ is positive by Proposition 2.2.8, a contradiction. Similarly if $b\neq 0$ then $b$ is positive, and again $a+b=0$ is positive by Proposition 2.2.8, a contradiction. Thus $a$ and $b$ must both be zero.

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

The properties of order allow one to obtain a stronger version of the principle of induction:

**Proposition 2.2.14** (Strong principle of induction). *Let $m_0$ be a natural number, and let $P(m)$ be a property pertaining to an arbitrary natural number $m$. Suppose that for each $m \ge m_0$, we have the following implication: if $P(m')$ is true for all natural numbers $m_0 \le m' < m$, then $P(m)$ is also true. (In particular, this means that $P(m_0)$ is true, since in this case the hypothesis is vacuous.) Then we can conclude that $P(m)$ is true for all natural numbers $m \ge m_0$* 

***Remark 2.2.15*** In applications we usually use this principle with $m_0=0$ or $m_0=1$.

***Proof*** See Exercise 2.2.5.


 
[^6]: From a logic point of view, there is not difference between a lemma, proposition, theorem or collary—they are all claims waiting to be proved. However, we use these terms to suggest different levels of importance and difficulty. A lemma is an easily proved claim which is helpful for proving other propositions and theorems, but is usually not particularly interesting in its own right. A proposition is a statement which is interesting in its own right, while a theorem is a more important statement than a proposition which says something definitive on the subject, and often takes more effort to prove than a proposition or lemma. A collary is a quick consequence of a proposition or theorem that was proved recently.
