# Smart Environment Monitoring System

This Arduino project continuously monitors smoke, light, and temperature using analog sensors and triggers appropriate actions:

- Activates a buzzer and motor (via relay) if smoke is detected.
- Adjusts LED brightness based on ambient light using an LDR.
- Controls fan speed based on temperature using an LM35 temperature sensor.

---

## Hardware Required

| Component                | Quantity | Description                       |
|--------------------------|----------|-----------------------------------|
| Arduino Uno/Nano         | 1        | Main controller                   |
| MQ-2 Smoke Sensor        | 1        | Smoke/gas sensor (Analog out)     |
| LDR                      | 1        | Light sensor                      |
| LM35 Temperature Sensor  | 1        | Analog temperature sensor         |
| Relay Module             | 1        | To control motor (NO pin)         |
| DC Motor or Load         | 1        | Controlled via relay              |
| LED                      | 1        | Controlled brightness             |
| Buzzer / Alarm           | 1        | Indicates smoke alert             |
| Fan                      | 1        | PWM-controlled via MOSFET/driver  |
| Resistors                | 2        | For LDR voltage divider           |
| Breadboard & Jumper Wires| As needed| Circuit connections               |

---

## Circuit Diagram

A Fritzing or hand-drawn wiring diagram is recommended here (e.g., `circuit_diagram.png`).

---

## Logic Summary

### Smoke Detection
- Uses MQ-2 analog output.
- Normalized and compared to `SMOKE_THRESHOLD`.
- Triggers buzzer and turns on motor via relay when threshold is exceeded.

### LDR and LED
- LED brightness is inversely mapped from LDR input.
- Brighter in dark, dimmer in light.

### Temperature & Fan
- LM35 provides analog voltage: 10 mV/°C.
- Fan speed is mapped to temperature reading using PWM.

---

## Sample Serial Output

Smoke Level: 0.21
LDR Value: 683
Temperature (°C): 28.54
