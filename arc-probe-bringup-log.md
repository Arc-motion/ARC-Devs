# ARC-Probe Bring-Up Log

## 2026-05-12 09:43 CEST - iOS app bring-up path established for ARC BLE/Mesh demo

Today we opened a parallel app bring-up track for the ARC mobile interface, using the recovered React Native/Expo lamp app as the starting point for iOS testing.

Completed:

- iOS native project generated from the Expo/React Native app
- CocoaPods installed and iOS pods resolved successfully
- Xcode toolchain verified with the local Xcode installation
- iPhone XR detected over USB, paired, and confirmed with Developer Mode enabled
- iOS simulator build completed successfully
- LampBLE launched on the iPhone simulator and loaded the React Native JavaScript bundle
- simulator UI smoke test passed; expected log observed that Mesh native module is not available in simulator
- Apple Developer access established, enabling the next physical-device signing steps

This confirms that the ARC mobile app is no longer Android-only at the project level. The shared TypeScript/UI layer can build and boot on iOS, and the remaining radio validation is now a physical-device/signing task rather than an app-porting blocker.

Current status:

iOS app/UI bring-up milestone: PASS.

Physical iPhone BLE/Mesh radio bring-up: READY FOR NEXT TEST.

Next steps:

- run the app directly on the iPhone XR with Apple Developer signing
- verify iOS Bluetooth permission flow
- test BLE scan and connect against ARC hardware
- decide the app bundle identifier and build/version naming

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
