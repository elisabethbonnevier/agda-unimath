---
title: Pointed types equipped with automorphisms
---

```agda
module structured-types.pointed-types-equipped-with-automorphisms where

open import foundation.automorphisms
open import foundation.cartesian-product-types
open import foundation.contractible-types
open import foundation.dependent-pair-types
open import foundation.equivalences
open import foundation.functions
open import foundation.functoriality-dependent-pair-types
open import foundation.fundamental-theorem-of-identity-types
open import foundation.homotopies
open import foundation.identity-types
open import foundation.structure-identity-principle
open import foundation.universe-levels

open import structured-types.pointed-types
```

## Idea

A pointed type equipped with an automorphism is a pair consisting of a pointed type `A` and an automorphism on the underlying type of `A`. The base point is not required to be preserved.

## Definitions

### Types equipped with an automorphism

```agda
Pointed-Type-With-Aut :
  (l : Level) → UU (lsuc l)
Pointed-Type-With-Aut l =
  Σ (Pointed-Type l) (λ X → Aut (type-Pointed-Type X))

module _
  {l : Level} (X : Pointed-Type-With-Aut l)
  where

  pointed-type-Pointed-Type-With-Aut : Pointed-Type l
  pointed-type-Pointed-Type-With-Aut = pr1 X

  type-Pointed-Type-With-Aut : UU l
  type-Pointed-Type-With-Aut =
    type-Pointed-Type pointed-type-Pointed-Type-With-Aut

  pt-Pointed-Type-With-Aut : type-Pointed-Type-With-Aut
  pt-Pointed-Type-With-Aut =
    pt-Pointed-Type pointed-type-Pointed-Type-With-Aut

  aut-Pointed-Type-With-Aut : Aut type-Pointed-Type-With-Aut
  aut-Pointed-Type-With-Aut = pr2 X

  map-aut-Pointed-Type-With-Aut :
    type-Pointed-Type-With-Aut → type-Pointed-Type-With-Aut
  map-aut-Pointed-Type-With-Aut = map-equiv aut-Pointed-Type-With-Aut

  inv-map-aut-Pointed-Type-With-Aut :
    type-Pointed-Type-With-Aut → type-Pointed-Type-With-Aut
  inv-map-aut-Pointed-Type-With-Aut = map-inv-equiv aut-Pointed-Type-With-Aut

  issec-inv-map-aut-Pointed-Type-With-Aut :
    (map-aut-Pointed-Type-With-Aut ∘ inv-map-aut-Pointed-Type-With-Aut) ~ id
  issec-inv-map-aut-Pointed-Type-With-Aut =
    issec-map-inv-equiv aut-Pointed-Type-With-Aut

  isretr-inv-map-aut-Pointed-Type-With-Aut :
    (inv-map-aut-Pointed-Type-With-Aut ∘ map-aut-Pointed-Type-With-Aut) ~ id
  isretr-inv-map-aut-Pointed-Type-With-Aut =
    isretr-map-inv-equiv aut-Pointed-Type-With-Aut
```

### Morphisms of pointed types with automorphisms

```agda
hom-Pointed-Type-With-Aut :
  {l1 l2 : Level} →
  Pointed-Type-With-Aut l1 → Pointed-Type-With-Aut l2 → UU (l1 ⊔ l2)
hom-Pointed-Type-With-Aut {l1} {l2} X Y =
  Σ ( type-Pointed-Type-With-Aut X → type-Pointed-Type-With-Aut Y)
    ( λ f →
      (f (pt-Pointed-Type-With-Aut X) ＝ pt-Pointed-Type-With-Aut Y)
      ×
      ( ( f ∘ (map-aut-Pointed-Type-With-Aut X)) ~
        ( (map-aut-Pointed-Type-With-Aut Y) ∘ f)))

module _
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1) (Y : Pointed-Type-With-Aut l2)
  (f : hom-Pointed-Type-With-Aut X Y)
  where

  map-hom-Pointed-Type-With-Aut :
    type-Pointed-Type-With-Aut X → type-Pointed-Type-With-Aut Y
  map-hom-Pointed-Type-With-Aut = pr1 f

  preserves-point-map-hom-Pointed-Type-With-Aut :
    ( map-hom-Pointed-Type-With-Aut (pt-Pointed-Type-With-Aut X)) ＝
    ( pt-Pointed-Type-With-Aut Y)
  preserves-point-map-hom-Pointed-Type-With-Aut = pr1 (pr2 f)

  preserves-aut-map-hom-Pointed-Type-With-Aut :
    ( map-hom-Pointed-Type-With-Aut ∘ map-aut-Pointed-Type-With-Aut X) ~
    ( ( map-aut-Pointed-Type-With-Aut Y) ∘ map-hom-Pointed-Type-With-Aut)
  preserves-aut-map-hom-Pointed-Type-With-Aut = pr2 (pr2 f)
```

## Properties

### Characterization of the identity type of morphisms of pointed types with automorphisms

```agda
htpy-hom-Pointed-Type-With-Aut :
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1)
  (Y : Pointed-Type-With-Aut l2) (h1 h2 : hom-Pointed-Type-With-Aut X Y) →
  UU (l1 ⊔ l2)
htpy-hom-Pointed-Type-With-Aut X Y h1 h2 =
  Σ ( map-hom-Pointed-Type-With-Aut X Y h1
      ~ map-hom-Pointed-Type-With-Aut X Y h2)
    ( λ H →
      ( ( preserves-point-map-hom-Pointed-Type-With-Aut X Y h1) ＝
        ( ( H (pt-Pointed-Type-With-Aut X)) ∙
          ( preserves-point-map-hom-Pointed-Type-With-Aut X Y h2)))
      ×
      ( ( x : type-Pointed-Type-With-Aut X) →
        ( ( ( preserves-aut-map-hom-Pointed-Type-With-Aut X Y h1 x) ∙
            ( ap (map-aut-Pointed-Type-With-Aut Y) (H x))) ＝
          ( ( H (map-aut-Pointed-Type-With-Aut X x)) ∙
            ( preserves-aut-map-hom-Pointed-Type-With-Aut X Y h2 x)))))

refl-htpy-hom-Pointed-Type-With-Aut :
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1)
  (Y : Pointed-Type-With-Aut l2) (h : hom-Pointed-Type-With-Aut X Y) →
  htpy-hom-Pointed-Type-With-Aut X Y h h
refl-htpy-hom-Pointed-Type-With-Aut X Y h =
  pair refl-htpy (pair refl (λ x → right-unit))

htpy-hom-Pointed-Type-With-Aut-eq :
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1)
  (Y : Pointed-Type-With-Aut l2) (h1 h2 : hom-Pointed-Type-With-Aut X Y) →
  h1 ＝ h2 → htpy-hom-Pointed-Type-With-Aut X Y h1 h2
htpy-hom-Pointed-Type-With-Aut-eq X Y h1 .h1 refl =
  refl-htpy-hom-Pointed-Type-With-Aut X Y h1

is-contr-total-htpy-hom-Pointed-Type-With-Aut :
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1)
  (Y : Pointed-Type-With-Aut l2) (h1 : hom-Pointed-Type-With-Aut X Y) →
  is-contr
    ( Σ ( hom-Pointed-Type-With-Aut X Y)
        ( htpy-hom-Pointed-Type-With-Aut X Y h1))
is-contr-total-htpy-hom-Pointed-Type-With-Aut X Y h1 =
  is-contr-total-Eq-structure
    ( λ ( map-h2 : type-Pointed-Type-With-Aut X → type-Pointed-Type-With-Aut Y)
        ( str-h2 : ( ( map-h2 (pt-Pointed-Type-With-Aut X)) ＝
                     ( pt-Pointed-Type-With-Aut Y)) ×
                   ( ( x : type-Pointed-Type-With-Aut X) →
                     ( map-h2 (map-aut-Pointed-Type-With-Aut X x)) ＝
                     ( map-aut-Pointed-Type-With-Aut Y (map-h2 x))))
        ( H : map-hom-Pointed-Type-With-Aut X Y h1 ~ map-h2)
      → ( ( preserves-point-map-hom-Pointed-Type-With-Aut X Y h1) ＝
          ( ( H (pt-Pointed-Type-With-Aut X)) ∙
            ( pr1 str-h2)))
        ×
        ( ( x : type-Pointed-Type-With-Aut X) →
          ( ( ( preserves-aut-map-hom-Pointed-Type-With-Aut X Y h1 x) ∙
              ( ap (map-aut-Pointed-Type-With-Aut Y) (H x))) ＝
            ( ( H (map-aut-Pointed-Type-With-Aut X x)) ∙
              ( pr2 str-h2 x)))))
    ( is-contr-total-htpy (map-hom-Pointed-Type-With-Aut X Y h1))
    ( pair (map-hom-Pointed-Type-With-Aut X Y h1) refl-htpy)
    ( is-contr-total-Eq-structure
      ( λ ( pt-h2 :
            ( map-hom-Pointed-Type-With-Aut X Y h1
              ( pt-Pointed-Type-With-Aut X)) ＝
            ( pt-Pointed-Type-With-Aut Y))
          ( aut-h2 :
            ( x : type-Pointed-Type-With-Aut X) →
            ( map-hom-Pointed-Type-With-Aut X Y h1
              ( map-aut-Pointed-Type-With-Aut X x)) ＝
            ( map-aut-Pointed-Type-With-Aut Y
              ( map-hom-Pointed-Type-With-Aut X Y h1 x)))
          ( α : preserves-point-map-hom-Pointed-Type-With-Aut X Y h1 ＝ pt-h2)
        → ( ( x : type-Pointed-Type-With-Aut X) →
            ( ( preserves-aut-map-hom-Pointed-Type-With-Aut X Y h1 x) ∙
              ( refl)) ＝
            ( aut-h2 x)))
      ( is-contr-total-path
        ( preserves-point-map-hom-Pointed-Type-With-Aut X Y h1))
      ( pair (preserves-point-map-hom-Pointed-Type-With-Aut X Y h1) refl)
      ( is-contr-equiv'
        ( Σ ( ( x : type-Pointed-Type-With-Aut X) →
              ( map-hom-Pointed-Type-With-Aut X Y h1
                ( map-aut-Pointed-Type-With-Aut X x)) ＝
              ( map-aut-Pointed-Type-With-Aut Y
                ( map-hom-Pointed-Type-With-Aut X Y h1 x)))
            ( λ aut-h2 →
              ( x : type-Pointed-Type-With-Aut X) →
              preserves-aut-map-hom-Pointed-Type-With-Aut X Y h1 x ＝ aut-h2 x))
        ( equiv-tot (equiv-concat-htpy right-unit-htpy))
        ( is-contr-total-htpy
          ( preserves-aut-map-hom-Pointed-Type-With-Aut X Y h1))))

is-equiv-htpy-hom-Pointed-Type-With-Aut :
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1)
  (Y : Pointed-Type-With-Aut l2) (h1 h2 : hom-Pointed-Type-With-Aut X Y) →
  is-equiv (htpy-hom-Pointed-Type-With-Aut-eq X Y h1 h2)
is-equiv-htpy-hom-Pointed-Type-With-Aut X Y h1 =
  fundamental-theorem-id 
    ( is-contr-total-htpy-hom-Pointed-Type-With-Aut X Y h1)
    ( htpy-hom-Pointed-Type-With-Aut-eq X Y h1)

eq-htpy-hom-Pointed-Type-With-Aut :
  {l1 l2 : Level} (X : Pointed-Type-With-Aut l1)
  (Y : Pointed-Type-With-Aut l2) (h1 h2 : hom-Pointed-Type-With-Aut X Y) →
  htpy-hom-Pointed-Type-With-Aut X Y h1 h2 → h1 ＝ h2
eq-htpy-hom-Pointed-Type-With-Aut X Y h1 h2 =
  map-inv-is-equiv (is-equiv-htpy-hom-Pointed-Type-With-Aut X Y h1 h2)
```

