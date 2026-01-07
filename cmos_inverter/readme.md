# CMOS Inverter Simulation in LTspice

## Overview
This project simulates a **CMOS inverter** using LTspice with BSIM4 65nm MOSFET models. The CMOS inverter is the basic building block of digital circuits, inverting the input signal (0 → 1, 1 → 0) with very low static power consumption.

<grok-card data-id="4a4633" data-type="image_card"  data-arg-size="LARGE" ></grok-card>



<grok-card data-id="143776" data-type="image_card"  data-arg-size="LARGE" ></grok-card>


## Circuit Explanation
- **Components**: One PMOS (pull-up, connected to VDD) and one NMOS (pull-down, connected to GND).
- **Connections**: Gates tied together (input Vin), drains tied together (output Vout).
- **Operation**:
  - Vin high → NMOS ON, PMOS OFF → Vout low.
  - Vin low → PMOS ON, NMOS OFF → Vout high.
- **Advantages**: Near-zero static power, high noise margins, fast switching.

## Applications
- Foundation for all digital logic gates (NAND, NOR, etc.).
- Used in microprocessors, memory, oscillators, and low-power devices.

<grok-card data-id="7466d3" data-type="image_card"  data-arg-size="LARGE" ></grok-card>


## Repository Files
- `cmos_inverter.asc` — LTspice schematic.
- `nmos_65nm.mod` & `pmos_65nm.mod` — BSIM4 65nm models.

## How to Run
1. Install LTspice (free from Analog Devices).
2. Open `.asc` file.
3. **DC Sweep**: Sweep Vin (0 to 1.2V) → Plot VTC curve.
4. **Transient**: Use pulse input → Observe switching delay and rise/fall times.

## Expected Results
- Sharp VTC with switching threshold ~VDD/2.
- Propagation delay ~10-50ps.
- Low static power, dynamic power depends on frequency.

## Learning Goals
- Understand CMOS digital operation.
- Practice SPICE simulation.
- Analyze power, delay, and noise margins.

## Troubleshooting
- Model not found? Add folder to LTspice library paths.
- Convergence issues? Add small time steps or `.OPTIONS GMIN=1e-12`.

MIT License. Contributions welcome!