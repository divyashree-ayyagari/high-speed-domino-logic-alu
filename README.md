# High-Speed Domino Logic ALU

**Design and transient-delay analysis of static CMOS and domino logic circuits using Cadence Virtuoso and the GPDK 90 nm technology library.**

## Overview

This project explores the design and performance of a High-Speed Domino Logic Arithmetic and Logic Unit (ALU). Static CMOS and domino logic implementations of basic logic gates, full adders, and a 4-bit Ripple Carry Adder (RCA) were designed and simulated to compare propagation delays.

Domino logic uses clock-controlled precharge and evaluation phases. Its reduced evaluation-network complexity can improve switching speed, making it useful for investigating high-performance digital circuit design.

## Objectives

- Design and compare static CMOS and domino logic gates.
- Implement AND, OR, XOR, and NOT gates.
- Design full-adder circuits using both logic styles.
- Construct a 4-bit Ripple Carry Adder.
- Perform transient simulations and measure propagation delay.
- Analyze the speed trade-offs between static CMOS and domino logic.

## Tools and Technology

- **EDA tool:** Cadence Virtuoso
- **Technology library:** GPDK 90 nm
- **Analysis:** Transient simulation
- **Design focus:** CMOS logic, dynamic logic, arithmetic circuits, propagation delay

## Design Methodology

1. **Basic logic gates:** Designed the required logic gates in static CMOS and domino logic.
2. **Symbol creation:** Created reusable symbols for the gates.
3. **Full-adder design:** Combined logic gates to implement full-adder sum and carry outputs.
4. **Ripple-carry adder:** Cascaded four full-adder stages to implement a 4-bit RCA.
5. **Transient analysis:** Simulated the circuits and measured propagation delays using the 50% input and output signal points.
6. **Comparative analysis:** Compared the reported delays of static CMOS and domino logic implementations.

## Simulation Results

The following values are taken from the project's transient-analysis report.

| Circuit output | Static CMOS delay (ps) | Domino logic delay (ps) |
|---|---:|---:|
| OR gate | 30.47814 | 17.79383 |
| AND gate | 78.46593 | 15.45340 |
| XOR gate | 109.3648 | 86.42561 |
| Full-adder sum | 152.6271 | 18.81798 |
| Full-adder carry | 55.26170 | 43.49789 |
| RCA carry-out | 1052.411 | 23.54965 |
| RCA sum S0 | 6.234291 | 10.27589 |
| RCA sum S1 | 168.4028 | 141.9527 |
| RCA sum S2 | 299.9228 | 258.6295 |
| RCA sum S3 | 455.1787 | 390.7408 |

### Key Observations

- The reported domino OR gate delay is lower than the static CMOS OR gate delay.
- The domino AND gate also shows a lower reported propagation delay.
- The domino XOR implementation is faster in the reported simulation results, although its advantage is smaller than that of the AND gate.
- The full-adder sum and carry paths show lower reported delays with domino logic.
- The reported RCA sum delays illustrate how propagation delay varies across the four output bits.
- The RCA carry-out measurements show a large difference between the two implementations; this result should be rechecked against the original waveforms and measurement setup before drawing a general conclusion.

## Understanding Domino Logic

Domino logic is a dynamic logic family that operates in two phases:

- **Precharge:** The dynamic node is charged before evaluation.
- **Evaluation:** The NMOS pull-down network conditionally discharges the dynamic node according to the input combination.

This approach can reduce the complexity and capacitance of the evaluation network. However, domino circuits require careful clocking and are sensitive to noise, charge sharing, and input-transition constraints.

## Skills Demonstrated

- CMOS digital circuit design
- Dynamic and domino logic
- Cadence Virtuoso schematic design
- Full-adder and ripple-carry adder design
- Transient simulation
- Propagation-delay measurement
- Comparative circuit analysis

## Limitations and Future Work

- Revalidate the reported RCA carry-out delay using the original transient waveforms.
- Extend the design to wider adders.
- Evaluate power consumption and transistor sizing under consistent simulation conditions.
- Investigate noise margins, charge sharing, keeper sizing, and clock timing.
- Compare additional arithmetic architectures.

## Disclaimer

This repository documents an academic circuit-design project. The reported measurements reflect the simulations described in the project report and are not independent silicon measurements.
