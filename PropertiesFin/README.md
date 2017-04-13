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
2. Now suppose $${{F}}(n)=\{x\in{{N}}:\ x<n\}$$. Consider $$x\in{{F}}(S(n))={{F}}(n)\cup\{n\}$$. Then, either $$x=n<S(n)$$ or $$x\in{{F}}(n)$$, so that by the induction hypothesis, $$x<n<S(n)$$, so that by strict transitivity, $$x<S(n)$$. Either way, $$x\in\{x\in{{N}}:\ x<S(n)\}$$. On the other hand, suppose $$x\in\{x\in{{N}}:\ x<S(n)\}$$; then $$x<S(n)$$. By alternative totality, it is not the case that $$S(n) \leq x$$, so that by the contrapositive of [Lemma SxLESGx](../PropertiesOrder/WellOrder.md#lemma-sxlesgx), it is not the case that $$n<x$$. Hence, by strict totality, either $$x<n$$ or $$x=n$$ i.e.
$$
x\in\{x\in{{N}}:\ x<n\}\cup\{n\}={{F}}(n)\cup\{n\}={{F}}(S(n))
$$
Putting both of this together, one has that $${{F}}(S(n))=\{x\in{{N}}:\ x<S(n)\}$$.

This is a important result and it is, henceforth, assumed implicitly in the rest of this book.


## Corollary FkSSFn

_If $$n,k\in{{N}}$$ such that $$k<n$$, then $${{F}}(k)\subset{{F}}(n)$$_.

**Proof**: Let $$x\in{{F}}(k)$$. Then, by the theorem above, $$x\in{{N}}$$ and $$x<k$$, so that, by strict transitivity and $$k<n$$, $$x<n$$. Hence, $$x\in{{F}}(n)$$. Thus, one has that $${{F}}(k)\subseteq{{F}}(n)$$.

At the same time, note that $$k\in{{F}}(n)$$ since $$k<n$$. However, obviously $$k=k$$, so that $$k<k$$ is impossible by alternative totality; thus, $$k\notin{{F}}(k)$$. So, it is not the case that $${{F}}(n)\subseteq{{F}}(k)$$. Along with the result from the previous paragraph, this implies that $${{F}}(k)\subset{{F}}(n)$$.


&nbsp;
> Now I turn to an alternative characterization of induction using $${{F}}$$. This principle of induction is often termed **strong induction** while the usual one, characterized by [Peano axiom 4](../WarmUp.md#definition-peano-axioms), is called **weak induction**. This is somewhat ironic considering the fact that one can derive strong induction from weak induction, as I am about to do. The reason that strong induction is considered "strong" is because its _inductive hypothesis_ is indeed logically stronger as one shall see:


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
> I next present a lemma which, while simple, is used often in the main lemma of the next section. So, it is worth spelling it out completely:


## Lemma SFSxWSFx

**Subset of $${{F}}(S(n))$$ Without $$n$$ is Subset of $${{F}}(n)$$**: _For any $$U\subseteq{{F}}(S(n))$$ such that $$n \notin U$$, $$U\subseteq{{F}}(n)$$_.

**Proof**: Fix any $$u \in U$$. Then, since $$n \notin U$$, $$u \neq n$$. At the same time, since $$U\subseteq{{F}}(S(n))$$, $$u\in{{F}}(S(n))$$ i.e. $$u\in{{N}}$$ and $$u<S(n)$$; thus, by a lemma from the previous chapter, $$u \leq n$$. So, altogether, $$u \leq n$$ and $$u \neq n$$ i.e. $$u<n$$. Hence, $$u\in{{F}}(n)$$. Since the previous argument is true for arbitrary $$u$$, $$U\subseteq{{F}}(n)$$.