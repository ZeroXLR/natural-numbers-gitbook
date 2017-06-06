{% set N = "\\mathbb{N}" %}
{% set U = "\\mathcal{U}" %}
{% set S = "\\mathcal{S}" %}
{% set E = "\\emptyset" %}

## The Idea of a Set

The theory of sets is deep and has many subtleties. Strictly speaking, what exactly are sets and what behaviors one should expect from them are still matters of debate in mathematical philosophy and logic. However, at the informal level &mdash; the level at which this book uses set theory &mdash; sets are conceptually simple things. They are just unordered collections of arbitrary objects. Note that when I say "unordered collections" and "objects", I do not pretend to mean anything mathematically precise by them. In fact, I cannot do so without either circular reasoning or infinite regress. Rather, I am merely appealing to one's intuitive ideas of what an "unordered collection" and an "arbitrary object" should be and hope that everyone more or less agrees on those ideas.

Moving on, a set is denoted either in **explicit form** where all the elements of the set are written down between curly braces or in **set builder form** where the condition/predicate satisfied by the elements of the set is written down between curly braces. An example of the former is $$\{0, 1\}$$, whereas as example of the latter is $$\{x:\ x\in{{N}}\ \text{and}\ x<2\}$$ (pretend that $${{N}}$$ is defined in the last example). Sometimes, in set builder notation, one of the conditions is snuck onto the left side of the '$$:$$'. For instance, I could have equally written the last example as $$\{x\in{{N}}:\ x<2\}$$.

If one thinks about the two denotations for a while, one will eventually realize that the set builder form is more expressive than the explicit form. One can, for example, easily denote and manipulate infinite sets with the set builder form, while one cannot humanly write down the explicit form of an infinite set. However, the set builder form is also _too_ powerful. In general, collections of the form $$\{x:\ \phi(x)\}$$ cannot be sets for arbitrary conditions $$\phi$$, lest one wants to fall victim to [Russell's Paradox](https://en.wikipedia.org/wiki/Russell's_paradox). Some of those arbitrary collections must either not exist or be something "larger" than sets, called **classes**. I do not want to talk extensively about classes in this book since their concept ventures too close to the deeper foundations of set theory that I wish to avoid. However, I mention them to motivate mention of a special class worth keeping in mind, even within informal set theory &mdash; the **universal class** $${{U}}$$ that contains all sets. In most set theories, this also means that $${{U}}$$ contains all the mathematical objects being talked about because, in those theories, most objects of mathematical interest are sets!

## Membership and Set Equality

As discussed above, sets are collections containing objects. To show that an object $$x$$ is inside a set $$A$$, one writes $$x \in A$$. One says that $$x$$ is a **member** of $$A$$. Two sets are equal if and only if they contain exactly the same members. More precisely, one says that sets $$A$$ and $$B$$ are equal if and only if given $$x \in A$$, one can show that $$x \in B$$ and given $$x \in B$$, one can show that $$x \in A$$.


## The Empty Set

One of the most important, if trivial, examples of sets is the **empty set** that contains no objects. It is either denoted by $$\emptyset$$ or denoted in its obvious explicit form $$\{\}$$. Interestingly, it can have many set builder forms. Inside a set theory where all objects of interest are sets, one of those forms is $$\{x\in{{U}}:\ x \neq x\}$$. This says that the empty set contains all and only those objects that are not equal to themselves. Of course, in any reasonable mathematical theory, every object _is_ in fact equal to itself. So, this denotation is basically a roundabout way of saying that the empty set has no members.


## Subsets

One calls a set $$A$$ a **subset** of a set $$B$$ when every object inside $$A$$ is also inside $$B$$ i.e. if $$x \in A$$, then $$x \in B$$. This fact is denoted by $$A \subseteq B$$. If, in addition, $$A$$ is not the whole of $$B$$, then one calls $$A$$ a **proper subset** of $$B$$, denoting this fact by $$A \subset B$$.

It should not be hard to see that two sets are equal if and only if each is a subset of the other. Furthermore, note the following useful observation: if $$A \subset B$$, then one necessarily has an object in $$B$$ that is not in $$A$$.


## Operations on Sets

In this book, I primarily use three operations to make new sets from old ones (assuming a set theory where all objects being talked about are also sets):
* **Union**: Given a set of many other sets $${{S}}$$,
$$
\bigcup{{S}}=\{x\in{{U}}:\ x \in S\ \text{for some}\ S \in {{S}}\}
$$ i.e. $$\bigcup{{S}}$$ is the set of all objects that are in _at least one_ of the sets inside $${{S}}$$.
* **Intersection**: Given a set of many other sets $${{S}}$$,
$$
\bigcap{{S}}=\{x\in{{U}}:\ x \in S\ \text{for all}\ S \in {{S}}\}
$$ i.e. $$\bigcap{{S}}$$ is the set of all objects that are common to _all_ the sets inside $${{S}}$$. Technically, $${{S}}$$ should be non-empty for $$\bigcap{{S}}$$ to be a set; otherwise, the intersection would be the whole of $${{U}}$$ which is not a set.
* **Power**: Given a set $$S$$
$$
\mathcal{P}S=\{X\in{{U}}:\ X \subseteq S\}
$$ i.e. $$\mathcal{P}S$$ is the set of all subsets of $$S$$.


## The Cartesian Product of Sets

Even though sets are unordered, one can manually construct order out of them. For instance, the ordered pair $$(x,y)$$ can be defined as $$\{\{x\},\{x,y\}\}$$. Given this definition, it is not hard to show that one can tell the left element $$x$$ apart from the right element $$y$$ in $$(x,y)$$ i.e. one can show that if $$(a,b)=(x,y)$$, then $$a=x$$ and $$b=y$$. Given two sets $$X$$ and $$Y$$, the set of all ordered pairs, where the left and right elements are taken from $$X$$ and $$Y$$ respectively, is denoted by $$X \times Y$$. More explicitly,
$$
X \times Y = \{p \in {{U}}:\ p=(x,y)\ \text{for some}\ x \in X\ \text{and some}\ y \in Y\}
$$ This set is called the **Cartesian Product** of $$X$$ and $$Y$$.

## Functions as Sets

A function $$f$$ with the **domain** set $$X$$ and the **codomain** set $$Y$$ is just a subset of $$X \times Y$$ satisfying thus:
* For every $$x \in X$$, there is _exactly one_ $$y\in Y$$ such that $$(x,y)\in f$$. One says that $$x$$ is **mapped to** $$y$$ and denotes this fact as $$f(x)$$. This denotation is unambiguous since, as said before, there is just a single $$y$$ that $$f(x)$$ could ever refer to.

Such a function $$f$$ is denoted as $$f:X \to Y$$. Next, I present the salient concepts about functions that the reader needs to keep in his/her mind while going through this book.

Given two functions $$f:X \to Y$$ and  $$f':Y \to Z$$ with matching codomain and domain $$Y$$, their **composition** $$(f' \circ f):X \to Z$$, defined by $$(f' \circ f)(x)=f'(f(x))$$, is also a function. The reader should translate this definition into the language of sets and verify that the claim is indeed true.

The set of all elements of $$Y$$ that gets mapped to by an element of a subset $$U \subseteq X$$ is denoted by $$f(U)$$. This is called the image set of $$U$$. More explicitly,
$$
f(U)=\{y \in Y:\ y=f(x)\ \text{for some}\ x \in U\}
$$
Obviously $$f(U)$$ is always a subset of $$Y$$.

For a given element of $$Y$$, the set of all elements of $$X$$ that map to that element is denoted by $$f^{-1}(y)$$. More explicitly,
$$
f^{-1}(y)=\{x \in X:\ f(x)=y\}
$$
Obviously $$f^{-1}(y)$$ is always a subset of $$X$$.

One says that $$f$$ is **injective** iff $$f(x)=f(\tilde{x})$$ implies $$x=\tilde{x}$$. Alternatively, by logical contraposition, $$x \neq \tilde{x}$$ implies $$f(x) \neq f(\tilde{x})$$.

On the other hand, one says that $$f$$ is **surjective** iff for every $$y \in Y$$ there exists an $$x \in X$$ such that $$f(x)=y$$. Using notation defined earlier, the reader can verify that surjectivity is equivalent to any of the following assertions:
* $$f(X)=Y$$
* $$f^{-1}(y)\neq{{E}}$$ for any $$y \in Y$$.

If a function is both injective and surjective, it is called **bijective**.

I now present some elementary results about functions in general. These results will be used later on in the book, which is why I present them with full proofs, instead of asking the reader to recall them by heart from prerequisite knowledge.


# Lemma RSIS

**Restriction to Subset and its Image is Surjection**: _For any function $$f:X \to Y$$ and $$U \subseteq X$$, restricting the function's domain and codomain to $$U$$ and $$f(U)$$, respectively, produces a surjection; furthermore, if $$f$$ is an injection, so is this restriction_.

**Proof**: As per the theorem, let $$f_U:U \to \tilde{Y}=f(U)$$ where for all $$x \in U$$, $$f_U(x)=f(x)$$. Now, suppose $$y \in \tilde{Y}$$. Then, by definition of $$f(U)$$, $$f(x)=y$$ for some $$x \in U$$. But then, $$f_U(x)=y$$. Hence, every $$y$$ in the codomain of $$f_U$$ is the image of some $$x$$ in its domain i.e. $$f_U$$ is surjective. Next, let $$f_U(x)=f_U(\tilde{x})$$ for $$x,\tilde{x} \in U$$. Then, $$f(x)=f(\tilde{x})$$ and, since $$U \subseteq X$$, $$x,\tilde{x} \in X$$. Thus, if $$f$$ is injective, then certainly $$x=\tilde{x}$$, meaning $$f_U$$ is injective too.


## Lemma ISSI

**Image of a Subset is a Subset of the Image**: _For any function $$f:X \to Y$$ and $$U \subseteq X$$, $$f(U) \subseteq Y$$_. _Furthermore, if $$f$$ is injective and $$U$$ is a strict subset of $$X$$, then $$f(U)$$ is a strict subset of $$Y$$_.

**Proof**: Let $$y \in f(U)$$. Then, there is some $$u \in U$$ such that $$f(u)=y$$. But, $$u \in X$$ also, so that $$y=f(u) \in Y$$. Hence, $$f(U) \subseteq Y$$.

Now, let $$f$$ be injective and $$U \subset X$$. Then, $$x \notin U$$ for some $$x \in X$$ i.e. for any $$u \in U$$, $$u \neq x$$. So, by injectivity, $$f(u) \neq f(x)$$ for all $$u \in U$$. Hence, $$f(x) \notin f(U)$$ but $$f(x) \in Y$$. So, $$f(U) \subset Y$$.


## Lemma LInvBijThenBij

**Left Inverse of a Bijection is a Bijection**: _If one has a function $$f:X \to Y$$ and a bijection $$f':Y \to X$$ where $$f(f'(y))=y$$ for all $$y \in Y$$ (i.e. $$f$$ is a **left inverse** of $$f'$$), then $$f$$ is bijection_.

**Proof**: Let me first show that $$f$$ is injective i.e. assuming $$f(x)=f(\tilde{x})$$, I will proceed to prove that $$x=x'$$. Now, since $$f'$$ is bijective, and therefore surjective, there are $$y,\tilde{y} \in Y$$ such that $$f'(y)=x$$ and  $$f'(\tilde{y})=\tilde{x}$$. Thus,
$$
y=f(f'(y))=f(x)=f(\tilde{x})=f(f'(\tilde{y}))=\tilde{y}
$$
where the beginning and ending equalities come from the given hypothesis that $$f$$ is a left inverse of $$f'$$. So $$f'$$ being a function, it maps equal values to exactly one value; hence, $$x=f'(y)=f'(\tilde{y})=\tilde{x}$$, which is the sought after result.

Next, showing the surjectivity of $$f$$ is very easy: for any $$y \in Y$$, there is obviously an element $$f'(y)$$ of $$X$$ such that $$f$$ maps that element to $$y$$ as $$f(f'(y))=y$$.


## Lemma CBB

**Composition of Bijections is a Bijection**: _Given bijections $$f:X \to Y$$ and $$f':Y \to Z$$, the composition $$(f' \circ f):X \to Z$$ is also a bijection_.

**Proof**: Given $$z \in Z$$, there is a $$y \in Y$$ such that $$f'(y)=z$$ (as $$f'$$ is surjective) and an $$x \in X$$ such that $$f(x)=y$$ (as $$f$$ is surjective). Hence, $$(f' \circ f)(x)=f'(f(x))=z$$. Next, given $$f'(f(x))=f'(f(\tilde{x}))$$, one first gets $$f(x)=f(\tilde{x})$$ (as $$f'$$ is injective) and then gets $$x=\tilde{x}$$ (as $$f$$ is injective).