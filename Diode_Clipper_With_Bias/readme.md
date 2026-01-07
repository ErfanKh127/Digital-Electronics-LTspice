# Biased Diode Clipper Simulation in LTspice

## Overview
This project simulates a **biased shunt diode clipper** (positive clipping with bias) in LTspice.

- **Input**: 10V peak, 60Hz sine wave (Vi: SINE(0 10V 60Hz)).
- **Series resistor**: R1 = 100Ω.
- **Diode**: D1 (default 1N4148 or similar) in shunt to ground.
- **Bias battery**: V1 = 2V (positive bias on cathode side).

The circuit clips the positive portion of the input waveform starting from **+2.7V** approx. (+2V bias + ~0.7V diode drop).

<grok-card data-id="0f6de3" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Your current LTspice schematic

<grok-card data-id="aae774" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard biased positive shunt clipper (similar configuration)

<grok-card data-id="1507fc" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Another example of biased series clipper (for reference)

## Circuit Operation
- When Vi ≤ +2.7V → diode reverse-biased → no clipping → Vo ≈ Vi.
- When Vi > +2.7V → diode forward-biased → clamps Vo to ~+2.7V.
- Negative half-cycle passes unchanged (diode remains off).
- R1 limits current through the diode during clipping.

This is a **positive clipper with positive bias**, useful for protecting circuits or shaping waveforms.

<grok-card data-id="868444" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Expected input (blue) vs clipped output (red) waveforms

<grok-card data-id="6cfe91" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Another typical clipped waveform example

## Files
- `Diode_Clipper_With_Bias.asc` → Main schematic (rename if desired).
- No external models needed (uses built-in diode).

## How to Run
1. Open the `.asc` file in LTspice.
2. Run transient simulation (already set to 0.1s → covers multiple cycles).
3. Plot Vi (input) and Vo (output) → observe clipping above ~2.7V.
4. **Experiment ideas**:
   - Change V1 value to adjust clipping level.
   - Reverse diode/battery for negative clipping.
   - Add another diode branch for double-sided clipping.

## Learning Goals
- Understand diode clipper types (shunt, series, biased, unbiased).
- See effect of bias voltage on clipping threshold.
- Analyze waveform distortion and protection applications (e.g., overvoltage limiting).

MIT License. Feel free to modify and expand! 🚀