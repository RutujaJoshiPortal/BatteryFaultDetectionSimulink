# BatteryFaultDetectionSimulink
Safety monitor model for battery packs using Simulink with embedded C code generation.

# 🔋 Battery Pack Safety Monitor

This project is a **Batatery Fault Detection Using Simulink** designed to detect unsafe conditions in lithium-ion battery packs. It monitors key electrical and thermal parameters, generates fault flags, and is ready for **C code generation** for embedded system deployment.

---

## 📌 Features

- ✅ Monitors:
  - Cell voltages (overvoltage / undervoltage)
  - Pack current (overcurrent)
  - Cell temperatures (overtemperature)
- ⚠️ Detects:
  - OV_Fault: Overvoltage
  - UV_Fault: Undervoltage
  - OC_Fault: Overcurrent
  - OT_Fault: Overtemperature
  - AllSafe flag: Active when no faults are detected
- 🧠 Optional latching fault logic
- ⚙️ Code-generation ready (`ert.tlc`) for deployment on embedded targets (e.g., STM32, TI C2000)

---

## 📁 Project Structure

