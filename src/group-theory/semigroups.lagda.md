---
title: Semigroups
---

```agda
module group-theory.semigroups where

open import foundation.dependent-pair-types
open import foundation.identity-types
open import foundation.sets
open import foundation.universe-levels
```

## Idea

Semigroups are sets equipped an associative binary operation. 

## Definition

```agda
has-associative-mul : {l : Level} (X : UU l) → UU l
has-associative-mul X =
  Σ (X → X → X) (λ μ → (x y z : X) → Id (μ (μ x y) z) (μ x (μ y z)))

has-associative-mul-Set :
  {l : Level} (X : Set l) → UU l
has-associative-mul-Set X =
  has-associative-mul (type-Set X)

Semigroup :
  (l : Level) → UU (lsuc l)
Semigroup l = Σ (Set l) has-associative-mul-Set

module _
  {l : Level} (G : Semigroup l)
  where

  set-Semigroup : Set l
  set-Semigroup = pr1 G

  type-Semigroup : UU l
  type-Semigroup = type-Set set-Semigroup

  is-set-type-Semigroup : is-set type-Semigroup
  is-set-type-Semigroup = is-set-type-Set set-Semigroup

  has-associative-mul-Semigroup : has-associative-mul type-Semigroup
  has-associative-mul-Semigroup = pr2 G

  mul-Semigroup : type-Semigroup → type-Semigroup → type-Semigroup
  mul-Semigroup = pr1 has-associative-mul-Semigroup

  mul-Semigroup' : type-Semigroup → type-Semigroup → type-Semigroup
  mul-Semigroup' x y = mul-Semigroup y x

  associative-mul-Semigroup :
    (x y z : type-Semigroup) →
    Id ( mul-Semigroup (mul-Semigroup x y) z)
       ( mul-Semigroup x (mul-Semigroup y z))
  associative-mul-Semigroup = pr2 has-associative-mul-Semigroup
```
