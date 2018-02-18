{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


> Sets of the form $${{F}}(n)$$ have special properties that are not satisfied by arbitrary sets. In this section, I present a lemma that is crucial in proving these peculiar properties. To warm up towards this important lemma, I begin with an easy result:


## Lemma SFSxWSFx

**Subset of $${{F}}(S(n))$$ Without $$n$$ is Subset of $${{F}}(n)$$**: _$$U\subseteq{{F}}(n)$$ if $$U\subseteq{{F}}(S(n))$$ and $$n \notin U$$_.

**Proof**: Fix any $$u \in U$$; I show that $$u\in{{F}}(n)$$. Well, since $$n \notin U$$, $$u \neq n$$. At the same time, since $$U\subseteq{{F}}(S(n))$$, $$u\in{{F}}(S(n))$$ i.e. $$u\in{{N}}$$ and $$u<S(n)$$; thus, by a lemma from the previous chapter, $$u \leq n$$. So, altogether, $$u \leq n$$ and $$u \neq n$$ i.e. $$u<n$$. Hence, $$u\in{{F}}(n)$$.


## Lemma BFSxRBFx

**Bijection from $${{F}}(S(n))$$ to Subset Restricts to Bijection from $${{F}}(n)$$ to Subset**: _Fix an $$n\in{{N}}$$_. _If one has a bijection $$f:{{F}}(S(n)) \to X$$ for some $$X\subset{{F}}(S(n))$$, then one has a bijection $$f':{{F}}(n) \to X'$$ for some $$X'\subset{{F}}(n)$$_.

**Proof**: There are two cases to consider:

<span style="text-decoration: underline;">_**Suppose first that $$n \notin X$$:**_</span> Thus, $$X\subseteq{{F}}(n)$$ by [Lemma SFSxWSFx](#lemma-sfsxwsfx). Now, restrict $$f$$ to the domain $${{F}}(n)$$ and the codomain $$X'=f({{F}}(n))$$ as described in [Lemma RSIS](../SetsOverview.md#lemma-rsis). By the lemma, this restriction is bijective. Also, since $${{F}}(n) \subset {{F}}(S(n))$$, by [Lemma ISSI](../SetsOverview.md#lemma-issi),
$$
X'=f({{F}}(n)) \subset f({{F}}(S(n)))=X \subseteq {{F}}(n)
$$ Thus, this restriction is the required bijection from $${{F}}(n)$$ to a strict subset of itself.

<span style="text-decoration: underline;">_**Suppose next that $$n \in X$$:**_</span> Then, as $$f$$ is a bijection, $$f(x_n)=n$$ for some $$x_n\in{{F}}(S(n))$$. Now define $$f':{{F}}(n) \to X'$$ where $$X'=X\setminus\{n\}$$ thus:
$$
f'(x)=\begin{cases} f(x) &\text{if } x \neq x_n \\
                    f(n) &\text{if } x=x_n \end{cases}
$$
The above definition is still valid if $$x_n\notin{{F}}(n)$$; in that case, its second alternative is just redundant. Also, note that $$X\setminus\{n\}\subseteq{{F}}(n)$$ by [Lemma SFSxWSFx](#lemma-sfsxwsfx).

* Now, firstly, this function does indeed map values into $$X\setminus\{n\}$$ as advertised. To see this, fix any $$x\in{{F}}(n)$$. If $$x \neq x_n$$, then by the injectivity of $$f$$
$$
X \ni f'(x)=f(x) \neq f(x_n)=n
$$ If $$x=x_n$$, then $$x_n\in{{F}}(n)$$ so that $$x_n \neq n$$. Hence, by injectivity again,
$$
n=f(x_n) \neq f(n)=f'(x) \in X
$$ In both cases, $$f'(x) \neq n$$ and $$f'(x) \in X$$. Hence, $$f'(x) \in X\setminus\{n\}=X'$$.

* Secondly, $$f'$$ is injective. For, suppose $$x \neq \tilde{x}$$ for $$x,\tilde{x}\in{{F}}(n)$$. If neither $$x$$ nor $$\tilde{x}$$ is $$x_n$$, then by injectivity
$$
f'(x)=f(x) \neq f(\tilde{x})=f'(\tilde{x})
$$
Otherwise w.l.o.g. assume that $$\tilde{x}=x_n$$. Then, $$x_n\in{{F}}(n)$$ so that $$f'(x_n)$$ makes sense. Also, in this case, $$x \neq x_n$$ (so $$f'(x)=f(x)$$). Hence, by injectivity applied to $$x \neq n$$ (which happens because $$x\in{{F}}(n)$$)
$$
f'(x)=f(x) \neq f(n)=f'(x_n)=f'(\tilde{x})
$$
Thus, in both cases, $$x \neq \tilde{x}$$ implies $$f'(x) \neq f'(\tilde{x})$$ i.e. $$f'$$ is injective.

* Thirdly, $$f'$$ is surjective. Indeed, take any $$y\in X'=X\setminus\{n\}$$. Since $$f$$ is bijective, $$f(x)=y$$ for some $$x\in{{F}}(S(n))$$. Now, since $$f(x)=y \neq n=f(x_n)$$ (because $$y\in X\setminus\{n\}$$) one must have $$x \neq x_n$$, lest $$f$$ map one value to multiple values. Now, $${{F}}(S(n))={{F}}(n)\cup\{n\}$$. So, either $$x=n$$ or $$x\in{{F}}(n)$$. For the former, note that $$x_n \neq x=n$$ so that $$x_n\in{{F}}(n)$$. But then, one has $$x_n\in{{F}}(n)$$ such that $$f'(x_n)=f(n)=f(x)=y$$. Otherwise, for the latter, since $$x \neq x_n$$ by before, $$f'(x)=f(x)=y$$; thus, again, one has $$x\in{{F}}(n)$$ such that $$f'(x)=y$$.

* Finally, as $$X$$ a strict subset of $${{F}}(S(n))$$, some $$x\in{{F}}(S(n))$$ is not in $$X$$. This $$x$$ cannot be $$n$$ as it was assumed earlier that $$n$$ is in $$X$$. Thus, $$x\in{{F}}(n)$$. Also, since $$X'=X\setminus\{n\} \subseteq X$$, $$x$$ cannot be in $$X$$. In other words, $$X'$$ is missing an element $$x$$ of $${{F}}(n)$$ despite being a subset of $${{F}}(n)$$ i.e. $$X'$$ is a strict subset of $${{F}}(n)$$.


&nbsp;
> The consequences of this lemma are numerous. They are explored next.