{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


## Theorem NBFPS

_There exist no bijections from $${{F}}(n)$$ to a proper subset of it_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. $${{F}}(0)={{E}}$$ has no proper subsets. So, in fact, it is impossible to have functions, let alone bijections, from $${{F}}(0)$$ to a proper subset of it.
2. Now say the claim holds for an $$n\in{{N}}$$ i.e. there exist no bijections from $${{F}}(n)$$ to a proper subset of it. Then, by the contrapositive of the [previous lemma](FunctionsOverFinI.md#lemma-bfsxrbfx), there can be no bijections from $${{F}}(S(n))$$ to a strict subset of it.

> Rephrasing the above theorem a little bit, one gets the following: if there is a bijection from $${{F}}(n)$$ to a subset of itself, then that subset is the whole of $${{F}}(n)$$.


## Corollary NoBijFnFk

_There exist no bijections from $${{F}}(n)$$ to $${{F}}(k)$$ where $$k<n$$_.


## Corollary ifInjthenBij

_If $$f:{{F}}(n) \to Y\subseteq{{F}}(n)$$ is an injection, then it is also a surjection (thus, a bijection) and, in fact, $$Y={{F}}(n)$$_.

**Proof**: By [Lemma RSIS](FunctionsOverFinI.md#lemma-rsis), restricting $$f$$'s codomain to $$f({{F}}(n))$$ produces a bijection. So, by the [previous theorem](#theorem-nbfps), it must be that $$f({{F}}(n))={{F}}(n)$$. But then, by [Lemma ISSI](FunctionsOverFinI.md#lemma-issi), $${{F}}(n)=f({{F}}(n)) \subseteq Y$$. Hence, $$Y={{F}}(n)$$ (as $$Y\subseteq{{F}}(n)$$ by hypothesis), so that $$f({{F}}(n))=Y$$. But this means precisely that $$f$$ is surjective.


## Corollary FnFkInjthenSurj

_If there is an injection from $${{F}}(n)$$ to $${{F}}(k)$$ where $$k \leq n$$, then it also a surjection and, in fact, $$k=n$$_.


&nbsp;
> There is also a surjective analog of [Corollary ifInjthenBij](#corollary-ifinjthenbij). For that one needs an additional concept from informal set theory. Recall that for any function $$f:X \to Y$$, one has the set $$
f^{-1}(y)=\{x \in X:\ f(x)=y\} \subseteq X
$$ given any $$y \in Y$$. Thus, $$f$$ being surjective means precisely that $$f^{-1}(y)\neq{{E}}$$ for any $$y \in Y$$.


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


## Lemma LInvBijThenBij

**Left Inverse of a Bijection is a Bijection**: _If one has a function $$f:X \to Y$$ and a bijection $$f':Y \to X$$ where $$f(f'(y))=y$$ for all $$y \in Y$$, then $$f$$ is bijection_.

> I leave the proof of this simple but very general set-theoretic fact to the readers.


## Corollary ifSurjthenBij

_If $$f:{{F}}(n)\to{{F}}(n)$$ is an surjection, then it is also a bijection_.

> This result is a straightforward application of the previous two lemmas. As with the previous lemma, I leave the readers to fill in the relevant details here.