{% set N = "\\mathbb{N}" %}


## Manifesto

It is often the case that one is interested in defining functions over the natural numbers. For example, one wants to define addition, multiplication and exponentiation over the natural numbers. To do this, one usually specifies the value of the intended function on $$0$$. Then, assuming that one has already defined the function for $$n$$, one proceeds to define the value of the function on $$S(n)$$.

This is the basic procedure of defining a recursive function over $${{N}}$$. First, however, one must be sure that this procedure even works &mdash; it is not immediately obvious that a function defined as such even exists **as a set** (recall that in set theory, a function $$X \to Y$$ is just a many-to-one subset of $$X \times Y$$).


{% set F = "\\mathcal{F}" %}

## Theorem RecDef0

**Definition by Recursion 0**. _Let $$X$$ be a set. Let $$x$$ be some element of $$X$$ and let $$\varphi:X \to X$$ be any function. Then, there exists a **unique** function $$f:{{N}} \to X$$ such that_

* $$f(0)=x$$ _and_
* $$f(S(n))=\varphi(f(n))$$.

**Proof**: Consider the class $${{F}}$$ of all subsets of $${{N}} \times X$$ that satisfy the two conditions above i.e.
$$
{{F}} = \{F \subseteq {{N}} \times X:\ (0,x) \in F \ \ \text{and}\ \ (S(n),\varphi(F_n)) \in F \ \text{if}\ (n,F_n) \in F\}
$$
This class is non-empty because obviously the entire product set $${{N}} \times X$$ itself satisfies both of the conditions of $${{F}}$$.

Now, define $$f$$ to be the intersection of all the $$F$$'s in $${{F}}$$ i.e. $$f=\bigcap{{F}}=\{p:\ F\in{{F}}\ \text{implies}\ p \in F\}$$. This is a valid set because $${{F}}$$ is non-empty; otherwise, one ends up with the bizarre consequence that $$f$$ is the universal class which is not a set. Also, since every element in $${{F}}$$ satisfies both the conditions in the theorem, so must $$f$$ satisfy both conditions of the theorem.

Next, one must show that $$f$$ is many-to-one i.e. it maps the same value to at most one value. This is substantially harder to show compared to the properties shown in the previous paragraph. Essentially, one has to show that if $$n\in{{N}}$$ and $$y,y' \in X$$ and $$(n,y), (n,y') \in f$$, then $$y = y'$$. This can be accomplished using induction:

* The property to be shown is true for $$0$$. For, suppose $$(0,y),(0,y') \in f$$. Well, $$(0,x) \in f$$ also. Now, if both $$y$$ and $$y'$$ are $$x$$, one is done. Otherwise, assume for the sake of a contradiction that one of them is not $$x$$. Without loss of generality let it be $$y$$ which is not equal to $$x$$. Consider, now, the set $$f'=f\setminus\{(0,y)\}$$. $$(0,x) \in f'$$ because $$(0,x) \in f$$ and $$(0,x)\neq(0,y)$$ by construction. Also, say $$(n,f_n) \in f'$$. Then, $$(n,f_n) \in f$$ also; so since $$f$$ satisfies the second condition of this theorem, $$(S(n),\varphi(f_n)) \in f$$. But as $$S(n) \neq 0$$ by [Peano axiom 3](README.md#introduction), it must be that $$(S(n),\varphi(f_n))\neq(0,y)$$; hence, $$(S(n),\varphi(f_n)) \in f'$$. Thus, $$f'$$ also satisfies the conditions of $${{F}}$$ i.e. $$f'\in{{F}}$$. But then,
$$
f=\bigcap{{F}} \subseteq f' = f\setminus\{(0,y)\} \subset f
$$
which is a contradiction, as $$f$$ cannot be a strict subset of itself.
* Now, suppose that the property is true for some $$n\in{{N}}$$. Thus, there is one and only one $$f_n \in X$$ such that $$(n,f_n) \in f$$. Now, consider any two $$(S(n),y),(S(n),y') \in f$$. Certainly, $$(S(n),\varphi(f_n)) \in f$$ also. Note that since $$\varphi$$ is a function, it has to be many-to-one, so that $$\varphi(f_n)$$ refers to a unique element of $$X$$. Hence, if both $$y$$ and $$y'$$ equal $$\varphi(f_n)$$, then necessarily $$y$$ equals $$y'$$ and one is done. Otherwise, assume for the sake of a contradiction that one of them is not $$\varphi(f_n)$$; w.l.o.g. let this be $$y$$. Consider, now, the set $$f' = f\setminus\{(S(n),y)\}$$. $$(0,x) \in f'$$ because $$(0,x) \in f$$ and $$(0,x)\neq(S(n),y)$$ (since $$0 \neq S(n)$$ by [Peano axiom 3](README.md#introduction)). Next, suppose $$(\nu,f_\nu) \in f'$$; then, $$(\nu,f_\nu) \in f$$ so that $$(S(\nu),\varphi(f_\nu)) \in f$$. Now, if $$\nu=n$$, then by the initial assumption, there is only one $$f_n$$ such that $$(n,f_n)=(\nu,f_n) \in f$$; so one must have $$f_\nu=f_n$$. Then, by construction, $$\varphi(f_\nu)=\varphi(f_n) \neq y$$; so one has that $$(S(\nu),\varphi(f_\nu))\neq(S(n),y)$$. If, on the other hand, $$\nu \neq n$$, then, by [Peano axiom 2](README#introduction), one has $$S(\nu) \neq S(n)$$, so that $$(S(\nu),\varphi(f_\nu))\neq(S(n),y)$$ again. Thus, in both cases, $$(S(\nu),\varphi(f_\nu)) \in f$$ and $$(S(\nu),\varphi(f_\nu))\neq(S(n),y)$$ i.e. $$(S(\nu),\varphi(f_\nu)) \in f'$$. Thus, $$f'$$ also satisfies the conditions of $${{F}}$$ i.e. $$f'\in{{F}}$$. But then,
$$
f=\bigcap{{F}} \subseteq f' = f\setminus\{(S(n),y)\} \subset f
$$
which is a contradiction.

This completes the induction to show that $$f$$ is many-to-one.

To complete the demonstration that $$f$$ is a function, one still needs to show that the domain and codomain of $$f$$ are $${{N}}$$ and $$X$$ respectively. Since the proofs needed for both are quite similar, I only demonstrate the fact that $$f$$'s domain is $${{N}}$$ i.e. that
$$
\text{dom}f=\{n:\ \exists \chi \in X\ [(n,\chi) \in f]\}={{N}}
$$
Well, certainly, since $$f\subseteq{{N}} \times X$$, $$\text{dom}f\subseteq{{N}}$$. Now, clearly $$0\in\text{dom}f$$ since $$(0,x) \in f$$. Also, if $$n\in\text{dom}f$$, then there is a $$\chi$$ such that $$(n,\chi) \in f$$; hence, $$(S(n),\varphi(\chi)) \in f$$ so that $$S(n) \in f$$. Thus, by induction, $${{N}}\subseteq\text{dom}f$$.

Finally, I show that $$f$$ is unique. To begin with, assume that there is another function $$f':{{N}} \to X$$ which satisfies the conditions of this theorem. Then, in particular, $$f'$$ is a subset of $${{N}} \times X$$ satisfying the conditions of $${{F}}$$ i.e. $$f'\in{{F}}$$. Hence, $$f=\bigcap{{F}} \subseteq f'$$. Next, to show that $$f' \subseteq f$$, suppose $$(n,\chi') \in f'$$. Then, necessarily, as $$f'\subseteq{{N}} \times X$$, $$n\in{{N}}$$ and $$\chi' \in X$$. Now, certainly, as $$f$$'s domain is the whole of $${{N}}$$, there is some $$\chi \in X$$ such that $$(n,\chi) \in f$$. Since $$f \subseteq f'$$, this means that $$(n,\chi) \in f'$$ also. But then, as $$f'$$ is a many-to-one mapping, it must be that $$\chi'=\chi$$; hence, $$(n,\chi') \in f$$ too.


## Theorem RecDef1

**Definition by Recursion 1**. _Let $$X$$ be a set. Let $$x$$ be some element of $$X$$ and let $$\varphi:X\times{{N}} \to X$$ be any function. Then, there exists a **unique** function $$f:{{N}} \to X$$ such that_

* $$f(0)=x$$ _and_
* $$f(S(n))=\varphi(f(n),n)$$.

**Proof Sketch**: Simply modify all occurrences of $$\varphi$$ in the previous proof appropriately. The logical structure itself needs no change.


## Examples

The two theorems just seen are among the most powerful in this book. They allow one to construct all the basic algebraic and order structure of $${{N}}$$:

* **Addition**: In [Theorem RecDef0](#theorem-recdef0), let $$X$$ be $${{N}}$$, $$x$$ be any natural number and $$\varphi$$ be the successor function $$S$$ itself. Then, the theorem says that to every choice of $$x$$ as above, there corresponds a unique function $$A_x:{{N}}\to{{N}}$$ such that $$A_x(0)=x$$ and $$A_x(S(y))=S(A_x(y))$$. Now, one can easily define the infix function $$+:{{N}}\times{{N}}\to{{N}}$$ to be $$x+y=A_x(y)$$ for any $$x,y\in{{N}}$$. In the view of this infix function, the conditions $$A_x(0)=x$$ and $$A_x(S(y))=S(A_x(y))$$ become $$x+0=x$$ and $$x+S(y)=S(x+y)$$ respectively. From this and the fact that $$S$$ is many-to-one, it is easy to see that $$x+S(0)=S(x+0)=S(x)$$. Denoting $$S(0)$$ as $$1$$, this becomes $$x+1=S(x)$$.
* **Multiplication**: In [Theorem RecDef1](#theorem-recdef1), choose $${{N}}$$, $$0$$ and addition ($$+$$) to be the raw materials for constructing multiplication. Then, the theorem says that to every $$x\in{{N}}$$ there corresponds a unique function $$M_x:{{N}}\to{{N}}$$ such that $$M_x(0)=0$$ and $$M_x(S(y))=M_x(y)+y$$. Now, one can define the infix function $$\cdot:{{N}}\times{{N}}\to{{N}}$$ as $$x \cdot y = M_x(y)$$ for every $$x,y\in{{N}}$$. Hence, $$x \cdot 0 = 0$$ and $$x\cdot(y+1)=x \cdot y + x$$.
* **Partial Order**: Define the $${{N}}$$-relation (i.e. subset of $${{N}}\times{{N}}$$) $$\leq$$ thus: $$x \leq y$$ iff $$\exists n\in{{N}}\ [x+n=y]$$. It is easy to see that this definition is at least **reflexive**: $$x \leq x$$ since $$x+0=x$$. Verifying the other two properties of a partial order will have to wait.
* **The Family of Sets $$\text{Fin}$$**: In [Theorem RecDef1](#theorem-recdef1), choose $$\mathcal{P}{{N}}=\{\Sigma:\Sigma\subseteq{{N}}\}$$, $$\emptyset$$ and $$\text{append}:(\Sigma,n)\mapsto\Sigma\cup\{n\}$$ to be the raw materials for constructing this family. Then, the theorem says that there is a unique function $$\text{Fin}:{{N}}\to\mathcal{P}{{N}}$$ such that $$\text{Fin}(0)=\emptyset$$ and $$\text{Fin}(S(n))=\text{Fin}(n)\ \text{append}\ n$$. Later, it will be shown that $$\text{Fin}(n)$$ is precisely the set of all natural numbers strictly less than $$n$$.