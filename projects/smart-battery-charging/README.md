# Smart LiFePO4 Battery Charging and UPS Backup System

**Electrical & Embedded Systems | Laboratory Prototype | 2026**

This university laboratory project investigated an Arduino-monitored charger/backup design. The **implemented hardware** is a mains-isolated AC-to-DC front end and buck converter with sensing, audible alarms and a **10-ohm resistive dummy load**. **Automatic CC-CV LiFePO4 charging and battery-based UPS transfer were proposed for Phase II, not demonstrated.**

## Implemented prototype
- 230 V AC / 18 V AC isolated transformer, KBPC3510 bridge rectifier, fuse, safety switch, filter capacitor, LM2596 buck converter
- Arduino Uno with INA219 I2C voltage/current monitoring, DS18B20 1-Wire temperature probe and buzzer alarm
- Bench validation of buck output under a resistor load rather than a live LiFePO4 cell
- Laboratory alarm test with a >4.2 V voltage threshold; >2.0 A current threshold documented in the firmware description

## Recorded test points (10-ohm dummy load)

| Buck output | Current | Load power | Observed status |
|---|---|---|---|
| 3.30 V | 0.330 A | 1.09 W | Normal, 28.4 C |
| 3.65 V | 0.365 A | 1.33 W | Normal, 30.1 C |
| 4.35 V | 0.435 A | 1.89 W | Alarm, above 4.2 V |

Values above are taken from the November 2026 technical report, not independently re-tested for this README.

## Planned Phase II (not yet implemented)
- Closed-loop CC-CV charging using digitally adjusted buck feedback
- Arduino-controlled protection relay and MOSFET load transfer
- LiFePO4 battery pack with dedicated BMS
- OLED display, remote IoT monitoring and state-of-health experiments

## Technical scope note
The 17-page technical report mixes implemented hardware with proposed control methods. Its example Arduino source excerpt is incomplete in the PDF; a tested, buildable firmware project is **not** claimed here. Do not assume that the laboratory circuit is a proven live charger or production-ready UPS.

**Portfolio:** https://hareramkumarportfolioreadytodeploy.vercel.app/
