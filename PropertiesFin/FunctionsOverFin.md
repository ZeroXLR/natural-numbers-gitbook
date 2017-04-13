{% set N = "\\mathbb{N}" %}
{% set F = "\\text{Fin}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


> Before the start of the next section of this chapter, recall the definitions of **injections** and **surjections**: a function $$f:X \to Y$$ is called injective iff $$f(x)=f(x')$$ implies $$x=x'$$ (alternatively, $$x \neq x'$$ implies $$f(x) \neq f(x')$$) while the same function is called surjective iff for every $$y \in Y$$ there exists an $$x \in X$$ such that $$f(x)=y$$ (alternatively, $$f(X)=\{y \in Y:\ \exists x \in X\ [y=f(x)]\}=Y$$). A function is a **bijection** iff it is both injective and surjective. I next present two lemmas about functions. I could instead ask the readers to call on prerequisite set theory knowledge. However, seeing the proofs will give the readers a good refresher on the current material.


## Lemma RSIS

**Restriction to Subset and its Image is Surjection**: _For any function $$f:X \to Y$$ and $$X' \subseteq X$$, restricting the function's domain and codomain to $$X'$$ and $$f(X')$$, respectively, produces a surjection; furthermore, if $$f$$ is an injection, so is this restriction_.

**Proof**: As per the theorem, let $$f':X' \to Y'=f(X')$$ where for all $$x \in X'$$, $$f'(x)=f(x)$$. Now, suppose $$y \in Y'$$. Then, by the definition of $$f(X')$$, there exists some $$x \in X'$$ such that $$f(x)=y$$. But then, $$f'(x)=y$$. Hence, every $$y$$ in the codomain of $$f'$$ is the image of some $$x$$ in its domain; thus, $$f'$$ is surjective. Now, suppose for $$x,x' \in X'$$ that $$f'(x)=f'(x')$$. Then, $$f(x)=f(x')$$ and, since $$X' \subseteq X$$, $$x,x' \in X$$. Thus, if $$f$$ is injective, $$x=x'$$. Thus, $$f'$$ is injective too.


## Lemma ISSI

**Image of a Subset is a Subset of the Image**: _For any function $$f:X \to Y$$ and $$U \subseteq X$$, $$f(U) \subseteq Y$$. Furthermore, if $$f$$ is injective and $$U$$ is a strict subset of $$X$$, then $$f(U)$$ is a strict subset of $$Y$$_.

**Proof**: Let $$y \in f(U)$$. Then, there is some $$u \in U$$ such that $$f(u)=y$$. But, $$u \in X$$ also, so that $$y=f(u) \in Y$$. Hence, $$f(U) \subseteq Y$$.

Now, suppose that $$f$$ is injective and $$U \subset X$$. Then, there is some $$x \in X$$ such that $$x \notin U$$ i.e. given any $$u \in U$$, $$u \neq x$$. Applying injectivity to the last part yields that $$f(u) \neq f(x)$$. Hence, $$f(x) \notin f(U)$$ even though $$f(x) \in Y$$. So, $$f(U) \subset Y$$.


&nbsp;
> The following lemma, while simple, is used often in the main lemma of this section. So, it is worth spelling it out completely:


## Lemma SFSxWSFx

**Subset of $${{F}}(S(n))$$ Without $$n$$ is Subset of $${{F}}(n)$$**: _For any $$U\subseteq{{F}}(S(n))$$ such that $$n \notin U$$, $$U\subseteq{{F}}(n)$$_.

**Proof**: Fix any $$u \in U$$. Then, since $$n \notin U$$, $$u \neq n$$. At the same time, since $$U\subseteq{{F}}(S(n))$$, $$u\in{{F}}(S(n))$$ i.e. $$u\in{{N}}$$ and $$u<S(n)$$; thus, by a lemma from the previous chapter, $$u \leq n$$. So, altogether, $$u \leq n$$ and $$u \neq n$$ i.e. $$u<n$$. Hence, $$u\in{{F}}(n)$$. Since the previous argument is true for arbitrary $$u$$, $$U\subseteq{{F}}(n)$$.


## Lemma BFSxRBFx

**Bijection from $${{F}}(S(n))$$ to Subset Restricts to Bijection from $${{F}}(n)$$ to Subset**: _For any $$n\in{{N}}$$, suppose $$f:{{F}}(S(n)) \to X$$ is a bijection where $$X\subseteq{{F}}(S(n))$$. Then, there exists a bijection $$f':{{F}}(n) \to X'$$ where $$X'\subseteq{{F}}(n)$$. Furthermore, if $$X$$ is a strict subset of $${{F}}(S(n))$$, then $$X'$$ is a strict subset of $${{F}}(n)$$_.

**Proof**: There are two cases to consider:

<span style="text-decoration: underline;">_**Suppose first that $$n \notin X$$:**_</span> Thus, $$X\subseteq{{F}}(n)$$ by [Lemma SFSxWSFx](#lemma-sfsxwsfx). Now, consider the restriction of $$f$$ to the domain $${{F}}(n)$$ and the codomain $$X'=f({{F}}(n))$$ as described in [Lemma RSIS](#lemma-rsis). By the lemma, this restriction must be surjective and injective i.e. bijective. Also, since $${{F}}(n) \subset {{F}}(S(n))$$, by [Lemma ISSI](#lemma-issi),
$$
X'=f({{F}}(n)) \subset X \subseteq {{F}}(n)
$$
Thus, this restriction is the required bijection from $${{F}}(n)$$ to a subset of itself. In this case, this subset is also strict, as required by the second part of the theorem.

<span style="text-decoration: underline;">_**Suppose next that $$n \in X$$:**_</span> Then, as $$f$$ is a bijection, there is some $$x_n\in{{F}}(S(n))$$ such that $$f(x_n)=n$$. Now define $$f':{{F}}(n) \to X'=X\setminus\{n\}\subseteq{{F}}(n)$$ thus:
$$
f'(x)=\begin{cases} f(x) &\text{if } x \neq x_n \\
                    f(n) &\text{if } x=x_n \end{cases}
$$
It doesn't matter if $$x_n\notin{{F}}(n)$$; in that case, the second alternative above will simply never occur. Also, $$X\setminus\{n\}\subseteq{{F}}(n)$$ by [Lemma SFSxWSFx](#lemma-sfsxwsfx).

* Firstly, one must show that this function does map values into $$X\setminus\{n\}$$. Well, fix any $$x\in{{F}}(n)$$. Otherwise, if $$x \neq x_n$$, then by the injectivity of $$f$$
$$
X \ni f'(x)=f(x) \neq f(x_n)=n
$$ If $$x=x_n$$, then $$x_n\in{{F}}(n)$$ so that $$x_n \neq n$$. Hence, by injectivity of $$f$$ again,
$$
n=f(x_n) \neq f(n)=f'(x) \in X
$$ In both cases, $$f'(x) \neq n$$ and $$f'(x) \in X$$. Hence, $$f'(x) \in X\setminus\{n\}=X'$$.

* Secondly, I will show that $$f'$$ is also injective. So suppose $$x \neq x'$$ for $$x,x'\in{{F}}(n)$$. If neither $$x$$ nor $$x'$$ is $$x_n$$, then by the injectivity of $$f$$
$$
f'(x)=f(x) \neq f(x')=f'(x')
$$
Otherwise w.l.o.g. assume that $$x'=x_n$$. Then, necessarily, $$x_n\in{{F}}(n)$$ so that $$f'(x_n)$$ makes sense. Also, in this case, necessarily, $$x \neq x_n$$ (so $$f'(x)=f(x)$$). Hence, by the injectivity of $$f$$ applied to the fact that $$x \neq n$$ (because $$x\in{{F}}(n)$$)
$$
f'(x)=f(x) \neq f(n)=f'(x_n)=f'(x')
$$
Thus, in both cases, $$x \neq x'$$ implies $$f'(x) \neq f'(x')$$ i.e. $$f'$$ is injective.

* Thirdly, I show that $$f'$$ is surjective. So take any $$y\in X'=X\setminus\{n\}$$. Since $$f$$ is bijective, there is some $$x\in{{F}}(S(n))={{F}}(n)\cup\{n\}$$ such that $$f(x)=y$$. Now, since $$f(x)=y \neq n=f(x_n)$$ (because $$y\in X\setminus\{n\}$$), and $$f$$, being a function, cannot map one value to more than one value, one has $$x \neq x_n$$. Now, because $$x\in{{F}}(n)\cup\{n\}$$, either $$x=n$$ or $$x\in{{F}}(n)$$. If the former is the case, note that $$x_n \neq x=n$$ so that $$x_n\in{{F}}(n)$$. Then, there is in fact an $$x_n\in{{F}}(n)$$ such that $$f'(x_n)=f(n)=f(x)=y$$. On the other hand, if the latter is the case, then since $$x \neq x_n$$ by before, $$f'(x)=f(x)$$; thus, here too, one has an $$x\in{{F}}(n)$$ such that $$f'(x)=y$$.

* Finally, if $$X$$ is a strict subset of $${{F}}(S(n))$$, then, there is an $$x\in{{F}}(S(n))$$ that is not in $$X$$. Now, $$x$$ cannot be $$n$$, as one already assumed, at the start of this case, that $$n$$ _is_ in $$X$$. Thus, $$x\in{{F}}(n)$$. Also, since $$X'=X\setminus\{n\} \subseteq X$$, $$x$$ cannot be in $$X'$$; otherwise, $$x$$ would be in $$X$$. So, in summary, $$X'$$ does not contain an element $$x$$ of $${{F}}(n)$$, even though it is a subset of $${{F}}(n)$$. This implies that $$X'$$ is a strict subset of $${{F}}(n)$$, as required by the second part of the theorem.


## Theorem NBFPS

_There Exist No Bijections from $${{F}}(n)$$ to a Proper Subset of it_.

**Proof**: Do induction on $$n\in{{N}}$$:
1. $${{F}}(0)={{E}}$$ has no proper subsets. So, in fact, it is impossible to have functions, let alone bijections, from $${{F}}(0)$$ to a proper subset of it.
2. Now say the claim holds for an $$n\in{{N}}$$ and say for a contradiction that there is a bijection from $${{F}}(S(n))$$ to some strict subset $$X$$ of the same. Then, by the [previous lemma](#lemma-bfsxrbfx), there is also a bijection from $${{F}}(n)$$ to a strict subset $$X'$$ of $${{F}}(n)$$. But this contradicts the initial hypothesis.