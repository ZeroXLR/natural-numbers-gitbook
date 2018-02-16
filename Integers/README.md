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

Given an equivalence relation $$\sim$$ over a set $$X$$ and $$x \in X$$, the set $$[x] = \{\chi \in X:\ \chi \sim x\} \subseteq X$$ is called the **equivalence class** of $$x$$.

## Definition Partitions

Given a set $$X$$, a **partition** $$P$$ of $$X$$ is a subset of $${{P}}X$$ such that:
* $${{E}} \neq P$$
* $$\bigcup P = X$$
* $$A \neq B$$ implies $$A \cap B = {{E}}$$ for all $$A, B \in P$$