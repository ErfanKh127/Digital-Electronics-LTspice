# BiCMOS Half Adder and Full Adder Simulation in LTspice

## Overview
This project simulates **BiCMOS** implementations of a **Half Adder** and **Full Adder** at the transistor level using 65nm BSIM models.

- **Technology**: BiCMOS (combines Bipolar for speed/drive + CMOS for low power/density)
- **Half Adder**: XOR + AND gates for Sum and Carry (using NMOS/PMOS + BJTs)
- **Full Adder**: Built from two Half Adders + OR (or mirror adder style), with inputs A, B, Cin → outputs Sum, Cout
- **Models**: pmos-bsim065 / nmos-bsim065 (BSIM4 65nm)

BiCMOS adders offer higher speed and better drive than pure CMOS, useful in high-performance arithmetic circuits.

<grok-card data-id="d9e8d1" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example LTspice CMOS Full Adder Simulation (similar setup)

<grok-card data-id="9fe4a8" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard CMOS Half Adder Transistor Schematic (reference)

<grok-card data-id="d9ac6c" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Conventional CMOS Full Adder Transistor Level (pure CMOS reference)

<grok-card data-id="d7dd56" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example BiCMOS Circuit (concept similar)

## Circuit Details
- **Half Adder** (top): Generates Sum (XOR) and Carry (AND) from A and B.
- **Full Adder** (bottom): Adds A, B, Cin → Sum and Carry-out.
- Transistors labeled with instances (e.g., H19 pmos-bsim065) – hierarchical or multiple gates.
- Inputs: A, B, notA, notB (inverted for complementary logic).

## Files
- `FullAdder_Bicmos.asc` — Main schematic with both Half and Full Adder blocks
- BSIM4 65nm model library (included or .include required)

## How to Run
1. Open the `.asc` file in LTspice.
2. Add transient sources for A, B, Cin (pulse trains to test all combinations).
3. Run transient simulation → Plot Sum and Carry outputs vs inputs.
4. **Experiments**:
   - Test truth tables (00→00, 01→10, 10→10, 11→01 w/carry).
   - Measure propagation delay, power consumption.
   - Compare with pure CMOS version.

## Learning Goals
- Transistor-level design of arithmetic logic (XOR, AND, full addition).
- Advantages of BiCMOS over CMOS (speed, drive capability).
- Verification of digital circuits in SPICE.
- Understanding carry propagation in adders.

MIT License. Awesome step into digital VLSI—try a ripple-carry adder next! 🚀