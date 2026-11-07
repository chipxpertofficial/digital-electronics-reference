# Boolean Algebra & Minimization

The algebra used to simplify logic before it becomes gates.

## Core laws

| Law | AND form | OR form |
|---|---|---|
| Identity | `A·1 = A` | `A+0 = A` |
| Null | `A·0 = 0` | `A+1 = 1` |
| Idempotent | `A·A = A` | `A+A = A` |
| Complement | `A·A' = 0` | `A+A' = 1` |
| Commutative | `A·B = B·A` | `A+B = B+A` |
| Associative | `A(BC) = (AB)C` | `A+(B+C) = (A+B)+C` |
| Distributive | `A(B+C)=AB+AC` | `A+BC=(A+B)(A+C)` |
| Absorption | `A(A+B) = A` | `A+AB = A` |

## De Morgan's theorems

- `(A·B)' = A' + B'`
- `(A+B)' = A' · B'`

Generalizes: complement the whole expression by complementing each variable and swapping `·`↔`+`.

## Canonical forms

- **SOP (sum of products):** OR of AND terms — one minterm per `1` row of the truth table.
- **POS (product of sums):** AND of OR terms — one maxterm per `0` row.

Example (F = 1 for A=1 or B=1):
- SOP: `F = A + B`  ·  POS: `F = (A + B)`

## Karnaugh maps (K-maps)

A K-map arranges minterms so that physically adjacent cells differ by one variable (Gray-code ordering), making groupings visible.

2-variable map for `F = A'B + AB' + AB` (= `A + B`):

```
        B=0   B=1
 A=0  |  0  |  1  |
 A=1  |  1  |  1  |
```
Group the right column (B) and the bottom row (A) → `F = A + B`.

**Grouping rules:** groups are rectangles of size 1,2,4,8…; wrap around edges; bigger groups = fewer literals. Don't-cares (`X`) may be included when they help.

## Hazards

A **static hazard** is a brief wrong output (glitch) during a single-input change caused by unequal path delays. Cover it by adding the redundant (consensus) product term that spans the two adjacent groups.
