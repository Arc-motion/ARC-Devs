# ARC-Probe Bring-Up Log

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
