# Tiguan Monitor v0.4.0
Android app (Kotlin + Jetpack Compose), landscape-first, for VW Tiguan 5N 2011 CCTA / 4Motion (Winca head unit & phones).
ELM327 Wi-Fi TCP default: `192.168.0.10:35000` (configurable in Settings).

## Changelog v0.4.0
- Fixed `ATRV` battery voltage command validation in `ObdClient`.
- Added coroutine `Mutex` to serialize socket commands between live polling and manual DTC/Mode 06 scans.
- Added `FLAG_KEEP_SCREEN_ON` and modern fullscreen immersive mode for Winca head units.
- Added configurable IP, port, and polling interval saved via `SharedPreferences`.
- Added automatic Supported PIDs discovery (`0100` / `0120`) and additional EA888 sensors: Calculated Load (`0104`), Throttle Position (`0111`), Timing Advance (`010E`), Fuel Rail Pressure (`0123`), Barometric Pressure (`0133`), and Boost calculation (`MAP - Baro`).
- Upgraded `ChartsScreen` with live multi-parameter selector (RPM, MAP/Boost, Coolant, STFT, LTFT, Timing) and min/max/current readouts.
- Added thermal and voltage warning highlights (Coolant >= 105°C, IAT >= 55°C, Voltage < 13.2V running).
- Added GitHub Actions workflow (`.github/workflows/build-apk.yml`) for cloud APK compilation without a local PC.

## Build via GitHub Actions (No PC required)
1. Upload the contents of `TiguanMonitorV2/` to the root of a GitHub repository.
2. Open the **Actions** tab on GitHub and run **Build Tiguan Monitor APK**.
3. Download the artifact `TiguanMonitor-0.4.0-debug` and install the `.apk` on your Android device / Winca unit.
