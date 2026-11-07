# Combinational Circuits

Output depends only on the present inputs — no memory.

## Half adder

| A | B | Sum | Carry |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

`Sum = A ⊕ B`, `Carry = A·B`.

## Full adder

Adds three bits (A, B, Cin):

`Sum = A ⊕ B ⊕ Cin`, `Cout = A·B + Cin·(A ⊕ B)`.

A **ripple-carry adder** chains `n` full adders; carry propagation sets the delay. **Carry-lookahead** computes carries in parallel using generate `G=A·B` and propagate `P=A⊕B`.

## Multiplexer (4:1)

Selects one of `2^n` inputs with `n` select lines.

| S1 | S0 | Y |
|---|---|---|
| 0 | 0 | I0 |
| 0 | 1 | I1 |
| 1 | 0 | I2 |
| 1 | 1 | I3 |

`Y = S1'S0'·I0 + S1'S0·I1 + S1 S0'·I2 + S1 S0·I3`. A mux is a universal building block — any truth table maps onto one.

## Decoder (2:4)

One output high per input combination; the basis of address decoding and memory selection.

| A1 | A0 | Y3 Y2 Y1 Y0 |
|---|---|---|
| 0 | 0 | 0 0 0 1 |
| 0 | 1 | 0 0 1 0 |
| 1 | 0 | 0 1 0 0 |
| 1 | 1 | 1 0 0 0 |

## Encoder, comparator

- **Priority encoder:** outputs the index of the highest-priority active input, plus a valid bit.
- **Magnitude comparator:** produces `A>B`, `A=B`, `A<B`. Equality is a bitwise XNOR reduced with AND.
