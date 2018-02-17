{% set N = "\\mathbb{N}" %}
{% set N = "\\mathbb{Z}" %}
{% set P = "\\mathcal{P}" %}
{% set E = "\\emptyset" %}
{% set S = "\\Sigma" %}


> One of the algebraic shortcomings of the natural numbers is that non-zero naturals have no inverses. We can fix this by using the integers. In fact, we can construct the integers using the natural numbers. We do this now and explore some of their properties. But first, we need to introduce some new mathematical ideas to make the construction work.


## Definition Equivalence Relations

An **equivalence relation** $$\sim$$ over a set $$X$$ is a subset of $$X \times X$$ such that:
* _it is reflexive_: $$(x, x) \in \sim$$ for all $$x \in X$$
* _it is transitive_: if $$(x, y) \in \sim$$ and $$(y, z) \in \sim$$, then $$(x, z) \in \sim$$
* _it is symmetric_: if $$(x, y) \in \sim$$, then $$(y, x) \in \sim$$

We often write $$x \sim y$$ instead of $$(x, y) \in \sim$$.


## Definition Equivalence Classes

Given an equivalence relation $$\sim$$ over a set $$X$$ and $$x \in X$$, the set $$[x] = \{\xi \in X:\ \xi \sim x\}$$ is called the **equivalence class** of $$x$$. Note that $$[x]$$ is necessarily a subset of $$X$$. Also, by reflexivity, $$[x]$$ is never empty because at least $$x \in [x]$$.


## Lemma CharEquiClass

**Characterization of Equivalence Classes**: _Given an equivalence relation $$\sim$$ on a set $$X$$, the following are equivalent_:
* $$x \sim y$$
* $$[x] = [y]$$
* $$[x] \cap [y] \neq {{E}}$$

**Proof**: Suppose $$x \sim y$$. Now consider an arbitrary element $$\xi \in [x]$$. Then, by definition, $$\xi \sim x$$. So using transitivity on this and our initial supposition, we get $$\xi \sim y$$. Hence, $$\xi \in [y]$$. Thus, since $$\xi$$ was an arbitrary element of $$[x]$$, $$[x] \subseteq [y]$$. By an entirely analogous argument applied to $$y \sim x$$ (which we get from the symmetry of $$x \sim y$$), we get $$[y] \subseteq [x]$$.

Now suppose $$[x] = [y]$$. Note that by reflexivity, $$x \in [x]$$. Hence, since $$[x] = [y]$$, $$x
\in [y]$$ also. So obviously $$x \in [x] \cap [y]$$ and we see that $$[x] \cap [y] \neq {{E}}$$.

The readers can show the final implication that if $$[x] \cap [y] \neq {{E}}$$, then $$x \sim y$$.


## Definition Equivalence Quotient

Given an equivalence relation $$\sim$$ over a set $$X$$, the set of all equivalence classes of elements of $$X$$: $$X / \sim \ = \{[x]: x \in X\}$$ is called the **quotient set** relative to $$\sim$$. Note that since each $$[x] \subseteq X$$, the quotient set is a subset of the power set $${{P}}X$$ of $$X$$.


## Definition Equivalence Well-Defined-ness

Given a function $$f:X \to Y$$ and an equivalence relation $$\sim$$ on $$X$$, we say that $$f$$ is **well-defined relative to $$\sim$$** if whenever $$x \sim \chi$$ we also have $$f(x) = f(\chi)$$ for all $$x,\chi \in X$$.

If $$f$$ is well-defined relative to $$\sim$$, then, there is a natural way to define a function $$[f]$$ from $$X / \sim$$ to $$Y$$: simply put $$[f]([x]) = f(x)$$. This well-defined _as a function_ because if $$[x] = [\chi]$$, then by the lemma above, $$x \sim \chi$$. Hence, the well-defined-ness of $$f$$ relative to $$\sim$$ gives
$$
[f](x) = f(x) = f(\chi) = [f]([\chi])
$$ Thus, $$[f]$$ maps values in its domain to unique values in its codomain, as a function should.