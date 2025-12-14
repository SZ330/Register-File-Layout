## Summary
This project implements a **16 × 13-bit register file** using custom CMOS logic and layout in **Cadence Virtuoso**. The design consists of a **4-to-16 wordline decoder**, a **16 × 13 array of DFF-based storage elements**, and a **per-bit 16:1 read multiplexer network**.

Each register stores 13 bits and is selected via a 4-bit address. Write operations occur on the active clock edge when the write enable is asserted, while read operations are combinational. The register file uses **edge-triggered D flip-flops** for storage rather than SRAM bitcells.

The layout follows a **bit-sliced, row-organized structure** to improve regularity and routing efficiency. Wordlines run horizontally across the register array, while data and clock signals are distributed vertically. Major functional blocks—including the decoder, register array, and read multiplexers—are placed to minimize routing congestion and ensure clear signal flow.

## Results
Pre-layout and post-layout performance was evaluated using **HSPICE simulations**.
Energy consumption and maximum operating frequency are summarized below.

| Measurement        | Pre-layout        | Post-layout       |
|--------------------|-------------------|-------------------|
| Read enable energy | 7.099 pJ          | 9.972 pJ          |
| Write enable energy| 9.144 pJ          | 13.03 pJ          |
| Maximum frequency  | 3.00 GHz          | 2.70 GHz          |

Post-layout simulations account for parasitic effects and confirm correct
functionality at a maximum clock frequency of **2.7 GHz**. The final post-layout
register file occupies an area of **79.58 μm × 45.03 μm**, corresponding to a
total area of **3,583.49 μm²**.
