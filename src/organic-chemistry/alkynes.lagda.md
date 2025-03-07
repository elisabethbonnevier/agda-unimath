---
title: Alkynes
---

```agda
module organic-chemistry.alkynes where

open import elementary-number-theory.natural-numbers

open import foundation.dependent-pair-types
open import foundation.universe-levels
open import foundation.embeddings

open import univalent-combinatorics.finite-types

open import organic-chemistry.saturated-carbons
open import organic-chemistry.hydrocarbons
```

## Idea

An **n-alkyne** is a hydrocarbon equipped with a choice of $n$ carbons, each of which has a triple bond.

## Definition

```agda
n-alkyne : {l1 l2 : Level} → hydrocarbon l1 l2 → ℕ → UU (lsuc l1 ⊔ l2)
n-alkyne {l1} {l2} H n =
  Σ ( UU-Fin l1 n)
    ( λ carbons →
      Σ ( type-UU-Fin n carbons ↪ vertex-hydrocarbon H)
        ( λ embed-carbons →
          (c : type-UU-Fin n carbons) →
          has-triple-bond-hydrocarbon H (pr1 embed-carbons c)))
```
