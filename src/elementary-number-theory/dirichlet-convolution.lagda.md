---
title: Dirichlet convolution
---

```agda
module elementary-number-theory.dirichlet-convolution where

open import elementary-number-theory.arithmetic-functions
open import elementary-number-theory.bounded-sums-arithmetic-functions
open import elementary-number-theory.inequality-natural-numbers
open import elementary-number-theory.modular-arithmetic-standard-finite-types
open import elementary-number-theory.multiplication-natural-numbers
open import elementary-number-theory.natural-numbers
open import elementary-number-theory.nonzero-natural-numbers

open import foundation.coproduct-types
open import foundation.decidable-types
open import foundation.decidable-propositions
open import foundation.dependent-pair-types
open import foundation.empty-types
open import foundation.functions
open import foundation.identity-types
open import foundation.universe-levels

open import ring-theory.rings
```

## Definition

```agda
module _
  {l : Level} (R : Ring l)
  where

  dirichlet-convolution-arithmetic-functions-Ring :
    (f g : type-arithmetic-functions-Ring R) →
    type-arithmetic-functions-Ring R
  dirichlet-convolution-arithmetic-functions-Ring f g (pair zero-ℕ H) =
    ex-falso (H refl) 
  dirichlet-convolution-arithmetic-functions-Ring f g (pair (succ-ℕ n) H) =
    bounded-sum-arithmetic-function-Ring R
      ( succ-ℕ n)
      ( λ x → div-ℕ-decidable-Prop (pr1 x) (succ-ℕ n) (pr2 x))
      ( λ { (pair x K) H →
            mul-Ring R
              ( f ( pair x K))
              ( g ( quotient-div-nonzero-ℕ x (succ-nonzero-ℕ' n) H))})
```
