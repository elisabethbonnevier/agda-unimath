---
title: Divisibility in modular arithmetic
---

```agda
module elementary-number-theory.divisibility-modular-arithmetic where

open import elementary-number-theory.divisibility-integers
open import elementary-number-theory.divisibility-standard-finite-types
open import elementary-number-theory.modular-arithmetic
open import elementary-number-theory.natural-numbers
open import elementary-number-theory.absolute-value-integers

open import foundation.decidable-types
open import foundation.dependent-pair-types
open import foundation.identity-types
open import foundation.universe-levels

open import univalent-combinatorics.fibers-of-maps
```

## Idea

For two numbers `x` and `y` in `ℤ-Mod k`, we say that `x` divides `y` if there is a number `u` in `ℤ-Mod k` such that `mul-ℤ-Mod k u x = y`.

## Definition

```agda
div-ℤ-Mod : (k : ℕ) → ℤ-Mod k → ℤ-Mod k → UU lzero
div-ℤ-Mod k x y = Σ (ℤ-Mod k) (λ u → mul-ℤ-Mod k u x ＝ y)
```

## Properties

### The divisibility relation is reflexive

```agda
refl-div-ℤ-Mod : {k : ℕ} (x : ℤ-Mod k) → div-ℤ-Mod k x x
refl-div-ℤ-Mod {ℕ.zero-ℕ} = refl-div-ℤ
refl-div-ℤ-Mod {ℕ.succ-ℕ k} = refl-div-Fin
```

### The divisibility relation is transitive

```agda
trans-div-ℤ-Mod :
  {k : ℕ} (x y z : ℤ-Mod k) →
  div-ℤ-Mod k x y → div-ℤ-Mod k y z → div-ℤ-Mod k x z
trans-div-ℤ-Mod {zero-ℕ} = trans-div-ℤ
trans-div-ℤ-Mod {succ-ℕ k} = trans-div-Fin (succ-ℕ k)
```

### The divisibility relation is decidable

```agda
is-decidable-div-ℤ-Mod : (k : ℕ) (x y : ℤ-Mod k) →
  is-decidable (div-ℤ-Mod k x y)
is-decidable-div-ℤ-Mod zero-ℕ x y = is-decidable-div-ℤ x y  
is-decidable-div-ℤ-Mod (succ-ℕ k) x y = is-decidable-fib-Fin 
  {succ-ℕ k} {succ-ℕ k} (mul-ℤ-Mod' (succ-ℕ k) x) y
```
