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

> This theorem is henceforth assumed implicitly in what follows


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

> The above theorem is often stated in terms of properties: if $$\phi$$ is an unary property such that $$\phi(0)$$ is true and for every $$n\in{{N}}$$, if $$\phi(k)$$ being true for all $$k\in{{N}}$$ such that $$k<n$$ implies $$\phi(n)$$ being true, then $$\phi$$ is true for all of $${{N}}$$


## Interlude

Before the start of the next section of this chapter, recall the definitions of **injections** and **surjections**: a function $$f:X \to Y$$ is called injective iff $$f(x)=f(x')$$ implies $$x=x'$$ while the same function is called surjective iff for every $$y \in Y$$ there exists an $$x \in X$$ such that $$f(x)=y$$ (alternatively, $$f(X)=\{y \in Y:\ \exists x \in X\ [y=f(x)]\}=Y$$). A function is a **bijection** iff it is both injective and surjective. I next present two lemmas about functions. I could instead ask the readers to call on prerequisite set theory knowledge. However, seeing the proofs will give the readers a good refresher on the current material.


## Lemma RSIS

**Restriction to Subset and its Image is Surjection**: _For any function $$f:X \to Y$$ and $$X' \subseteq X$$, restricting the function's domain to $$X'$$ and codomain to $$f(X')$$ produces a surjection; furthermore, if $$f$$ is an injection, so is this restriction_.

**Proof**: As per the theorem, let $$f':X' \to Y'=f(X')$$ where for all $$x \in X'$$, $$f'(x)=f(x)$$. Now, suppose $$y \in Y'$$. Then, by definition of $$f(X')$$, there exists some $$x \in X'$$ such that $$f(x)=y$$. But then, $$f'(x)=y$$. Hence, every $$y$$ in the codomain of $$f'$$ is the image of some $$x$$ in its domain; thus, $$f'$$ is surjective. Now, suppose for $$x,x' \in X'$$ that $$f'(x)=f'(x')$$. Then, $$f(x)=f(x')$$ and, since $$X' \subseteq X$$, $$x,x' \in X$$. Thus, if $$f$$ is injective, $$x=x'$$. Thus, $$f'$$ is injective too.


## Lemma ISSI

**Image of a Subset is a Subset of the Image**: _For any function $$f:X \to Y$$ and $$S \subseteq X$$, $$f(S) \subseteq Y$$_.

**Proof**: Let $$y \in f(S)$$. Then, there is some $$s \in S$$ such that $$f(s)=y$$. But, $$s \in X$$ also, so that $$y=f(s) \in Y$$.


## Lemma BFSxRBFx

**Bijection from $${{F}}(S(n))$$ to Subset Restricts to Bijection from $${{F}}(n)$$ to Subset**: _For any $$n\in{{N}}$$, suppose $$f:{{F}}(S(n)) \to X$$ is a bijection where $$X\subseteq{{F}}(S(n))$$. Then, there exists a bijection $$f':{{F}}(n) \to X'$$ where $$X'\subseteq{{F}}(n)$$. Furthermore, if $$X$$ is a strict subset of $${{F}}(S(n))$$, then $$X'$$ is a strict subset of $${{F}}(n)$$_.

**Proof**: Suppose first that $$n \notin X$$. Then, for any $$x \in X$$, $$x \neq n$$ and $$x\in{{F}}(S(n))$$. By the latter, $$x<S(n)$$, so that $$x \leq n$$. Hence, together with $$x \neq n$$, $$x<n$$ i.e. $$x\in{{F}}(n)$$. Thus, $$X\subseteq{{F}}(n)$$. Now, consider the restriction of $$f$$ to the domain $${{F}}(n)$$ and the codomain $$X'=f({{F}}(n))$$ as described in [Lemma RSIS](#lemma-rsis). By the lemma, this restriction must be surjective and injective i.e. bijective. Also, since $${{F}}(n) \subseteq {{F}}(S(n))$$, by [Lemma ISSI](#lemma-issi),
$$
X'=f({{F}}(n)) \subseteq f({{F}}(S(n)))=X \subseteq {{F}}(n)
$$
Thus, this restriction is the required bijection from $${{F}}(n)$$ to a subset of itself. Note also that $$f(n) \in X$$ but $$f(n) \in X'$$ because for any $$x\in{{F}}(n)$$, $$x \neq n$$ meaning $$f(x) \neq f(n)$$ by injectivity. Hence, $$X' \subset X\subseteq{{F}}(n)$$ so that $$X'$$ is a strict subset of $${{F}}(n)$$.

Now suppose that $$n \in X$$. Then, as $$f$$ is a bijection, there is some $$x_n\in{{F}}(S(n))$$ such that $$f(x_n)=n$$. Now define $$f':{{F}}(n) \to X'=X\setminus\{n\}\subseteq{{F}}(n)$$ thus:
$$
f'(x)=\begin{cases} f(x) &\text{if } x \neq x_n \\
                    f(n) &\text{if } x=x_n \end{cases}
$$
It doesn't matter if $$x_n\notin{{F}}(n)$$; in that case, the second alternative above will simply never occur. Also, the fact that $$X\setminus\{n\}\subseteq{{F}}(n)$$ is easy to verify: for any $$x \in X\setminus\{n\}$$, $$x \in X$$ so that $$x \in {{F}}(S(n))$$, but, at the same time, $$x \neq n$$. Hence, together, $$x\in{{F}}(n)$$.

Firstly, one must show that this function does map values into $$X\setminus\{n\}$$. Well, fix any $$x\in{{F}}(n)$$. If $$x \neq x_n$$, then by the injectivity of $$f$$
$$
X \ni f'(x)=f(x) \neq f(x_n)=n
$$ If $$x=x_n$$, then $$x_n\in{{F}}(n)$$ so that $$x_n \neq n$$. Hence, by injectivity again,
$$
n=f(x_n) \neq f(n)=f'(x) \in X
$$ In both cases, $$f'(x) \neq n$$ and $$f'(x) \in X$$. Hence, $$f'(x) \in X\setminus\{n\}=X'$$.

Secondly, I will show that $$f'$$ is also injective. So suppose $$f'(x)=f'(x')$$ for $$x,x'\in{{F}}(n)$$. If neither $$x$$ nor $$x'$$ is $$x_n$$, then
$$
f'(x)=f(x)=f(x')=f'(x')
$$
So, by the injectivity of $$f$$, $$x=x'$$. Otherwise w.l.o.g. assume that $$x'=x_n$$. Then,
$$
f'(x)=f'(x')=f'(x_n)=f(n)
$$
Now, for a contradiction, say $$x \neq x_n$$. Then, $$f'(x)=f(x)$$, so that $$f(x)=f(n)$$ by above. Hence, by the injectivity, $$x=n$$ but this contradicts the fact that $$x\in{{F}}(n)$$. Hence, $$x=x_n=x'$$. Thus, in both cases, $$f'(x)=f'(x')$$ implies $$x=x'$$ i.e. $$f'$$ is injective.

Thirdly, I show that $$f'$$ is surjective. So take any $$y\in X'=X\setminus\{n\}$$. Since $$f$$ is bijective, there is some $$x\in{{F}}(S(n))={{F}}(n)\cup\{n\}$$ such that $$f(x)=y$$. Now, since $$y \neq n=f(x_n)$$, and $$f$$ cannot map a single value to more than one value, $$x \neq x_n$$. Now, either $$x=n$$ or $$x\in{{F}}(n)$$. If the former is the case, note that $$x_n \neq x=n$$ so that $$x_n\in{{F}}(n)$$. Then, there is in fact an $$x_n\in{{F}}(n)$$ such that $$f'(x_n)=f(n)=y$$. On the other hand, if the latter is the case, then since $$x \neq x_n$$ by before, $$f'(x)=f(x)$$; thus, here too, one has an $$x\in{{F}}(n)$$ such that $$f'(x)=y$$.

Finally, if $$X$$ is a strict subset of $${{F}}(S(n))$$, then, there is an $$x\in{{F}}(S(n))$$ that is not in $$X$$. Now, $$x$$ cannot be $$n$$ since in this case $$n \in X$$. Thus, $$x\in{{F}}(n)$$. Also, $$x$$ cannot be in $$X'$$ since it itself is a subset of $$X$$. So since $$X'=X\setminus\{n\}$$ is already a subset of $${{F}}(n)$$, this implies that $$X'$$ is a strict subset of $${{F}}(n)$$.


## Theorem NBFPS

_There Exist No Bijections from $${{F}}(n)$$ to a Proper Subset of it_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. $${{F}}(0)={{E}}$$ has no proper subsets. So there aren't even any functions from $${{F}}(0)$$ to a proper subset of it.
2. Now say the claim holds for an $$n\in{{N}}$$ and say for a contradiction that there is a bijection from $${{F}}(S(n))$$ to some strict subset $$X$$ of the same. Then, by the [previous lemma](#lemma-bfsxrbfx), there is also a bijection from $${{F}}(n)$$ to a strict subset $$X'$$ of $${{F}}(n)$$. But this contradicts the initial hypothesis.