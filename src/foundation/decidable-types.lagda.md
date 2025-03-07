---
title: Decidable types
---

```agda
module foundation.decidable-types where

open import foundation.cartesian-product-types
open import foundation.coproduct-types
open import foundation.dependent-pair-types
open import foundation.double-negation
open import foundation.empty-types
open import foundation.equivalences
open import foundation.functions
open import foundation.hilberts-epsilon-operators
open import foundation.negation
open import foundation.retractions
open import foundation.propositions
open import foundation.propositional-truncations
open import foundation.raising-universe-levels
open import foundation.type-arithmetic-empty-type
open import foundation.unit-type
open import foundation.universe-levels
```

## Idea

A type is said to be decidable if we can either construct an element, or we can prove that it is empty. In other words, we interpret decidability via the Curry-Howard interpretation of logic into type theory. A related concept is that a type is either inhabited or empty, where inhabitedness of a type is expressed using the propositional truncation.

## Definition

### The Curry-Howard interpretation of decidability

```agda
is-decidable : {l : Level} (A : UU l) → UU l
is-decidable A = A + (¬ A)

is-decidable-fam :
  {l1 l2 : Level} {A : UU l1} (P : A → UU l2) → UU (l1 ⊔ l2)
is-decidable-fam {A = A} P = (x : A) → is-decidable (P x)
```

### The predicate that a type is inhabited or empty

```agda
is-inhabited-or-empty : {l1 : Level} → UU l1 → UU l1
is-inhabited-or-empty A = type-trunc-Prop A + is-empty A
```

### A type `A` is said to be merely decidable if it comes equipped with an element of `type-trunc-Prop (is-decidable A)`.

```agda
is-merely-decidable-Prop :
  {l : Level} → UU l → Prop l
is-merely-decidable-Prop A = trunc-Prop (is-decidable A)

is-merely-decidable : {l : Level} → UU l → UU l
is-merely-decidable A = type-trunc-Prop (is-decidable A)
```

## Examples


### The unit type and the empty type are decidable

```
is-decidable-unit : is-decidable unit
is-decidable-unit = inl star

is-decidable-empty : is-decidable empty
is-decidable-empty = inr id
```

## Properties

### Coproducts of decidable types are decidable

```agda
is-decidable-coprod :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  is-decidable A → is-decidable B → is-decidable (A + B)
is-decidable-coprod (inl a) y = inl (inl a)
is-decidable-coprod (inr na) (inl b) = inl (inr b)
is-decidable-coprod (inr na) (inr nb) = inr (ind-coprod (λ x → empty) na nb)
```

### Cartesian products of decidable types are decidable

```agda
is-decidable-prod :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  is-decidable A → is-decidable B → is-decidable (A × B)
is-decidable-prod (inl a) (inl b) = inl (pair a b)
is-decidable-prod (inl a) (inr g) = inr (g ∘ pr2)
is-decidable-prod (inr f) (inl b) = inr (f ∘ pr1)
is-decidable-prod (inr f) (inr g) = inr (f ∘ pr1)

is-decidable-prod' :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  is-decidable A → (A → is-decidable B) → is-decidable (A × B)
is-decidable-prod' (inl a) d with d a
... | inl b = inl (pair a b)
... | inr nb = inr (nb ∘ pr2)
is-decidable-prod' (inr na) d = inr (na ∘ pr1)
```

### Function types of decidable types are decidable

```agda
is-decidable-function-type :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  is-decidable A → is-decidable B → is-decidable (A → B)
is-decidable-function-type (inl a) (inl b) = inl (λ x → b)
is-decidable-function-type (inl a) (inr g) = inr (λ h → g (h a))
is-decidable-function-type (inr f) (inl b) = inl (ex-falso ∘ f)
is-decidable-function-type (inr f) (inr g) = inl (ex-falso ∘ f)

is-decidable-function-type' :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  is-decidable A → (A → is-decidable B) → is-decidable (A → B)
is-decidable-function-type' (inl a) d with d a
... | inl b = inl (λ x → b)
... | inr nb = inr (λ f → nb (f a))
is-decidable-function-type' (inr na) d = inl (ex-falso ∘ na)
```

### The negation of a decidable type is decidable

```agda
is-decidable-neg :
  {l : Level} {A : UU l} → is-decidable A → is-decidable (¬ A)
is-decidable-neg d = is-decidable-function-type d is-decidable-empty
```

### Decidable types are closed under coinhabited types; retracts, and equivalences

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  is-decidable-iff :
    (A → B) → (B → A) → is-decidable A → is-decidable B
  is-decidable-iff f g (inl a) = inl (f a)
  is-decidable-iff f g (inr na) = inr (λ b → na (g b))

module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where
  
  is-decidable-retract-of :
    A retract-of B → is-decidable B → is-decidable A
  is-decidable-retract-of (pair i (pair r H)) (inl b) = inl (r b)
  is-decidable-retract-of (pair i (pair r H)) (inr f) = inr (f ∘ i)

  is-decidable-is-equiv :
    {f : A → B} → is-equiv f → is-decidable B → is-decidable A
  is-decidable-is-equiv {f} (pair (pair g G) (pair h H)) =
    is-decidable-retract-of (pair f (pair h H))

  is-decidable-equiv :
    (e : A ≃ B) → is-decidable B → is-decidable A
  is-decidable-equiv e = is-decidable-iff (map-inv-equiv e) (map-equiv e)

is-decidable-equiv' :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (e : A ≃ B) →
  is-decidable A → is-decidable B
is-decidable-equiv' e = is-decidable-equiv (inv-equiv e)
```

### Decidability implies double negation elimination

```agda
dn-elim-is-decidable :
  {l : Level} {P : UU l} → is-decidable P → (¬¬ P → P)
dn-elim-is-decidable (inl x) p = x
dn-elim-is-decidable (inr x) p = ex-falso (p x)
```

### The double negation of `is-decidable` is always provable

```agda
dn-is-decidable : {l : Level} {P : UU l} → ¬¬ (is-decidable P)
dn-is-decidable {P = P} f =
  map-neg (inr {A = P} {B = ¬ P}) f
    ( map-neg (inl {A = P} {B = ¬ P}) f)
```

### Decidable types have ε-operators

```agda
elim-trunc-Prop-is-decidable :
  {l : Level} {A : UU l} → is-decidable A → ε-operator-Hilbert A
elim-trunc-Prop-is-decidable (inl a) x = a
elim-trunc-Prop-is-decidable (inr f) x =
  ex-falso (apply-universal-property-trunc-Prop x empty-Prop f)
```

### `is-decidable` is an idempotent operation

```agda
idempotent-is-decidable :
  {l : Level} (P : UU l) → is-decidable (is-decidable P) → is-decidable P
idempotent-is-decidable P (inl (inl p)) = inl p
idempotent-is-decidable P (inl (inr np)) = inr np
idempotent-is-decidable P (inr np) = inr (λ p → np (inl p))
```

### Being inhabited or empty is a proposition

```agda
abstract
  is-prop-is-inhabited-or-empty :
    {l1 : Level} (A : UU l1) → is-prop (is-inhabited-or-empty A)
  is-prop-is-inhabited-or-empty A =
    is-prop-coprod
      ( λ t → apply-universal-property-trunc-Prop t empty-Prop)
      ( is-prop-type-trunc-Prop)
      ( is-prop-neg)

is-inhabited-or-empty-Prop : {l1 : Level} → UU l1 → Prop l1
pr1 (is-inhabited-or-empty-Prop A) = is-inhabited-or-empty A
pr2 (is-inhabited-or-empty-Prop A) = is-prop-is-inhabited-or-empty A
```

### Any inhabited type is a fixed point for `is-decidable`

```agda
is-fixed-point-is-decidable-is-inhabited :
  {l : Level} {X : UU l} → type-trunc-Prop X → is-decidable X ≃ X
is-fixed-point-is-decidable-is-inhabited {l} {X} t =
  right-unit-law-coprod-is-empty X (¬ X) (is-nonempty-is-inhabited t)
```

### Raising types converves decidability

```agda
module _
  (l : Level) {l1 : Level} (A : UU l1)
  where

  is-decidable-raise : is-decidable A → is-decidable (raise l A)
  is-decidable-raise (inl p) = inl (map-raise p)
  is-decidable-raise (inr np) = inr (λ p' → np (map-inv-raise p'))
```
