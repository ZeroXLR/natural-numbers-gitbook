{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


> Having explored order, I will now explore properties of the family of sets $${{F}}:{{N}}\to{{P}}{{N}}$$. As a reminder, I used the recursion theorems earlier to show that such a family $${{F}}$$ exists such that $${{F}}(0)={{E}}$$ and $${{F}}(S(n))={{F}}(n)\cup\{n\}$$.


## Theorem FinAlt

**Alternative Characterization of Fin**: _$${{F}}(n)=\{x\in{{N}}:\ x<n\}$$_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. Since $$0$$ is the least natural number, there are no natural numbers strictly less than $$n$$ (by alternative totality). So, $$\{x\in{{N}}:\ x<0\}={{E}}={{F}}(0)$$.
2. Now suppose $${{F}}(n)=\{x\in{{N}}:\ x<n\}$$. Consider $$x\in{{F}}(S(n))={{F}}(n)\cup\{n\}$$. Then, either $$x=n<S(n)$$ or $$x\in{{F}}(n)$$, so that by the induction hypothesis, $$x<n<S(n)$$, so that by strict transitivity, $$x<S(n)$$. Either way, $$x\in\{x\in{{N}}:\ x<S(n)\}$$. On the other hand, suppose $$x\in\{x\in{{N}}:\ x<S(n)\}$$; then $$x<S(n)$$. By alternative totality, it is not the case that $$S(n) \leq x$$, so that by the contrapositive of [Lemma SxLESGx](../Order/WellOrder.md#lemma-sxlesgx), it is not the case that $$n<x$$. Hence, by strict totality, either $$x<n$$ or $$x=n$$ i.e.
$$
x\in\{x\in{{N}}:\ x<n\}\cup\{n\}={{F}}(n)\cup\{n\}={{F}}(S(n))
$$
Putting both of this together, one has that $${{F}}(S(n))=\{x\in{{N}}:\ x<S(n)\}$$.

This is a important result and it is, henceforth, assumed implicitly in the rest of this book.


## Corollary FkSSFn

_For $$n,k\in{{N}}$$, $$k<n$$ iff $${{F}}(k)\subset{{F}}(n)$$_.

**Proof**: Let $$x\in{{F}}(k)$$. Then, by the theorem above, $$x\in{{N}}$$ and $$x<k$$, so that, by strict transitivity and $$k<n$$, $$x<n$$. Hence, $$x\in{{F}}(n)$$. Thus, one has that $${{F}}(k)\subseteq{{F}}(n)$$. At the same time, note that $$k\in{{F}}(n)$$ since $$k<n$$. However, obviously $$k=k$$, so that $$k<k$$ is impossible by alternative totality; thus, $$k\notin{{F}}(k)$$. So, it is not the case that $${{F}}(n)\subseteq{{F}}(k)$$. Along with the result from the previous paragraph, this implies that $${{F}}(k)\subset{{F}}(n)$$.

Conversely, suppose $${{F}}(k)\subset{{F}}(n)$$. Then, there exists an $$x$$ in $${{F}}(n)$$ that is not in $${{F}}(k)$$. Hence, $$x<n$$ but not $$x<k$$. By applying alternative totality to the latter, one gets that $$k \leq x$$. And, by applying semi-strict transitivity to $$k \leq x$$ and $$x<n$$, one gets that $$k<n$$, which was to be proven.


## Corollary FinInj

**$${{F}}$$ is Injective**: _For $$n,k\in{{N}}$$, $$k=n$$ iff $${{F}}(k)={{F}}(n)$$_.

**Proof**: The forward direction is clear from the fact that $${{F}}$$ is a function that maps equals to equals. For the other direction, if $${{F}}(k)={{F}}(n)$$, then, every element in $${{F}}(k)$$ must be in $${{F}}(n)$$ and vice versa. Thus, it is neither the case that $${{F}}(k)\subset{{F}}(n)$$ nor the case that $${{F}}(n)\subset{{F}}(k)$$. Hence, by the corollary above, it is neither the case that $$k<n$$ nor the case that $$n<k$$. So, by alternative totality, $$k=n$$.

&nbsp;
> Combining the two corollaries above immediately yields:

## Corollary FkSFn

_For $$n,k\in{{N}}$$, $$k \leq n$$ iff $${{F}}(k)\subseteq{{F}}(n)$$_.


&nbsp;
> Now I turn to an alternative characterization of induction using $${{F}}$$. This principle of induction is often termed **strong induction** while the usual one, characterized by [Peano axiom 4](../Peano.md#definition-peano-axioms), is called **weak induction**. This is somewhat ironic considering the fact that one can derive strong induction from weak induction, as I am about to do. The reason that strong induction is considered "strong" is because its _inductive hypothesis_ is indeed logically stronger as one shall see:


## Theorem InductionAlt

**Alternative Principle of Induction**: _If $${{S}}$$ is a set where for every $$n\in{{N}}$$, $${{F}}(n)\subseteq{{S}}$$ implies $$n\in{{S}}$$, then $${{N}}\subseteq{{S}}$$_.

**Proof**: Suppose $${{S}}$$ is a set satisfying the condition of the above theorem. I will use normal induction on
$$
{{S}}'=\{x\in{{N}}:\ {{F}}(x)\subseteq{{S}}\}
$$
to first show that for every $$x\in{{N}}$$, $${{F}}(x)\subseteq{{S}}$$.
1. Well, the empty set is a subset of every set; so $${{F}}(0)={{E}}\subseteq{{S}}$$. Hence, $$0\in{{S}}'$$.
2. Suppose that $$x\in{{S}}'$$ i.e. $${{F}}(x)\subseteq{{S}}$$. Since $${{S}}$$ satisfies the condition of the theorem, this implies that $$x\in{{S}}$$. Thus, $${{F}}(S(x))={{F}}(x)\cup\{x\}\subseteq{{S}}$$ i.e. $$S(x)\in{{S}}'$$.

Hence, by normal induction, for any given natural $$x$$, $${{F}}(x)\subseteq{{S}}$$; finally, using the condition in the theorem, on this result, yields that the given $$x$$ is in $${{S}}$$. Hence, $${{N}}\subseteq{{S}}$$.

The above theorem is often stated in terms of properties: if $$\phi$$ is an unary property such that $$\phi(0)$$ is true and for every $$n\in{{N}}$$, if $$\phi(k)$$ being true for all $$k\in{{N}}$$ such that $$k<n$$ implies $$\phi(n)$$ being true, then $$\phi$$ is true for all of $${{N}}$$.


&nbsp;
> One can also do induction over each $${{F}}(n)$$ instead of over the whole of $${{N}}$$ itself. One can use this, for instance, to show properties about natural numbers within a bounded range.


## Theorem InductionFin

**Finite Induction**: _Fix any $$n\in{{N}}$$_. _Now suppose $${{S}}$$ is a set such that_:

* _$$0\in{{S}}$$_
* _$$x\in{{S}}$$ and $$S(x)<n$$ imply $$S(x)\in{{S}}$$_

_Then $${{F}}(n)\subseteq{{S}}$$_.

**Proof**: Fix a natural $$n$$ and a set $${{S}}$$ that satisfies the hypotheses of the theorem. I will now show that $${{F}}(n)\subseteq{{S}}$$. However, I will do so, in a slightly round-about way: I will show, in fact, that for all $$y\in{{N}}$$, if $$y\in{{F}}(n)$$, then $$y\in{{S}}$$. This rephrasing of $${{F}}(n)\subseteq{{S}}$$ allows me to do normal induction on $$y$$:

1. By the hypotheses, $$0\in{{S}}$$. So, the consequent being true, the implication, "if $$0\in{{F}}(n)$$, then $$0\in{{S}}$$" is always true.
2. Now suppose that the implication holds for some $$y$$. To show now that the implication holds for $$S(y)$$, assume the antecedent of the implication: $$S(y)\in{{F}}(n)$$; thus, $$S(y)<n$$. Now, since $$y<S(y)$$, one also has that $$y<n$$ (via transitivity), so that $$y\in{{F}}(n)$$. Hence, since the implication holds for $$y$$, it must be that $$y\in{{S}}$$. In summary then, $$y\in{{S}}$$ and $$S(y)<n$$. So, given that $${{S}}$$ satisfies the hypotheses of the theorem, $$S(y)\in{{S}}$$.

This completes the induction. As usual, one can state this result in terms of properties. Fix an $$n\in{{N}}$$. If $$\phi$$ is an unary property such that $$\phi(0)$$ is true and, for $$x\in{{N}}$$, if $$\phi(x)$$ and $$S(x)<n$$ being true implies $$\phi(S(x))$$ being true, then $$\phi$$ is true for all of $${{F}}(n)$$.