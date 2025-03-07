---
title: Nil ideals
---

```agda
module ring-theory.nil-ideals-rings where

open import foundation.propositions
open import foundation.universe-levels

open import ring-theory.ideals-rings
open import ring-theory.nilpotent-elements-rings
open import ring-theory.rings
```

## Idea

A nil ideal in a ring is an ideal in which every element is nilpotent

## Definition

### Nil left ideals

```agda
module _
  {l1 l2 : Level} (R : Ring l1) (I : left-ideal-Ring l2 R)
  where
  
  is-nil-left-ideal-ring-Prop : Prop (l1 ⊔ l2)
  is-nil-left-ideal-ring-Prop =
    Π-Prop
      ( type-left-ideal-Ring R I)
      ( λ x →
        is-nilpotent-element-ring-Prop R (inclusion-left-ideal-Ring R I x))

  is-nil-left-ideal-Ring : UU (l1 ⊔ l2)
  is-nil-left-ideal-Ring = type-Prop is-nil-left-ideal-ring-Prop

  is-prop-is-nil-left-ideal-Ring : is-prop is-nil-left-ideal-Ring
  is-prop-is-nil-left-ideal-Ring =
    is-prop-type-Prop is-nil-left-ideal-ring-Prop
```

### Nil right ideals

```agda
module _
  {l1 l2 : Level} (R : Ring l1) (I : right-ideal-Ring l2 R)
  where
  
  is-nil-right-ideal-ring-Prop : Prop (l1 ⊔ l2)
  is-nil-right-ideal-ring-Prop =
    Π-Prop
      ( type-right-ideal-Ring R I)
      ( λ x →
        is-nilpotent-element-ring-Prop R (inclusion-right-ideal-Ring R I x))

  is-nil-right-ideal-Ring : UU (l1 ⊔ l2)
  is-nil-right-ideal-Ring = type-Prop is-nil-right-ideal-ring-Prop

  is-prop-is-nil-right-ideal-Ring : is-prop is-nil-right-ideal-Ring
  is-prop-is-nil-right-ideal-Ring =
    is-prop-type-Prop is-nil-right-ideal-ring-Prop
```

### Nil two-sided ideals

```agda
module _
  {l1 l2 : Level} (R : Ring l1) (I : two-sided-ideal-Ring l2 R)
  where
  
  is-nil-two-sided-ideal-ring-Prop : Prop (l1 ⊔ l2)
  is-nil-two-sided-ideal-ring-Prop =
    Π-Prop
      ( type-two-sided-ideal-Ring R I)
      ( λ x →
        is-nilpotent-element-ring-Prop R (inclusion-two-sided-ideal-Ring R I x))

  is-nil-two-sided-ideal-Ring : UU (l1 ⊔ l2)
  is-nil-two-sided-ideal-Ring = type-Prop is-nil-two-sided-ideal-ring-Prop

  is-prop-is-nil-two-sided-ideal-Ring : is-prop is-nil-two-sided-ideal-Ring
  is-prop-is-nil-two-sided-ideal-Ring =
    is-prop-type-Prop is-nil-two-sided-ideal-ring-Prop
```

