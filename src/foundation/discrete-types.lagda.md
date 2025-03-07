---
title: Discrete types
---

```agda
module foundation.discrete-types where

open import foundation-core.discrete-types public

open import foundation.apartness-relations
open import foundation.binary-relations
open import foundation.coproduct-types
open import foundation.decidable-equality
open import foundation.decidable-types
open import foundation.dependent-pair-types
open import foundation.identity-types
open import foundation.negation
open import foundation.propositional-truncations
open import foundation.propositions
open import foundation.sets
open import foundation.tight-apartness-relations
open import foundation.universe-levels
```

## Idea

A discrete type is a type that has decidable equality.

## Properties

### The apartness relation on a discrete type is negated equality

```agda
module _
  {l : Level} (X : Discrete-Type l)
  where

  rel-apart-Discrete-Type : Rel-Prop l (type-Discrete-Type X)
  rel-apart-Discrete-Type x y = neg-Prop' (x ＝ y)
  
  apart-Discrete-Type : (x y : type-Discrete-Type X) → UU l
  apart-Discrete-Type x y = type-Prop (rel-apart-Discrete-Type x y)

  antireflexive-apart-Discrete-Type : is-antireflexive rel-apart-Discrete-Type
  antireflexive-apart-Discrete-Type x r = r refl

  symmetric-apart-Discrete-Type :
    is-symmetric apart-Discrete-Type
  symmetric-apart-Discrete-Type x y H p = H (inv p)

  cotransitive-apart-Discrete-Type :
    is-cotransitive rel-apart-Discrete-Type
  cotransitive-apart-Discrete-Type x y z r
    with has-decidable-equality-type-Discrete-Type X x z
  ... | inl refl = unit-trunc-Prop (inr (λ s → r (inv s)))
  ... | inr np = unit-trunc-Prop (inl np)

  is-tight-apart-Discrete-Type :
    is-tight rel-apart-Discrete-Type
  is-tight-apart-Discrete-Type x y =
    dn-elim-is-decidable (has-decidable-equality-type-Discrete-Type X x y)

  apartness-relation-Discrete-Type :
    Apartness-Relation l (type-Discrete-Type X)
  pr1 apartness-relation-Discrete-Type = rel-apart-Discrete-Type
  pr1 (pr2 apartness-relation-Discrete-Type) = antireflexive-apart-Discrete-Type
  pr1 (pr2 (pr2 apartness-relation-Discrete-Type)) =
    symmetric-apart-Discrete-Type
  pr2 (pr2 (pr2 apartness-relation-Discrete-Type)) =
    cotransitive-apart-Discrete-Type

  type-with-apartness-Discrete-Type : Type-With-Apartness l l
  pr1 type-with-apartness-Discrete-Type = type-Discrete-Type X
  pr2 type-with-apartness-Discrete-Type = apartness-relation-Discrete-Type

  tight-apartness-relation-Discrete-Type :
    Tight-Apartness-Relation l (type-Discrete-Type X)
  pr1 tight-apartness-relation-Discrete-Type =
    apartness-relation-Discrete-Type
  pr2 tight-apartness-relation-Discrete-Type =
    is-tight-apart-Discrete-Type

  type-with-tight-apartness-Discrete-Type : Type-With-Tight-Apartness l l
  pr1 type-with-tight-apartness-Discrete-Type =
    type-with-apartness-Discrete-Type
  pr2 type-with-tight-apartness-Discrete-Type =
    is-tight-apart-Discrete-Type
```
