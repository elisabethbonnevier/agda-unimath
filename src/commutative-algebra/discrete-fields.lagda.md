---
title: Discrete fields
---

```agda
module commutative-algebra.discrete-fields where

open import commutative-algebra.commutative-rings

open import foundation.universe-levels

open import ring-theory.division-rings
```

## Idea

A discrete field is a commutative division ring. They are called discrete, because only nonzero elements are assumed to be invertible.

## Definition

```agda
is-discrete-field-Commutative-Ring :
  { l : Level} → Commutative-Ring l → UU l
is-discrete-field-Commutative-Ring R =
  is-division-Ring (ring-Commutative-Ring R)
```
