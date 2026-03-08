# DC-Motor-Soft-Starter-Simulation
Simulation of a DC motor soft-starting method using multi-stage armature resistors to limit inrush current and reduce torque spikes during startup.
# DC Motor Starting Simulation

## Overview

This project investigates the starting behavior of a separately excited DC motor and proposes a method to limit the high inrush current during startup using external resistors.

When a DC motor starts from standstill, the back EMF is zero which causes a very large current to flow through the armature. This can damage the motor windings and produce excessive torque.

To solve this problem, a multi-stage resistor starting method is implemented and simulated.

The project compares two approaches:

• 3-stage resistor starting  
• 4-stage resistor starting  

The simulation analyses current, speed, torque and voltage behaviour during motor startup.

---

## Motor Parameters

| Parameter | Value |
|----------|------|
Supply Voltage | 240 V
Armature Resistance | 0.6 Ω
Rated Current | 16.2 A

---

## Problem

At startup:

Back EMF = 0

Therefore,

Ia = V / Ra

Because Ra is very small (<1Ω), the starting current becomes extremely high and may exceed **10× the rated current**.

---

## Solution

External resistors are connected in series with the armature during startup.

As the motor speed increases:

1. Back EMF increases
2. Current decreases
3. External resistors are gradually removed

This prevents excessive current while allowing the motor to accelerate smoothly.

---

## Simulation Cases

### Case 1 — 3 Stage Starting Resistors

Results:

• Faster startup  
• Rated speed ≈ 7.5 seconds  
• Maximum current ≈ 42 A  
• Torque spike ≈ 75 Nm  

Disadvantage:

Current exceeds safe operating limit.

---

### Case 2 — 4 Stage Starting Resistors

Results:

• Smoother current profile  
• Rated speed ≈ 9.3 seconds  
• Maximum current ≈ 22.5 A  
• Torque ≈ 57 Nm  

Advantage:

Safe current levels and reduced torque stress.

---

## Results Comparison

| Method | Speed Time | Max Current | Safety |
|------|------|------|------|
3 Stage | ~7.5 s | 42 A | Risky |
4 Stage | ~9.3 s | 22.5 A | Safe |

The **4-stage resistor method provides smoother starting characteristics and prevents motor damage.**

---

## Simulation Outputs

The simulation produces the following waveforms:

• Armature Current  
• Electromagnetic Torque  
• Motor Speed  
• Terminal Voltage  

These waveforms demonstrate the improvement in current control when using staged resistors.

---

## Alternative Starting Methods

Other techniques to reduce starting current include:

• PWM controlled DC chopper  
• Buck-Boost converter starter  
• Fuzzy logic motor control  
• Capacitor assisted soft start  

---

## Key Learning Outcomes

• DC motor dynamic behaviour  
• Motor starting current control  
• Multi-stage resistor starter design  
• Simulation of electrical machines

---

## Author

**Disha Harwalkar**

MSc Electrical and Electronics Engineering  
University of Greenwich
