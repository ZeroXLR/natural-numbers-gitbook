{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> Having dealt with the albegraic properties of the natural numbers, I turn to explore their order properties. Recall that I defined the order thus: $$x \leq y$$ iff $$\exists n\in{{N}}\ [x+n=y]$$. Furthermore, I have already shown, quite trivially, that this order is **reflexive**.


## Theorem Transitivity

**Transitivity**: _For all $$x,y,z\in{{N}}$$, if $$x \leq y$$ and $$y \leq z$$, then $$x \leq z$$_.

**Proof**: If one assumes the hypothesis, then there are $$n,n'\in{{N}}$$ such that $$x+n=y$$ and $$y+n'=z$$. So, after substitution and [associativity](../PropertiesAddAndMultiply.md#theorem-assocadd), $$(x+n)+n'=x+(n+n')=z$$. So, there is, in fact, a natural number $$n''=n+n'$$ such that $$x+n''=z$$ i.e. $$x \leq z$$.


&nbsp;
> The above proof aside, I will, henceforth, use the previously proved properties of the natural numbers without explicit warnings. I leave it to the readers to fill in the relevant details from the list of properties proved so far.


## Lemma NoInvs

> This lemma seems like it belongs in the previous chapter. However, its implications are most felt in this chapter on order. In particular, it will be an important step in showing that the order on the natural numbers is **antisymmetric**.

**No Non-Zero Natural Number has Inverses**: _For all $$x,y\in{{N}}$$, if $$x \neq 0$$, then $$x+y \neq 0$$_.

**Proof**: One doesn't even need induction for this. A simple case analysis suffices. Assume the lemma's hypothesis. Now, If $$y=0$$ then, obviously, $$x+y=x+0=x \neq 0$$. Otherwise, there is some natural number $$y'$$ such that $$S(y')=y$$. So now, $$x+y=x+S(y')=S(x+y')$$ and this can never be $$0$$.


## Theorem AntiSymmetry

**AntiSymmetry**: _For all $$x,y\in{{N}}$$, if $$x \leq y$$ and $$y \leq x$$, then $$x=y$$_.

**Proof**: Assuming the hypothesis yields that there are $$n,n'\in{{N}}$$ such that $$x+n=y$$ and $$y+n'=x$$. Hence, $$(x+n)+n'=x+(n+n')=x=x+0$$. After cancelling, $$n+n'=0$$ which, by the previous lemma's contrapositive, yields $$n=0$$. Hence, $$x=x+0=x+n=y$$.


## Interlude 0

Thus, the aforementioned order on $${{N}}$$ is **reflexive**, **transitive** and **antisymmetric**. It is therefore a _**partial order**_. In the context of a semiring, this partial order, if it exists, is actually called the _**canonical partial order**_ on the semiring. Not all semirings have a canonical partial order. For instance, if one defined the exact same relation on the integers, one would not get a partial order because antisymmetry would fail. One would get, for example, both $$0\leq 1$$ (because $$0+1=1$$) and $$1 \leq 0$$ (because $$1+(-1)=0$$); but clearly $$0 \neq 1$$ as integers. This happens _precisely_ because the integers have additive inverses; hence, the crucial [Lemma NoInvs](#lemma-noinvs) fails for them. It should not be very hard to convince oneself that any semiring that does not have inverses (for non-zero elements) has a canonical partial order. In the particular case of the natural numbers, however, one can go further still. It turns out that, here, one actually has a _**total order**_ i.e. any two natural numbers can be compared with one another. This will be discussed next.


## Lemma SxLx

**$$S(x)$$ is Larger than $$x$$**: _For any $$x\in{{N}}$$, $$x \leq S(x)$$_.

**Proof**: $$x+1=S(x)$$; so there is an $$n\in{{N}}$$ such that $$x+n=S(x)$$: $$1$$.


## Lemma ZLNN

**Zero is the Least Natural Number**: _For any $$x\in{{N}}$$, $$0 \leq x$$_.

**Proof**: $$0+x=x$$; so there is clearly an $$n\in{{N}}$$ such that $$0+n=x$$: $$x$$ itself.


## Lemma SSwap

_For any $$x,y\in{{N}}$$, $$x+S(y)=S(x)+y$$_.

**Proof**: $$x+S(y)=S(x+y)=S(y+x)=y+S(x)=S(x)+y$$.


## Theorem Totality

**Totality**: _For every $$x,y\in{{N}}$$, either $$x \leq y$$ or $$y \leq x$$_.

**Proof**: Let $${{S}}=\{x\in{{N}}:\ \forall y\in{{N}}\ [x \leq y\ \text{or}\ y \leq x]\}$$.
1. $$0\in{{S}}$$ by [Lemma ZLNN](#lemma-zlnn).
2. Now, assume that $$x\in{{S}}$$. Consequently, for any $$y\in{{N}}$$,
    * either $$y \leq x$$. In this case, [Lemma SxLx](#lemma-sxlx) and [transitivity](#theorem-transitivity) gives $$y \leq S(x)$$, so that $$S(x)\in{{S}}$$.
    * or $$x \leq y$$. Then there is some $$n\in{{N}}$$ such that $$x+n=y$$. If $$n=0$$, then $$x+0=x=y$$. So, by [Lemma SxLx](#lemma-sxlx), $$y=x \leq S(x)$$, so that $$S(x)\in{{S}}$$. Otherwise, if $$n \neq 0$$, then there is some $$n'\in{{N}}$$ such that $$S(n')=n'+1=n$$. Hence, $$y=x+n=x+S(n')=S(x)+n'$$ by the previous lemma. Thus, $$S(x) \leq y$$, so that $$S(x)\in{{S}}$$ again.


&nbsp;
> The theorem above is sometimes presented in a slightly different form. For this alternative form, one first needs the simple idea of a strict order:


## Definition Strict Order

**Strict Order**: Given two natural numbers $$x$$ and $$y$$, one says that $$x$$ is **strictly less** than $$y$$ iff $$x \leq y$$ and $$x \neq y$$. One denotes this as $$x<y$$.


## Theorem TotalityAlt

**Totality (Alternative Form)**: _For every $$x,y\in{{N}}$$, exactly one of $$x<y$$, $$x=y$$ or $$y<x$$ is true_.

> The proof of this is very easy. All one has to do is to argue that if one of the cases happen, the other two cases cannot happen. That at least one of the cases happen is already guaranteed by the original theorem on totality.


## Interlude 1

One has now shown that the natural numbers are totally ordered. Believe it or not, one can go _even_ further! The natural numbers are also _**well-ordered**_ i.e. every non-empty subset of the naturals have a smallest/least element. Thus, one cannot have "bottomless chasms" in the natural numbers. At some point, as one descends down a non-empty natural subset according to order, one must reach the bottom in a finite number of steps.


## Definition LE

**Least Element**: Let $$X\subseteq{{N}}$$. Then, an element $$n \in X$$ is called the **least element** of $$X$$ iff for any $$x \in X$$, it is the case that $$n \leq x$$.


## Lemma ULE

**Uniqueness of the Least Element**: _If $$X\subseteq{{N}}$$ has a least element $$n$$, then it is unique_.

**Proof**: Suppose $$n'$$ is some other least element of $$X$$. Then, as $$n \in X$$, $$n' \leq n$$. At the same time, since $$n$$ is also a least element and $$n' \in X$$, $$n \leq n'$$. So, $$n=n'$$ by antisymmetry.


## Theorem Well-Ordering

**Well Ordering of $${{N}}$$**: _If $$X\subseteq{{N}}$$ and $$X\neq\emptyset$$, then $$X$$ has a least element_.

**Proof**: Do induction with $${{S}}=\{n\in{{N}}:\ \text{if}\ X\subseteq{{N}}\ \text{and}\ n \in X\ \text{, then}\ X\ \text{ has a least element}\}$$.
1. $$0\in{{S}}$$ because [it is already the least natural number](#lemma-zlnn).
2. Now suppose that $$n\in{{S}}$$. One now has to show that $$S(n)\in{{S}}$$ also. To that end, consider any $$X\subseteq{{N}}$$ such that $$S(n) \in X$$. Now, if $$n \in X$$, then one is done because by the initial hypothesis, any subset with $$n$$ must have a least element. Otherwise, consider $$X'=X\cup\{n\}$$. Clearly, $$n \in X'$$, so that $$X'$$ has some least element $$l$$. Now
    * If $$l \neq n$$, then $$l \in X$$. It is easy to see in this case that $$l$$ is the least element of $$X$$. For, fix any $$s \in X$$; then certainly $$s \in X'$$ also. But then as $$l$$ is the least element of $$X'$$, $$l \leq s$$.
    * Otherwise, $$l=n$$. In this case, one can show that $$S(n)$$ is the least element of $$X$$. Well, for starters, fix any $$s \in X$$. Since $$s \in X'$$ also and $$l=n$$ is the least element of $$X'$$, $$n \leq s$$ i.e. there is some $$k\in{{N}}$$ such that $$n+k=s$$. Now, $$k \neq 0$$ as otherwise, $$s=n+0=n\notin{{N}}$$. Thus, there is a $$k'\in{{N}}$$ such that $$S(k')=k$$. So, $$s=n+k=n+S(k')=S(n)+k'$$ (using [Lemma SSwap](#lemma-sswap)). Hence, $$S(n) \leq s$$.


&nbsp;
> One can also flesh out well-ordering in terms of the existence of **greatest elements** in **bounded** subsets of $${{N}}$$.


## Definition GE

**Greatest Element**: Let $$X\subseteq{{N}}$$. Then, an element $$n \in X$$ is called the **greatest element** of $$X$$ iff for any $$x \in X$$, $$x \leq n$$.


## Lemma UGE

**Uniqueness of the Greatest Element**: _If $$X\subseteq{{N}}$$ has a greatest element $$n$$, then it is unique_.

> The proof of this is entirely analogous to the proof that least elements are unique.


## Definition Upper Bound

**Upper Bound on a Subset of $${{N}}$$**: Let $$X\subseteq{{N}}$$. A natural number $$n$$ is called an **upper bound** on $$X$$ iff for any $$x \in X$$, $$x \leq n$$.


&nbsp;
> Thus, the greatest element of a subset of $${{N}}$$ is precisely an upper bound which is in the subset itself.


## Definition Bounded Subset

**Bounded Subsets of $${{N}}$$**: Let $$X\subseteq{{N}}$$. Then one says that $$X$$ is **bounded above** iff an upper bound on it exists.


## Lemma SxLESGx

**$$S(x)$$ is the Least Element Strictly Greater Than $$x$$**: _For any $$x,y\in{{N}}$$, if $$x<y$$, then $$S(x) \leq y$$_.

**Proof Sketch**: If $$x<y$$, then there is a natural $$k'$$ such that $$x+S(k')=S(x)+k'=y$$ i.e. $$S(x) \leq y$$.


## Theorem Well-Ordering-Alt

**Well-Ordering on $${{N}}$$ (Alternative Form)**: _If $$X\subseteq{{N}}$$ is non-empty and bounded above, then $$X$$ has a greatest element_.

**Proof**: Form the set of all upper bounds on $$X$$, $$X'$$. This is non-empty since $$X$$ is bounded above. Hence, by well-ordering, $$X'$$ has a least element $$l$$. Now, clearly as $$l$$ is an upper bound on $$X$$, for any $$x \in X$$, $$x \leq l$$. The only thing that remains to be shown, to conclude that $$l$$ is the greatest element of $$X$$, is that $$l \in X$$.

If $$l=0$$, since $$0$$ is the least element period, for any $$x \in X$$, $$l \leq x$$. Hence, by antisymmetry, $$x=l$$. Now, as $$X$$ is non-empty, there is at least one natural $$x \in X$$ and by the previous sentence, $$l=x \in X$$.

Otherwise, $$l \neq 0$$. Hence, there is some $$l' \in {{N}}$$ such that $$S(l')=l$$. Since $$l'<S(l')$$ ($$l' \neq S(l')$$ as $$S$$ has no fixed points and $$l' \leq S(l')$$ by an earlier lemma), it cannot be that $$l=S(l') \leq l'$$ by alternative totality. Hence, $$l' \notin X'$$; otherwise, $$l$$ would no longer be the least element of $$X'$$. Thus, $$l'$$ is not an upper bound on $$X$$. In other words, there is an $$x \in X$$ such that $$x \leq l'$$ is not true; hence, $$l'<x$$ by alternative totality. So, by the previous lemma, $$l=S(l') \leq x$$. But then, by antisymmetry, $$l=x \in X$$.