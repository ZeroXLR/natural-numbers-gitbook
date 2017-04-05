{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> I now prove the expected algebraic properties of $$+$$ and $$\cdot$$. By the end of all the proofs, one will have characterized the natural numbers as a special algebraic object called a [semiring](https://en.wikipedia.org/wiki/Semiring).


## Lemma AssocAdd

**Associativity of Addition**: _For all $$x,y,z\in{{N}}$$, $$(x+y)+z=x+(y+z)$$_.

**Proof**: As usual, let $${{S}}=\{z\in{{N}}:\ \forall x,y\in{{N}}\ [(x+y)+z=x+(y+z)]\}$$.

1. $$0\in{{S}}$$ because $$(x+y)+0=x+y=x+(y+0)$$ by the [definition of addition](RecursiveDefinitions.md#examples) applied to $$x+y$$ for the first equality and to $$y$$ for the second equality.
2. Suppose, now, that $$z\in{{S}}$$. Then, for any $$x,y\in{{N}}$$:
$$
\begin{aligned}
x+(y+S(z)) &= x+S(y+z) \ \text{by the definition of addition}\\
           &= S(x+(y+z)) \ \text{by the definition of addition}\\
           &= S((x+y)+z) \ \text{since }z\in{{S}}\\
           &= (x+y)+S(z)
\end{aligned}
$$

This completes the induction and shows that $${{N}}\subseteq{{S}}$$, so that any natural number must satisfy the set condition of $${{S}}$$, which is the lemma itself.


## Lemma CommutAdd

**Commutativity of Addition**: _For all $$x,y\in{{N}}$$, $$x+y=y+x$$_.

**Proof**: As always, let $${{S}}=\{y\in{{N}}:\ \forall x\in{{N}}\ [x+y=y+x]\}$$.

1. One needs to show that $$0\in{{S}}$$ i.e. for all $$x\in{{N}}$$, $$x+0=0+x$$ This, itself, requires a mini-induction on $$x$$!
    * Well, if $$x=0$$, $$x+0=0+0=0=0+0=0+x$$. The reader can fill in the details as needed.
    * Now, suppose the claim is true for $$x$$. Then, $$0+S(x)=S(0+x)$$ by one of the [recursive properties of addition](RecursiveDefinitions.md#examples). But, as $$x$$ satisfies the claim, $$S(0+x)=S(x+0)$$; then, $$S(x+0)=S(x)$$ as $$x+0=x$$ by the other [recursive property of addition](RecursiveDefinitions.md#examples). And finally, the latter property also produces $$S(x)=S(x)+0$$.
2. Now, suppose $$y\in{{S}}$$. Then, for any $$x\in{{N}}$$:
$$
\begin{aligned}
x+S(y) &= S(x+y) \ \text{by the definition of addition}\\
       &= S(y+x) \ \text{since }y\in{{S}}\\
       &= (y+x)+S(0) \ \text{by a property of addition shown earlier}\\
       &= y+(x+S(0)) \ \text{by associativity}\\
\end{aligned}
$$
At this point, one is stuck. One needs the fact that $$x+S(0)=S(0)+x$$ to push the argument through. Because if that were true,
$$
\begin{aligned}
y+(x+S(0)) &= y+(S(0)+x) \ \text{by the property yet to be proven}\\
           &= (y+S(0))+x \ \text{by associativity}\\
           &= S(y)+x \ \text{by a property of addition shown earlier}
\end{aligned}
$$ So then, how does one show that $$x+S(0)=S(0)+x$$? By induction on $$x$$ of course!
    * If $$x=0$$, $$x+S(0)=S(x)=S(0)=S(0)+0=S(0)+x$$. The reader can fill in the relevant details.
    * Now, assume that the claim is true for $$x$$. Then
    $$
    \begin{aligned}
        S(x)+S(0) &= S(S(x)) \ \text{by a property of addition shown earlier}\\
                  &= S(x+S(0)) \ \text{by the same property used on }x\\
                  &= S(S(0)+x) \ \text{as }x\text{ satisfies the claim}\\
                  &= S(0)+S(x) \ \text{by the definition of addition}
    \end{aligned}
    $$


## Lemma IdAdd

**Identity of Addition**: _For all $$x\in{{N}}$$, $$x+0=0+x=x$$_.

**Proof**: Obviously $$x+0=x$$ by the [definition of addition](RecursiveDefinitions.md#examples) itself. At the same time, by [commutativity](#lemma-commutadd), $$0+x=x+0=x$$.


## Lemma CancAdd

**Addition is Cancellative**: _For all $$x,y,z\in{{N}}$$, if $$x+z=y+z$$, then $$x=y$$_.

**Proof**: Note that by the [definition of addition](RecursiveDefinitions.md#examples), the lemma is certainly true for $$z=0$$. In fact, the lemma is also true for $$z=S(0)$$: if $$x+S(0)=y+S(0)$$, then $$S(x)=x+S(0)=y+S(0)=S(y)$$ (I am using a [property of addition shown in the previous chapter](RecursiveDefinitions.md#examples)). Then, by [Peano axiom 2](WarmUp.md#definition-peano-axioms), $$x=y$$. Thus, to prove the lemma with induction, one simply needs to assume that it holds for some $$z\in{{N}}$$ and then show that it holds for $$S(z)$$. So suppose it holds for $$z$$ and suppose $$x+S(z)=y+S(z)$$. Then,
$$
\begin{aligned}
(x+z)+S(0) &= x+(z+S(0)) \ \text{by associativity}\\
           &= x+S(z) \ \text{by a property of addition shown earlier}\\
           &= y+S(z) \ \text{by hypothesis}\\
           &= y+(z+S(0)) \ \text{by a property of addition shown earlier}\\
           &= (y+z)+S(0) \ \text{by associativity}
\end{aligned}
$$
Now, since the lemma is true for $$S(0)$$, $$x+y=y+z$$. But the lemma is also true for $$z$$; so, $$x=y$$.

Note that because of [commutativity](#lemma-commutadd), one can also cancel from the left i.e. if $$z+x=z+y$$, then $$x=y$$.


&nbsp;
> So far, I have shown that the addition function on $${{N}}$$ is associative, commutative and cancellative. It also has an identity. What this means is that $${{N}}$$ is a cancellative, commutative [monoid](https://en.wikipedia.org/wiki/Monoid) under $$+$$.