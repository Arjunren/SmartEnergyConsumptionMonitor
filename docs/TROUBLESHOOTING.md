# Troubleshooting — SmartEnergyConsumptionMonitor

| Symptom | Check |
|---|---|
| No AC current proxy | Verify sensor power, grounds, pin table, voltage limits, and module orientation. |
| Invalid sample | Check 0–2048 ADC RMS counts range and sensor calibration. |
| Wi-Fi disconnected | Check SSID, 2.4 GHz coverage, and local network policy. |
| MQTT disconnected | Check broker DNS, port 8883, CA PEM, device credentials, and publish ACL. |
| Unexpected alert | Inspect raw AC current proxy and reserved; calibrate the threshold in `logic.h`. |
| Build failure | Confirm PlatformIO is installed and dependency downloads are permitted. |

Reports uncalibrated RMS ADC counts, never billing-grade watts; CT installation needs qualified supervision.
