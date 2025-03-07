---
title: Orbits of higher group actions
---

```agda
module group-theory.orbits-higher-group-actions where

open import foundation.dependent-pair-types
open import foundation.universe-levels

open import group-theory.higher-group-actions
open import group-theory.higher-groups
```

## Idea

The type of orbits of a higher group action `X` acted upon by `G` is the total space of `X`.

## Definition

```agda
orbit-action-∞-Group :
  {l1 l2 : Level} (G : ∞-Group l1) (X : action-∞-Group l2 G) → UU (l1 ⊔ l2)
orbit-action-∞-Group G X = Σ (classifying-type-∞-Group G) X
```
