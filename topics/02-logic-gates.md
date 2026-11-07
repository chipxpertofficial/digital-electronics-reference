# Logic Gates

The primitive building blocks. Each gate computes a Boolean function of its inputs.

## The seven basic gates (2-input truth tables)

| A | B | AND | OR | NAND | NOR | XOR | XNOR |
|---|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 1 | 1 | 0 | 1 |
| 0 | 1 | 0 | 1 | 1 | 0 | 1 | 0 |
| 1 | 0 | 0 | 1 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 | 1 |

**NOT (inverter):** `0 → 1`, `1 → 0`.

## Universal gates

**NAND** and **NOR** are *universal* — any Boolean function can be built from only NAND gates, or only NOR gates.

- NOT from NAND: `A NAND A = A'`
- AND from NAND: `(A NAND B) NAND (A NAND B)`
- OR from NAND: `(A NAND A) NAND (B NAND B)` (De Morgan)

This is why standard-cell libraries lean heavily on NAND/NOR: they are compact and fast in CMOS.

## XOR identities

- `A ⊕ 0 = A`
- `A ⊕ 1 = A'`
- `A ⊕ A = 0`
- XOR of a bus = **odd-parity** of its bits.

## Timing terms

- **Propagation delay (t_pd):** time from an input change to the output settling.
- **Fan-in / fan-out:** number of inputs a gate has / loads it can drive.
