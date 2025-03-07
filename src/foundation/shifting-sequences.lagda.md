---
title : Shifting sequences
---

```agda
module foundation.shifting-sequences where

open import elementary-number-theory.natural-numbers

open import foundation.universe-levels
```

## Idea

Given a sequence `f : ℕ → A` and an element `a : A` we define `shift-ℕ a f : ℕ → A` by

```md
  shift-ℕ a f zero-ℕ := a
  shift-ℕ a f (succ-ℕ n) := f n
```

## Definition

```agda
shift-ℕ : {l : Level} {A : UU l} (a : A) (f : ℕ → A) → ℕ → A
shift-ℕ a f zero-ℕ = a
shift-ℕ a f (succ-ℕ n) = f n
```
