# Master Panel 3.2.0

- Adds separate saved TDP slider ceilings for battery (up to 85 W) and DC (up to 120 W) under Performance → TDP range.
- Raising a ceiling or plugging in does not raise active TDP. A lower source/ceiling clamps the current target and short boost; queued actions recheck the latest source before writing.
- Caution starts above 65 W on battery and above 75 W on DC, consistently in panel and widget.
- Reset now selects 45 W without short boost, or the active lower ceiling. Exit and crash recovery use the same fallback instead of restoring old high power limits.
- Keeps verified SMU readback and failure rollback. A software ceiling does not bypass firmware restrictions or certify sustained 120 W operation.
- Preserves saved controls, package upgrades and both matching interfaces; gyro remains removed.

Windows runtime checks use a generic runner and mock hardware. Physical GPD Win 5 power, cooling, controller and reboot behavior still require device testing.

# Master Panel 3.1.0

- Removes Gyro completely from the desktop panel, Game Bar widget and native runtime: no sensor discovery, motion sampling, calibration or mouse-aim injection.
- Retains the shared engine, controller vibration controls and full-package in-app updater. Both app and widget update together, preserving saved preferences.
- Revalidates the software, native Windows app, signed widget, Program Files installer and upgrades from existing installations.

Real Win 5 controller focus, firmware writes, display/audio/fan controls and reboot persistence require device testing. No BIOS or battery charge-limit writes are added.
