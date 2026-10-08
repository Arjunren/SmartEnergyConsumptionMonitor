# Hardware — SmartEnergyConsumptionMonitor

## Parts and electrical limits
ESP32 DevKit and SCT-013 current transformer; rated burden resistor; 1.65 V ADC bias network. Power low-voltage modules from a suitable regulated supply, tie grounds together, and verify signal levels before connection. GPIO34 is input-only and ADC1 is used because ADC2 conflicts with Wi-Fi. Never apply more than 3.3 V to an ESP32 GPIO.

| ESP32 pin | Connection | Requirement |
|---|---|---|
| ESP32 3V3 | sensor VCC | Verify module supply rating |
| ESP32 GND | sensor GND | Common low-voltage ground |
| GPIO34 (ADC1) | analog signal | Never exceed 3.3 V |

Use a pull-down on GPIO14's driver input so the load remains off during boot. Low-voltage relays must not be connected directly to GPIO, and inductive loads need flyback protection.

## Sensor specification and calibration
The firmware accepts AC current proxy from 0 to 2048 ADC RMS counts. Secondary value is reserved (none). Reports uncalibrated RMS ADC counts, never billing-grade watts; CT installation needs qualified supervision. Use a multimeter and the sensor data sheet for the exact module revision. For any AC current measurement, use only an approved current transformer and never connect mains conductors to the ESP32.
