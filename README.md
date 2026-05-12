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