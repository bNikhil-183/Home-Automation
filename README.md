# Smart Environment Monitoring System 
This Arduino-based project monitors environmental conditions like **smoke**, **light**, and **temperature**, and takes automatic actions based on the readings:

- Triggers an alarm if smoke is detected.
- Adjusts LED brightness based on ambient light using an LDR.
- Controls fan speed based on temperature using a temperature sensor.

---

## Hardware Components

| Component            | Quantity | Notes                     |
|---------------------|----------|---------------------------|
| Arduino Uno / Nano  | 1        |                           |
| Smoke Sensor (MQ-2) | 1        | Connected to A1           |
| LDR                 | 1        | Connected to A0           |
| Temperature Sensor (LM35) | 1  | Connected to A2           |
| LED                 | 1        | Connected to Pin 9 (PWM)  |
| Buzzer / Alarm      | 1        | Connected to Pin 2        |
| Fan (DC or PWM)     | 1        | Connected to Pin 11 (PWM) |
| Resistors           | 2        | For LDR voltage divider   |
| Breadboard + Wires  | As needed|                           |

---

## Circuit Connections

| Arduino Pin | Component         |
|-------------|------------------|
| A0          | LDR (via voltage divider)  |
| A1          | Smoke sensor (Analog output) |
| A2          | LM35 temperature sensor     |
| D2          | Buzzer / Alarm (Digital)    |
| D9 (PWM)    | LED                         |
| D11 (PWM)   | Fan                         |
| GND & 5V    | Shared among all components |

> **Tip:** Use `map()` to calibrate LDR, temperature, and fan speed values correctly based on actual readings.

---

## 🧠 Features & Logic

###Smoke Detection
- Reads analog value from MQ-2 sensor.
- Normalizes it based on sensor range.
- Triggers alarm if value exceeds threshold (`0.17` by default).

### Light-Responsive LED
- Uses LDR to measure light intensity.
- LED gets **brighter in the dark** and **dim in bright light**.

### 🌡️ Temperature-Based Fan
- LM35 sensor provides analog voltage (10mV per °C).
- Temperature is calculated and mapped to control fan speed (PWM).

---

## Serial Monitor Output

Example Output:
Smoke Level: 0.12
LDR Value: 648
Temperature (°C): 28.43
