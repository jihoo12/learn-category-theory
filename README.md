# learn-category-theory

## morphism
In the world of category theory, a morphism is the abstract generalization of a "process" or a "relationship" between two objects
<br>
<br>
if objects are things (like sets,groups,or spaces), Morphisms are the arrows that connect them. they can represent almost any kind of structural connection.
<br>
<br>

### Formal definition
A morphism $f: A \to B$ is a constituent of a category that consists of:
- A Source (Domain): The object $A$ where the arrow starts.
- A Target (Codomain): The object B where the arrow ends

For a collection of morphisms to be valid in a category, they must follow two golden rules:
- Composition: If you have a morphism $f: A \to B$ and another $g: B \to C$, there must be a third morphism $g \circ f: A \to C$ (the "composite").
- Identity: Every object $A$ must have an identity morphism $id_A: A \to A$ that does "nothing" when composed with other arrows.

## functor
**mapping between categories**
if you think of a category as a collection of objects and the morphism between them  
a funtor is a way to transport that entire structure into different category without breaking the rules of how those morphism work.

### components
To define a functor $F$ from category $\mathcal{C}$ to category $\mathcal{D}$ (written as $F : \mathcal{C} \to \mathcal{D}$), you need two things:
- object mapping: for every object $X$ in $mathcal{C}$,there is an object $F(X)$ in $mathcal{D}$.
- morphism mapping: for every morphism $f: X \to Y$ in $mathcal{C}$, there is an morphism $F(f): F(X) \to F(Y)$ in $\mathcal{D}$.

### rules
A mapping isn't a functor unless it respects the "spirit" of the original category. it must follow two strict rules"
- preservation of Identity
The functor must take the "do nothing" morphism of an object and turn it into the "do nothing" morphism of the new object.
$$F(\text{id}_X) = \text{id}_{F(X)}$$

- preservation of composition
if you can do two steps in the first category ($f$ then $g$),the functor must allow you to do those same steps in the second category and get the same result.
$$F(g \circ f) = F(g) \circ F(f)$$

### types of functors

| Type | Description |
| --- | --- |
| **Covariant** | The "standard" functor. It preserves the direction of arrows ($X \to Y$ stays $F(X) \to F(Y)$). |
| **Contravariant** | A "reversing" functor. It flips the arrows ($X \to Y$ becomes $F(Y) \to F(X)$). |
| **Endofunctor** | A functor that maps a category back to itself ($F: \mathcal{C} \to \mathcal{C}$). |

## monoid
a monoid (specifically a monoid object) is a generalization of the algebraic monoid you might know from basic math (like integers under addition).
<br>
Instead of just looking at a set with a binary operation, category theory looks at an object within a monoidal category that behaves like a monoid.

### the ingredients
To define a monoid in a category $C$, you first need $C$ to be a monoidal category.  
This means the category has:
- A way to combine objects: The tensor product $\otimes$.
- A "neutral" object: The unit object $I$.

### the definition
A monoid in ($(C, \otimes, I)$) consists of:
- An object $M$.
- A multiplication morphism; $\mu : M \otimes M \to M$.
- A unit morphism: $\eta : I \to M$.

For these to qualify as a monoid, they must satisfy two "rules" (axioms) represented by commuting diagrams:  
AssociativityThis ensures that if you combine three things, the grouping doesn't matter.
<br>
$$(M \otimes M) \otimes M \xrightarrow{\mu \otimes 1_M} M \otimes M \xrightarrow{\mu} M$$
must equal
$$M \otimes (M \otimes M) \xrightarrow{1_M \otimes \mu} M \otimes M \xrightarrow{\mu} M$$
UnitalityThis ensures that the unit $\eta$ actually acts like an identity element.
$$I \otimes M \xrightarrow{\eta \otimes 1_M} M \otimes M \xrightarrow{\mu} M$$
and
$$M \otimes I \xrightarrow{1_M \otimes \eta} M \otimes M \xrightarrow{\mu} M$$
must both be equal to the identity morphism $1_M$.

## natural transformation
relationship between functors
assume there are two categories C,D and there are two functors $F,G : C \to D$
natural transformation $alpha$ is a way to transform functor F to G
at this time for $X \in C$, $F(X)\xrightarrow{\alpha x}G(X)$ must exist in D and that arrows must preserve structure
for natural transformation it must satisifies that
for $(f: X \to Y) \in C$,for category D that must satisfies that
$$\alpha_Y \circ F(f) = G(f) \circ \alpha_X$$
| $F(X)$ | $\xrightarrow{\alpha_X}$ | $G(X)$ |
| --- | --- | --- |
| $\downarrow F(f)$ |  | $\downarrow G(f)$ |
| $F(Y)$ | $\xrightarrow{\alpha_Y}$ | $G(Y)$ |