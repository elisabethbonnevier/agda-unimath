---
title: Necklaces
---

```agda
module univalent-combinatorics.necklaces where

open import elementary-number-theory.natural-numbers

open import foundation.dependent-pair-types
open import foundation.equivalences
open import foundation.function-extensionality
open import foundation.functions
open import foundation.homotopies
open import foundation.identity-types
open import foundation.structure-identity-principle
open import foundation.universe-levels

open import structured-types.types-equipped-with-endomorphisms

open import univalent-combinatorics.cyclic-types
open import univalent-combinatorics.finite-types
open import univalent-combinatorics.standard-finite-types
```

## Idea

A necklace is an arrangement of coloured beads. Two necklaces are considered the same if one can be obtained from the other by rotating.

## Definition

### Necklaces

```agda
necklace : (l : Level) → ℕ → ℕ → UU (lsuc l)
necklace l m n = Σ (Cyclic-Type l m) (λ X → type-Cyclic-Type m X → Fin n)

module _
  {l : Level} (m : ℕ) (n : ℕ) (N : necklace l m n)
  where

  cyclic-necklace : Cyclic-Type l m
  cyclic-necklace = pr1 N

  endo-necklace : Endo l
  endo-necklace = endo-Cyclic-Type m cyclic-necklace

  type-necklace : UU l
  type-necklace = type-Cyclic-Type m cyclic-necklace

  endomorphism-necklace : type-necklace → type-necklace
  endomorphism-necklace = endomorphism-Cyclic-Type m cyclic-necklace

  is-cyclic-endo-necklace : is-cyclic-Endo m endo-necklace
  is-cyclic-endo-necklace = mere-equiv-endo-Cyclic-Type m cyclic-necklace

  colouring-necklace : type-necklace → Fin n
  colouring-necklace = pr2 N
```

### Necklace patterns

```agda
necklace-pattern : (l : Level) → ℕ → ℕ → UU (lsuc l)
necklace-pattern l m n =
  Σ ( Cyclic-Type l m)
    ( λ X → Σ (UU-Fin lzero n) (λ C → type-Cyclic-Type m X → type-UU-Fin n C))
```

## Properties

### Characterization of the identity type

```agda
module _
  {l1 l2 : Level} (m n : ℕ)
  where
  
  equiv-necklace :
    (N1 : necklace l1 m n) (N2 : necklace l2 m n) → UU (l1 ⊔ l2)
  equiv-necklace N1 N2 =
    Σ ( equiv-Cyclic-Type m (cyclic-necklace m n N1) (cyclic-necklace m n N2))
      ( λ e →
        ( colouring-necklace m n N1) ~
        ( ( colouring-necklace m n N2) ∘
          ( map-equiv-Cyclic-Type m
            ( cyclic-necklace m n N1)
            ( cyclic-necklace m n N2)
            ( e))))

module _
  {l : Level} (m n : ℕ)
  where

  id-equiv-necklace :
    (N : necklace l m n) → equiv-necklace m n N N
  pr1 (id-equiv-necklace N) = id-equiv-Cyclic-Type m (cyclic-necklace m n N)
  pr2 (id-equiv-necklace N) = refl-htpy

module _
  {l : Level} (m n : ℕ)
  where
  
  extensionality-necklace :
    (N1 N2 : necklace l m n) → Id N1 N2 ≃ equiv-necklace m n N1 N2
  extensionality-necklace N1 =
    extensionality-Σ
      ( λ {X} f e →
        ( colouring-necklace m n N1) ~
        ( f ∘ map-equiv-Cyclic-Type m (cyclic-necklace m n N1) X e))
      ( id-equiv-Cyclic-Type m (cyclic-necklace m n N1))
      ( refl-htpy)
      ( extensionality-Cyclic-Type m (cyclic-necklace m n N1))
      ( λ f → equiv-funext)

  refl-extensionality-necklace :
    (N : necklace l m n) →
    Id (map-equiv (extensionality-necklace N N) refl) (id-equiv-necklace m n N)
  refl-extensionality-necklace N = refl
```
