{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> I end the exploration of order by showing some algebraic properties of order. The first few results deal with the fact that addition and multiplication preserve order:


## Theorem APO

**Addition Preserves Order**: _For any $$x,y,z\in{{N}}$$, $$x \leq y$$, iff $$x+z \leq y+z$$_.

**Proof**: Suppose $$x \leq y$$. Then one has a $$k\in{{N}}$$ such that $$x+k=y$$. Hence,
$$
(x+k)+z=x+(k+z)=x+(z+k)=(x+z)+k=y+z
$$
So, $$x+z \leq y+z$$.

Conversely, supposing $$x+z \leq y+z$$, by the the same sequence of equalities as above (except in reverse), one has that for some natural $$k$$, $$(x+k)+z=y+z$$. Then, by cancellation, one has that $$x+k=y$$ i.e. $$x \leq y$$.


## Corollary APOStrict

**Addition Preserves Strict Order**: _For any $$x,y,z\in{{N}}$$, $$x<y$$, iff $$x+z<y+z$$_.


## Theorem MPO

**Multiplication Preserves Order**: _For any $$x,y,z\in{{N}}$$, if $$x \leq y$$, then $$z \cdot x \leq z \cdot y$$_. _Also, if $$z \neq 0$$ and $$z \cdot x \leq z \cdot y$$, then $$x \leq y$$_.

**Proof**: Suppose that $$x \leq y$$. Then, $$x+k=y$$ for some natural $$k$$. So, $$
z \cdot (x+k)=z \cdot x+z \cdot k=z \cdot y
$$ by distributivity. Hence, $$z \cdot x \leq z \cdot y$$.

Now for the reverse direction (along with $$z \neq 0$$), one needs induction on $$x$$:
1. If $$x=0$$, then obviously $$x \leq y$$ because $$0$$ is the least natural number period.
2. Now assume that the reverse direction is true for some $$x$$. Now, suppose $$z \cdot S(x)=z \cdot x+z \leq z \cdot y$$ and $$z \neq 0$$. Then, for some natural $$k$$,
$$
(z \cdot x+z)+k=z \cdot x+(z+k)=z \cdot y
$$
Thus, $$z \cdot x \leq z \cdot y$$. So, by the inductive hypothesis, $$x \leq y$$. Now, since $$z \neq 0$$, it cannot have inverses. Therefore, $$z+k \neq 0$$, so that $$z \cdot x \neq z \cdot y$$ by (the contrapositive of) cancellation. Thus, $$x \neq y$$; otherwise, multiplication being a function, $$z \cdot x$$ would have equaled $$z \cdot y$$. Hence, $$x<y$$. But then, as $$S(x)$$ is the least element strictly greater than $$x$$, $$S(x) \leq y$$, which was to be shown.


## Corollary MPOStrict

**Multiplication Preserves Strict Order**: _For any $$x,y,z\in{{N}}$$, where $$z \neq 0$$, $$x<y$$ iff $$z \cdot x<z \cdot y$$_.


&nbsp;
> Of course, in all the theorems and corollaries above, one can change whether $$z$$ adds/multiplies from the left or the right by commutativity. Next, I define a limited from of subtraction which uses order to enforce the condition that only smaller (or equal) values should be subtracted from larger (or equal) values:


## Definition LimitedSubtraction

Note first that for $$x,y\in{{N}}$$, if $$x \leq y$$, then, by definition, one has a $$k\in{{N}}$$ such that $$x+k=y$$. This $$k$$ is, in fact, unique. For if there were another $$k'\in{{N}}$$ such that $$x+k'=y$$, then one would have $$x+k=x+k'$$, so that, by cancellation, $$k=k'$$.

Recall next that $$\leq$$ is [actually a subset of $${{N}}\times{{N}}$$](../RecursiveDefinitions.md#examples). Define, now, the following set $$
\geq\ =\{(y,x)\in{{N}}\times{{N}}:\ (x,y)\in\ \leq\}
$$ and then define subtraction as an infix-function $$-:\ \geq\ \to{{N}}$$ as follows. For any $$(y,x)\in\ \geq$$, by definition, $$x \leq y$$, so that there is a unique $$\delta_x^y\in{{N}}$$ such that $$x+\delta_x^y=y$$; so, simply set $$y-x=\delta_x^y$$.

The reader can proceed to investigate various algebraic properties of this definition. He or she will quickly find out that this subtraction is neither commutative nor even associative! However, multiplication does distribute over it.


&nbsp;
> Next, I define limited forms of the division function


## Definition LimitedDivision

Limited division comes in two forms: one form is floored while the other form is ceiling-ed. First, for any $$x,y\in{{N}}$$ **with $$y \neq 0$$**, define $$L_{x/y}=\{p\in{{N}}:\ y \cdot p \leq x\}$$ and $$U_{x/y}=\{p\in{{N}}:\ x \leq y \cdot p\}$$. I leave it to the readers to check that both of these sets are always non-empty and that, in the case of $$L_{x/y}$$, it is bounded above (**$$y \neq 0$$ is crucial for showing this!**). Hence, by the two forms of well-ordering, one can respectively define:

* $$\lfloor\square/\square\rfloor:{{N}}\times({{N}}\setminus\{0\})\ni(x,y)\mapsto\text{max}(L_{x/y})\in{{N}}$$
* $$\lceil\square/\square\rceil:{{N}}\times({{N}}\setminus\{0\})\ni(x,y)\mapsto\text{min}(U_{x/y})\in{{N}}$$

The reader can also check the following properties for him or herself:

* $$\lfloor x/y \rfloor \leq \lceil x/y \rceil$$
* $$\lfloor x/y \rfloor = \lceil x/y \rceil$$ iff there exists a $$p\in{{N}}$$ such that $$y \cdot p=x$$. Note that, such a $$p$$ must be both $$\text{max}(L_{x/y})$$ and $$\text{min}(U_{x/y})$$. Therefore, it has to be unique, as greatest and least elements always are. Hence, in this case, one writes this $$p$$ as simply $$x/y$$.
* $$z\cdot\lfloor x/y \rfloor \leq \lfloor (z \cdot x)/y \rfloor$$ and $$\lceil (z \cdot x)/y \rceil \leq z\cdot\lceil x/y \rceil$$; but if $$\lfloor x/y \rfloor = \lceil x/y \rceil$$, then $$z \cdot (x/y)=(z \cdot x)/y$$

No doubt, the reader can think of the usual properties of normal division and test how they fare against these limited forms of division.