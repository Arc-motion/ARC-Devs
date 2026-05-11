# ARC-Probe Bring-Up Log

## 2026-05-11 12:46 CEST - BLE Sensor app connected with live environment data

The FreeRTOS bring-up was extended from a simple LED heartbeat to a live BLE Sensor profile test on the STM32WBA5 development platform.

Completed:

- BLE advertising verified
- connection from the ST BLE Sensor app verified
- Environment view opened without freezing the target
- live temperature and relative humidity values received from the onboard SHT40 sensor
- sensor response observed when touching the board and breathing near the sensor

This confirms that FreeRTOS, the BLE stack, the GATT environment service, and the environmental sensor path can run together on the development board.

Current status:

FreeRTOS + BLE + live environment data milestone: PASS.

Next steps:

- keep the sensor read path non-blocking and isolated from the BLE runtime
- repeat the same environment data test on the first ARC-Probe PCB
- compare sensor response against expected board placement and enclosure effects

## 2026-05-11 - First FreeRTOS heartbeat on STM32WBA5

Today we completed a first firmware bring-up step on the STM32WBA5 development platform while waiting for the ARC-Probe PCB.

The goal was simple: verify that the development chain works end to end before moving the same workflow onto custom hardware.

Completed:

- ST-Link connection to the development board verified
- STM32WBA target detected over SWD
- FreeRTOS-based firmware built and flashed successfully
- firmware verified after flashing
- board reset successfully after programming
- blue LED heartbeat confirmed after reset

The blinking LED is a useful early milestone: it confirms that the firmware starts, the FreeRTOS scheduler is running, and a basic application task is executing.

Current status:

FreeRTOS alive milestone: PASS.

Next steps:

- add a small runtime log or status signal
- verify the wireless runtime path more explicitly
- repeat the same bring-up flow on the first ARC-Probe PCB after basic power checks
