# Simplest Microprocessor

An interactive, browser-based simulation of a very basic 8-bit CPU, built for teaching how a microprocessor works — from the whole chip down to individual logic gates.

**Run it:** open `index.html` in any modern browser (no build, no install).

## The machine

- **6-bit instructions**, **8-bit data**, **4 registers** (R0–R3)
- **2 operations:** ADD and SUB (SUB = A + NOT B + 1, two's complement)
- **ALU:** one 8-bit adder-subtractor (8 XOR gates + 8 full adders); the control unit sends a single SUB line
- **Flags (outside the CPU):** SF = bit 7, ZF = NOR of all bits, PF = XNOR of all bits — built from the result with gates
- Results are shown on a **monitor**; register values are set directly by the user
- Cycle: **Load → Decode → Execute**

### Instruction format

| Bits | 5 4 | 3 2 | 1 0 |
|------|-----|-----|-----|
| Field | opcode | Rd | Rs |

| Mnemonic | Opcode | Example |
|----------|--------|---------|
| HLT | `00` | `000000` |
| ADD Rd, Rs | `01` | `010001` = ADD R0, R1 |
| SUB Rd, Rs | `10` | `101011` = SUB R2, R3 |

Register codes: R0 = `00`, R1 = `01`, R2 = `10`, R3 = `11`.

## Features

- **Drill-down view:** CPU chip + FLAGS chip → inside the CPU (IR, control unit, registers, ALU, monitor) → opcode decoder / ALU / register ports → full adders and 1-bit memory cells → logic gates, all showing live bit values
- **Cables:** each multi-wire connection is one cable; zoom in and it splits into its separate wires (orange = 1, grey = 0), all routed with 90° corners
- **Zoom & pan:** two-finger pinch on phones, Ctrl + scroll or the −/+ buttons on desktop, drag to move
- **Real pin counts** on every chip, colour-grouped (data in, data out, control, operation lines), with a tooltip on each pin describing its job and current value
- **Play / Step / Reset** with adjustable speed and optional auto-follow
- **Add / remove instructions** with a live binary breakdown; set register values directly
- **ISA legend** with Bangla names
- **Narration** in English and Bangla (text and voice; voice uses the browser's speech engine — Bangla needs a Bengali voice installed)

## Author

Abduz Zami — Lecturer, Dept. of CSE, BGMEA University of Fashion & Technology (BUFT)
