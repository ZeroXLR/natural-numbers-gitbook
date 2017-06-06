{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}

## Definition Peano Axioms

The natural numbers are defined axiomatically by the Peano axioms. In other words, their existences and properties are stated outright on the backdrop of a larger theory like set theory or first order logic. In this case, as mentioned earlier, the backdrop is informal set theory. With this overview in mind, one now assumes that there exists a unique set $${{N}}$$ such that

<ol start="0">
    <li>the symbol $$0$$ is in it</li>
    <li>for every $$n$$ in this set, the string $$S(n)$$ is in the set too; $$S(n)$$ is called the <em><strong>successor</em></strong> of $$n$$ while $$n$$ is called the <em><strong>predecessor</em></strong> of $$S(n)$$</li>
    <li>for every $$n,n' \in {{N}}$$, $$n=n'$$ if and only if $$S(n)=S(n')$$; this says that one can think of $$S$$ as a <em><strong>function</em></strong> since it maps equals to equals ... furthermore, thought of as a function, it is also <em><strong>injective</em></strong> since it maps <em>only</em> equals to equals
    <li>there exists no natural number $$n$$ such that $$S(n)=0$$</li>
    <li>if $$\Sigma$$ is a set where $$0\in\Sigma$$ and for every $$n\in{{N}}$$, $$n\in\Sigma$$ implies $$S(n)\in\Sigma$$, then $${{N}}\subseteq\Sigma$$; this is the <em><strong>principle of induction</em></strong> over the natural numbers</li>
</ol>

One caveat needs attention: in first order logic, where the very behavior of the equals-sign $$=$$ is, by default, undefined, one also needs to add two more properties to the list: that $$=$$ be an **equivalence relation** and that $${{N}}$$ be **closed under** $$=$$. However, despite my adherence to rigor in this book, I will not split hairs to _this_ extent. Instead, over here, the equals-sign is simply the same equality used in informal set theory with all its expected properties.


&nbsp;
> The last Peano axiom, the principle of induction, is _the_ main work horse in almost every proof about the naturals. Thus, it is worthwhile to explore a few simple instances of its use.


## Lemma ExPre

**Existence of a Predecessor**. _If $$n\in{{N}}$$ and $$n \neq 0$$, then there is an $$n'\in{{N}}$$ such that $$S(n')=n$$_.

**Proof**: The principle of induction over $${{N}}$$, as [it was presented](#definition-peano-axioms), is an axiom that operates on a set $${{S}}$$. Thus, to use it in proving lemma like this, one must first _convert the lemma into a set_ like so:
$$
{{S}}=\{n\in{{N}}:\ n=0\ \ \text{or}\ \ \exists n'\in{{N}}\ [n=S(n')]\}
$$
i.e. one has just _made this lemma into the condition of some set $${{S}}$$_. Now, if one can prove that $${{N}}\subseteq{{S}}$$, one will have proved the lemma for all of $${{N}}$$. For then, every $$n$$ in $${{N}}$$ would also be in $${{S}}$$; thus, it must satisfy the condition of $${{S}}$$ &mdash; which is the lemma itself.

With this overview of the objective, let's proceed to apply [Peano axiom 4](#definition-peano-axioms), as promised, to $${{S}}$$:

* Clearly $$0\in{{S}}$$ because it satisfies both $$n\in{{N}}$$ (by the [Peano axiom 0](#definition-peano-axioms)) and the first alternative of $${{S}}$$'s condition, $$n=0$$.
* Next, suppose $$n$$ is in both $${{N}}$$ and $${{S}}$$. Then clearly $$S(n)\in{{S}}$$ also because
    * $$S(n)\in{{N}}$$ by [Peano axiom 1](#definition-peano-axioms) and
    * there is obviously an $$n'\in{{N}}$$ such that $$S(n)=S(n')$$, namely, $$n$$ itself.

Thus, $${{N}}\subseteq{{S}}$$ by the conclusion of the last Peano axiom.


## Lemma SNoFPs

**$$S$$ has No Fixed Points**: _For any $$n\in{{N}}$$, $$n \neq S(n)$$_.

**Proof**: This time, $${{S}}=\{n\in{{N}}:\ n \neq S(n)\}$$.

* $$0\in{{S}}$$ because it satisfies both the conditions of $${{S}}$$ &mdash; i.e. both $$0\in{{N}}$$ and $$0 \neq S(0)$$ &mdash; by [Peano axioms 0 and 3](#definition-peano-axioms) respectively.
* Suppose $$n\in{{S}}$$, then certainly $$n \neq S(n)$$ where $$S(n)\in{{S}}$$ by [Peano axiom 1](#definition-peano-axioms). This, along with the contrapositive of [Peano axiom 2](#definition-peano-axioms), implies that $$S(n) \neq S(S(n))$$. But then, $$S(n)$$ satisfies $${{S}}$$'s condition so that $$S(n)\in{{S}}$$.

Thus, by the principle of induction, $${{N}}\subseteq{{S}}$$.


## Remarks

A couple of key points are already visible in these simple proofs about the naturals.

* Firstly, Peano axioms 0 and 1 are ubiquitous throughout the proofs. In fact, this is the case with all proofs about the naturals. However, unlike the ubiquitous induction principle, they are also very simple. It should be obvious whenever they are applicable. For these reasons, as are the cases with simple results, I henceforth leave them out of all proofs. Their applicability is implicit.
* Secondly, note how the induction principle is applied: one first wraps the lemma/theorem being proven in a set; only then, does Peano axiom 4 become applicable. This is largely unnecessary. One can, instead, state Peano axiom 4 as such
    <ol start="4">
        <li>if $$\phi$$ is an unary property such that $$\phi(0)$$ is true and for every $$n\in{{N}}$$, $$\phi(n)$$ implies $$\phi(S(n))$$, then $$\phi$$ is true for all of $${{N}}$$</li>
    </ol>