# Master Panel 3.0.2

Windows controls for GPD Win 5, now with an Xbox Game Bar widget and a dedicated Gyro tab.

[Download the Windows package](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v3.0.2) · [Quick start](QUICK-START.txt)

Run Master Panel and press the physical **Keyboard/Mouse ↔ Gamepad Swap button** to open/hide the panel. **Open with Windows** starts it at sign-in and restores saved controls. Win+G → Widgets → Master Panel opens the installed widget; the desktop app supplies its controls.

## In this release

- Widget navigation uses one controller input source at a time, with trigger hysteresis and no tab wrapping. LT/RT switch tabs; Menu opens header actions and B returns. Directional navigation stays inside the current menu or dialog.
- Controller **Vibration level** offers Off / Low / High. Apply temporarily or choose Permanent and Flash vibration. Writes use the existing firmware gate, backup, checksum, RAM readback and recovery journal. Physical vibration and reboot persistence still need Win 5 testing.
- Settings → Components can download missing PawnIO, FxSound and RTSS directly from their publishers, verify pinned checksums and open their normal installation wizards. They are optional downloads and are not bundled or silently installed.
- Entering the active Game Bar widget starts an installed FxSound minimized if it is not already running, with a retry limit. It does not change audio power, volume, mute or presets.
- Compact Audio uses an inline mute button; the desktop Fan console is separated from the preset buttons.
- Gyro → Diagnose sensor reads Windows sensor/I2C driver names, hardware IDs, versions and service status for the support report. An accelerometer alone cannot supply gyro aiming. The reported Bosch Accelerometer case is **not yet confirmed working**; no unverified sensor driver is installed.
- The desktop panel and widget continue to use the same controls and saved settings. Existing display, audio, TDP, fan, mapping and dashboard features remain available.

## Install

Use **Settings → Updates → Check for updates → Download → Update & restart** to upgrade both the panel and widget. The 3.0.1 updater first loads a compatibility EXE, then completes the matching full package; keep the app hidden and your game closed while it finishes. Saved settings are retained.

For a fresh install or a manual fallback, exit the old Master Panel copy from its tray menu, then run **Master-Panel-v3.0.2-Setup.exe**. Setup installs the matching desktop app and widget together in **C:\Program Files\Master Panel**, creates shortcuts and adds a Windows uninstall entry. No command window is needed. Your saved settings stay in the existing user data folder.

The widget is signed with the included self-signed certificate. Setup adds that public certificate to Windows Trusted People and grants the widget loopback access to Master Panel. No private signing key is distributed. The Setup EXE has no commercial code-signing certificate, so Windows may show Unknown Publisher.

WebView2 is required for the full interface, PawnIO for supported hardware controls, and Xbox Game Bar for the widget. Settings → Components offers the official optional PawnIO, FxSound and RTSS downloads. Their own Windows installer wizards may require approval or a restart. Open Win+G → Widgets → Master Panel after installation; the desktop app must be running. When Game Bar is dismissed, a pinned widget is telemetry-only in this release. Use Win+G to adjust controls.

## Validation and limits

See VALIDATION-3.0.2.txt in the installed folder for the checks actually completed. Mock/software tests do not prove physical sensor orientation, real controller routing, firmware flash persistence or device behavior. The build Mac cannot test GPD Win 5 hardware. Gyro does not write firmware or BIOS. Battery data is read-only and charge limits are not changed.

## Source and notices

This public repository distributes release files and documentation. GitHub’s automatic source archives contain that documentation. The complete application project is supplied separately to the owner for continued development; it includes vendored Go dependencies and the C# widget source. Third-party notices are available in Settings → Third-party licenses.

Powered by Vincent · mythvietnamese@gmail.com
