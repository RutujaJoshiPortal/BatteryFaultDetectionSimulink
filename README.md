# 🔋 Battery Pack Safety Monitor

This project is a **Battery Fault Detection Using Simulink** designed to detect unsafe conditions in lithium-ion battery packs. It monitors key electrical and thermal parameters, generates fault flags, and is ready for **C code generation** for embedded system deployment.

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

```
BatteryPackSafetyMonitor/
├── BatteryMonitor.slx                    # Simulink model
├── BatteryMonitor_ert_rtw/              # Generated C code files
├── README.md                            # This file
├── BatteryMonitor_Technical_Report.docx # Editable Word report
├── BatteryMonitor_Technical_Report.pdf  # Printable PDF report
├── LICENSE                              # (Optional) License info
```

---

## 🚀 Getting Started

### Prerequisites
- MATLAB + Simulink (recommended R2021b or newer)
- Simulink Coder
- Embedded Coder (for advanced target integration)

### Run the Model
1. Open `BatteryFaaultDetectionSimulink.slx` in MATLAB Simulink.
2. Set thresholds via `Constant` blocks.
3. Run simulations using `Signal Builder` or `From Workspace` blocks.
4. View fault outputs via `Scope` blocks or the model’s `Outports`.

### Generate C Code
1. Go to **Model Settings > Code Generation**
2. Set:
   - System target file: `ert.tlc`
   - Language: `C`
3. Press **Ctrl + B** or click **Build** to generate code.

---

## 📊 Test Scenarios

| Test Case        | Inputs                        | Expected Output                  |
|------------------|-------------------------------|----------------------------------|
| Normal           | 3.7V, 25°C, 50A               | AllSafe = true                   |
| Overvoltage      | 4.3V                          | OV_Fault = true                  |
| Undervoltage     | 2.5V                          | UV_Fault = true                  |
| Overtemperature  | 65°C                          | OT_Fault = true                  |
| Overcurrent      | 120A                          | OC_Fault = true                  |
| Multiple Faults  | 4.3V, 65°C                    | OV_Fault = true, OT_Fault = true|

---

## 📄 Documentation

- 📘 `BatteryFaultDetectionSimulink_Technical_Report.pdf`: Technical details on architecture, logic, simulation, and testing.

---

## 📚 References

- MathWorks Documentation – Simulink & Simulink Coder
- ISO 26262: Functional Safety Standard for Road Vehicles
- Battery Management Systems (Gregory L. Plett)

---

## 🛠 Future Work

- Integrate CAN communication output
- Add real-time fault logging
- Deploy on STM32 / TI BMS controllers
- Add GUI for monitoring live simulation

---

## 📜 License

This project is open-source. You can choose a license such as MIT, BSD, or GPL and include it in the `LICENSE` file.

---

## 👩‍💻 Author

**Rutuja Joshi**  
Battery Application Engineer | Systems & Embedded Software  
[LinkedIn](https://www.linkedin.com/in/joshirutuja28/)
