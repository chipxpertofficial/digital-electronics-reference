# Latches & Flip-Flops

Storage elements — the point where memory enters a circuit.

## Latch vs flip-flop

- **Latch:** level-sensitive. Transparent while the enable/clock level is active.
- **Flip-flop:** edge-sensitive. Samples only on the clock edge (rising or falling).

## SR latch (NOR)

| S | R | Q(next) | |
|---|---|---|---|
| 0 | 0 | Q | hold |
| 0 | 1 | 0 | reset |
| 1 | 0 | 1 | set |
| 1 | 1 | — | invalid |

## D flip-flop

`Q(next) = D` on the clock edge. The workhorse of synchronous design — every register is a row of D flip-flops.

## JK flip-flop

| J | K | Q(next) | |
|---|---|---|---|
| 0 | 0 | Q | hold |
| 0 | 1 | 0 | reset |
| 1 | 0 | 1 | set |
| 1 | 1 | Q' | toggle |

## T flip-flop

`Q(next) = Q ⊕ T`. With T=1 it toggles every edge → divides the clock by 2.

## Timing constraints

- **Setup time (t_su):** data must be stable *before* the clock edge.
- **Hold time (t_h):** data must stay stable *after* the clock edge.
- **Clock-to-Q (t_cq):** delay from edge to output valid.

Max clock: `T_clk ≥ t_cq + t_logic + t_su` (setup check). Hold violations (`t_cq + t_logic_min ≥ t_h`) are not fixed by slowing the clock — they need added delay or careful placement.

## Metastability

Sampling an asynchronous input that violates setup/hold can leave a flop between 0 and 1 for an unbounded time. Mitigate with a **2-flop synchronizer**; cross multi-bit buses with a Gray code or a handshake/FIFO.
