# 🔊 Capacitive Touch Volume Controller

A modern, USB-powered capacitive volume controller that uses a single touchpad and an RGB LED to simulate digital volume control behavior. Built with the RP2040 microcontroller, this project integrates capacitive sensing, RGB visual feedback, and optional OLED display output — all designed in **KiCad**.

---

## 🚀 Features

- 🖐️ Capacitive touch input (single-point)
- 🌈 WS2812B RGB LED for visual feedback
- ⚡ USB-C powered (with fuse and Schottky protection)
- 🧠 RP2040 microcontroller core
- 🖥️ Optional 0.96" I²C OLED header
- 🧩 Beginner-friendly, surface-mount layout (SMD)

---

## 🧠 How It Works

- When a user touches the copper pad, the RP2040 measures capacitive charge delay through a 1MΩ resistor.
- The firmware interprets this as a "volume adjust" interaction.
- The RGB LED brightness or color changes to reflect volume level.
- Optionally, volume level can be displayed numerically via OLED.

---

## 📐 Schematic Blocks

### 🔋 Power & Protection
- `J1`: USB-C Receptacle (16-pin)
- `F1`: Resettable PTC fuse
- `D1`: Schottky diode (SS14)
- `C1`: 0.1 µF decoupling capacitor

### 🧠 Microcontroller Core
- `U1`: RP2040 QFN-56
- `Y1`: 3.2x2.5mm crystal (optional)
- `C2–C4`: Bypass and regulator caps (1µF + 0.1µF)
- `R1`: 10kΩ pull-up for RUN pin

### ✋ Touch Sensing
- `TP1`: Touch pad test point
- `R2`: 1MΩ sensing resistor

### 🌈 RGB LED Output
- `D2`: WS2812B (PLCC4)
- `R3`: 330Ω data-line protection
- `C5`: 100 µF bulk cap

### 🖥️ Optional OLED Display
- `J2`: Conn_01x04 (SDA, SCL, GND, 3.3V)
- `R4`, `R5`: 4.7kΩ I²C pull-up resistors

---

## 📦 Bill of Materials (BOM)

| Ref | Value/Part | Notes |
|-----|------------|-------|
| C1 | 0.1 µF | USB input filter |
| C2 | 1 µF | VREG_VOUT cap |
| C3, C4 | 0.1 µF | IOVDD/DVDD bypass |
| C5 | 100 µF | WS2812B power smoothing |
| D1 | Schottky | SS14 or similar |
| D2 | WS2812B | PLCC4 5050 |
| F1 | PTC Fuse | 500mA or similar |
| J1 | USB-C | HRO_TYPE-C-31-M-12 |
| J2 | OLED Header | 1x04, 2.54mm |
| R1 | 10kΩ | RUN pin pull-up |
| R2 | 1MΩ | Capacitive touch |
| R3 | 330Ω | LED data resistor |
| R4, R5 | 4.7kΩ | I²C pull-ups |
| TP1 | Test Point | Touch surface |
| U1 | RP2040 | QFN-56 |
| Y1 | Crystal | 3.2x2.5mm SMD

---

## 🛠️ Getting Started

1. Flash firmware via SWD or USB bootloader
2. Touch pad triggers volume state change
3. LED reflects level (brightness, hue, etc.)
4. (Optional) OLED displays numerical volume level

---

## 📸 Preview
![image](https://github.com/user-attachments/assets/05208933-c4e2-4caa-9462-76f17e701323)

---

## 🧑‍💻 Author

Designed by [Your Name] — May 2025  
Built in KiCad 7 — RP2040-powered — USB-C elegance

---

## 🪪 License

MIT License — free to use, remix, and distribute.
