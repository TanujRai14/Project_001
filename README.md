# 🔌 Project_001: Smart USB Power Meter using ESP32, INA219 & OLED

This project is a compact **Smart USB Power Meter** designed using an **ESP32**, **INA219 current sensor**, and **OLED display**, all integrated on a custom **2-layer PCB**. The circuit allows real-time monitoring of **USB voltage and current** through a **Type-C connector**, displaying the results on a 0.96” OLED screen.

---

## ✨ Features

- ✅ Measures **voltage and current** of any USB-powered device
- 📟 Displays data on a **128x64 OLED** screen via **I2C**
- 📶 Powered by **ESP32** for wireless capabilities & efficient control
- 🔍 Uses **INA219** precision current sensor for accurate readings
- 🔧 Onboard **AMS1117** 5V to 3.3V regulator for safe ESP32 operation
- 🧵 Designed with **standard trace widths** (0.2mm, 0.3mm, 0.5mm)
- 🛠️ Full **GND pour** on bottom layer, all signals routed on top
- 📡 Dedicated **Antenna Keep-Out Zone** for WiFi stability

---

## 🧩 Hardware Components

| Component        | Description                                           |
|------------------|-------------------------------------------------------|
| **ESP32 Module** | WiFi-enabled microcontroller (ESP-WROOM-32)           |
| **INA219**       | I2C-based voltage and current sensor                  |
| **OLED Display** | 128x64 OLED via I2C (address: 0x3C or 0x78)           |
| **AMS1117-3.3V** | LDO regulator to step down 5V to 3.3V                  |
| **USB Type-C**   | Input connector for USB voltage/current measurement   |
| **Passives**     | Capacitors & resistors for filtering & pull-ups       |

---

## 🛠️ PCB Design Highlights

- 🔲 **2-layer PCB**
  - Top Layer: Signal routing
  - Bottom Layer: Solid GND plane for noise reduction

- 🔌 **Trace Widths**
  - Signal traces: `0.2 mm`
  - Power traces: `0.3 mm`
  - INA219 high-current path: `0.5 mm`

- 📏 **Routing Guidelines**
  - Uniform SPI/I2C trace lengths
  - Minimum crosstalk and EMI
  - Proper decoupling at power pins
  - Dedicated Keep-Out Zone for ESP32 Antenna

---

## ⚙️ Working Principle

1. A USB device is connected via the **USB Type-C** input (J1).
2. The **INA219 sensor** measures the input current and voltage.
3. **ESP32** reads the data from INA219 via **I2C protocol**.
4. The ESP32 processes the values and displays them on the **OLED**.
5. **AMS1117** provides regulated **3.3V** to ESP32 and peripherals.

---

## 🧠 ESP32 Pin Mapping

| ESP32 Pin | Connected To       | Function       |
|-----------|--------------------|----------------|
| GPIO 21   | SDA (INA219, OLED) | I2C Data (SDA) |
| GPIO 22   | SCL (INA219, OLED) | I2C Clock (SCL)|
| 3.3V      | VCC (All Modules)  | Power Supply   |
| GND       | GND Plane          | Common Ground  |

---

## 🔋 Power Supply

| Source     | Purpose                         |
|------------|----------------------------------|
| **5V Input** | USB Type-C (J1)                 |
| **3.3V Reg** | AMS1117 provides 3.3V to ESP32, INA219, OLED |

---

## 🖼 PCB Layout Summary

- 🧠 ESP32 placed at center with Antenna keep-out on the left
- 🔬 INA219 close to USB input for accurate shunt readings
- 🔌 AMS1117 and capacitors placed for clean 3.3V regulation
- 📟 OLED connector on top side for vertical screen mounting
- 📐 Optimized signal routing for analog/digital separation

---

## 📦 File Contents

- 📁 `Gerber Files` – Ready for PCB manufacturing
- 📁 `Schematic PDF` – Complete circuit diagram
- 📁 `Firmware Code` – ESP32 code to:
  - Read INA219 data
  - Update OLED display in real-time

---

## 🚀 Use Cases

- USB power monitor for embedded systems
- Current profiling for smartphones or peripherals
- Educational tool for learning power electronics and PCB design

---

## 💡 Future Improvements

- Add UART header for serial debugging/monitoring
- Add USB data passthrough or toggle switch
- Enable ESP32 WiFi mode for wireless logging and dashboard
- Add Li-ion charging support to make it portable

---

## 👨‍💻 Author

Designed  by **Tanuj Rai**

Feel free to fork and modify for your use. Pull requests are welcome!

---
