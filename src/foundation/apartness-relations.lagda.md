---
title: Apartness relations
---

```agda
module foundation.apartness-relations where

open import foundation.binary-relations
open import foundation.cartesian-product-types
open import foundation.coproduct-types
open import foundation.dependent-pair-types
open import foundation.disjunction
open import foundation.empty-types
open import foundation.existential-quantification
open import foundation.identity-types
open import foundation.negation
open import foundation.propositional-truncations
open import foundation.propositions
open import foundation.universe-levels
```

## Idea

An apartness relation on a type `A` is a relation `R` which is

  - Antireflexive: For any `a : A` we have `¬ (R a a)`
  - Symmetric: For any `a b : A` we have `R a b → R b a`
  - Cotransitive: For any `a b c : A` we have `R a b → R a c ∨ R b c`.

The idea of an apartness relation `R` is that `R a b` holds if you can positively establish a difference between `a` and `b`. For example, two subsets `A` and `B` of a type `X` are apart if we can find an element that is in the symmetric difference of `A` and `B`.

## Definitions

### Apartness relations

```agda
module _
  {l1 l2 : Level} {A : UU l1} (R : A → A → Prop l2)
  where

  is-antireflexive : UU (l1 ⊔ l2)
  is-antireflexive = (a : A) → ¬ (type-Prop (R a a))

  is-consistent : UU (l1 ⊔ l2)
  is-consistent = (a b : A) → (a ＝ b) → ¬ (type-Prop (R a b))

  is-cotransitive : UU (l1 ⊔ l2)
  is-cotransitive =
    (a b c : A) → type-hom-Prop (R a b) (disj-Prop (R a c) (R b c))

  is-apartness-relation : UU (l1 ⊔ l2)
  is-apartness-relation =
    ( is-antireflexive) ×
    ( ( is-symmetric (λ x y → type-Prop (R x y))) ×
      ( is-cotransitive))

Apartness-Relation : {l1 : Level} (l2 : Level) (A : UU l1) → UU (l1 ⊔ lsuc l2)
Apartness-Relation l2 A =
  Σ (A → A → Prop l2) is-apartness-relation

module _
  {l1 l2 : Level} {A : UU l1} (R : Apartness-Relation l2 A)
  where

  rel-Apartness-Relation : A → A → Prop l2
  rel-Apartness-Relation = pr1 R

  apart-Apartness-Relation : A → A → UU l2
  apart-Apartness-Relation x y = type-Prop (rel-Apartness-Relation x y)

  antirefl-Apartness-Relation : is-antireflexive rel-Apartness-Relation
  antirefl-Apartness-Relation = pr1 (pr2 R)

  consistent-Apartness-Relation : is-consistent rel-Apartness-Relation
  consistent-Apartness-Relation x .x refl =
    antirefl-Apartness-Relation x

  symmetric-Apartness-Relation : is-symmetric apart-Apartness-Relation
  symmetric-Apartness-Relation = pr1 (pr2 (pr2 R))

  cotransitive-Apartness-Relation : is-cotransitive rel-Apartness-Relation
  cotransitive-Apartness-Relation = pr2 (pr2 (pr2 R))
```

### Types equipped with apartness relation

```agda
Type-With-Apartness :
  (l1 l2 : Level) → UU (lsuc l1 ⊔ lsuc l2)
Type-With-Apartness l1 l2 =
  Σ (UU l1) (λ A → Apartness-Relation l2 A)

module _
  {l1 l2 : Level} (A : Type-With-Apartness l1 l2)
  where

  type-Type-With-Apartness : UU l1
  type-Type-With-Apartness = pr1 A

  apartness-relation-Type-With-Apartness :
    Apartness-Relation l2 type-Type-With-Apartness
  apartness-relation-Type-With-Apartness = pr2 A

  rel-apart-Type-With-Apartness : Rel-Prop l2 type-Type-With-Apartness
  rel-apart-Type-With-Apartness =
    rel-Apartness-Relation apartness-relation-Type-With-Apartness

  apart-Type-With-Apartness :
    (x y : type-Type-With-Apartness) → UU l2
  apart-Type-With-Apartness =
    apart-Apartness-Relation apartness-relation-Type-With-Apartness

  antirefl-apart-Type-With-Apartness :
    is-antireflexive rel-apart-Type-With-Apartness
  antirefl-apart-Type-With-Apartness =
    antirefl-Apartness-Relation apartness-relation-Type-With-Apartness

  consistent-apart-Type-With-Apartness :
    is-consistent rel-apart-Type-With-Apartness
  consistent-apart-Type-With-Apartness =
    consistent-Apartness-Relation apartness-relation-Type-With-Apartness

  symmetric-apart-Type-With-Apartness :
    is-symmetric apart-Type-With-Apartness
  symmetric-apart-Type-With-Apartness =
    symmetric-Apartness-Relation apartness-relation-Type-With-Apartness

  cotransitive-apart-Type-With-Apartness :
    is-cotransitive rel-apart-Type-With-Apartness
  cotransitive-apart-Type-With-Apartness =
    cotransitive-Apartness-Relation apartness-relation-Type-With-Apartness
```

### Apartness on the type of functions into a type with an apartness relation

```agda
module _
  {l1 l2 l3 : Level} (X : UU l1) (Y : Type-With-Apartness l2 l3)
  where
  
  rel-apart-function-into-Type-With-Apartness :
    Rel-Prop (l1 ⊔ l3) (X → type-Type-With-Apartness Y)
  rel-apart-function-into-Type-With-Apartness f g =
    ∃-Prop X (λ x → apart-Type-With-Apartness Y (f x) (g x))

  apart-function-into-Type-With-Apartness :
    Rel (l1 ⊔ l3) (X → type-Type-With-Apartness Y)
  apart-function-into-Type-With-Apartness f g =
    type-Prop (rel-apart-function-into-Type-With-Apartness f g)

  is-prop-apart-function-into-Type-With-Apartness :
    (f g : X → type-Type-With-Apartness Y) →
    is-prop (apart-function-into-Type-With-Apartness f g)
  is-prop-apart-function-into-Type-With-Apartness f g =
    is-prop-type-Prop (rel-apart-function-into-Type-With-Apartness f g)
```

## Properties

```agda
module _
  {l1 l2 l3 : Level} (X : UU l1) (Y : Type-With-Apartness l2 l3)
  where

  is-antireflexive-apart-function-into-Type-With-Apartness :
    is-antireflexive (rel-apart-function-into-Type-With-Apartness X Y)
  is-antireflexive-apart-function-into-Type-With-Apartness f H =
    apply-universal-property-trunc-Prop H
      ( empty-Prop)
      ( λ (x , a) → antirefl-apart-Type-With-Apartness Y (f x) a)

  is-symmetric-apart-function-into-Type-With-Apartness :
    is-symmetric (apart-function-into-Type-With-Apartness X Y)
  is-symmetric-apart-function-into-Type-With-Apartness f g H =
    apply-universal-property-trunc-Prop H
      ( rel-apart-function-into-Type-With-Apartness X Y g f)
      ( λ (x , a) →
        unit-trunc-Prop
          ( x , symmetric-apart-Type-With-Apartness Y (f x) (g x) a))

  is-cotransitive-apart-function-into-Type-With-Apartness :
    is-cotransitive (rel-apart-function-into-Type-With-Apartness X Y)
  is-cotransitive-apart-function-into-Type-With-Apartness f g h H =
    apply-universal-property-trunc-Prop H
      ( disj-Prop
        ( rel-apart-function-into-Type-With-Apartness X Y f h)
        ( rel-apart-function-into-Type-With-Apartness X Y g h))
      ( λ (x , a) →
        apply-universal-property-trunc-Prop
         ( cotransitive-apart-Type-With-Apartness Y (f x) (g x) (h x) a)
         ( disj-Prop
           ( rel-apart-function-into-Type-With-Apartness X Y f h)
           ( rel-apart-function-into-Type-With-Apartness X Y g h))
         ( λ { (inl b) →
               inl-disj-Prop
                 ( rel-apart-function-into-Type-With-Apartness X Y f h)
                 ( rel-apart-function-into-Type-With-Apartness X Y g h)
                 ( unit-trunc-Prop (x , b)) ;
               (inr b) →
               inr-disj-Prop
                 ( rel-apart-function-into-Type-With-Apartness X Y f h)
                 ( rel-apart-function-into-Type-With-Apartness X Y g h)
                 ( unit-trunc-Prop (x , b))}))

  exp-Type-With-Apartness : Type-With-Apartness (l1 ⊔ l2) (l1 ⊔ l3)
  pr1 exp-Type-With-Apartness = X → type-Type-With-Apartness Y
  pr1 (pr2 exp-Type-With-Apartness) =
    rel-apart-function-into-Type-With-Apartness X Y
  pr1 (pr2 (pr2 exp-Type-With-Apartness)) =
    is-antireflexive-apart-function-into-Type-With-Apartness
  pr1 (pr2 (pr2 (pr2 exp-Type-With-Apartness))) =
    is-symmetric-apart-function-into-Type-With-Apartness
  pr2 (pr2 (pr2 (pr2 exp-Type-With-Apartness))) =
    is-cotransitive-apart-function-into-Type-With-Apartness
```
