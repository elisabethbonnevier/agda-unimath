---
title: Cardinalities of sets
---

```agda
module set-theory.cardinalities where

open import foundation.dependent-pair-types
open import foundation.embeddings
open import foundation.equivalences
open import foundation.function-extensionality
open import foundation.functoriality-propositional-truncation
open import foundation.identity-types
open import foundation.law-of-excluded-middle
open import foundation.mere-embeddings
open import foundation.mere-equivalences
open import foundation.propositional-extensionality
open import foundation.propositional-truncations
open import foundation.propositions
open import foundation.set-truncations
open import foundation.sets
open import foundation-core.sets
open import foundation.universe-levels
```

## Idea

The cardinality of a set is its isomorphism class. We take isomorphism classes of sets by set truncating the universe of sets of any given universe level. Note that this definition takes advantage of the univalence axiom: By the univalence axiom isomorphic sets are equal, and will be mapped to the same element in the set truncation of the universe of all sets.

## Definition

### Cardinalities

```agda
cardinal-Set : (l : Level) → Set (lsuc l)
cardinal-Set l = trunc-Set (Set l)

cardinal : (l : Level) → UU (lsuc l)
cardinal l = type-Set (cardinal-Set l)

cardinality : {l : Level} → Set l → cardinal l
cardinality A = unit-trunc-Set A
```

### Inequality of cardinalities

```agda
leq-cardinality-Prop' :
  {l1 l2 : Level} → Set l1 → cardinal l2 → Prop (l1 ⊔ l2)
leq-cardinality-Prop' {l1} {l2} X =
  map-universal-property-trunc-Set
    ( Prop-Set (l1 ⊔ l2))
    ( λ Y' → mere-emb-Prop (type-Set X) (type-Set Y'))

compute-leq-cardinality-Prop' :
  {l1 l2 : Level} (X : Set l1) (Y : Set l2) →
  Id ( leq-cardinality-Prop' X (cardinality Y))
     ( mere-emb-Prop (type-Set X) (type-Set Y))
compute-leq-cardinality-Prop' {l1} {l2} X =
  triangle-universal-property-trunc-Set
    ( Prop-Set (l1 ⊔ l2))
    ( λ Y' → mere-emb-Prop (type-Set X) (type-Set Y'))
    
leq-cardinality-Prop :
  {l1 l2 : Level} → cardinal l1 → cardinal l2 → Prop (l1 ⊔ l2)
leq-cardinality-Prop {l1} {l2} =
  map-universal-property-trunc-Set
    ( hom-Set (cardinal-Set l2) (Prop-Set (l1 ⊔ l2)))
    ( leq-cardinality-Prop')

_≤-cardinality_ : {l1 l2 : Level} → cardinal l1 → cardinal l2 → UU (l1 ⊔ l2)
X ≤-cardinality Y = type-Prop (leq-cardinality-Prop X Y)

is-prop-≤-cardinality :
  {l1 l2 : Level} {X : cardinal l1} {Y : cardinal l2} → is-prop (X ≤-cardinality Y)
is-prop-≤-cardinality {X = X} {Y = Y} =
  is-prop-type-Prop (leq-cardinality-Prop X Y)

compute-leq-cardinality :
  {l1 l2 : Level} (X : Set l1) (Y : Set l2) →
  ( cardinality X ≤-cardinality cardinality Y) ≃
  ( mere-emb (type-Set X) (type-Set Y))
compute-leq-cardinality {l1} {l2} X Y =
  equiv-eq-Prop
    ( ( htpy-eq
        ( triangle-universal-property-trunc-Set
          ( hom-Set (cardinal-Set l2) (Prop-Set (l1 ⊔ l2)))
          ( leq-cardinality-Prop') X) (cardinality Y)) ∙
      ( compute-leq-cardinality-Prop' X Y))

unit-leq-cardinality :
  {l1 l2 : Level} (X : Set l1) (Y : Set l2) →
  mere-emb (type-Set X) (type-Set Y) → cardinality X ≤-cardinality cardinality Y
unit-leq-cardinality X Y = map-inv-equiv (compute-leq-cardinality X Y)

inv-unit-leq-cardinality :
  {l1 l2 : Level} (X : Set l1) (Y : Set l2) →
  cardinality X ≤-cardinality cardinality Y → mere-emb (type-Set X) (type-Set Y)
inv-unit-leq-cardinality X Y = pr1 (compute-leq-cardinality X Y)

refl-≤-cardinality : {l : Level} (X : cardinal l) → X ≤-cardinality X
refl-≤-cardinality {l} =
  apply-dependent-universal-property-trunc-Set'
    ( λ X → set-Prop (leq-cardinality-Prop X X))
    ( λ A → unit-leq-cardinality A A (refl-mere-emb (type-Set A)))

transitive-≤-cardinality :
  {l1 l2 l3 : Level} (X : cardinal l1) (Y : cardinal l2) (Z : cardinal l3) →
  X ≤-cardinality Y → Y ≤-cardinality Z → X ≤-cardinality Z
transitive-≤-cardinality {l1} {l2} {l3} X Y Z =
  apply-dependent-universal-property-trunc-Set'
  (λ u →
    set-Prop
      (function-Prop
        (u ≤-cardinality Y)
        (function-Prop (Y ≤-cardinality Z)
          (leq-cardinality-Prop u Z))))
  (λ a →
    apply-dependent-universal-property-trunc-Set'
    (λ v →
      set-Prop
        (function-Prop
          ((cardinality a) ≤-cardinality v)
          (function-Prop (v ≤-cardinality Z)
            (leq-cardinality-Prop (cardinality a) Z))))
    (λ b →
      apply-dependent-universal-property-trunc-Set'
      (λ w →
        set-Prop
          (function-Prop
            ((cardinality a) ≤-cardinality (cardinality b))
            (function-Prop ((cardinality b) ≤-cardinality w)
              (leq-cardinality-Prop (cardinality a) w))))
      (λ c a<b b<c →
        unit-leq-cardinality
          a
          c
          (transitive-mere-emb
            (inv-unit-leq-cardinality b c b<c)
            (inv-unit-leq-cardinality a b a<b)))
      Z)
    Y)
  X
```

## Properties

### Given two sets `X` and `Y`, the type `# X ＝ # Y` is equivalent to the type of mere equivalences from `X` to `Y`.

```agda
is-effective-cardinality :
  {l : Level} (X Y : Set l) →
  (cardinality X ＝ cardinality Y) ≃ mere-equiv (type-Set X) (type-Set Y)
is-effective-cardinality X Y =
  ( equiv-trunc-Prop (extensionality-Set X Y)) ∘e
  ( is-effective-unit-trunc-Set (Set _) X Y)
```

### Using this and assuming excluded middle , we can show `≤-cardinality` is a partial order by showing that it is antisymmetric.

```agda
antisymmetric-≤-cardinality :
  {l1 : Level} (X Y : cardinal l1) → (LEM l1) → 
  X ≤-cardinality Y → Y ≤-cardinality X → X ＝ Y
antisymmetric-≤-cardinality {l1} X Y lem =
  apply-dependent-universal-property-trunc-Set'
  (λ u →
    set-Prop
      (function-Prop
        (u ≤-cardinality Y)
        (function-Prop
          (Y ≤-cardinality u)
          (Id-Prop (cardinal-Set l1) u Y))))
  (λ a →
    apply-dependent-universal-property-trunc-Set'
    (λ v →
      set-Prop
        (function-Prop
          ((cardinality a) ≤-cardinality v)
          (function-Prop
            (v ≤-cardinality (cardinality a))
            (Id-Prop (cardinal-Set l1) (cardinality a) v))))
    (λ b a<b b<a →
      map-inv-equiv (is-effective-cardinality a b)
        (antisymmetric-mere-emb lem
        (inv-unit-leq-cardinality _ _ a<b)
        (inv-unit-leq-cardinality _ _ b<a)))
    Y)
  X
```
