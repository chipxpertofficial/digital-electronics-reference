# Memory

How bits are stored in bulk.

## Taxonomy

```
Memory
├── RAM (volatile)
│   ├── SRAM  — 6T cell, fast, no refresh, caches/registers
│   └── DRAM  — 1T1C cell, dense, needs refresh, main memory
└── ROM / NVM (non-volatile)
    ├── Mask ROM, PROM, EPROM, EEPROM
    └── Flash (NAND / NOR)
```

## SRAM vs DRAM

| | SRAM | DRAM |
|---|---|---|
| Cell | 6 transistors | 1 transistor + 1 capacitor |
| Speed | fast | slower |
| Density | low | high |
| Refresh | none | periodic |
| Use | cache, on-chip | main memory |

## Organization

A memory of `2^n × m` has `n` address lines and `m` data lines. Address decoding selects one word line; sense amps read the column. Larger arrays split addressing into **row** and **column** (as in DRAM's RAS/CAS).

## Key terms

- **Access time:** address valid → data valid.
- **Cycle time:** minimum time between successive accesses.
- **Word vs byte addressing:** granularity of a single address.
