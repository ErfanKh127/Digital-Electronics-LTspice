# BJT Differential Amplifier (Long-Tailed Pair) Simulation in LTspice

## Overview
This project simulates a classic **BJT differential amplifier** (long-tailed pair) using two matched 2N3904 NPN transistors.

- **Supply**: +10V (V2)
- **Input**: 10mV peak, 100Hz sine wave (single-ended at left base via C1)
- **Tail current source**: High resistance (R1=150kΩ + R2=100Ω) for approximate constant current
- **Collector loads**: R4=820Ω (left), R5=68kΩ & R6=1.2kΩ (right, unbalanced for demo)
- **Emitter coupling**: C2=0.1µF (bypass for AC?)
- **Output coupling**: C3=10µF, C4=100µF, with load R9=10kΩ

This topology is the core of op-amp input stages—excellent common-mode rejection and differential gain.

<grok-card data-id="4e55b0" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Your LTspice schematic (Draft6.asc)

<grok-card data-id="3fd4a7" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard BJT Differential Pair Schematic

<grok-card data-id="fe5f1f" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Classic Long-Tailed Pair Diagram

## Circuit Operation
- Differential input → opposite-phase outputs at collectors.
- Common-mode input → minimal output (high CMRR).
- Tail resistance sets current; higher value → better rejection.
- Here: Single-ended input demonstrates amplification and inversion.

Expected differential gain ≈ 20–40 (depending on load balance).

<grok-card data-id="18439e" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical differential input/output waveforms (180° phase shift)

<grok-card data-id="bf5fd7" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example waveforms showing common-mode rejection

## Files
- `Draft6.asc` → Rename to `bjt_differential_amplifier.asc`
- No external models needed (built-in 2N3904)

## How to Run
1. Open the `.asc` file in LTspice.
2. Run transient (.tran 0.1) → Plot input vs collector voltages (observe differential action).
3. Run .op for DC operating point.
4. **Experiments**:
   - Apply differential input (two out-of-phase sources).
   - Balance collector resistors → symmetric outputs.
   - Add true current source in tail → improve CMRR.
   - AC analysis for gain/CMRR.

## Learning Goals
- Understand differential vs common-mode signals.
- High CMRR mechanism in long-tailed pairs.
- Foundation of operational amplifier input stages.
- Effects of component matching and tail current.

MIT License. Ideal for analog IC basics—extend to full op-amp! 🚀