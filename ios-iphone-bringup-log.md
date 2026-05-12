# iOS iPhone Bring-Up Log

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
