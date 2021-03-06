{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set U = "\\mathcal{U}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


## Theorem NBFPS

_There exist no bijections from $${{F}}(n)$$ to a proper subset of itself_.

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


## Lemma SurjInvBij

**Surjection produces Inverted Bijection**: _If $$f:{{F}}(n)\to{{F}}(n)$$ is an surjection, then there exists a bijection $$f':{{F}}(n)\to{{F}}(n)$$ such that $$f(f'(y))=y$$ for $$y\in{{F}}(n)$$_.

**Proof**: By theorem's hypothesis, $$f^{-1}(y)\neq{{E}}$$ and $$f^{-1}(y)\subseteq{{F}}(n)\subseteq{{N}}$$ for any $$y\in{{F}}(n)$$. Thus by well-ordering, for every $$y\in{{F}}(n)$$, there is a unique element $$\text{min}(f^{-1}(y)) \in f^{-1}(y)$$. So, the following function is automatically well-defined:
$$
f':{{F}}(n) \ni y\mapsto\text{min}(f^{-1}(y)) \in f^{-1}(y)\subseteq{{F}}(n)
$$

Next, for any $$y\in{{F}}(n)$$, $$f'(y)=\text{min}(f^{-1}(y)) \in f^{-1}(y)$$. Hence, by definition of the set $$f^{-1}(y)$$, $$f(f'(y))=y$$.

Finally, to show this function's bijectivity, I will instead show its injectivity. That it is surjective will then follow from [Corollary ifInjthenBij](#corollary-ifinjthenbij). So, suppose for $$y,y'\in{{F}}(n)$$ that $$f'(y)=f'(y')$$. Then, by the definition of $$f'$$, $$\text{min}(f^{-1}(y))=\text{min}(f^{-1}(y'))$$. So,
$$
y=f(\text{min}(f^{-1}(y)))=f(\text{min}(f^{-1}(y')))=y'
$$
since $$f$$, being a function, maps values to unique values.


## Corollary ifSurjthenBij

_If $$f:{{F}}(n)\to{{F}}(n)$$ is a surjection, then it is also a bijection_.

> This result is a straightforward application of the previous lemma and [Lemma LInvBijThenBij](../SetsOverview.md#lemma-linvbijthenbij). I leave it for the readers to fill in the relevant details.


## Lemma BFxSABFSxSS

**Bijection from $${{F}}(n)$$ to Set Ascends to Bijection from $${{F}}(S(n))$$ to Superset**: _Fix an $$n\in{{N}}$$_. _If for an arbitrary set $$X$$ one has a bijection $$f:{{F}}(n) \to X$$, then for arbitrary $$y\in{{U}}$$ such that $$y \notin X$$, one has a bijection $$\tilde{f}:{{F}}(S(n)) \to X\cup\{y\}$$_.

**Proof Sketch**: Define $$\tilde{f}:{{F}}(S(n)) \to X\cup\{y\}$$ thus:
$$
\tilde{f}(x)=\begin{cases} f(x) &\text{if } x<n \\
                           y    &\text{if } x=n \end{cases}
$$ Now, every $$x\in{{F}}(S(n))$$ is either less that $$n$$ or is $$n$$. If $$x<n$$, $$\tilde{f}(x)$$ refers to the unique value $$f(x)$$ in $$X$$ since $$f$$ is a well-defined by hypothesis. If $$x=n$$, $$\tilde{f}(x)$$ obviously refers to the unique value $$y \in X\cup\{y\}$$. In both cases, $$\tilde{f}$$ maps each value in its domain to a unique value in its codomain, making the function well-defined. A proof of bijectivity is left to the reader.


## Theorem SFnBSFk

**Subset of $${{F}}(n)$$ is Bijective to Some $${{F}}(k)$$**: _Fix an $$n\in{{N}}$$_. _For every $$U\subseteq{{F}}(n)$$, there is a $$k \leq n$$ with some bijection from $${{F}}(k)$$ to $$U$$_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. If $$U\subseteq{{F}}(0)={{E}}$$, then $$U={{E}}$$. So, there is a $$k$$, namely $$0$$, and a bijection, namely
$$
\text{id}_{{E}}:{{E}}={{F}}(k)={{F}}(0) \ni x\mapsto x \in U={{E}}
$$
This function is vacuously well-defined and vacuously bijective.
2. Now suppose the claim is true for $${{F}}(n)$$. Consider any $$U\subseteq{{F}}(S(n))$$. If $$n \notin U$$, then certainly $$U\subseteq{{F}}(n)$$. So immediately, the inductive hypothesis gives a $$k \leq n<S(n)$$ and a bijection $${{F}}(k) \to U$$. Now, suppose $$n \in U$$. Here, $$U\setminus\{n\}\subseteq{{F}}(n)$$ and the inductive hypothesis gives a $$k \leq n<S(n)$$ and a bijection $$f:{{F}}(k) \to U\setminus\{n\}$$. Lift this smaller bijection to a bigger bijection from $$f^U:{{F}}(S(k))$$ to $$U$$ as per the lemma above. Note furthermore that as $$k<S(n)$$, $$S(k) \leq S(n)$$. Hence, this bijection satisfies the theorem's requirements as applied to $${{F}}(S(n))$$.


## Corollary SFnBSUFk

**Subset of $${{F}}(n)$$ is Bijective to Some Unique $${{F}}(k)$$**: _Fix an $$n\in{{N}}$$_. _For every $$U\subseteq{{F}}(n)$$, there is **exactly one** $$k \leq n$$ with some bijection from $${{F}}(k)$$ to $$U$$_.

**Proof**: Continuing from the end of the previous proof, only the uniqueness part remains to be shown. For this, the reader should keep in their minds [results about functions shown earlier](../SetsOverview.md#functions-as-sets). So, suppose there is some other $$\tilde{k}\in{{N}}$$ with a bijection $${{F}}(\tilde{k}) \to U$$. Now, totality gives either $$\tilde{k} \leq k$$ or $$k\leq\tilde{k}$$. Assume w.l.o.g. that $$\tilde{k} \leq k$$; the other case is handled similarly. Continuing, the bijection associated with $$\tilde{k}$$ induces a left inverse $$\phi:U\to{{F}}(\tilde{k})$$ that is also a bijection. Composing, one gets a bijectiion $$(\phi \circ f):{{F}}(k)\to{{F}}(\tilde{k})$$. Since $$\tilde{k} \leq k$$, it must be that $${{F}}(\tilde{k})\subseteq{{F}}(k)$$. But $${{F}}(k)$$ is not bijective to any of its proper subsets. Hence, $${{F}}(\tilde{k})={{F}}(k)$$, so that $$\tilde{k}=k$$.