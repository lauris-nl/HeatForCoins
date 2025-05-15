# HeatForCoins.yaml
 project with ESP32 C3 zero, coin acceptors and heaters
# HeatForCoins Wiring Guide

## Overview

This page explains how to correctly wire the "HeatForCoins" system, a coin-operated terrace heater controller using an ESP32-C3 Zero board. It integrates a 12V coin acceptor, a solenoid-based coin return, and a digital TM1637 display.

---

## Power Supply

* **Input Voltage:** 12V DC (from a standard 12V wall adapter)
* **Step-down Module:** A buck converter is used to step down from 12V to 5V for powering the ESP32-C3 Zero.

### Connections:

| Component              | Voltage | Connects To                          |
| ---------------------- | ------- | ------------------------------------ |
| ESP32-C3 Zero          | 5V      | Output of Buck Converter             |
| Coin Acceptor          | 12V     | Direct to 12V adapter                |
| Solenoid (Coin Return) | 12V     | Through transistor, from 12V adapter |
| Buck Converter         | 12V In  | 12V adapter                          |
| Buck Converter         | 5V Out  | ESP32-C3 Zero (5V pin + GND)         |

---

## ESP32-C3 Zero Wiring

### Buck Converter to ESP32:

* **Buck GND** → **ESP32 GND**
* **Buck 5V** → **ESP32 5V (or VBUS)**

### Coin Acceptor:

* **Power:**

  * **Red:** +12V (from adapter)
  * **Black:** GND
* **Signal:**

  * **White or Yellow (Pulse Out):** → Connect to ESP32 GPIO (e.g. GPIO10)
  * Use a voltage divider or optocoupler if signal is >3.3V (some models output 12V pulses)

### Solenoid (Muntbak Opener):

* **Positive:** Direct to 12V adapter
* **Negative:** To collector of NPN transistor (e.g. IRLZ44N or 2N2222)
* **Transistor base:** Connect via 1kΩ resistor to ESP32 GPIO (e.g. GPIO9)
* **Transistor emitter:** To GND
* **Flyback Diode:** Place a 1N4007 diode in parallel across the solenoid terminals (cathode to +12V side)

---

## TM1637 Display

* **CLK (Clock):** GPIO23
* **DIO (Data):** GPIO22
* **VCC:** 3.3V or 5V (depending on your module)
* **GND:** To ESP32 GND

---

## Summary of GPIO Usage (Example)

| GPIO   | Function            |
| ------ | ------------------- |
| GPIO10 | Coin acceptor pulse |
| GPIO9  | Solenoid trigger    |
| GPIO23 | TM1637 CLK          |
| GPIO22 | TM1637 DIO          |

---

## Additional Notes

* Always test the coin acceptor output voltage before connecting to an ESP32 pin.
* Use `INPUT_PULLUP` if the signal line floats.
* Make sure the ESP32-C3 is powered by **regulated 5V** only.
* Mount all high-current parts (like solenoid) on separate power tracks if you design a PCB.

---

## Coming Up

* YAML configuration reference
* Enclosure design STL
* Home Assistant integration tips

> ⚠️ If you're unsure about wiring or voltage levels, use a multimeter and test before applying power.

---

Need help? Open an issue on the [GitHub repo](https://github.com/lauris-nl/HeatForCoins/edit/main/README.md) or contact us via Home Assistant Community!
