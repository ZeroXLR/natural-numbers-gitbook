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
> So far, I have shown that the addition function on $${{N}}$$ is associative, commutative and cancellative. It also has an identity. What this means is that $${{N}}$$ is a cancellative, commutative [monoid](https://en.wikipedia.org/wiki/Monoid) under $$+$$. I now turn to multiplication:


## Lemma AssocMultiply

**Associativity of Multiplication**: _For all $$x,y,z\in{{N}}$$, $$(x \cdot y) \cdot z=x \cdot (y \cdot z)$$_.

**Proof**: As usual, let $${{S}}=\{z\in{{N}}:\ \forall x,y\in{{N}}\ [(x \cdot y) \cdot z=x \cdot (y \cdot z)]\}$$.

1. $$0\in{{S}}$$ because $$(x \cdot y) \cdot 0=0=x \cdot 0=x \cdot (y \cdot 0)$$ by the [definition of multiplication](RecursiveDefinitions.md#examples).
2. Suppose, now, that $$z\in{{S}}$$. Then, for any $$x,y\in{{N}}$$:
$$
\begin{aligned}
x \cdot (y \cdot S(z)) &= x \cdot (y \cdot z + y) \ \text{by the definition of multiplication}\\
                       &= x \cdot (y \cdot z) + x \cdot y \ \text{by the same definition}\\
                       &= (x \cdot y) \cdot z + x \cdot y \ \text{since }z\in{{S}}\\
                       &= (x \cdot y) \cdot S(z) \ \text{by the definition of multiplication}
\end{aligned}
$$


## Lemma RDistMultiplyAdd

**Right Distributivity of Multiplication over Addition**: _For all $$x,y,z\in{{N}}$$, $$(x+y) \cdot z=x \cdot z + y \cdot z$$_.

**Proof**: Let $${{S}}=\{z\in{{N}}:\ \forall x,y\in{{N}}\ [(x+y) \cdot z=x \cdot z + y \cdot z]\}$$.
1. $$0\in{{S}}$$ as $$(x+y) \cdot 0=0=0+0=x \cdot 0 + y \cdot 0=x \cdot z + y \cdot z$$.
2. Consider some $$z\in{{S}}$$. Then $$(x+y) \cdot S(z)=(x+y) \cdot z + (x+y)$$
$$
\begin{aligned}
(x+y) \cdot S(z) &= (x+y) \cdot z + (x+y) \ \text{by the definition of multiplication}\\
                 &= (x \cdot z + y \cdot z)+(x+y) \ \text{since }z\in{{S}}\\
                 &= (x \cdot z + x)+(y \cdot z + y) \ \text{by associativity and commutativity of addition}\\
                 &= x \cdot S(z) + y \cdot S(z) \ \text{by the definition of multiplication}
\end{aligned}
$$


## Lemma CommutMultiply

**Commutativity of Multiplication**: _For all $$x,y\in{{N}}$$, $$x \cdot y=y \cdot x$$_.

**Proof**: As always, let $${{S}}=\{y\in{{N}}:\ \forall x\in{{N}}\ [x \cdot y=y \cdot x]\}$$.

1. One needs to show that $$0\in{{S}}$$ i.e. for all $$x\in{{N}}$$, $$x \cdot 0=0 \cdot x$$. So do induction on $$x$$
    * Well, if $$x=0$$, $$x \cdot 0=0 \cdot 0=0=0 \cdot 0=0 \cdot x$$.
    * Now, say the claim holds for $$x$$. Then, $$0 \cdot S(x)=0 \cdot x + 0=0 \cdot x=x \cdot 0=0=S(x) \cdot 0$$. The reader can fill in the details as needed.
2. Now, suppose $$y\in{{S}}$$. Then, for any $$x\in{{N}}$$:
$$
\begin{aligned}
x \cdot S(y) &= x \cdot y + x \ \text{by the definition of multiplication}\\
       &= y \cdot x + x \ \text{since }y\in{{S}}\\
       &= y \cdot x + (0 + x) \ \text{zero is the additive identity}\\
       &= y \cdot x + (x \cdot 0 + x) \ \text{by the definition of multiplication}\\
       &= y \cdot x + x \cdot S(0) \ \text{by the definition of multiplication}\\
\end{aligned}
$$
Just as with addition, one is now stuck. One needs the fact that $$x \cdot S(0)=S(0) \cdot x$$ to push the argument through. Because if that were true,
$$
\begin{aligned}
y \cdot x + x \cdot S(0) &= y \cdot x + S(0) \cdot x \ \text{by the property yet to be proven}\\
                         &= (y+S(0)) \cdot x \ \text{by right distributivity}\\
                         &= S(y) \cdot x \ \text{by a property of addition shown earlier}
\end{aligned}
$$ So, just like before, one does induction on $$x$$:
    * If $$x=0$$, $$x \cdot S(0)=x \cdot 0 + x=0+0=0=S(0) \cdot 0=S(0) \cdot x$$. The reader can fill in the relevant details.
    * Now, assume that the claim is true for $$x$$. Then
    $$
    \begin{aligned}
        S(x) \cdot S(0) &= (x+S(0)) \cdot S(0) \ \text{by a property of addition shown earlier}\\
                        &= x \cdot S(0) + S(0) \cdot S(0) \ \text{by right distributivity}\\
                        &= S(0) \cdot x + S(0) \cdot S(0) \ \text{as }x\text{ satisfies the claim}\\
                        &= S(0) \cdot x + (S(0) \cdot 0 + S(0)) \ \text{by the definition of multiplication}\\
                        &= S(0) \cdot x + (0 + S(0)) \ \text{by the definition of multiplication}\\
                        &= S(0) \cdot x + S(0) \ \text{zero is the additive identity}\\
                        &= S(0) \cdot S(x) \ \text{by the definition of multiplication}
    \end{aligned}
    $$


## Lemma IdMultiply

**Identity of Multiplication**: _For all $$x\in{{N}}$$, $$x \cdot 1=1 \cdot x=x$$ where $$1=S(0)$$_.

**Proof**: Note that $$x \cdot 1=x \cdot S(0)=x \cdot 0 + x = 0+x=x$$. The reader can fill in the relevant details for manipulations involving $$+$$. For the manipulations involving $$\cdot$$, note the [definition of multiplication and some associated properties shown earlier](RecursiveDefinitions.md#examples). At the same time, by [commutativity](#lemma-commutmultiply), $$1 \cdot x=x \cdot 1=x$$.


## Lemma LDistMultiplyAdd

**Left Distributivity of Multiplication over Addition**: _For all $$x,y,z\in{{N}}$$, $$z \cdot (x+y)=z \cdot x + z \cdot y$$_.

**Proof Sketch**: Simply apply [commutativity](#lemma-commutmultiply) of $$\cdot$$ to [right distributivity](#lemma-rdistmultiplyadd).


## Lemma ZAnnMultiply

**Zero Annihilates by Multiplication**: _For all $$x\in{{N}}$$, $$x \cdot 0=0 \cdot x=0$$_.

**Proof Sketch**: Obviously $$x \cdot 0=0$$ by definition. Applying [commutativity](#lemma-commutmultiply) to this yields the other equality.


## Lemma NoZDiv

**$${{N}}$$ has No Zero Divisors**: _For all $$x,y\in{{N}}$$, if $$x \cdot y = 0$$, then $$x=0$$ or $$y=0$$_.

**Proof**: Suppose, for the sake of proving the contrapositive, that neither $$x\in{{N}}$$ nor $$y\in{{N}}$$ is $$0$$. Then, by [Lemma ExPre](WarmUp.md#lemma-expre), there are $$x',y'\in{{N}}$$ such that $$S(x')=x$$ and $$S(y')=y$$. Then,
$$
x \cdot y=S(x') \cdot S(y')=S(x') \cdot y'+S(x')=S(S(x') \cdot y'+x')
$$
by the [definitions of addition and multiplication alone](RecursiveDefinitions.md#examples). But then, by [Peano axiom 3](WarmUp.md#definition-peano-axioms), $$S(S(x') \cdot y'+x') = x \cdot y \neq 0$$.


## Lemma CancMultiply

**Multiplication is Cancellative**: _For all $$x,y,z\in{{N}}$$, if $$z \neq 0$$ and $$x \cdot z=y \cdot z$$, then $$x=y$$_.

**Proof**: Let $${{S}}=\{x\in{{N}}:\ \forall y,z\in{{N}}\ [\text{if}\ z \neq 0\ \text{and}\ x \cdot z=y \cdot z\text{, then}\ x=y]\}$$.
1. To show $$0\in{{S}}$$, suppose that $$z \neq 0$$ and $$0 \cdot z=0=y \cdot z$$. But then by the [previous lemma](#lemma-nozdiv), $$y$$ must be $$0$$.
2. Now, assume that $$x\in{{S}}$$. To show $$S(x)\in{{S}}$$ also, assume the hypothesis of the lemma i.e. suppose that $$z \neq 0$$ and that
$$
S(x) \cdot z=z \cdot S(x)=z \cdot x + z=x \cdot z + z=y \cdot z
$$
Now, by [Peano axiom 3](WarmUp.md#definition-peano-axioms), $$S(x) \neq 0$$. Since also, $$z \neq 0$$ by hypothesis, one has that $$y \neq 0$$; otherwise, $$S(x) \cdot z=y \cdot z=0$$ contradicting the previous lemma. Hence, by [Lemma ExPre](WarmUp.md#lemma-expre), there is a $$y'\in{{N}}$$ such that $$S(y')=y$$. So,
$$
x \cdot z + z=y \cdot z=S(y') \cdot z=z \cdot S(y')=z \cdot y' + z=y' \cdot z + z
$$
Now, by [additive cancellation](#lemma-cancadd), $$x \cdot z=y' \cdot z$$. But as $$x\in{{S}}$$ and $$z \neq 0$$, this means that $$x=y'$$, so that $$S(x)=S(y')=y$$ by [Peano axiom 2](WarmUp.md#definition-peano-axioms). This concludes the induction.

Note that because of [commutativity](#lemma-commutmultiply), one can also cancel from the left i.e. if $$z \cdot x=z \cdot y$$, then $$x=y$$.


## Remarks

This concludes the basic exploration of the algebraic structure of $${{N}}$$. All of these properties imply that $${{N}}$$ is a commutative, cancellative semiring that is also multiplicatively cancellative for all values except $$0$$.