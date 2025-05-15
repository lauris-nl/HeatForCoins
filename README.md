# HeatForCoins.yaml

ESPhome project using an ESP32 DevKit V1 with coin acceptors and heater control.

## Overview

This project explains how to wire and configure the **HeatForCoins** system — a coin-operated terrace heater controller based on the **ESP32 DevKit V1**. It supports two coin acceptors, two digital TM1637 displays, a solenoid-controlled coin return, and integration with **Home Assistant** for heater activation.

---

## Power Supply

- **Input Voltage:** 12V DC (standard 12V power adapter)
- **ESP32 Power:** Use a 5V regulator or buck converter to safely power the ESP32 DevKit V1 via the `5V` pin.
- **Solenoid + Coin Acceptors:** Powered directly from the 12V supply.

> ⚠️ Do not power the ESP32 directly from 12V!

## Features

- 🪙 Dual coin slot support (with configurable pulse-to-value mapping)
- 🔥 Dual heater start/stop integration via Home Assistant
- 🧮 Two TM1637 4-digit displays with brightness control
- 🧲 Solenoid trigger to release coins
- 🧠 Adjustable kWh price and wattage via Home Assistant
- 💡 Adaptive brightness using Home Assistant’s Adaptive Lighting

---

## Wiring Notes

- TM1637 displays are daisy-chained on the same CLK/DIO pins (Display 1 on GPIO33/25, Display 2 on GPIO35/32)
- Coin acceptors are connected to GPIO18 and GPIO19
- Start/stop buttons: GPIO23 and GPIO22
- Solenoid output: GPIO13

> See full pin mapping in the [wiki](https://github.com/lauris-nl/HeatForCoins/wiki/ESP32-DevKit-V1-%E2%80%93-Dual-Coin%E2%80%90Heater-Control)

---

## Circuit Diagram

![Circuit diagram](https://github.com/lauris-nl/HeatForCoins/raw/main/circuit_image.png)

---

## Next Steps

- [x] YAML configuration
- [ ] 3D printable enclosure
- [ ] Power-loss recovery and coin balance handling
- [ ] MQTT support (optional)

---

> 🧪 Always verify voltage levels with a multimeter before connecting to the ESP32.
>  
> 🛠 Need help? [Open an issue](https://github.com/lauris-nl/HeatForCoins/issues) or join the discussion on the Home Assistant Community Forum.

