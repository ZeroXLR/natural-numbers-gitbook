{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


## Theorem NBFPS

_There exist no bijections from $${{F}}(n)$$ to a proper subset of it_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. $${{F}}(0)={{E}}$$ has no proper subsets. So, trivially, $${{F}}(0)$$ has no proper subsets bijective to it.
2. Now suppose there are no bijections from $${{F}}(n)$$ to a proper subset of it. Then, by the contrapositive of the [previous lemma](FunctionsOverFinI.md#lemma-bfsxrbfx), $${{F}}(S(n))$$ has no bijections to a strict subset of it.

> Rephrasing the above theorem a little bit, one gets the following: if there is a bijection from $${{F}}(n)$$ to a subset of itself, then that subset is the whole of $${{F}}(n)$$.


## Corollary NoBijFnFk

_There exist no bijections from $${{F}}(n)$$ to $${{F}}(k)$$ where $$k<n$$_.


## Corollary ifInjthenBij

_If $$f:{{F}}(n) \to Y\subseteq{{F}}(n)$$ is injective, then it is also surjective and, in fact, $$Y={{F}}(n)$$_.

**Proof**: By [Lemma RSIS](../SetsOverview.md#lemma-rsis), restricting $$f$$'s codomain to $$f({{F}}(n))$$ produces a bijection. So, by the [previous theorem](#theorem-nbfps), it must be that $$f({{F}}(n))={{F}}(n)$$. But then, by [Lemma ISSI](../SetsOverview.md#lemma-issi), $${{F}}(n)=f({{F}}(n)) \subseteq Y$$. Hence, $$Y={{F}}(n)$$ (as $$Y\subseteq{{F}}(n)$$ by hypothesis), so that $$f({{F}}(n))=Y$$. But this means precisely that $$f$$ is surjective.


## Corollary FnFkInjthenSurj

_If there is an injection from $${{F}}(n)$$ to $${{F}}(k)$$ where $$k \leq n$$, then it also a surjection and, in fact, $$k=n$$_.


&nbsp;
> There is also a surjective analog of [Corollary ifInjthenBij](#corollary-ifinjthenbij).


## Lemma SurjInvInj

**Surjection produces Inverted Injection**: _If $$f:{{F}}(n)\to{{F}}(n)$$ is an surjection, then there exists an bijection $$f':{{F}}(n)\to{{F}}(n)$$ such that $$f(f'(y))=y$$ (for $$y\in{{F}}(n)$$)_.

**Proof**: By the hypothesis of the theorem, $$f^{-1}(y)\neq{{E}}$$ and $$f^{-1}(y)\subseteq{{F}}(n)\subseteq{{N}}$$ for any $$y\in{{F}}(n)$$. Thus, by well-ordering, for every $$y\in{{F}}(n)$$, there is a unique element $$\text{min}(f^{-1}(y)) \in f^{-1}(y)$$. So, the following function is automatically well-defined:
$$
f':{{F}}(n) \ni y\mapsto\text{min}(f^{-1}(y)) \in f^{-1}(y)\subseteq{{F}}(n)
$$

Next, for any $$y\in{{F}}(n)$$, $$f'(y)=\text{min}(f^{-1}(y)) \in f^{-1}(y)$$. Hence, by definition of the set condition of $$f^{-1}(y)$$, $$f(f'(y))=y$$.

Finally, to check that this function is bijective, I will instead check that it is injective. That it is surjective will then follow from [Corollary ifInjthenBij](#corollary-ifinjthenbij). So, suppose for $$y,y'\in{{F}}(n)$$ that $$f'(y)=f'(y')$$; one now needs to show that $$y=y'$$. Well, by the definition of $$f'$$, $$\text{min}(f^{-1}(y))=\text{min}(f^{-1}(y'))$$. So,
$$
y=f(\text{min}(f^{-1}(y)))=f(\text{min}(f^{-1}(y')))=y'
$$
since $$f$$ is a function that maps equal values to equal values.


## Corollary ifSurjthenBij

_If $$f:{{F}}(n)\to{{F}}(n)$$ is an surjection, then it is also a bijection_.

> This result is a straightforward application of the previous lemma and [Lemma LInvBijThenBij](../SetsOverview.md#lemma-linvbijthenbij). I leave it for the readers to fill in the relevant details.


&nbsp;
> I end this section with another important result about $${{F}}$$. It partially alleviates the limitations put on subsets of $${{F}}(n)$$ by the [main theorem at the beginning](#theorem-nbfps). It says that even though there are no bijections between $${{F}}(n)$$ and a proper subset of it, there is a $$k<n$$ such that one has a bijection between $${{F}}(k)$$ and that proper subset.


## Theorem SFnBSFk

**Subset of $${{F}}(n)$$ is Bijective to Some $${{F}}(k)$$**: _Fix an $$n\in{{N}}$$_. _For every $$U\subseteq{{F}}(n)$$, there is a $$k \leq n$$ and a bijection from $${{F}}(k)$$ to $$U$$_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. If $$U\subseteq{{F}}(0)={{E}}$$, then $$U={{E}}$$. So, there is a $$k$$, namely $$0$$, and a bijection, namely
$$
\text{id}_{{E}}:{{E}}={{F}}(k)={{F}}(0) \ni x\mapsto x \in U={{E}}
$$
This function is vacuously well-defined and vacuously bijective.
2. Now suppose the claim is true for $${{F}}(n)$$. Consider any $$U\subseteq{{F}}(S(n))$$. If $$n \notin U$$, then certainly $$U\subseteq{{F}}(n)$$. So, one is done immediately &mdash; the inductive hypothesis guarantees that there is a $$k \leq n<S(n)$$ and a bijection $${{F}}(k) \to U$$. So, suppose $$n \in U$$. Here, $$U\setminus\{n\}\subseteq{{F}}(n)$$ and the inductive hypothesis gives a $$k \leq n<S(n)$$ and a bijection $$f:{{F}}(k) \to U\setminus\{n\}$$. Lift this smaller bijection to a bigger bijection $$f^U:{{F}}(S(k)) \to U$$ thus:
$$
f^U(x)=\begin{cases} f(x) &\text{if } x \neq k \\
                     n    &\text{if } x=k \end{cases}
$$
Showing that this function definition is well-defined and bijective is left as an easy exercise for the reader. Note, furthermore, that since $$k<S(n)$$, $$S(k) \leq S(n)$$. Hence, this bijection does satisfy the requirements of the theorem.