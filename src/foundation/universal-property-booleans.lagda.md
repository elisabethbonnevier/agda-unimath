---
title: The universal property of booleans
---

```agda
module foundation.universal-property-booleans where

open import foundation.booleans
open import foundation.cartesian-product-types
open import foundation.dependent-pair-types
open import foundation.equality-cartesian-product-types
open import foundation.equivalences
open import foundation.function-extensionality
open import foundation.functions
open import foundation.homotopies
open import foundation.identity-types
open import foundation.universe-levels
```

```agda
ev-true-false :
  {l : Level} (A : UU l) → (f : bool → A) → A × A
ev-true-false A f = pair (f true) (f false)

map-universal-property-bool :
  {l : Level} {A : UU l} →
  A × A → (bool → A)
map-universal-property-bool (pair x y) true = x
map-universal-property-bool (pair x y) false = y

abstract
  issec-map-universal-property-bool :
    {l : Level} {A : UU l} →
    ((ev-true-false A) ∘ map-universal-property-bool) ~ id
  issec-map-universal-property-bool (pair x y) =
    eq-pair refl refl

abstract
  isretr-map-universal-property-bool' :
    {l : Level} {A : UU l} (f : bool → A) →
    (map-universal-property-bool (ev-true-false A f)) ~ f
  isretr-map-universal-property-bool' f true = refl
  isretr-map-universal-property-bool' f false = refl

abstract
  isretr-map-universal-property-bool :
    {l : Level} {A : UU l} →
    (map-universal-property-bool ∘ (ev-true-false A)) ~ id
  isretr-map-universal-property-bool f =
    eq-htpy (isretr-map-universal-property-bool' f)

abstract
  universal-property-bool :
    {l : Level} (A : UU l) →
    is-equiv (λ (f : bool → A) → pair (f true) (f false))
  universal-property-bool A =
    is-equiv-has-inverse
      map-universal-property-bool
      issec-map-universal-property-bool
      isretr-map-universal-property-bool

ev-true :
  {l : Level} {A : UU l} → (bool → A) → A
ev-true f = f true

triangle-ev-true :
  {l : Level} (A : UU l) →
  (ev-true) ~ (pr1 ∘ (ev-true-false A))
triangle-ev-true A = refl-htpy

{-
aut-bool-bool :
  bool → (bool ≃ bool)
aut-bool-bool true = id-equiv
aut-bool-bool false = equiv-neg-𝟚

bool-aut-bool :
  (bool ≃ bool) → bool
bool-aut-bool e = map-equiv e true

decide-true-false :
  (b : bool) → coprod (Id b true) (Id b false)
decide-true-false true = inl refl
decide-true-false false = inr refl

eq-false :
  (b : bool) → (¬ (Id b true)) → (Id b false)
eq-false true p = ind-empty (p refl)
eq-false false p = refl

eq-true :
  (b : bool) → (¬ (Id b false)) → Id b true
eq-true true p = refl
eq-true false p = ind-empty (p refl)

Eq-𝟚-eq : (x y : bool) → Id x y → Eq-𝟚 x y
Eq-𝟚-eq x .x refl = reflexive-Eq-𝟚 x

eq-false-equiv' :
  (e : bool ≃ bool) → Id (map-equiv e true) true →
  is-decidable (Id (map-equiv e false) false) → Id (map-equiv e false) false
eq-false-equiv' e p (inl q) = q
eq-false-equiv' e p (inr x) =
  ind-empty
    ( Eq-𝟚-eq true false
      ( ap pr1
        ( eq-is-contr'
          ( is-contr-map-is-equiv (is-equiv-map-equiv e) true)
          ( pair true p)
          ( pair false (eq-true (map-equiv e false) x)))))
-}
```
