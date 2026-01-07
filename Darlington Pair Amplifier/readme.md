# Darlington Pair Amplifier Simulation in LTspice

## Overview
This project simulates a **Darlington pair amplifier** using an NPN (Q1: 2N3904) driving a PNP (Q2: 2N3906) in a complementary configuration.

- **Supplies**: +10V (V2) and -10V (V3) for bipolar operation
- **Input**: 10mV peak, 100Hz sine wave (V1 via C1=0.1µF)
- **Biasing**: R1=100Ω (input), R2=1kΩ, R3=15kΩ, R4=1kΩ, R5=15kΩ
- **Output stage**: R6=10Ω, R7=10Ω, R8=1kΩ (load?)

The Darlington pair provides extremely high current gain (β₁ × β₂), high input impedance, and is commonly used for power amplification or switching.

<grok-card data-id="883c88" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Basic Darlington Pair Configuration

<grok-card data-id="5dd53d" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Standard Darlington Transistor Symbol and Circuit

<grok-card data-id="23f3d6" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical Darlington Pair Schematic

<grok-card data-id="a9ce1d" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example LTspice Darlington Simulation

## Circuit Operation
- Q1 amplifies input current → drives Q2 base.
- Combined β very high (~ thousands).
- High input impedance, low output impedance.
- This complementary setup allows push-pull operation for better efficiency.
- Expected voltage gain moderate, but massive current gain.

<grok-card data-id="630371" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Typical Input vs Amplified Output Waveforms

<grok-card data-id="b1a518" data-type="image_card"  data-arg-size="LARGE" ></grok-card>

Example Waveform Showing High Gain

## Files
- `Draft7.asc` → Rename to `darlington_pair_amplifier.asc`
- No external models needed (built-in 2N3904 & 2N3906)

## How to Run
1. Open the `.asc` file in LTspice.
2. Run transient (.tran 0.1) → Plot input vs output (observe high current/voltage amplification).
3. Run .op for DC bias check.
4. **Experiments**:
   - Increase input amplitude → See linear range and clipping.
   - Change load resistor → Observe power delivery.
   - Compare with single transistor stage.

## Learning Goals
- Ultra-high current gain from cascaded transistors.
- Applications in power amplifiers, motor drivers, and relays.
- Trade-offs: Higher V_BE drop (~1.4V), slower switching.
- Complementary Darlington for audio/power output stages.

MIT License. Perfect for high-gain projects—keep building! 🚀