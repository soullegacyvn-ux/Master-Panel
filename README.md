# Master Panel 3.0.1

Windows controls for GPD Win 5, now with an Xbox Game Bar widget and a dedicated Gyro tab.

[Download the Windows installer](https://github.com/soullegacyvn-ux/Master-Panel/releases/download/v3.0.1/Master-Panel-v3.0.1-Setup.exe) · [Quick start](QUICK-START.txt)

Run Master Panel and press the physical **Keyboard/Mouse ↔ Gamepad Swap button** to open/hide the panel. **Open with Windows** starts it at sign-in and restores saved controls. Win+G → Widgets → Master Panel opens the installed widget; the desktop app supplies its controls.

## In this release

- Game Bar accepts hosted window activation and refreshes its own focus heartbeat before changes. Display, Sound, Fan and mapping use the same full panel and validated controls. Controller input is read inside the widget, with held-input protection; LT/RT switch tabs because Game Bar owns LB/RB.
- Mapping picker state is tracked per widget view. Fan presets compare curve values rather than JSON field order. Hidden views suspend, stale replies are discarded, and updates wait while a widget is in use.
- Gyro has its own tab with live motion preview, calibration, activation trigger, axis selection, sensitivity, deadzone, smoothing and inversion. It starts off. It reads the Windows gyro driver and sends relative mouse input; games must accept mouse aiming alongside a controller. Native axis orientation still needs device testing.
- Desktop and widget share one control engine and saved settings. Inactive views cancel queued edits and cannot send new hardware changes; opening them refreshes the shared state.
- The Win5 395 DC slider reaches 85 W; the 65–85 W segment uses vivid orange and a radiation caution icon. Source and firmware limits remain enforced.
- New slightly bolder MP vector branding across the app, tray and widget, plus refreshed headphone and gyro icons.
- Existing TDP/fan, display profiles/Night light, mapping, audio/FxSound, RTSS and compact customizable dashboard remain available. Lossless Scaling integration remains removed.

## Install

Exit the old Master Panel copy from its tray menu, then run **Master-Panel-v3.0.1-Setup.exe**. Setup installs the matching desktop app and widget together in **C:\Program Files\Master Panel**, creates shortcuts and adds a Windows uninstall entry. No command window is needed. Your saved settings stay in the existing user data folder.

The widget is signed with the included self-signed certificate. Setup adds that public certificate to Windows Trusted People and grants the widget loopback access to Master Panel. No private signing key is distributed. The Setup EXE has no commercial code-signing certificate, so Windows may show Unknown Publisher.

Use this full Setup for upgrades so both views are updated together. The older desktop-only self-updater does not install the widget.

WebView2 is required for the full interface, PawnIO for supported hardware controls, and Xbox Game Bar for the widget. FxSound and RTSS are optional separate installations. Open Win+G → Widgets → Master Panel after installation; the desktop app must be running. When Game Bar is dismissed, a pinned widget is telemetry-only in this release. Use Win+G to adjust controls.

## Validation and limits

See VALIDATION-3.0.1.txt in the installed folder for the checks actually completed. Mock/software tests do not prove physical sensor orientation, real controller routing, firmware flash persistence or device behavior. The build Mac cannot test GPD Win 5 hardware. Gyro does not write firmware or BIOS. Battery data is read-only and charge limits are not changed.

## Source and notices

This public repository distributes release files and documentation. GitHub’s automatic source archives contain that documentation. The complete application project is supplied separately to the owner for continued development; it includes vendored Go dependencies and the C# widget source. Third-party notices are available in Settings → Third-party licenses.

Powered by Vincent · mythvietnamese@gmail.com
