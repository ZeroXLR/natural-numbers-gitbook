<div style="text-align:center">
	<a rel="license" href="https://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="https://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
</div>

---


{% set N = "\\mathbb{N}" %}

## Introduction

In this GitBook I rigorously prove properties about the natural numbers from first principles. By _first principles_, I refer to [_**informal set theory**_](https://en.wikipedia.org/wiki/Naive_set_theory) and the [_**Peano axioms**_](https://en.wikipedia.org/wiki/Peano_axioms). Assuming the former to be self-explanatory, I simply list the latter. It is assumed that there exists a unique set $${{N}}$$ such that

1. the symbol $$0$$ is in it
2. for every $$n$$ in this set, the string $$S(n)$$ is in the set too; $$S(n)$$ is called the _**successor**_ of $$n$$
3. for every $$n,n' \in {{N}}$$, $$n=n'$$ if and only if $$S(n)=S(n')$$; thus, if one thinks of $$S$$ as a function, this axiom says that it is _**injective**_
4. there exists no natural number $$n$$ such that $$S(n)=0$$
5. if $$\Sigma$$ is a set where $$0\in\Sigma$$ and for every $$n\in{{N}}$$, $$n\in\Sigma$$ implies $$S(n)\in\Sigma$$, then $${{N}}\subseteq\Sigma$$; this is the _**principle of induction**_ over the natural numbers

One caveat needs attention: in first order logic, where the very behavior of the equals-sign $$=$$ is, by default, undefined, one also needs to add two more properties to the list: that $$=$$ be an [equivalence relation](https://en.wikipedia.org/wiki/Equivalence_relation) and that $${{N}}$$ be closed under $$=$$. However, despite my adherence to rigor in this book, I will not split hairs to _this_ extent. Instead, over here, the equals-sign is simply the same equality used in informal set theory with all its expected properties.