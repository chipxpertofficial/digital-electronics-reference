# Sequential Circuits

Built from flip-flops plus combinational logic; output depends on inputs *and* stored state.

## Registers & shift registers

- **Register:** `n` D flip-flops capturing `n` bits on each edge.
- **Shift register:** data moves one position per clock — SISO, SIPO, PISO, PIPO variants. Used for serialization, delays, and LFSR pattern generation.

## Counters

| Type | Clocking | Note |
|---|---|---|
| Ripple (async) | each FF clocked by the previous FF's output | simple, but cumulative delay/glitches |
| Synchronous | all FFs share one clock | clean, standard practice |
| Up/down | direction controlled | |
| Mod-N | resets after N−1 | e.g. BCD = mod-10 |
| Ring / Johnson | shift register feedback | one-hot / twisted-ring states |

A synchronous mod-8 counter cycles `000→001→…→111→000`, one state per edge.

## Finite state machines (FSM)

- **Moore:** output depends on the current state only. Outputs are glitch-free and registered-friendly.
- **Mealy:** output depends on state *and* inputs. Fewer states, but outputs can change between edges.

Design flow: state diagram → state table → state encoding (binary / Gray / **one-hot**) → next-state and output equations → flip-flops + logic.

**One-hot encoding** uses one flip-flop per state; it is common in FPGAs because it simplifies next-state logic and timing.

## Sequential hazards

- **Clock skew:** unequal clock arrival across flops; erodes the timing budget.
- **Race condition:** two signals change and the result depends on which wins — avoid by registering on one clock.
