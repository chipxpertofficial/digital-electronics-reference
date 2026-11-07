# Synchronous Design Practice

Rules that keep real digital systems correct and timeable.

## The synchronous discipline

1. One clock domain, one clock edge. Register state in flip-flops clocked together.
2. Keep combinational logic *between* registers; never build a combinational loop (except intended latches).
3. Reset every state element — choose synchronous or asynchronous-assert/synchronous-deassert consistently.

## Setup / hold recap

- **Setup:** `T_clk ≥ t_cq + t_comb(max) + t_su` → fix by shortening logic or lowering frequency.
- **Hold:** `t_cq + t_comb(min) ≥ t_h` → fix by adding delay; frequency-independent.
- **Slack = required − arrival.** Negative slack = a violated path.

## Clock domain crossing (CDC)

- Single control bit: **2-flop synchronizer**.
- Multi-bit bus: **Gray code** (if it only increments) or an **asynchronous FIFO** with Gray-coded pointers.
- Never let one combinational cone sample two unrelated clocks.

## Common pitfalls

| Pitfall | Symptom | Fix |
|---|---|---|
| Combinational loop | sim hangs / oscillation | break with a register |
| Gated clocks | skew, hold issues | use clock-enable instead |
| Async reset glitch | spurious reset | synchronize reset de-assertion |
| Metastability ignored | rare, random failures | synchronizer / FIFO |

## From logic to silicon

RTL → synthesis (maps to standard cells) → place & route → timing sign-off (STA checks every setup/hold path) → GDSII. The companion RTL examples and the full RTL-to-GDSII walkthrough are linked from the index.
