# Number Systems & Codes

The foundation of digital design: how numbers and data are represented in binary.

## Positional number systems

| System | Base | Digits | Example |
|---|---|---|---|
| Binary | 2 | 0,1 | `1011` = 11 |
| Octal | 8 | 0–7 | `13` = 11 |
| Decimal | 10 | 0–9 | `11` |
| Hexadecimal | 16 | 0–9, A–F | `B` = 11 |

A value `d_{n-1}...d_1 d_0` in base `b` equals `Σ d_i · b^i`.

## Conversions

- **Decimal → binary:** repeatedly divide by 2, read remainders bottom-to-top.
  `13 → 1101` (13/2=6 r1, 6/2=3 r0, 3/2=1 r1, 1/2=0 r1).
- **Binary → decimal:** sum the weights of the `1` bits. `1101 = 8+4+1 = 13`.
- **Binary ↔ hex:** group bits in fours from the LSB. `1101 0110 = D6`.
- **Binary ↔ octal:** group bits in threes from the LSB.

## Signed representations

| Scheme | +5 (4-bit) | −5 (4-bit) | Notes |
|---|---|---|---|
| Sign–magnitude | `0101` | `1101` | Two zeros (`0000`/`1000`) |
| 1's complement | `0101` | `1010` | Two zeros; end-around carry |
| **2's complement** | `0101` | `1011` | One zero; used everywhere in hardware |

**2's complement of a number:** invert all bits, add 1. Range for `n` bits: `−2^(n-1)` to `+2^(n-1) − 1`.

## Common codes

- **BCD (8421):** each decimal digit in 4 bits. `59 → 0101 1001`.
- **Gray code:** consecutive values differ by exactly one bit — used in position encoders and to cross clock domains safely.

| Decimal | Binary | Gray |
|---|---|---|
| 0 | 000 | 000 |
| 1 | 001 | 001 |
| 2 | 010 | 011 |
| 3 | 011 | 010 |
| 4 | 100 | 110 |

- **ASCII:** 7-bit character code (`'A'` = 0x41, `'0'` = 0x30).

> Build and simulate these as RTL in the companion repo and the step-by-step tutorials at https://chipxpert.in/.
