{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


> Sets of the form $${{F}}(n)$$ have special properties that are not satisfied by arbitrary sets. In this section, a few intermediate results are developed to warm up to these peculiar properties.


## Lemma SFSxWSFx

**Subset of $${{F}}(S(n))$$ Without $$n$$ is Subset of $${{F}}(n)$$**: _$$U\subseteq{{F}}(n)$$ if $$U\subseteq{{F}}(S(n))$$ and $$n \notin U$$_.

**Proof**: Fix any $$u \in U$$; I show that $$u\in{{F}}(n)$$. Well, since $$n \notin U$$, $$u \neq n$$. At the same time, since $$U\subseteq{{F}}(S(n))$$, $$u\in{{F}}(S(n))$$ i.e. $$u\in{{N}}$$ and $$u<S(n)$$; thus, by a lemma from the previous chapter, $$u \leq n$$. So, altogether, $$u \leq n$$ and $$u \neq n$$ i.e. $$u<n$$. Hence, $$u\in{{F}}(n)$$.


## Lemma BFSxSDBFxSS

**Bijection from $${{F}}(S(n))$$ to Set Descends to Bijection from $${{F}}(n)$$ to Subset**: _Fix an $$n\in{{N}}$$_. _If for an arbitrary set $$X$$ one has a bijection $$f:{{F}}(S(n)) \to X$$, then for any $$x \in X$$, one has a bijection $$f':{{F}}(n) \to X'=X\setminus\{x\}$$_.

**Proof**: Since $$f$$ is surjective, there is a natural $$k\in{{F}}(S(n))$$ such that $$f(k)=x$$. There are two cases to consider:

<span style="text-decoration: underline;">_**Suppose first that $$k=n$$:**_</span> Restrict $$f$$ to the domain $${{F}}(n)$$ and the codomain $$f({{F}}(n))$$ as described in [Lemma RSIS](../SetsOverview.md#lemma-rsis). By the lemma, this restriction is bijective. It remains to be seen that
$$
f({{F}}(n))=X\setminus\{x\}=X'
$$

To see this, one first shows that $$f({{F}}(n)) \subseteq X'$$. Well, notice that by [Lemma ISSI](../SetsOverview.md#lemma-issi) and the fact that $${{F}}(n)\subseteq{{F}}(S(n))$$, one has $$f({{F}}(n)) \subseteq X$$. Also, $$x=f(n) \notin f({{F}}(n))$$ for if it were, there would be some $$k'\in{{F}}(n)$$ such that $$f(k')=x$$. So by the injectivity of $$f$$, one would have $$n=k'\in{{F}}(n)$$, which is a contradiction.

Next, one shows that $$X' \subseteq f({{F}}(n))$$. So let $$y \in X'$$. Then certainly $$y \in X$$. So by the surjectivity of $$f$$, there is some $$k'\in{{F}}(S(n))$$ such that $$f(k')=y$$. But as $$y$$ is in $$X'$$ which does not contain $$x$$,
$$
f(k')=y \neq x=f(n)
$$ Hence, $$k' \neq n$$ because $$f$$, being a function, cannot map a single value to two different values. Altogether, one then has $$k'\in{{F}}(n)$$ so that $$y \in f({{F}}(n))$$ as there is the element $$k'$$ in $${{F}}(n)$$ mapping to $$y$$.

Thus, the restriction mentioned in the first paragraph is the required bijection from $${{F}}(n)$$ to $$X'$$.

<span style="text-decoration: underline;">_**Suppose next that $$k \neq n$$:**_</span> In this case, $$k\in{{F}}(n)$$. Define $$f':{{F}}(n) \to X'$$ thus:
$$
f'(\nu)=\begin{cases} f(\nu) &\text{if } \nu \neq k \\
                      f(n)   &\text{if } \nu=k \end{cases}
$$

* Now, firstly, this function does indeed map values into $$X'$$ as advertised. To see this, fix any $$\nu\in{{F}}(n)$$. If $$\nu \neq k$$, then by the injectivity of $$f$$
$$
X \ni f'(\nu)=f(\nu) \neq f(k)=x
$$ If $$\nu=k$$, then by injectivity again,
$$
x=f(k) \neq f(n)=f'(\nu) \in X
$$ In both cases, $$f'(\nu) \neq x$$ and $$f'(\nu) \in X$$. Hence, $$f'(\nu) \in X'$$.

* Secondly, $$f'$$ is injective. For, suppose $$\nu \neq \tilde{\nu}$$ for $$\nu,\tilde{\nu}\in{{F}}(n)$$. If neither $$\nu$$ nor $$\tilde{\nu}$$ is $$k$$, then by injectivity
$$
f'(\nu)=f(\nu) \neq f(\tilde{\nu})=f'(\tilde{\nu})
$$
Otherwise w.l.o.g. assume that $$\tilde{\nu}=k$$. Then, $$\nu \neq k$$ (so $$f'(\nu)=f(\nu)$$). Hence, by injectivity applied to $$\nu \neq n$$ (which happens because $$\nu\in{{F}}(n)$$)
$$
f'(\nu)=f(\nu) \neq f(n)=f'(k)=f'(\tilde{\nu})
$$
Thus, in both cases, $$\nu \neq \tilde{\nu}$$ implies $$f'(\nu) \neq f'(\tilde{\nu})$$ i.e. $$f'$$ is injective.

* Thirdly, $$f'$$ is surjective. Indeed, take any $$y\in X'$$. Since $$f$$ is bijective, $$f(\nu)=y$$ for some $$\nu\in{{F}}(S(n))$$. Now, since $$f(\nu)=y \neq x=f(k)$$ (because $$y\in X\setminus\{x\}$$) one must have $$\nu \neq k$$, lest $$f$$ map one value to multiple values. Now, $${{F}}(S(n))={{F}}(n)\cup\{n\}$$. So, either $$\nu=n$$ or $$\nu\in{{F}}(n)$$. For the former, note that $$k \neq \nu=n$$ so that $$k\in{{F}}(n)$$. But then, one has $$k\in{{F}}(n)$$ such that $$f'(k)=f(n)=f(\nu)=y$$. Otherwise, for the latter, since $$\nu \neq k$$ by before, $$f'(\nu)=f(\nu)=y$$; thus, again, one has $$\nu\in{{F}}(n)$$ such that $$f'(\nu)=y$$.


## Lemma BFSxRBFx

**Bijection from $${{F}}(S(n))$$ to Subset Restricts to Bijection from $${{F}}(n)$$ to Subset**: _Fix an $$n\in{{N}}$$_. _If one has a bijection $$f:{{F}}(S(n)) \to X$$ for some $$X\subset{{F}}(S(n))$$, then one has a bijection $$f':{{F}}(n) \to X'$$ for some $$X'\subset{{F}}(n)$$_.

**Proof**: There are two cases to consider:

<span style="text-decoration: underline;">_**Suppose first that $$n \notin X$$:**_</span> Thus, $$X\subseteq{{F}}(n)$$ by [Lemma SFSxWSFx](#lemma-sfsxwsfx). Now choose any $$x \in X$$; if at a loss, choose $$x=f(n)$$. Then, the [above lemma](#lemma-bfsxsdbfxss) gives a bijection from $${{F}}(n)$$ to $$X'=X\setminus\{x\}$$. Now, $$X'$$ is certainly a subset of $$X$$. Moreover, it is a strict subset of the same because $$X'$$ does not contain an element of $$X$$. Thus, it must also be a strict subset of $${{F}}(n)$$.

<span style="text-decoration: underline;">_**Suppose next that $$n \in X$$:**_</span> Then, the above lemma gives a bijection from $${{F}}(n)$$ to $$X'=X\setminus\{n\}$$. Note that $$X'$$, as a subset of $$X\subset{{F}}(S(n))$$, must also be a subset of $$F(S(n))$$. But, as $$X'$$ does not contain $$n$$, [Lemma SFSxWSFx](#lemma-sfsxwsfx) implies that $$X'\subseteq{{F}}(n)$$. Finally, as $$X$$ is a strict subset of $${{F}}(S(n))$$, some $$\nu\in{{F}}(S(n))$$ is not in $$X$$. This $$\nu$$ cannot be $$n$$ as it is being supposed that $$n$$ is in $$X$$. Thus, $$\nu\in{{F}}(n)$$. Also, $$\nu$$ cannot be in $$X'$$ since the latter is a subset of a set not containing $$\nu$$. In other words, $$X'$$ is missing an element $$\nu$$ of $${{F}}(n)$$ despite being a subset of $${{F}}(n)$$ i.e. $$X'\subset{{F}}(n)$$.