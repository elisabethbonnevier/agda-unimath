---
title: Steiner triple systems
---

```agda
module univalent-combinatorics.steiner-triple-systems where

open import elementary-number-theory.natural-numbers

open import foundation.universe-levels

open import univalent-combinatorics.steiner-systems
```

## Definition

```agda
Steiner-Triple-System : ℕ → UU (lsuc lzero)
Steiner-Triple-System n = Steiner-System 2 3 n
```

