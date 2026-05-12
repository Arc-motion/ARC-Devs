# iOS iPhone Bring-Up Log

## 2026-05-12 13:33 CEST - Mesh bring-up path connected with live telemetry

The iPhone Mesh bring-up path reached an end-to-end connected demo state against the STM32WBA5 target.

Completed:

- confirmed the STM32WBA5 firmware is still a BLE Sensor baseline with a Mesh scaffold, not a true BLE Mesh stack yet
- added a temporary firmware advertising shim so the iPhone can discover the target as a Mesh provisioning candidate
- added the native iOS `MeshManager` bridge for React Native and CoreBluetooth
- implemented iOS bring-up shims for scan, identify, provisioning, node connect, vendor send, and vendor status read
- verified the iPhone can scan the WBA5 target, select it, provision through the shim, and reach Connected in the app
- verified the WBA5 LED heartbeat remains active while connected
- bridged WBA5 SHT40 ENV notifications into OpenMesh-compatible telemetry for the app main view
- confirmed live Air temp updates in the main view from the real SHT40 sensor
- simulated Core temp, MCU temp, and Power telemetry in the iOS bridge using a 25.0-30.0 loop at 0.1 per second
- verified hue and intensity commands can be sent from the main frame through the Mesh UI path
- fixed the iOS shim so `SET_LAMP_CONFIG` versions are reflected back in telemetry and the app can clear pending settings version state

Current status:

Mesh UI/radio discovery/telemetry bring-up milestone: PASS.

Important caveat:

This is a controlled bring-up scaffold. Real BLE Mesh PB-GATT provisioning, Mesh Proxy transport, vendor model messaging, and firmware-side OpenMesh status generation still require the actual ST Mesh middleware or an equivalent firmware Mesh implementation.

Next steps:

- replace iOS provisioning and vendor-message shims with real BLE Mesh transport
- move OpenMesh telemetry/status generation from the iOS bridge into firmware
- keep the SHT40 Air temp mapping as the reference for real environmental telemetry
- implement firmware-backed schedule/time/config persistence so Mesh settings versions reflect target state

## 2026-05-12 10:09 CEST - LampBLE deployed and launched on physical iPhone

The iOS app bring-up moved from simulator validation to a real iPhone device run.

Completed:

- Apple Developer signing configured for the LampBLE iOS target
- app bundle identifier set to `com.arcmotion.lampble`
- physical iPhone selected as the deployment target
- native iOS device build completed successfully
- LampBLE installed and launched on the iPhone
- React Native JavaScript bundle loaded over Metro
- runtime log confirmed app startup with the expected Mesh-native-module warning on iOS

Current status:

Physical iPhone app deploy milestone: PASS.

Next steps:

- verify iOS Bluetooth permission flow on the iPhone
- test BLE scan and connect against ARC hardware
- keep Mesh transport clearly gated on iOS until a native iOS Mesh module exists
