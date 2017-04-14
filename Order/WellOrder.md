{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> One has now shown that the natural numbers are totally ordered. Believe it or not, one can go _even_ further! The natural numbers are also _**well-ordered**_ i.e. every non-empty subset of the naturals have a smallest/least element. Thus, one cannot have "bottomless chasms" in the natural numbers. At some point, as one descends down a non-empty natural subset according to order, one must reach the bottom in a finite number of steps.


## Definition LE

**Least Element**: Let $$X\subseteq{{N}}$$. Then, an element $$n \in X$$ is called the **least element** of $$X$$ iff for any $$x \in X$$, it is the case that $$n \leq x$$.


## Lemma ULE

**Uniqueness of the Least Element**: _If $$X\subseteq{{N}}$$ has a least element $$n$$, then it is unique_.

**Proof**: Suppose $$n'$$ is some other least element of $$X$$. Then, as $$n \in X$$, $$n' \leq n$$. At the same time, since $$n$$ is also a least element and $$n' \in X$$, $$n \leq n'$$. So, $$n=n'$$ by antisymmetry.


## Theorem Well-Ordering

**Well Ordering of $${{N}}$$**: _If $$X\subseteq{{N}}$$ and $$X\neq\emptyset$$, then $$X$$ has a least element_.

**Proof**: Do induction with $${{S}}=\{n\in{{N}}:\ \text{if}\ X\subseteq{{N}}\ \text{and}\ n \in X\ \text{, then}\ X\ \text{ has a least element}\}$$.
1. $$0\in{{S}}$$ because [it is already the least natural number](README.md#lemma-zlnn).
2. Now suppose that $$n\in{{S}}$$. One now has to show that $$S(n)\in{{S}}$$ also. To that end, consider any $$X\subseteq{{N}}$$ such that $$S(n) \in X$$. Now, if $$n \in X$$, then one is done because by the initial hypothesis, any subset with $$n$$ must have a least element. Otherwise, consider $$X'=X\cup\{n\}$$. Clearly, $$n \in X'$$, so that $$X'$$ has some least element $$l$$. Now
    * If $$l \neq n$$, then $$l \in X$$. It is easy to see in this case that $$l$$ is the least element of $$X$$. For, fix any $$s \in X$$; then certainly $$s \in X'$$ also. But then as $$l$$ is the least element of $$X'$$, $$l \leq s$$.
    * Otherwise, $$l=n$$. In this case, one can show that $$S(n)$$ is the least element of $$X$$. Well, for starters, fix any $$s \in X$$. Since $$s \in X'$$ also and $$l=n$$ is the least element of $$X'$$, $$n \leq s$$ i.e. there is some $$k\in{{N}}$$ such that $$n+k=s$$. Now, $$k \neq 0$$ as otherwise, $$s=n+0=n\notin{{N}}$$. Thus, there is a $$k'\in{{N}}$$ such that $$S(k')=k$$. So, $$s=n+k=n+S(k')=S(n)+k'$$ (using [Lemma SSwap](README.md#lemma-sswap)). Hence, $$S(n) \leq s$$.

Because least elements are unique by the [previous lemma](#lemma-ule), one can unambiguously denote the least element of $$X$$, as given by this theorem, as $$\text{min}(X)$$.


&nbsp;
> One can also flesh out well-ordering in terms of **greatest elements** in **bounded** subsets of $${{N}}$$.


## Definition GE

**Greatest Element**: Let $$X\subseteq{{N}}$$. Then, an element $$n \in X$$ is called the **greatest element** of $$X$$ iff for any $$x \in X$$, $$x \leq n$$.


## Lemma UGE

**Uniqueness of the Greatest Element**: _If $$X\subseteq{{N}}$$ has a greatest element $$n$$, then it is unique_.

> The proof of this is entirely analogous to the proof that least elements are unique.


## Definition Upper Bound

**Upper Bound on a Subset of $${{N}}$$**: Let $$X\subseteq{{N}}$$. A natural number $$n$$ is called an **upper bound** on $$X$$ iff for any $$x \in X$$, $$x \leq n$$.


&nbsp;
> Thus, the greatest element of a subset of $${{N}}$$ is precisely an upper bound which is in the subset itself.


## Definition Bounded Subset

**Bounded Subsets of $${{N}}$$**: Let $$X\subseteq{{N}}$$. Then one says that $$X$$ is **bounded above** iff an upper bound on it exists.


## Lemma SxLESGx

**$$S(x)$$ is the Least Element Strictly Greater Than $$x$$**: _For any $$x,y\in{{N}}$$, if $$x<y$$, then $$S(x) \leq y$$_.

**Proof Sketch**: If $$x<y$$, then there is a natural $$k'$$ such that $$x+S(k')=S(x)+k'=y$$ i.e. $$S(x) \leq y$$.

> The above lemma is sometimes used in its contrapositive form: _For any $$x,y\in{{N}}$$, if not $$S(x) \leq y$$, then not $$x<y$$_. By alternative totality, this is equivalent to: _For any $$x,y\in{{N}}$$, if $$y<S(x)$$, then $$y \leq x$$_.


## Theorem Well-Ordering-Alt

**Well-Ordering on $${{N}}$$ (Alternative Form)**: _If $$X\subseteq{{N}}$$ is non-empty and bounded above, then $$X$$ has a greatest element_.

**Proof**: Form the set of all upper bounds on $$X$$, $$X'$$. This is non-empty since $$X$$ is bounded above. Hence, by well-ordering, $$X'$$ has a least element $$l$$. Now, clearly as $$l$$ is an upper bound on $$X$$, for any $$x \in X$$, $$x \leq l$$. The only thing that remains to be shown, to conclude that $$l$$ is the greatest element of $$X$$, is that $$l \in X$$.

If $$l=0$$, since $$0$$ is the least element period, for any $$x \in X$$, $$l \leq x$$. Hence, by antisymmetry, $$x=l$$. Now, as $$X$$ is non-empty, there is at least one natural $$x \in X$$ and by the previous sentence, $$l=x \in X$$.

Otherwise, $$l \neq 0$$. Hence, there is some $$l' \in {{N}}$$ such that $$S(l')=l$$. Since $$l'<S(l')$$ ($$l' \neq S(l')$$ as $$S$$ has no fixed points and $$l' \leq S(l')$$ by an earlier lemma), it cannot be that $$l=S(l') \leq l'$$ by alternative totality. Hence, $$l' \notin X'$$; otherwise, $$l$$ would no longer be the least element of $$X'$$. Thus, $$l'$$ is not an upper bound on $$X$$. In other words, there is an $$x \in X$$ such that $$x \leq l'$$ is not true; hence, $$l'<x$$ by alternative totality. So, by the previous lemma, $$l=S(l') \leq x$$. But then, by antisymmetry, $$l=x \in X$$.

Because greatest elements are unique by the [Lemma UGE](#lemma-uge), one can unambiguously denote the greatest element of $$X$$, as given by this theorem, as $$\text{max}(X)$$.