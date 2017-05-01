{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> Having dealt with the albegraic properties of the natural numbers, I turn to explore their order properties. Recall that I defined the canonical order thus: $$x \leq y$$ iff $$\exists n\in{{N}}\ [x+n=y]$$. Furthermore, I have already shown, quite trivially, that this order is **reflexive**. On the other hand, I have, as yet, shown nothing about the order of divisibility.


## Theorem DivReflexivity

**Reflexivity of Divisibility**: _For all $$x\in{{N}}$$, $$x\ |\ x$$_.

**Proof**: This is just a rephrasing of [Theorem IdMultiply](../AddAndMultiply.md#theorem-idmultiply).


## Theorem Transitivity

**Transitivity**: _For all $$x,y,z\in{{N}}$$, if $$x \leq y$$ and $$y \leq z$$, then $$x \leq z$$_. _Also, if $$x\ |\ y$$ and $$y\ |\ z$$, then $$x\ |\ z$$_.

**Proof**: If one assumes the hypothesis, then there are $$n,n'\in{{N}}$$ such that $$x+n=y$$ and $$y+n'=z$$. So, after substitution and [associativity](../AddAndMultiply.md#theorem-assocadd), $$(x+n)+n'=x+(n+n')=z$$. So, there is, in fact, a natural number $$n''=n+n'$$ such that $$x+n''=z$$ i.e. $$x \leq z$$.

To show the second part of the theorem, one can use an analogous argument where one replaces addition with multiplication above.

&nbsp;
> The above proof aside, I will, henceforth, use the previously proved properties of the natural numbers without explicit warnings. I leave it to the readers to fill in the relevant details from the list of properties proved so far.


## Lemma NoInvs

> This lemma seems like it belongs in the previous chapter. However, its implications are most felt in this chapter on order. In particular, it will be an important step in showing that the order on the natural numbers is **antisymmetric**.

**No Non-Zero Natural Number has Additive Inverses**: _For all $$x,y\in{{N}}$$, if $$x \neq 0$$, then $$x+y \neq 0$$_.

**No Non-Unit Natural Number has Multiplicative Inverses**: _For all $$x,y\in{{N}}$$, if $$x \cdot y=1$$, then $$x=1$$_.

**Proof**: A simple case analysis suffices for the first part. Assume the lemma's hypothesis. Now, if $$y=0$$ then, obviously, $$x+y=x+0=x \neq 0$$. Otherwise, there is some natural $$y'$$ such that $$S(y')=y$$. So now, $$x+y=x+S(y')=S(x+y')$$ and this can never be $$0$$.

For the second part, a slightly lengthier analysis is needed. Assume, again, the lemma's hypothesis i.e. $$x \cdot y=1=S(0) \neq 0$$. Hence, neither $$x$$ nor $$y$$ can be zero. So, there are naturals $$x',y'$$ such that $$S(x')=x, S(y')=y$$. So, using the hypothesis again, one gets that
$$
x \cdot y=S(x') \cdot S(y')=S(x') \cdot y'+S(x')=S(S(x') \cdot y'+x')=S(0)
$$
Thus, $$S(x') \cdot y'+x'=x'+S(x') \cdot y'=0$$. So, since no non-zero natural can have additive inverses, one has that $$x'=0$$. This immediately implies that $$x=S(x')=S(0)=1$$.


## Theorem AntiSymmetry

**AntiSymmetry**: _For all $$x,y\in{{N}}$$, if $$x \leq y$$ and $$y \leq x$$, then $$x=y$$_. _Analogously, for the order of divisibility, if $$x\ |\ y$$ and $$y\ |\ x$$, then $$x=y$$_.

**Proof**: Assuming the hypothesis yields that there are $$n,n'\in{{N}}$$ such that $$x+n=y$$ and $$y+n'=x$$. Hence,
$$
x+(n+n')=(x+n)+n'=y+n'=x=x+0
$$
After (additive) cancelling, $$n+n'=0$$ which yields $$n=0$$ as no non-zero natural can have additive inverses. Hence, $$x=x+0=x+n=y$$.

To show the second part of the theorem, simply replace addition with multiplication above.


## Interlude 0

There is something special about the canonical order on the naturals: not all semirings have such a canonical partial order. For instance, if one defined the exact same relation on the integers, one would not get a partial order as antisymmetry would fail. One would get, for example, both $$0\leq 1$$ (because $$0+1=1$$) and $$1 \leq 0$$ (because $$1+(-1)=0$$); but clearly $$0 \neq 1$$ as integers. This happens _precisely_ because the integers have additive inverses; hence, the crucial [Lemma NoInvs](#lemma-noinvs) fails for them. It turns out that one can go further still with the naturals to get a **total order** i.e. any two natural numbers can be compared with one another. This will be discussed next. In what follows, I will concern myself only with the canonical order and not with the order of divisibility. The reason for this will be clarified at the end.


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
> The theorem above is sometimes presented in a slightly different form which I illustrate next:


## Definition Strict Order

**Strict Order**: Given two natural numbers $$x$$ and $$y$$, one says that $$x$$ is **strictly less** than $$y$$ iff $$x \leq y$$ and $$x \neq y$$. One denotes this as $$x<y$$.


## Theorem Strict Transitivity

**Strict Transitivity**: _For all $$x,y,z\in{{N}}$$, if $$x<y$$ and $$y<z$$, then $$x<z$$_.

## Theorem Semi-Strict Transitivity

**Semi-Strict Transitivity**: _For all $$x,y,z\in{{N}}$$, if either $$x \leq y$$ and $$y<z$$, or $$x<y$$ and $$y \leq z$$, then $$x<z$$_.


## Theorem TotalityAlt

**Totality (Alternative Form)**: _For every $$x,y\in{{N}}$$, exactly one of $$x<y$$, $$x=y$$ or $$y<x$$ is true_.

> The proofs of these are easy. I leave them for the readers to fill in.


## Failure of Totality for Divisibility

The reason why there are no divisibility analogues for the totality theorems is that divisibility is not total. For example, $$S(S(0))=2$$ neither is divisible by nor divides $$S(S(S(0)))=3$$.

To see this, suppose one had a natural $$y$$ such that $$S(S(0)) \cdot y=S(S(S(0)))$$. Now,
$$
S(S(0)) \cdot y=y \cdot S(S(0))=y \cdot S(0)+y=y+y
$$
Clearly, $$y$$ can't be $$0$$, lest $$3$$ be $$0$$. Hence, one has a natural $$y'$$ such that $$S(y')=y$$. Also, $$y$$ can't be $$S(0)=1$$, lest $$3$$ be the same as $$2$$. So, one has another natural $$y''$$ such that $$S(y'')=y'$$. Hence, $$y=S(S(y''))$$. Thus, after some algebra,
$$
y+y=S(S(y''))+S(S(y''))=\ldots=S(S(S(S(y''+y''))))
$$
But then $$S(S(S(S(y''+y''))))=S(S(0)) \cdot y=S(S(S(0)))$$; so, after three applications of the injectivity of $$S$$, one gets $$S(y''+y'')=0$$, which is absurd.

Conversely, suppose one has a natural $$y$$ such that $$S(S(S(0))) \cdot y=S(S(0)))$$. Then, again,
$$
S(S(S(0))) \cdot y=\ldots=(y+y)+y
$$
As before, $$2$$ can't be $$0$$ so that there is a natural $$y'$$ such that $$S(y')=y$$. Hence,
$$
(y+y)+y=(S(y')+S(y'))+S(y')=\ldots=S(S(S(y')))
$$
So, if $$S(S(S(y')))=S(S(0))$$, then $$S(y')=0$$, which is, again, absurd.