# Master Panel 3.0.2

- Updates now install the matching panel and widget together. The 3.0.1 EXE updater has a compatibility path that completes the full package after its first restart. Settings remain in the existing data folder; games and active hardware changes block the update handoff.
- Stabilizes widget controller input: one physical/routed source, separate trigger press/release thresholds, local menu focus, no tab wrapping and explicit Menu access to header actions. Settled gesture promises no longer block later controller commands.
- Adds Controller vibration Off / Low / High with Temporary and Permanent Flash actions. Retains the firmware 1.12 gate, original backup, byte allowlist, checksum, RAM readback and interrupted-commit recovery. Mapping profiles remain mapping-only.
- Adds optional publisher downloads for PawnIO 2.2.0, FxSound 1.2.14.0 and RTSS 7.3.7. Each download is size-limited and checked against a pinned SHA-256 before its standard installer can be opened. Nothing is downloaded at normal boot. RTSS is fetched directly from the publisher mirror rather than redistributed in Setup.
- Starts an installed FxSound minimized when the Game Bar widget becomes active, without changing audio settings.
- Makes widget Audio more compact with a mute button and separates the desktop Fan console from its presets.
- Adds on-demand sensor/driver diagnostics to Gyro and support reports. Seeing Bosch Accelerometer does not establish an available angular-rate sensor; that device's gyro remains unresolved pending driver diagnostics and hardware testing.

Choose Setup for a fresh installation. The separate versioned EXE is the compatibility entry for older in-app updaters. Windows CI checks the native builds, official download hashes, software regressions, Program Files install/uninstall and installed bridge. These checks do not prove physical vibration, controller routing, gyro operation or reboot persistence on a GPD Win 5.
