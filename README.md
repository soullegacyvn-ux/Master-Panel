# Master Panel 3.2.0

A compact control panel and Xbox Game Bar widget for GPD Win 5.

[Download the Windows package](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v3.2.0) · [Quick start](QUICK-START.txt)

Run Master Panel and press the physical **Keyboard/Mouse ↔ Gamepad Swap button** to open/hide the panel. **Open with Windows** starts it at sign-in and restores saved controls. Win+G → Widgets → Master Panel opens the installed widget; the desktop app supplies its controls.

## In this release

- Performance → TDP range saves separate battery and DC ceilings: battery 8–85 W, DC 8–120 W. Existing defaults remain 55 W battery / 85 W DC on the 395 model until changed. USB-C and unidentified AC stay at 40 W.
- Raising a ceiling only expands the slider. Plugging in never raises the current target. Lowering a ceiling or changing to a lower-power source constrains all three power limits, including short boost.
- Orange Caution starts strictly above 65 W on battery and above 75 W on DC. These are warning thresholds, not proof of available cooling or electrical capacity.
- Reset selects 45 W with short boost off, or a lower active ceiling. Normal app exit and previous-session recovery also use this baseline instead of restoring an old high limit.
- Both interfaces use the same native engine, saved range and explicit actions. Gyro remains removed.
- Existing controller/vibration controls, publisher-verified optional component downloads and the full-package in-app updater remain available.

The new ceiling is a software setting. The app still verifies SMU readback and reports rejected or firmware-clamped requests. It does not unlock BIOS limits or guarantee that a Win 5 can sustain 120 W.

## Install

Use **Settings → Updates → Check for updates → Download → Update & restart** to upgrade both the panel and widget. The 3.0.1 updater first loads a compatibility EXE, then completes the matching full package; keep the app hidden and your game closed while it finishes. Saved settings are retained.

For a fresh install or a manual fallback, exit the old Master Panel copy from its tray menu, then run **Master-Panel-v3.2.0-Setup.exe**. Setup installs the matching desktop app and widget together in **C:\Program Files\Master Panel**, creates shortcuts and adds a Windows uninstall entry. No command window is needed. Your saved settings stay in the existing user data folder.

The widget is signed with the included self-signed certificate. Setup adds that public certificate to Windows Trusted People and grants the widget loopback access to Master Panel. No private signing key is distributed. The Setup EXE has no commercial code-signing certificate, so Windows may show Unknown Publisher.

WebView2 is required for the full interface, PawnIO for supported hardware controls, and Xbox Game Bar for the widget. Settings → Components offers the official optional PawnIO, FxSound and RTSS downloads. Their own Windows installer wizards may require approval or a restart. Open Win+G → Widgets → Master Panel after installation; the desktop app must be running. When Game Bar is dismissed, a pinned widget is telemetry-only in this release. Use Win+G to adjust controls.

## Validation and limits

See VALIDATION-3.2.0.txt for the automated release gate scope. Software checks cover the shared UI, controller policy, installed bridge and package upgrades. Physical controller focus, vibration/flash persistence, display/audio/fan behavior and reboot recovery still need a real Win 5. No BIOS or battery charge-limit writes are added.

## Source and notices

This public repository distributes release files and documentation. GitHub’s automatic source archives contain that documentation. The complete application project is supplied separately to the owner for continued development; it includes vendored Go dependencies and the C# widget source. Third-party notices are available in Settings → Third-party licenses.

Powered by Vincent · mythvietnamese@gmail.com

