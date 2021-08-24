---
layout: default
title: Functors
---

Functors
===

This chapter we will change the tactic a bit (as I am sure you are a bit tired of jumping through different subjects) and we will examine some purely categorical concepts, using the structures that we saw so far as context. We will also generalize some of the concepts that we saw in these structures so they are valid for all categories.

Categories we saw so far
===

We already learned about many different types of categories: categories that have just one *object* (monoids, groups) 

![Types of categories](category_types_monoid.svg)

Categories that have only one *morphism* between any two objects (preorders, partial orders). 

![Types of categories](category_types_order.svg)

We also defined a lot of categories of different things most notably the ones based on logics/programming languages. But also less serious categories, as for example the color-mixing one. We even saw that those two categories have some similarities, like they are both distributive lattices and have greatest and least objects.

![Category of colors](category_color_mixing.svg)


But how exactly can we pinpoint such similarities and understand what they mean. How can we utilize the insights that we got from recognizing all of these structures as categories?  To do that, we must specify formal ways to connect categories to one another.

Categorical Isomorphisms
===

In chapter 1 we talked about set isomorphisms, which establish an equivalence between two sets. If you remember a set isomorphism is a two-way function between two sets. Or alternatively, you can think of an isomorphism as consisting of two "twin" functions each of which equals identity when composed with the other. 

![Set isomorphism](set_isomorphism.svg)

Then, in chapter 4 we mentioned order isomorphisms, which were like set isomorphisms, but with one extra condition - aside from being there, the function that defines the isomorphism has to preserve the order of the elements i.e. all elements have to have the same arrows pointing to and from them. Or more formally put: **a** and **b**, **a ≤ b** iff **F(a) ≤ F(b)**. 

![Order isomorphism](order_isomorphism.svg)

We can extend this definition to work for categories as well. Unlike orders, categories can have more than one morphism between two objects, so the definition would be a little more complex: given two categories, an isomorphism between them is an invertible function between the underlying sets of objects, *and* an invertible function between the morphisms that connect them, which maps each morphism to a morphism with the same signature. 

![Category isomorphism](category_isomorphism.svg)

Although longer, this definition is the same as the one we have for orders - it is just that with categories we have can have more than one arrows between two objects and so we need to specify which isomorphism corresponds to which, while in order theory we only need to verify that the corresponding morphisms actually exist (which is taken care of by the added condition). 

So those are categorical isomorphisms. But isomorphisms are actually very rare (the only one that comes to mind is the Curry-Howard-Lambek isomorphism from the last chapter). If two categories are isomorphic, then they are so similar that it would be more accurately counted as different representations of the same category.

<!--
comics:
OK, I think I got it - isomorphisms are when you have two similar pictures and you connect the dots.

Pretty much.
-->

More useful than isomorphisms, which are two-way connections between categories, are one-way connections between them, which we will examine next. 

What are functors
===

Having seen isomorphisms, which are the equivalent of two-way functions between categories, we can imagine how the equivalent one-way functions would look like. They are called *functors* and they work like this - a functor between two categories (let's call them **A** and **B**) consists of one function that maps the *objects* of **A** to the objects of **B** and one function that maps all *morphisms* of **A** to morphisms of **B** in a way that preserves the structure of the category.

![Functor](functor.svg)

Let's break the definition down.

object function
---

Firstly, we have a function between the categories' objects - these are just regular old functions, so the definition that we gave at chapter 1 applies.

> A function is a relationship between two sets which matches each element of one set, called the *domain* of the function, with exactly one element from another set, called the converse domain, or the *codomain* of the function.

![Functor for objects](functor_objects.svg)

morphism function
---

Secondly, functions between morphisms. Intuitively, we can think of them as just regular functions as well, but with the added requirement that signatures of the source and the target should match.

![Functor for morphisms](functor_morphisms.svg)

A more formal definition involves the concept of a set of morphisms that go between two objects in a category (called the *homomorphism set*). According to it, the function between morphisms of the two categories is just multiple functions between their homomorphism sets.

![Functor for morphisms](functor_morphisms_formal.svg)

Functor laws
---

Thirdly, the functions between the morphisms should preserve the structure of the category. As stated in the category definition in chapter 2.

> A category is a collection of **objects** (we can think of them as points) and **morphisms** (arrows) that go from one object to another, where:
> 1. Each object has to have the identity mophism.
> 2. There should be a way to compose two morphisms with an appropriate type signature into a third one in a way that is associative.

So this requirement translates to the following two laws, which are called the *functor laws*

1. Functions between morphisms should *preserve identities* i.e. all identity morphisms should be mapped to identity morphisms.

![Functor](functor_laws_identity.svg)

2. They should also *preserve composition* i.e. for any two morphisms **f** and **g**, the morphism that corresponds to their composition **F(g f)** in the source category should be the same as the morphism that corresponds to the composition of their counterparts in the target directory **F(g) F(f)**.

![Functor](functor_laws_composition.svg)

And this is all there is to it about functors - a simple but, as we will see shortly, very powerful idea.

Some examples 
===

Diagrams
---

Inductive and deductive functors
---

Functors in programming
---

Functors as selections
---

Functors as maps
---
If we take the 


Hom functors
---

Representable functors
===

Representable functors are set-valued functors that are isomorphic to the Hom functor

A Hom-functor can always be converted to any set-valued functor (Yoneda lemma). But not the other way around

So a functor is representable when we can convert its values to values of the Hom functor


Natural transformations
===

Limits
===

Yoneda Lemma
===
