{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> The last Peano axiom, the principle of induction, is _the_ main work horse in almost every proof about the naturals. Thus, it is worthwhile to explore a few simple instances of its use.


## Lemma ExPre

**Existence of a Predecessor**. _If $$n\in{{N}}$$ and $$n \neq 0$$, then there is an $$n'\in{{N}}$$ such that $$S(n')=n$$_.

**Proof**: The principle of induction over $${{N}}$$, as [it was presented](README.md#introduction), is an axiom that operates on a set $${{S}}$$. Thus, to use it in proving lemma like this, one must first _convert the lemma into a set_ like so:
$$
{{S}}=\{n\in{{N}}:\ n=0\ \ \text{or}\ \ \exists n'\in{{N}}\ [n=S(n')]\}
$$
i.e. one has just _made this lemma into the condition of some set $${{S}}$$_. Now, if one can prove that $${{N}}\subseteq{{S}}$$, one will have proved the lemma for all of $${{N}}$$. For then, every $$n$$ in $${{N}}$$ would also be in $${{S}}$$; thus, it must satisfy the condition of $${{S}}$$ &mdash; which is the lemma itself.

With this overview of the objective, let's proceed to apply [Peano axiom 4](README.md#introduction), as promised, on $${{S}}$$:

* Clearly $$0\in{{S}}$$ because it satisfies both $$n\in{{N}}$$ (by the [Peano axiom 0](README.md#introduction)) and the first alternative of $${{S}}$$'s condition, $$n=0$$.
* Next, suppose $$n$$ is in both $${{N}}$$ and $${{S}}$$. Then clearly $$S(n)\in{{S}}$$ also because
    * $$S(n)\in{{N}}$$ by [Peano axiom 1](README.md#introduction) and
    * there is obviously an $$n'\in{{N}}$$ such that $$S(n)=S(n')$$, namely, $$n$$ itself.

Thus, $${{N}}\subseteq{{S}}$$ by the conclusion of the last Peano axiom.


## Lemma SNoFPs

**$$S$$ has No Fixed Points**: _For any $$n\in{{N}}$$, $$n \neq S(n)$$_.

**Proof**: This time, $${{S}}=\{n\in{{N}}:\ n \neq S(n)\}$$.

* $$0\in{{S}}$$ because it satisfies both the conditions of $${{S}}$$ &mdash; i.e. both $$0\in{{N}}$$ and $$0 \neq S(0)$$ &mdash; by [Peano axioms 0 and 3](README.md#introduction) respectively.
* Suppose $$n\in{{S}}$$, then certainly $$n \neq S(n)$$ where $$S(n)\in{{S}}$$ by [Peano axiom 1](README.md#introduction). This, along with the contrapositive of [Peano axiom 2](README.md#introduction), implies that $$S(n) \neq S(S(n))$$. But then, $$S(n)$$ satisfies $${{S}}$$'s condition so that $$S(n)\in{{S}}$$.

Thus, by the principle of induction, $${{N}}\subseteq{{S}}$$.


## Remarks

A couple of key points are already visible in these simple proofs about the naturals.

* Firstly, Peano axioms 0 and 1 are ubiquitous throughout the proofs. In fact, this is the case with all proofs about the naturals. However, unlike the ubiquitous induction principle, they are also very simple. It should be obvious whenever they are applicable. For these reasons, as is the case with simple but popular results, I leave them out all proofs from now on.
* Secondly, note how the induction principle is applied: one needs to wrap the lemma/theorem being proven in a set; only then, does Peano axiom 4 become applicable. This is largely unnecessary. One can instead, state Peano axiom 4 as such
    <ol start="4">
        <li>if $$\phi$$ is an unary property such that $$\phi(0)$$ is true and for every $$n\in{{N}}$$, $$\phi(n)$$ implies $$\phi(S(n))$$, then $$\phi$$ is true for all of $${{N}}$$</li>
    </ol>

I end this chapter with a word of caution about the informal set notation that I have been using. Until now, I have been implicitly assuming that one can make sets such as $$\{n\in{{N}}:\ \phi(n)\}$$ for arbitrary properties $$\phi$$. Strictly speaking, this cannot be true lest one wants to fall victim to [Russell's Paradox](https://en.wikipedia.org/wiki/Russell's_paradox). Informal set theory largely ignores this subtlety and, most of the time, it is inconsequential to the theory being developed. However, it is still worthwhile keeping it in mind in any rigorous study of math.