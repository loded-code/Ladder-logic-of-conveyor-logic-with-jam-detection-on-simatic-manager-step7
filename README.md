# Ladder-logic-of-conveyor-logic-with-jam-detection-on-simatic-manager-step7
The ladder logic includes:  Motor run latch logic (manual restart for safety)  Flow sensor detection  ON-delay jam timer (TON)  Jam alarm latch  Motor inhibit on jam  Alarm lamp/buzzer output  Reset and recovery sequence
# Conveyor Control with Jam Detection (Siemens STEP-7)

This project implements an industrial conveyor control system with **automated jam detection** using **Siemens SIMATIC Manager STEP-7** for **S7-300 PLCs**. The logic monitors product flow via a sensor and triggers a jam alarm if the conveyor runs without detecting material for a predefined timeout.

---

## 🌐 Overview

Conveyors are widely used in manufacturing and logistics to move material between process stages. A jam in the conveyor can lead to:

- equipment damage
- part spillage
- downtime
- safety hazards
- production losses

This PLC logic detects jams early and ensures safe recovery via operator reset and manual restart.

---

## 🧰 Features

✔ Motor run control  
✔ Flow sensor feedback  
✔ Jam timeout via TON timer  
✔ Jam alarm latch  
✔ Motor inhibit on jam  
✔ Manual reset for safe restart  
✔ External alarm output (buzzer/lamp)  
✔ Fully compatible with PLCSIM simulation  

---

## 🛠 Platform & Tools

| Component | Value |
|---|---|
| PLC Family | Siemens S7-300 |
| CPU Used | CPU 315-2 PN/DP |
| Software | SIMATIC Manager STEP-7 |
| Language | LAD (Ladder Logic) + STL |
| Simulation | PLCSIM (optional) |

---

## 🚦 Operating Sequence

1. Operator presses **START**
2. Conveyor motor runs
3. Flow sensor detects product movement
4. If **no flow** while motor is running:
   - TON timer starts
5. If timeout expires (2 seconds):
   - Motor stops
   - Jam alarm is raised
   - Alarm lamp/buzzer activated
6. Operator clears jam mechanically
7. Operator presses **RESET**
8. Operator presses **START** to resume

This implementation uses **manual restart** for safety compliance.

---

## 🔎 Jam Detection Logic

**Condition:**

> Motor Running AND No Flow for Timeout

Implemented using `TON` timer with 2s preset.

---

## 📐 Core Ladder Logic Structure (Conceptual)

