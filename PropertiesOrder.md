{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> Having dealt with the albegraic properties of the natural numbers, I turn to explore their order properties. Recall that I defined the order thus: $$x \leq y$$ iff $$\exists n\in{{N}}\ [x+n=y]$$. Furthermore, I have already shown, quite trivially, that this order is **reflexive**.


## Lemma Transitivity

**Transitivity**: _For all $$x,y,z\in{{N}}$$, if $$x \leq y$$ and $$y \leq z$$, then $$x \leq z$$_.

**Proof**: If one assumes the hypothesis, then there are $$n,n'\in{{N}}$$ such that $$x+n=y$$ and $$y+n'=z$$. So, after substitution and [associativity](PropertiesAddAndMultiply.md#lemma-assocadd), $$(x+n)+n'=x+(n+n')=z$$. So, there is, in fact, a natural number $$n''=n+n'$$ such that $$x+n''=z$$ i.e. $$x \leq z$$.


&nbsp;
> The above proof aside, I will, henceforth, use the previously proved properties of the natural numbers without explicit warnings. I leave it to the readers to fill in the relevant details from the list of properties proved so far.


## Lemma NoInvs

> This lemma seems like it belongs in the previous chapter. However, its implications are most felt in this chapter on order. In particular, it will be an important step in showing that the order on the natural numbers is **antisymmetric**.

**No Non-Zero Natural Number has Inverses**: _For all $$x,y\in{{N}}$$, if $$x \neq 0$$, then $$x+y \neq 0$$_.

**Proof**: One doesn't even need induction for this. A simple case analysis suffices. Assume the lemma's hypothesis. Now, If $$y=0$$ then, obviously, $$x+y=x+0=x \neq 0$$. Otherwise, there is some natural number $$y'$$ such that $$S(y')=y$$. So now, $$x+y=x+S(y')=S(x+y')$$ and this can never be $$0$$.


## Lemma AntiSymmetry

**AntiSymmetry**: _For all $$x,y\in{{N}}$$, if $$x \leq y$$ and $$y \leq x$$, then $$x=y$$_.

**Proof**: Assuming the hypothesis yields that there are $$n,n'\in{{N}}$$ such that $$x+n=y$$ and $$y+n'=x$$. Hence, $$(x+n)+n'=x+(n+n')=x=x+0$$. After cancelling, $$n+n'=0$$. By the previous lemma, $$n=0$$. Hence, $$x=x+0=x+n=y$$.


## Interlude 0

Thus, the aforementioned order on $${{N}}$$ is **reflexive**, **transitive** and **antisymmetric**. It is therefore a _**partial order**_. In the context of a semiring, this partial order, if it exists, is actually called the _**canonical partial order**_ on the semiring. Not all semirings have a canonical partial order. For instance, if one defined the exact same relation on the integers, one would not get a partial order because antisymmetry would fail. One would get, for example, both $$0\leq 1$$ (because $$0+1=1$$) and $$1 \leq 0$$ (because $$1+(-1)=0$$); but clearly $$0 \neq 1$$ as integers. This happens _precisely_ because the integers have additive inverses; hence, the crucial [Lemma NoInvs](#lemma-noinvs) fails for them. It should not be very hard to convince oneself that any semiring that does not have inverses (for non-zero elements) has a canonical partial order. In the particular case of the natural numbers, however, one can go further still. It turns out that, here, one actually has a _**total order**_. This will the topic of discussion for the next part of this chapter.