---
title: Paths in undirected graphs
---

```agda
module graph-theory.paths-undirected-graphs where

open import elementary-number-theory.natural-numbers

open import foundation.dependent-pair-types
open import foundation.injective-maps
open import foundation.universe-levels

open import graph-theory.undirected-graphs
open import graph-theory.walks-undirected-graphs
```

## Idea

A path in an undirected graph G is a walk `w` in G such that the inclusion of the type of vertices on `w` into the vertices of `G` is an injective function. Note that we don't expect this function to be an embedding, since the type of vertices on `w` is equivalent to `Fin (n + 1)` where `n` is the length of the walk, whereas the type of vertices of `G` does not need to be a set.

## Definition

```agda
module _
  {l1 l2 : Level} (G : Undirected-Graph l1 l2)
  where

  is-path-walk-Undirected-Graph :
    {x y : vertex-Undirected-Graph G} → walk-Undirected-Graph G x y → UU l1
  is-path-walk-Undirected-Graph w =
    is-injective (vertex-vertex-on-walk-Undirected-Graph G w)

  path-Undirected-Graph :
    (x y : vertex-Undirected-Graph G) → UU (lsuc lzero ⊔ l1 ⊔ l2)
  path-Undirected-Graph x y =
    Σ (walk-Undirected-Graph G x y) is-path-walk-Undirected-Graph

  walk-path-Undirected-Graph :
    {x y : vertex-Undirected-Graph G} →
    path-Undirected-Graph x y → walk-Undirected-Graph G x y
  walk-path-Undirected-Graph p = pr1 p

  length-path-Undirected-Graph :
    {x y : vertex-Undirected-Graph G} →
    path-Undirected-Graph x y → ℕ
  length-path-Undirected-Graph p =
    length-walk-Undirected-Graph G (walk-path-Undirected-Graph p)
```

## Properties

### The constant walk is a path

```agda
is-path-refl-walk-Undirected-Graph :
  {l1 l2 : Level} (G : Undirected-Graph l1 l2) (x : vertex-Undirected-Graph G) →
  is-path-walk-Undirected-Graph G (refl-walk-Undirected-Graph {x = x})
is-path-refl-walk-Undirected-Graph G x =
  is-injective-is-contr
    ( vertex-vertex-on-walk-Undirected-Graph G refl-walk-Undirected-Graph)
    ( is-contr-vertex-on-walk-refl-walk-Undirected-Graph G x)
```
