# Inverter Comparison in LTspice: CMOS vs Resistor-Load NMOS

## Suggested Project/Repo Name
**`inverter-comparison-ltspice`**  
(or `cmos-vs-nmos-inverters`, `digital-inverters-simulation`)

## Overview
This LTspice project compares different **inverter** (NOT gate) implementations using 65nm BSIM4 models:
- **Resistor-load NMOS inverters** (with 100kΩ pull-up resistors) – classic but power-hungry.
- **Single NMOS with resistive pull-up** – early logic family style.
- **Pulse input** for transient analysis to observe switching behavior.

The goal is to highlight why **CMOS inverters** (PMOS + NMOS) dominate modern digital design: lower power, better noise margins, and rail-to-rail output.

<grok-card data-id="c4a22a" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard CMOS Inverter Schematic (for reference – not in this schematic yet)

<grok-card data-id="d4e302" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical Resistor-Load NMOS Inverter

## Current Schematic Contents
- Left: Pulse voltage source (0–250mV, 50ns period) → shared input.
- Middle: Two resistor-load NMOS inverters (M1 & M3 with 100kΩ pull-ups R1 & R3).
- Right: Another NMOS (M2) with 100kΩ pull-up (R2).
- V1: 250mV supply (low for demo; typical 65nm uses ~1.0–1.2V).
- .tran simulation: 0 to 300ns, 0.1ns step.
- Includes BSIM4 65nm library.

## Key Differences & Learning Points
- **Resistor-load NMOS**: High static power (current always flows when output low), asymmetric rise/fall times, poor noise margins.
- **CMOS (ideal)**: Near-zero static power, symmetric drive, full rail-to-rail swing.

<grok-card data-id="fe517d" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical VTC: CMOS (sharp, high gain) vs resistive-load (gradual, lower gain)

## Repository Files
- `Draft2.asc` (or rename to `inverter_comparison.asc`) — Main LTspice schematic.
- `BSIM4_065.lib` (or separate `nmos_65nm.mod`) — 65nm BSIM4 models.

## How to Run
1. Install LTspice (free from Analog Devices).
2. Open the `.asc` file.
3. Run transient simulation (already set: 300ns).
4. Plot inputs vs outputs → observe slow rise times due to RC pull-up.
5. (Optional) Add a true CMOS inverter for direct comparison.

## Suggestions for Improvement
- Add a proper CMOS inverter (PMOS on top, NMOS bottom).
- Increase VDD to 1.2V for realistic 65nm operation.
- Run DC sweep to plot Voltage Transfer Characteristics (VTC).
- Measure power consumption and propagation delay.

## Learning Goals
- Understand evolution from NMOS to CMOS logic.
- See real effects of pull-up resistors vs active pull-up (PMOS).
- Practice LTspice transient/DC analysis for digital circuits.

MIT License. Feel free to fork and enhance!