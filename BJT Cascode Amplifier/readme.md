# BJT Cascode Amplifier Simulation in LTspice

## Overview
This project simulates a **BJT cascode amplifier** using two 2N3904 NPN transistors (Q1 common-emitter bottom, Q2 common-base top).

- **Supply**: +10V (V2)
- **Input**: 200mV peak, 100Hz sine wave (V1)
- **Biasing**: R1=100Ω (input), R2=1kΩ & R3=3.3kΩ (emitter/base), R4=10kΩ (cascode base bias)
- **Load**: R5=3.9kΩ (collector), R6=10kΩ (output load)
- **Coupling**: C1=100µF (input), C2=10µF (cascode base bypass?), C3=10µF (output)

The cascode topology provides high gain, excellent bandwidth, and reduced Miller effect.

<grok-card data-id="683d1c" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard BJT Cascode Schematic

<grok-card data-id="5ac246" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Another typical BJT Cascode Example

<grok-card data-id="dcaf19" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Cascode in LTspice (similar)

## Circuit Operation
- Bottom transistor (Q1): Common-emitter stage provides most voltage gain.
- Top transistor (Q2): Common-base stage isolates Miller capacitance → higher bandwidth.
- Overall gain similar to single CE but with much better high-frequency response.
- Output taken after coupling capacitor C3.

Expected mid-band gain ≈ 40–60 dB, extended bandwidth vs single CE.

<grok-card data-id="dd0f5d" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical input (small) vs output waveforms (inverted, amplified)

<grok-card data-id="bc36d4" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Cascode vs CE comparison waveforms

<grok-card data-id="5cb15f" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical Bode plot showing extended bandwidth

## Files
- `Draft5.asc` → Rename to `bjt_cascode_amplifier.asc`
- No external models needed (built-in 2N3904)

## How to Run
1. Open the `.asc` file in LTspice.
2. Run transient (.tran 0.1) → Plot input vs output (high gain, clean amplification).
3. Run AC analysis (.ac dec 100 10 1Meg) → Plot gain/phase for superior bandwidth.
4. **Experiments**:
   - Compare with single CE stage.
   - Change input frequency → See reduced roll-off.
   - Adjust bias resistors → Optimize Q-point.

## Learning Goals
- Advantages of cascode topology (gain, bandwidth, output resistance).
- Miller effect reduction in high-frequency amplifiers.
- Comparison with single-stage CE amplifiers.
- AC vs transient analysis for broadband designs.

MIT License. Great for RF/preamp studies—expand further! 🚀