# Common Emitter Amplifier Simulation in LTspice

## Overview
This project simulates a classic **single-stage common emitter (CE) BJT amplifier** using a 2N3904 NPN transistor.

- **Supply**: Vcc = 10V
- **Input**: 50mV peak, 1kHz sine wave (with AC 1 for small-signal analysis)
- **Biasing**: Voltage divider (R1=10k, R2=2.2k), RB=100Ω (possibly for stability)
- **Emitter**: Rs=1k (degeneration), bypassed by CB=10µF
- **Collector**: RC=3.9k, RL=10k
- **Coupling**: C2=10µF (input), C3=10µF (output)

The design provides good voltage gain, stability, and reasonable bandwidth.

<grok-card data-id="e3f2a3" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Your LTspice schematic (CEAmplifier.asc)

<grok-card data-id="3ec6b7" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard Common Emitter Amplifier Schematic

<grok-card data-id="b260e2" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

CE Amplifier with Emitter Bypass Capacitor

## Circuit Operation
- **DC Bias**: Sets Q-point near mid-rail for maximum swing.
- **AC Gain**: High mid-band gain (~ -RC / re, boosted by bypass capacitor CB which removes degeneration at signal frequencies).
- **Phase**: 180° inversion (output inverted relative to input).
- **Coupling Capacitors**: Block DC while passing AC signal.

Expected mid-band voltage gain ≈ 30–50 (depending on exact re).

<grok-card data-id="7c13e0" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical Input (blue) vs Inverted Output (red) Waveforms

<grok-card data-id="9a9332" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example Frequency Response (Bode Plot)

## Files
- `CEAmplifier.asc` — Main schematic.
- No external models required (uses built-in 2N3904).

## How to Run
1. Open the `.asc` file in LTspice.
2. Run transient (.tran 50m) → Plot Vin vs Vout (observe amplification and inversion).
3. Run AC analysis (.ac dec 100 10 1Meg) → Plot gain/phase vs frequency for Bode response.
4. **Experiments**:
   - Remove CB → See reduced gain due to emitter degeneration.
   - Vary input amplitude → Check for distortion/clipping.
   - Sweep frequency → Identify low/high cutoff points.

## Learning Goals
- Understand BJT common emitter configuration and biasing.
- Role of bypass and coupling capacitors.
- Small-signal AC analysis vs transient behavior.
- Voltage gain, input/output impedance, and frequency response.

MIT License. Modify components and explore variations! 🚀