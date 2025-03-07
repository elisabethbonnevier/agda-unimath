---
title: Extensions of maps
---

```agda
module orthogonal-factorization-systems.extensions-of-maps where

open import foundation-core.dependent-pair-types

open import foundation.contractible-types
open import foundation.contractible-maps
open import foundation.equivalences
open import foundation.fibers-of-maps
open import foundation.function-extensionality
open import foundation.functions
open import foundation.functoriality-dependent-function-types
open import foundation.functoriality-dependent-pair-types
open import foundation.homotopies
open import foundation.identity-types
open import foundation.truncated-types
open import foundation.truncation-levels
open import foundation.type-arithmetic-dependent-pair-types
open import foundation.universe-levels

open import orthogonal-factorization-systems.local-types
```

## Idea

An _extension_ of a map `f : (x : A) → P x` along a map `i : A → B`
is a map `g : (y : B) → Q y` such that `Q` restricts along `i`
to `P` and `g` restricts along `i` to `f`.

```md
  A
  |  \
  i    f
  |      \
  v       v
  B - g -> P
```

## Definition

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (i : A → B)
  where

  is-extension :
    {P : B → UU l3} →
    ((x : A) → P (i x)) → ((y : B) → P y) → UU (l1 ⊔ l3)
  is-extension f g = f ~ (g ∘ i)

  extension :
    (P : B → UU l3) →
    ((x : A) → P (i x)) → UU (l1 ⊔ l2 ⊔ l3)
  extension P f = Σ ((y : B) → P y) (is-extension f)

  total-extension : (P : B → UU l3) → UU (l1 ⊔ l2 ⊔ l3)
  total-extension P = Σ ((x : A) → P (i x)) (extension P)
```

## Operations

### Vertical composition of extensions

```md
  A
  |  \
  i    f
  |      \
  v       v
  B - g -> P
  |       ^
  j      /
  |    h
  v  /
  C
```

```agda
module _
  {l1 l2 l3 l4 : Level} {A : UU l1} {B : UU l2} {C : UU l3} {P : C → UU l4}
  {i : A → B} {j : B → C}
  {f : (x : A) → P (j (i x))} {g : (x : B) → P (j x)} {h : (x : C) → P x}
  where
  
  _∘ext_ :
    is-extension j g h → is-extension i f g → is-extension (j ∘ i) f h
  (H ∘ext G) x = G x ∙ H (i x)
```

### Horizontal composition of extensions

```md
           A
        /  |  \
      f    g    h
    /      |      \
   v       v       v
  B - i -> C - j -> P
```

```agda
_∙ext_ :
  {l1 l2 l3 l4 : Level} {A : UU l1} {B : UU l2} {C : UU l3} {P : C → UU l4}
  {f : A → B} {g : A → C} {h : (x : A) → P (g x)}
  {i : B → C} {j : (z : C) → P z}
  (I : is-extension f g i) → is-extension g h j → is-extension f (λ x → tr P (I x) (h x)) (j ∘ i)
_∙ext_ {P = P} {j = j} I J x = ap (tr P (I x)) (J x) ∙ apd j (I x)
```

### Left whiskering of extensions

```md
  A
  |  \
  i    f
  |      \
  v       v
  B - g -> C - h -> P
```

```agda
_∙l-ext_ :
  {l1 l2 l3 l4 : Level} {A : UU l1} {B : UU l2} {C : UU l3} {P : C → UU l4}
  {i : A → B} {f : A → C} {g : B → C}
  (h : (x : C) → P x) (F : is-extension i f g) →
  (is-extension i (λ x → tr P (F x) (h (f x))) (h ∘ g))
h ∙l-ext F = apd h ∘ F
```

### Right whiskering of extensions

```md
  X - h -> A
           |  \
           i    f
           |      \
           v       v
           B - g -> P
```

```agda
_∙r-ext_ :
  {l1 l2 l3 l4 : Level} {A : UU l1} {B : UU l2} {P : B → UU l3} {X : UU l4}
  {i : A → B} {f : (x : A) → P (i x)} {g : (y : B) → P y} 
  (F : is-extension i f g) (h : X → A) →
  (is-extension (i ∘ h) (f ∘ h) g)
F ∙r-ext h = F ∘ h
```

## Properties

### The total type of extensions is equivalent to `(y : B) → P y`

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (i : A → B)
  where

  inv-compute-total-extension :
    (P : B → UU l3) → total-extension i P ≃ ((y : B) → P y)
  inv-compute-total-extension P =
    ( right-unit-law-Σ-is-contr ( λ f → is-contr-total-htpy' (f ∘ i))) ∘e
    ( equiv-left-swap-Σ)

  compute-total-extension :
    (P : B → UU l3) → ((y : B) → P y) ≃ total-extension i P
  compute-total-extension P = inv-equiv (inv-compute-total-extension P)
```

### If `P` is `k`-truncated then the type of extensions is `k`-truncated

```agda
module _
  {l1 l2 l3 : Level} (k : 𝕋) {A : UU l1} {B : UU l2} (i : A → B)
  where

  is-trunc-is-extension :
    {P : B → UU l3} (f : (x : A) → P (i x)) →
    ((x : A) → is-trunc (succ-𝕋 k) (P (i x))) →
    (g : (x : B) → P x) → is-trunc k (is-extension i f g)
  is-trunc-is-extension f is-trunc-P g =
    is-trunc-Π k λ x → is-trunc-P x (f x) (g (i x))

  is-trunc-extension :
    {P : B → UU l3} (f : (x : A) → P (i x)) →
    ((x : B) → is-trunc k (P x)) → is-trunc k (extension i P f)
  is-trunc-extension f is-trunc-P =
    is-trunc-Σ
      ( is-trunc-Π k is-trunc-P)
      ( is-trunc-is-extension f (is-trunc-succ-is-trunc k ∘ (is-trunc-P ∘ i)))

  is-trunc-total-extension :
    {P : B → UU l3} →
    ((x : B) → is-trunc k (P x)) → is-trunc k (total-extension i P)
  is-trunc-total-extension {P} is-trunc-P =
    is-trunc-equiv' k
      ( (y : B) → P y)
      ( compute-total-extension i P)
      ( is-trunc-Π k is-trunc-P)
```

### Characterizing extensions in terms of the precomposition function

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (i : A → B)
  {l : Level} (P : B → UU l)
  where

  equiv-fib'-precomp-extension :
    (f : (x : A) → P (i x)) → fib' (precomp-Π i P) f ≃ extension i P f
  equiv-fib'-precomp-extension f =
    equiv-tot (λ g → equiv-funext {f = f} {g ∘ i})
  
  equiv-fib-precomp-extension :
    (f : (x : A) → P (i x)) → fib (precomp-Π i P) f ≃ extension i P f
  equiv-fib-precomp-extension f =
    (equiv-fib'-precomp-extension f) ∘e (equiv-fib (precomp-Π i P) f)

  equiv-is-contr-extension-is-local-family :
    is-local-family i P ≃ ((f : (x : A) → P (i x)) → is-contr (extension i P f))
  equiv-is-contr-extension-is-local-family =
    equiv-map-Π (λ f → equiv-is-contr-equiv (equiv-fib-precomp-extension f))
    ∘e equiv-is-contr-map-is-equiv (precomp-Π i P)

  is-contr-extension-is-local-family :
    is-local-family i P → ((f : (x : A) → P (i x)) → is-contr (extension i P f))
  is-contr-extension-is-local-family =
    map-equiv equiv-is-contr-extension-is-local-family

  is-local-family-is-contr-extension :
    ((f : (x : A) → P (i x)) → is-contr (extension i P f)) → is-local-family i P
  is-local-family-is-contr-extension =
    map-inv-equiv equiv-is-contr-extension-is-local-family
```

## Examples

### Every map is an extension of itself along the identity

```agda
is-extension-self :
  {l1 l2 : Level} {A : UU l1} {P : A → UU l2}
  (f : (x : A) → P x) → is-extension id f f
is-extension-self _ = refl-htpy
```

### The identity is an extension of every map along themselves

```agda
is-extension-along-self :
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  (f : A → B) → is-extension f f id
is-extension-along-self _ = refl-htpy
```

## See also

- [`orthogonal-factorization-systems.lifts-of-maps`](orthogonal-factorization-systems.lifts-of-maps.html) for the dual notion.
