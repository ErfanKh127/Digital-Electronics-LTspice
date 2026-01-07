# Resistive-Load NMOS Inverter Simulation in LTspice

## Suggested Repo/Folder Name
`resistive-nmos-inverter-65nm`  
(or `nmos-resistive-load-inverter`, `early-nmos-logic-simulation`)

## Overview
This LTspice project simulates a **resistive-load NMOS inverter** using BSIM4 65nm models. It shows classic NMOS logic with a 100kΩ pull-up resistor—demonstrating high static power, asymmetric switching (fast fall, slow rise), and limited output swing. Great for understanding the limitations that led to **CMOS** dominance.

<grok-card data-id="3da31b" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Your current schematic (Draft3.asc)

<grok-card data-id="0647fb" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard Resistive-Load NMOS Inverter Schematic

<grok-card data-id="290cba" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Another Resistive-Load Example

<grok-card data-id="79b925" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard CMOS Inverter (for future comparison)

## Current Schematic Details
- Pulse input: PULSE(0 250m 32n 1n 1n 32n 66n) → ~7.6 MHz signal.
- VDD sources: Multiple 250mV supplies (low for demo; realistic 65nm uses ~1.0–1.2V).
- One NMOS (M1 BB) with 100kΩ pull-up (R1).
- Transient simulation: 300ns, 0.1ns step.
- Includes BSIM4 65nm library.

## Key Observations
- **Slow rise time**: Limited by RC constant of pull-up resistor.
- **Fast fall time**: Strong NMOS pull-down.
- **High static power**: Current flows when output low.
- **Output high level**: Drops below VDD due to resistor divider.

<grok-card data-id="0e70b1" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example transient waveforms showing asymmetry

<grok-card data-id="bab371" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical VTC: Gradual transition vs sharp CMOS

## Files
- `Draft3.asc` → Rename to `resistive_nmos_inverter.asc`
- `BSIM4_065.lib` — 65nm BSIM4 model library

## How to Run & Improve
1. Open in LTspice → Run transient → Plot input vs output1 (observe slow rise).
2. **Suggestions**:
   - Increase VDD to 1.2V for realistic behavior.
   - Add a CMOS inverter branch for direct comparison.
   - Run DC sweep to plot VTC and noise margins.
   - Measure power: Plot V(VDD)*I(Vsource).

## Learning Goals
- Limitations of early NMOS logic families.
- Why CMOS (active pull-up with PMOS) revolutionized digital design.
- Hands-on SPICE analysis of power, speed, and voltage levels.

MIT License. Add a CMOS version and expand the comparison! 🚀