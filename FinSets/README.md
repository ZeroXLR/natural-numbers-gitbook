{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


> We are now ready to define finite sets and explore a couple of their properties


## Definition FinSets

A **finite set** is a set $$X$$ such that there is a bijection $$f:{{F}}(n) \to X$$ for some $$n \in {{N}}$$. We say that this finite set $$X$$ has $$n$$ elements or that the **cardinality** of $$X$$ is $$n$$. Note that by [Corollary SFnBSUFk](../Fin/FunctionsOverFinII.md#corollary-sfnbsufk), this $$n$$ is unique. This is because if there were another $$\tilde{n} \in {{N}}$$ and a bijection $$\tilde{f}:{{F}}(\tilde{n}) \to X$$, we would have a bijective left inverse $$\tilde{f}^{-1}:X \to {{F}}(\tilde{n})$$. Now, composing this with the original bijection gives a bijection $$\tilde{f}^{-1} \circ f:{{F}}(n) \to {{F}}(\tilde{n})$$ and we can apply the aforementioned corollary to show that $$n = \tilde{n}$$.