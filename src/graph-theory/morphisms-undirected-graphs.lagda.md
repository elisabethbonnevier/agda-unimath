---
title: Morphisms of undirected graphs
---

```agda
module graph-theory.morphisms-undirected-graphs where

open import foundation.contractible-types
open import foundation.dependent-pair-types
open import foundation.equality-dependent-function-types
open import foundation.equivalences
open import foundation.functions
open import foundation.functoriality-dependent-function-types
open import foundation.functoriality-dependent-pair-types
open import foundation.fundamental-theorem-of-identity-types
open import foundation.homotopies
open import foundation.identity-types
open import foundation.structure-identity-principle
open import foundation.universe-levels
open import foundation.unordered-pairs

open import graph-theory.undirected-graphs
```

## Definitions

### Morphisms of undirected graphs

```agda
module _
  {l1 l2 l3 l4 : Level}
  (G : Undirected-Graph l1 l2) (H : Undirected-Graph l3 l4)
  where

  hom-Undirected-Graph : UU (lsuc lzero ⊔ l1 ⊔ l2 ⊔ l3 ⊔ l4)
  hom-Undirected-Graph =
    Σ ( vertex-Undirected-Graph G → vertex-Undirected-Graph H)
      ( λ f →
        ( p : unordered-pair-vertices-Undirected-Graph G) →
        edge-Undirected-Graph G p →
        edge-Undirected-Graph H (map-unordered-pair f p))

  vertex-hom-Undirected-Graph :
    hom-Undirected-Graph → vertex-Undirected-Graph G → vertex-Undirected-Graph H
  vertex-hom-Undirected-Graph f = pr1 f

  unordered-pair-vertices-hom-Undirected-Graph :
    hom-Undirected-Graph →
    unordered-pair-vertices-Undirected-Graph G →
    unordered-pair-vertices-Undirected-Graph H
  unordered-pair-vertices-hom-Undirected-Graph f =
    map-unordered-pair (vertex-hom-Undirected-Graph f)

  edge-hom-Undirected-Graph :
    (f : hom-Undirected-Graph)
    (p : unordered-pair-vertices-Undirected-Graph G) →
    edge-Undirected-Graph G p →
    edge-Undirected-Graph H
      ( unordered-pair-vertices-hom-Undirected-Graph f p)
  edge-hom-Undirected-Graph f = pr2 f
```

### Composition of morphisms of undirected graphs

```agda
module _
  {l1 l2 l3 l4 l5 l6 : Level}
  (G : Undirected-Graph l1 l2) (H : Undirected-Graph l3 l4)
  (K : Undirected-Graph l5 l6)
  where

  comp-hom-Undirected-Graph :
    hom-Undirected-Graph H K → hom-Undirected-Graph G H →
    hom-Undirected-Graph G K
  pr1 (comp-hom-Undirected-Graph (pair gV gE) (pair fV fE)) = gV ∘ fV
  pr2 (comp-hom-Undirected-Graph (pair gV gE) (pair fV fE)) p e =
    gE (map-unordered-pair fV p) (fE p e)
```

### Identity morphisms of undirected graphs

```agda
module _
  {l1 l2 : Level} (G : Undirected-Graph l1 l2)
  where

  id-hom-Undirected-Graph : hom-Undirected-Graph G G
  pr1 id-hom-Undirected-Graph = id
  pr2 id-hom-Undirected-Graph p = id
```


## Properties

### Characterizing the identity type of morphisms of undirected graphs

```agda
module _
  {l1 l2 l3 l4 : Level}
  (G : Undirected-Graph l1 l2) (H : Undirected-Graph l3 l4)
  where

  htpy-hom-Undirected-Graph :
    (f g : hom-Undirected-Graph G H) → UU (lsuc lzero ⊔ l1 ⊔ l2 ⊔ l3 ⊔ l4)
  htpy-hom-Undirected-Graph f g =
    Σ ( vertex-hom-Undirected-Graph G H f ~ vertex-hom-Undirected-Graph G H g)
      ( λ α →
        ( p : unordered-pair-vertices-Undirected-Graph G) →
        ( e : edge-Undirected-Graph G p) →
        Id ( tr
             ( edge-Undirected-Graph H)
             ( htpy-unordered-pair α p)
             ( edge-hom-Undirected-Graph G H f p e))
           ( edge-hom-Undirected-Graph G H g p e))

  refl-htpy-hom-Undirected-Graph :
    (f : hom-Undirected-Graph G H) → htpy-hom-Undirected-Graph f f
  pr1 (refl-htpy-hom-Undirected-Graph f) = refl-htpy
  pr2 (refl-htpy-hom-Undirected-Graph f) p e =
    ap ( λ t →
         tr (edge-Undirected-Graph H) t (edge-hom-Undirected-Graph G H f p e))
       ( preserves-refl-htpy-unordered-pair
         ( vertex-hom-Undirected-Graph G H f) p)

  htpy-eq-hom-Undirected-Graph :
    (f g : hom-Undirected-Graph G H) → Id f g → htpy-hom-Undirected-Graph f g
  htpy-eq-hom-Undirected-Graph f .f refl = refl-htpy-hom-Undirected-Graph f

  abstract
    is-contr-total-htpy-hom-Undirected-Graph :
      (f : hom-Undirected-Graph G H) →
      is-contr (Σ (hom-Undirected-Graph G H) (htpy-hom-Undirected-Graph f))
    is-contr-total-htpy-hom-Undirected-Graph f =
      is-contr-total-Eq-structure
        ( λ gV gE α →
          ( p : unordered-pair-vertices-Undirected-Graph G) →
          ( e : edge-Undirected-Graph G p) →
          Id ( tr
               ( edge-Undirected-Graph H)
               ( htpy-unordered-pair α p)
               ( edge-hom-Undirected-Graph G H f p e))
             ( gE p e))
        ( is-contr-total-htpy (vertex-hom-Undirected-Graph G H f))
        ( pair (vertex-hom-Undirected-Graph G H f) refl-htpy)
        ( is-contr-equiv'
          ( Σ ( (p : unordered-pair-vertices-Undirected-Graph G) →
                edge-Undirected-Graph G p →
                edge-Undirected-Graph H
                  ( unordered-pair-vertices-hom-Undirected-Graph G H f p))
              ( λ gE →
                (p : unordered-pair-vertices-Undirected-Graph G) →
                (e : edge-Undirected-Graph G p) →
                Id (edge-hom-Undirected-Graph G H f p e) (gE p e)))
          ( equiv-tot
            ( λ gE →
              equiv-map-Π
                ( λ p →
                  equiv-map-Π
                    ( λ e →
                      equiv-concat
                        ( pr2 (refl-htpy-hom-Undirected-Graph f) p e)
                        ( gE p e)))))
          ( is-contr-total-Eq-Π
            ( λ p gE →
              ( e : edge-Undirected-Graph G p) →
              Id (edge-hom-Undirected-Graph G H f p e) (gE e))
            ( λ p → is-contr-total-htpy (edge-hom-Undirected-Graph G H f p))))

  is-equiv-htpy-eq-hom-Undirected-Graph :
    (f g : hom-Undirected-Graph G H) →
    is-equiv (htpy-eq-hom-Undirected-Graph f g)
  is-equiv-htpy-eq-hom-Undirected-Graph f =
    fundamental-theorem-id
      ( is-contr-total-htpy-hom-Undirected-Graph f)
      ( htpy-eq-hom-Undirected-Graph f)

  extensionality-hom-Undirected-Graph :
    (f g : hom-Undirected-Graph G H) → Id f g ≃ htpy-hom-Undirected-Graph f g
  pr1 (extensionality-hom-Undirected-Graph f g) =
    htpy-eq-hom-Undirected-Graph f g
  pr2 (extensionality-hom-Undirected-Graph f g) =
    is-equiv-htpy-eq-hom-Undirected-Graph f g

  eq-htpy-hom-Undirected-Graph :
    (f g : hom-Undirected-Graph G H) → htpy-hom-Undirected-Graph f g → Id f g
  eq-htpy-hom-Undirected-Graph f g =
    map-inv-is-equiv (is-equiv-htpy-eq-hom-Undirected-Graph f g)
```
