# Voltage Divider Biased Common Emitter Amplifier in LTspice

## Overview
This project simulates a **voltage divider biased common emitter (CE) amplifier** using a 2N3904 NPN transistor.

- **Supply**: +12V (V2)
- **Input**: 10mV peak, 1kHz sine wave (V1 with AC 10 for small-signal)
- **Biasing**: Voltage divider R3=68kΩ, R4=4.7kΩ → stable Q-point
- **Emitter**: R2=100Ω (degeneration for stability)
- **Collector load**: R1=10kΩ
- **Coupling**: C1=1µF (input), C2=1µF (output), C3=1µF (emitter bypass for AC gain)

This is a classic stable design with good gain and linearity.

<grok-card data-id="a0cded" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Your LTspice schematic (Draft4.asc)

<grok-card data-id="a6d612" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard voltage divider biased CE amplifier

<grok-card data-id="2dfbd7" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Another typical CE with bypass capacitor

## Circuit Operation
- **DC Bias**: Voltage divider sets base ~1-2V, emitter follower gives good thermal stability.
- **AC Gain**: Mid-band ≈ -R1 / (R2 || re) → boosted by C3 bypass at signal frequencies.
- **Phase**: 180° inversion.
- **Coupling caps**: Block DC, pass AC signal.

Expected gain ≈ 80–100 (high due to bypass).

<grok-card data-id="0fea38" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical transient: small input (blue) vs large inverted output (yellow)

<grok-card data-id="e3fdc7" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example input-output waveforms showing 180° shift

<grok-card data-id="a61224" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical frequency response (Bode plot)

## Files
- `Draft4.asc` → Rename to `ce_amplifier_voltage_divider.asc`
- No external models needed (built-in 2N3904)

## How to Run
1. Open the `.asc` file in LTspice.
2. Run transient (.tran 10m) → Plot "in" vs "out" (observe high gain and inversion).
3. For AC analysis: Add `.ac oct 100 1 1Meg` → Plot gain/phase.
4. **Experiments**:
   - Remove C3 → See reduced gain due to degeneration.
   - Increase input amplitude → Check clipping.
   - Vary frequency → See low/high cutoff from coupling/bypass caps.

## Learning Goals
- Voltage divider biasing advantages (stability over fixed bias).
- Effect of emitter bypass capacitor on gain.
- Transient vs AC analysis in amplifiers.
- Gain, bandwidth, and distortion trade-offs.

MIT License. Experiment and expand! 🚀