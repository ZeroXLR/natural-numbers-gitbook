{% set N = "\\mathbb{N}" %}
{% set S = "\\Sigma" %}


> I end the exploration of order by showing two small but important results: it will be shown that addition and multiplication preserve order.


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
> Of course, in all the theorems and corollaries above, one can change whether $$z$$ adds/multiplies from the left or the right by commutativity.