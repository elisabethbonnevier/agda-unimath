---
title: Alkynes
---

```agda
module organic-chemistry.alkenes where

open import elementary-number-theory.natural-numbers

open import foundation.dependent-pair-types
open import foundation.universe-levels
open import foundation.embeddings

open import univalent-combinatorics.finite-types

open import organic-chemistry.saturated-carbons
open import organic-chemistry.hydrocarbons
```

## Idea

An **n-alkene** is a hydrocarbon equipped with a choice of $n$ carbons, each of which has a double bond. For an n-alkene, the embedding from the given type (the first component of the n-alkene structure) specifies which carbons have double bonds. For example, 1-butene and but-2-ene have the same geometry, and the embedding is what differentiates them (while the third tautometer, isobutylene, is branched, thus has a different geometry).

## Definition

```agda
n-alkene : {l1 l2 : Level} → hydrocarbon l1 l2 → ℕ → UU (lsuc lzero ⊔ l1 ⊔ l2)
n-alkene H n =
  Σ (UU-Fin lzero n) λ carbons →
    Σ ( type-UU-Fin n carbons ↪ vertex-hydrocarbon H)
      ( λ embed-carbons →
        ( c : type-UU-Fin n carbons) →
        pr1 (has-double-bond-hydrocarbon H (pr1 embed-carbons c)))
```
