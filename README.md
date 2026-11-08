# Digital Electronics Reference

A concise, exam- and interview-ready reference for **digital electronics and digital
logic design** — number systems, Boolean algebra, combinational and sequential circuits,
flip-flops, memory, and the timing rules behind real synchronous hardware. Every topic
includes the truth tables and the key equations, not just prose.

## Contents

| # | Topic | Covers |
|---|---|---|
| 01 | [Number Systems & Codes](topics/01-number-systems.md) | binary/hex/octal, 2's complement, BCD, Gray, ASCII |
| 02 | [Logic Gates](topics/02-logic-gates.md) | 7 gates, universal NAND/NOR, XOR identities |
| 03 | [Boolean Algebra & Minimization](topics/03-boolean-algebra.md) | laws, De Morgan, SOP/POS, K-maps, hazards |
| 04 | [Combinational Circuits](topics/04-combinational-circuits.md) | adders, mux, decoder, encoder, comparator |
| 05 | [Latches & Flip-Flops](topics/05-latches-flipflops.md) | SR/D/JK/T, setup/hold, metastability |
| 06 | [Sequential Circuits](topics/06-sequential-circuits.md) | registers, counters, FSMs (Moore/Mealy), one-hot |
| 07 | [Memory](topics/07-memory.md) | SRAM vs DRAM, ROM/flash, organization |
| 08 | [Synchronous Design Practice](topics/08-timing-and-design-practice.md) | STA, CDC, pitfalls, RTL→GDSII |

## How to use this

Read a topic for the concept and its truth table, then build and simulate the matching
design in the companion RTL library,
**[vlsi-verilog-examples](https://github.com/chipxpertofficial/vlsi-verilog-examples)**.
Step-by-step tutorials for each concept are at the [ChipXpert learning site](https://chipxpert.in/).

## License

MIT — see [LICENSE](LICENSE). Maintained by the ChipXpert VLSI training team.
