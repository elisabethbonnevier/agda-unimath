---
title: Functoriality of dependent function types
---

```agda
module foundation-core.functoriality-dependent-function-types where

open import foundation-core.coherently-invertible-maps
open import foundation-core.constant-maps
open import foundation-core.contractible-maps
open import foundation-core.contractible-types
open import foundation-core.dependent-pair-types
open import foundation-core.equivalences
open import foundation-core.fibers-of-maps
open import foundation-core.functions
open import foundation-core.functoriality-dependent-pair-types
open import foundation-core.homotopies
open import foundation-core.identity-types
open import foundation-core.path-split-maps
open import foundation-core.universe-levels

open import foundation.function-extensionality
open import foundation.type-theoretic-principle-of-choice
```

## Properties

### The operation `map-Π` preserves homotopies

```agda
htpy-map-Π :
  {l1 l2 l3 : Level} {I : UU l1} {A : I → UU l2} {B : I → UU l3}
  {f f' : (i : I) → A i → B i} (H : (i : I) → (f i) ~ (f' i)) →
  (map-Π f) ~ (map-Π f')
htpy-map-Π H h = eq-htpy (λ i → H i (h i))

htpy-map-Π' :
  {l1 l2 l3 l4 : Level} {I : UU l1} {A : I → UU l2} {B : I → UU l3}
  {J : UU l4} (α : J → I) {f f' : (i : I) → A i → B i} →
  ((i : I) → (f i) ~ (f' i)) → (map-Π' α f ~ map-Π' α f')
htpy-map-Π' α H = htpy-map-Π (λ j → H (α j))
```

### We compute the fibers of map-Π

```agda
equiv-fib-map-Π :
  {l1 l2 l3 : Level} {I : UU l1} {A : I → UU l2} {B : I → UU l3}
  (f : (i : I) → A i → B i) (h : (i : I) → B i) →
  ((i : I) → fib (f i) (h i)) ≃ fib (map-Π f) h
equiv-fib-map-Π f h =
  equiv-tot (λ x → equiv-eq-htpy) ∘e distributive-Π-Σ
```

### Families of equivalences induce equivalences on dependent function types

```agda
abstract
  is-equiv-map-Π :
    {l1 l2 l3 : Level} {I : UU l1} {A : I → UU l2} {B : I → UU l3}
    (f : (i : I) → A i → B i) (is-equiv-f : is-fiberwise-equiv f) →
    is-equiv (map-Π f)
  is-equiv-map-Π f is-equiv-f =
    is-equiv-is-contr-map
      ( λ g →
        is-contr-equiv' _
          ( equiv-fib-map-Π f g)
          ( is-contr-Π (λ i → is-contr-map-is-equiv (is-equiv-f i) (g i))))

equiv-map-Π :
  {l1 l2 l3 : Level} {I : UU l1} {A : I → UU l2} {B : I → UU l3}
  (e : (i : I) → (A i) ≃ (B i)) → ((i : I) → A i) ≃ ((i : I) → B i)
pr1 (equiv-map-Π e) = map-Π (λ i → map-equiv (e i))
pr2 (equiv-map-Π e) = is-equiv-map-Π _ (λ i → is-equiv-map-equiv (e i))
```

### For any map `f : A → B` and any family `C` over `B`, if `f` satisfies the property that `C b → (fib f b → C b)` is an equivalence for every `b : B` then the precomposition function `((b : B) → C b) → ((a : A) → C (f a))` is an equivalence

This condition simplifies, for example, the proof that connected maps satisfy a dependent universal property.

```agda
is-equiv-precomp-Π-fiber-condition :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {f : A → B} {C : B → UU l3} →
  ((b : B) → is-equiv (λ (c : C b) → const (fib f b) (C b) c)) →
  is-equiv (precomp-Π f C)
is-equiv-precomp-Π-fiber-condition {f = f} {C} H =
  is-equiv-comp
    ( map-reduce-Π-fib f (λ b u → C b))
    ( map-Π (λ b u t → u))
    ( is-equiv-map-Π (λ b u t → u) H)
    ( is-equiv-map-reduce-Π-fib f (λ b u → C b))
```

### If `f` is coherently invertible, then precomposing by `f` is an equivalence

```agda
tr-precompose-fam :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (C : B → UU l3)
  (f : A → B) {x y : A} (p : x ＝ y) → tr C (ap f p) ~ tr (λ x → C (f x)) p
tr-precompose-fam C f refl = refl-htpy

abstract
  is-equiv-precomp-Π-is-coherently-invertible :
    {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (f : A → B) →
    is-coherently-invertible f →
    (C : B → UU l3) → is-equiv (precomp-Π f C)
  is-equiv-precomp-Π-is-coherently-invertible f
    ( pair g (pair issec-g (pair isretr-g coh))) C = 
    is-equiv-has-inverse
      (λ s y → tr C (issec-g y) (s (g y)))
      ( λ s → eq-htpy (λ x → 
        ( ap (λ t → tr C t (s (g (f x)))) (coh x)) ∙
        ( ( tr-precompose-fam C f (isretr-g x) (s (g (f x)))) ∙
          ( apd s (isretr-g x)))))
      ( λ s → eq-htpy λ y → apd s (issec-g y))
```

### If `f` is an equivalence, then precomposing by `f` is an equivalence

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  (H : is-equiv f) (C : B → UU l3)
  where
  
  abstract
    is-equiv-precomp-Π-is-equiv : is-equiv (precomp-Π f C)
    is-equiv-precomp-Π-is-equiv =
      is-equiv-precomp-Π-is-coherently-invertible f
        ( is-coherently-invertible-is-path-split f
          ( is-path-split-is-equiv f H))
        ( C)

  map-inv-is-equiv-precomp-Π-is-equiv :
    ((a : A) → C (f a)) → ((b : B) → C b)
  map-inv-is-equiv-precomp-Π-is-equiv =
    map-inv-is-equiv is-equiv-precomp-Π-is-equiv

  issec-map-inv-is-equiv-precomp-Π-is-equiv :
    (h : (a : A) → C (f a)) →
    (precomp-Π f C (map-inv-is-equiv-precomp-Π-is-equiv h)) ~ h
  issec-map-inv-is-equiv-precomp-Π-is-equiv h =
    htpy-eq (issec-map-inv-is-equiv is-equiv-precomp-Π-is-equiv h)

  isretr-map-inv-is-equiv-precomp-Π-is-equiv :
    (g : (b : B) → C b) → 
    (map-inv-is-equiv-precomp-Π-is-equiv (precomp-Π f C g)) ~ g
  isretr-map-inv-is-equiv-precomp-Π-is-equiv g =
    htpy-eq (isretr-map-inv-is-equiv is-equiv-precomp-Π-is-equiv g)

equiv-precomp-Π :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (e : A ≃ B) →
  (C : B → UU l3) → ((b : B) → C b) ≃ ((a : A) → C (map-equiv e a))
pr1 (equiv-precomp-Π e C) = precomp-Π (map-equiv e) C
pr2 (equiv-precomp-Π e C) =
  is-equiv-precomp-Π-is-equiv (map-equiv e) (is-equiv-map-equiv e) C
```

## See also

- Arithmetical laws involving dependent function types are recorded in
  [`foundation.type-arithmetic-dependent-function-types`](foundation.type-arithmetic-dependent-function-types.html).
- Equality proofs in dependent function types are characterized in
  [`foundation.equality-dependent-function-types`](foundation.equality-dependent-function-types.html).

- Functorial properties of function types are recorded in
  [`foundation.functoriality-function-types`](foundation.functoriality-function-types.html).
- Functorial properties of dependent pair types are recorded in
  [`foundation.functoriality-dependent-pair-types`](foundation.functoriality-dependent-pair-types.html).
- Functorial properties of cartesian product types are recorded in
  [`foundation.functoriality-cartesian-product-types`](foundation.functoriality-cartesian-product-types.html).
