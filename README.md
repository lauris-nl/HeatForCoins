# HeatForCoins.yaml
 project with ESP32 C3 zero, coin acceptors and heaters
# HeatForCoins Wiring Guide

## Overview

This page explains how to correctly wire the "HeatForCoins" system, a coin-operated terrace heater controller using an ESP32-C3 Zero board. It integrates a 12V coin acceptor, a solenoid-based coin return, and a digital TM1637 display.

---

## Power Supply

* **Input Voltage:** 12V DC (from a standard 12V wall adapter)
* **Step-down Module:** A buck converter is used to step down from 12V to 5V for powering the ESP32-C3 Zero.

([https://github.com/lauris-nl/HeatForCoins/wiki](https://github.com/lauris-nl/HeatForCoins/wiki/ESP32-DevKit-V1-%E2%80%93-Dual-Coin%E2%80%90Heater-Control))

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
