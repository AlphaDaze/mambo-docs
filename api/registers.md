---
layout: default
title: Registers
parent: API
nav_order: 2
---

## MAMBO Register Support

- ISA independent register naming scheme

|:---|:---|
|  **reg0** to **reg10**  |  First 11 general purpose registers.<br /> Map r0/x0 to r11/x11 on AARCH32/AARCH64 |

- Aliases for Program Counter(**pc**), Stack Pointer(**sp**), Frame Pointer(**fp**)
- Call**e**-**S**aved register(**es**)

- Registers support addition and subtraction
- Native registers defined(r0-r15 and x0-x31)
- regset supports bitwise mask for registers pushed or popped
  - Mask is M_[register name]

## MAMBO Register Helper Functions

Functions used to prevent spilling and restore registers for instrumentation

| Function  | Description  |
|:---|:---|
|  `mambo_get_scratch_regs() `  |  Register allocation routines |
|  `mambo_free_scratch_regs() `  |  Register deallocation routines |

