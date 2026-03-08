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
## Circuit Design 

The DC motor starting system consists of:

1. DC voltage source (240 V)
2. Separately excited DC motor
3. Armature resistance
4. External starting resistors
5. Switching mechanism to remove resistors
6. Measurement blocks for current, torque and speed

The resistors are connected in series with the armature during startup.  
As the motor accelerates and back EMF increases, the resistors are removed sequentially to maintain safe current levels.
The model for starting the DC motor with external resistors is designed and implemented. The figure1 below shows the circuit and the figure 2 shows the 4 stages of resistors connected in series to the armature.

<img width="424" height="496" alt="Screenshot 2026-03-08 193803" src="https://github.com/user-attachments/assets/a3b74447-d3e8-4dc0-882c-3548230c1990" />

---

## Simulation Workflow

The simulation follows these steps:

1. Motor starts at zero speed (Back EMF = 0)
2. External resistors limit the starting current
3. Motor speed increases gradually
4. Resistors are removed at predefined time intervals
5. Current, torque and speed waveforms are recorded

---

## Key Equations

Armature current:

Ia = (V − Eb) / Ra

Where:

V = Supply voltage  
Eb = Back EMF  
Ra = Armature resistance  

Back EMF is proportional to motor speed:

Eb = k × ω

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

<img width="592" height="709" alt="Screenshot 2026-03-08 185412" src="https://github.com/user-attachments/assets/3bf25983-af67-4ee2-b000-b2f623ac802b" />

<img width="456" height="669" alt="Screenshot 2026-03-08 185452" src="https://github.com/user-attachments/assets/22c0ff73-19a6-4328-a613-288bdc51d815" />

<img width="466" height="660" alt="Screenshot 2026-03-08 185506" src="https://github.com/user-attachments/assets/9bd24681-8682-43b6-9537-dfc2ff0c3ccf" />

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
