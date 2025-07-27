# Project_001
 Smart USB Power Meter using ESP32, INA219 & OLED
This project is a compact Smart USB Power Meter designed using an ESP32, INA219 current sensor, and OLED display, all integrated on a custom 2-layer PCB. The circuit allows real-time monitoring of USB voltage and current through a Type-C connector, displaying the results on a 0.96” OLED screen.

 Features
 Measures voltage and current of any USB-powered device

 Displays data on a 128x64 OLED screen via I2C

 Powered by ESP32 for wireless capabilities & efficient control

 Uses INA219 precision current sensor for accurate readings

 Onboard AMS1117 5V to 3.3V regulator for safe ESP32 operation

 Designed with standard trace widths (0.2mm, 0.3mm, 0.5mm)

 Full GND pour on bottom layer, signals on top layer

 Dedicated Antenna keep-out zone for ESP32 WiFi

 Hardware Components
Component	Description
ESP32 Module	WiFi-enabled microcontroller (ESP-WROOM-32)
INA219	I2C-based voltage and current sensor
OLED Display	128x64 OLED via I2C (0x3C or 0x78 address)
AMS1117-3.3V	LDO Voltage regulator for 5V to 3.3V conversion
USB Type-C	Input connector for USB voltage/current monitoring
Passive Components	Capacitors, resistors for pull-up and filtering

 PCB Design Highlights
2-layer PCB

Top Layer: All signal routing

Bottom Layer: Solid GND plane for noise reduction and return path

Trace Widths:

Signal traces: 0.2 mm

Power traces: 0.3 mm

INA219 high-current path: 0.5 mm

SPI/I2C routing kept at uniform lengths to prevent signal skew

Antenna Keep-Out Zone defined near ESP32 for WiFi performance

 Working Principle
The USB device is connected via the USB-C input (J1).

The INA219 measures current flowing to the device and voltage across the USB.

ESP32 reads INA219 data using I2C communication.

ESP32 processes and displays the readings on the OLED screen.

The AMS1117 steps down the USB 5V input to 3.3V for the ESP32 and sensors.

 PCB Layout Summary
ESP32 centrally placed for optimized routing and antenna clearance

INA219 sensor placed close to USB input for accurate shunt measurements

AMS1117 regulator and related filtering capacitors near the power rail

OLED connector on the top for vertical mounting

Proper decoupling capacitors placed near power pins

Clean separation between analog/current paths and digital traces

 Use Case
You can use this board as:

A USB power consumption meter for embedded development

A current profiling tool for mobile phones and USB-powered devices

An educational project on power measurement and PCB design

 Power Supply
Input: 5V via USB-C

Onboard regulated 3.3V via AMS1117 for ESP32, INA219, and OLED

🔌 Pin Connections (ESP32)
ESP32 Pin	Connected To	Function
GPIO 21	SDA (INA219/OLED)	I2C SDA
GPIO 22	SCL (INA219/OLED)	I2C SCL
3.3V	VCC for modules	Power supply
GND	GND plane	Common ground

 File Contents
PCB layout files (Gerbers, KiCad/Altium/etc.)

Schematic PDF

Firmware (ESP32 code for reading INA219 and updating OLED)

README.md (You’re reading it!)

 Improvements & Ideas
Add UART header for serial monitoring

Optional micro-USB to USB-C adapter compatibility

Integration with ESP32 WiFi for remote power monitoring
