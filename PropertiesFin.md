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
2. Now suppose $${{F}}(n)=\{x\in{{N}}:\ x<n\}$$. Consider $$x\in{{F}}(S(n))={{F}}(n)\cup\{n\}$$. Then, either $$x=n<S(n)$$ or $$x\in{{F}}(n)$$, so that by the induction hypothesis, $$x<n<S(n)$$, so that by strict transitivity, $$x<S(n)$$. Either way, $$x\in\{x\in{{N}}:\ x<S(n)\}$$. On the other hand, suppose $$x\in\{x\in{{N}}:\ x<S(n)\}$$; then $$x<S(n)$$. By alternative totality, it is not the case that $$S(n) \leq x$$, so that by the contrapositive of [Lemma SxLESGx](PropertiesOrder/README.md#lemma-sxlesgx), it is not the case that $$n<x$$. Hence, by strict totality, either $$x<n$$ or $$x=n$$ i.e.
$$
x\in\{x\in{{N}}:\ x<n\}\cup\{n\}={{F}}(n)\cup\{n\}={{F}}(S(n))
$$
Putting both of this together, one has that $${{F}}(S(n))=\{x\in{{N}}:\ x<S(n)\}$$.