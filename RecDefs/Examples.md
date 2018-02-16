{% set N = "\\mathbb{N}" %}
{% set U = "\\mathcal{U}" %}


## Examples

The two theorems just seen are among the most powerful in this book. They allow one to construct all the basic algebraic and order structure of $${{N}}$$:

* **Addition**: In [RecDef0](README.md#theorem-recdef0), let $$X$$ be $${{N}}$$, $$x$$ be any natural and $$\varphi$$ be the successor function $$S$$ itself. Then, the theorem says that to every such $$x$$ as above, there corresponds a unique function $$A_x:{{N}}\to{{N}}$$ such that $$A_x(0)=x$$ and $$A_x(S(y))=S(A_x(y))$$. Now, simply define the infix-function $$+:{{N}}\times{{N}}\to{{N}}$$ to be $$x+y=A_x(y)$$ for any $$x,y\in{{N}}$$. Using this function, the conditions $$A_x(0)=x$$ and $$A_x(S(y))=S(A_x(y))$$ become $$x+0=x$$ and $$x+S(y)=S(x+y)$$ respectively. Also, using the fact that $$S$$ maps equals to equals, it is easy to see that $$x+S(0)=S(x+0)=S(x)$$. Denoting $$S(0)$$ as $$1$$, this becomes $$x+1=S(x)$$.
* **Multiplication**: In [RecDef1](README.md#theorem-recdef1), choose $${{N}}$$, $$0$$ and addition ($$+$$) to be the raw materials for constructing multiplication. Then, the theorem says that to every $$x\in{{N}}$$ there corresponds a unique function $$M_x:{{N}}\to{{N}}$$ such that $$M_x(0)=0$$ and $$M_x(S(y))=M_x(y)+x$$. Now, define the infix-function $$\cdot:{{N}}\times{{N}}\to{{N}}$$ as $$x \cdot y = M_x(y)$$ for every $$x,y\in{{N}}$$. Hence, $$x \cdot 0 = 0$$ and $$x\cdot(y+1)=x \cdot y + x$$ (assuming $$\cdot$$ has higher precedence than $$+$$ i.e. $$x \cdot y + x=(x \cdot y) + x$$).
* **Exponentiation**: In [RecDef1](README.md#theorem-recdef1), choose $${{N}}$$, $$S(0)$$ and multiplication ($$\cdot$$) as inputs. Then, to every $$x\in{{N}}$$ one gets a unique function $$E_x:{{N}}\to{{N}}$$ such that $$E_x(0)=S(0)$$ and $$E_x(S(y))=E_x(y) \cdot x$$. Now, define the placeholder-function $$\square^\square:{{N}}\times{{N}}\to{{N}}$$ as $$x^y = E_x(y)$$ for every $$x,y\in{{N}}$$. Hence, $$x^0 = 1$$ and $$x^{y+1}=x^y \cdot x$$ (assuming $$\square^\square$$ has higher precedence than $$\cdot$$).
* **Factorial**: In [RecDef1](README.md#theorem-recdef1), choose $${{N}}$$, $$S(0)$$ and the placeholder-function $$
\square\cdot S(\square):{{N}}\times{{N}}\ni(n,n') \mapsto n \cdot S(n')\in{{N}}
$$ as inputs. Then, one has a unique postfix-function $$!:{{N}}\to{{N}}$$ such that $$0!=S(0)$$ and $$S(y)!=y! \cdot S(y)$$.
* **Canonical Order**: The order that I am about to define comes about as a by-product of addition. Concretely, define the $${{N}}$$-relation (i.e. subset of $${{N}}\times{{N}}$$), $$\leq$$, thus: $$(x,y)\in\ \leq$$ iff $$\exists n\in{{N}}\ [x+n=y]$$. One often writes $$(x,y)\in\ \leq$$ in infix-form: $$x \leq y$$. One can see that this order is at least **reflexive**: $$x \leq x$$ since $$x+0=x$$. Verifying the other two properties of a partial order must wait.
* **Order of Divisibility**: I can also define an analogous order on the naturals based on multiplication. For this, define the $${{N}}$$-relation, $$\ |\ $$, thus: $$(x,y)\in \ |\ $$ iff $$\exists n\in{{N}}\ [x \cdot n=y]$$. One often writes $$(x,y)\in \ |\ $$ in infix-form: $$x\ |\ y$$ where $$x$$ is called a **factor** of $$y$$ while $$y$$ is called a **multiple** of $$x$$. Just like previous order, this is a partial order. However, verification of this fact must wait.
* **The Family of Sets $$\text{Fin}$$**: In [RecDef1](README.md#theorem-recdef1), choose $$\mathcal{P}{{N}}$$, $$\emptyset$$ and the infix-function $$
\oplus:\mathcal{P}{{N}}\times{{N}}\ni(\Sigma,n)\mapsto\Sigma\cup\{n\}\in\mathcal{P}{{N}}
$$ as inputs. Then, one gets a unique function $$\text{Fin}:{{N}}\to\mathcal{P}{{N}}$$ such that $$\text{Fin}(0)=\emptyset$$ and $$\text{Fin}(S(n))=\text{Fin}(n) \oplus n$$. Later, I show that $$\text{Fin}(n)$$ is precisely the set of all naturals strictly less than $$n$$.