# Master Panel 3.3.1

A compact control panel and Xbox Game Bar widget for GPD Win 5.

[Download the Windows package](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v3.3.1) · [Quick start](QUICK-START.txt)

Run Master Panel and press the physical **Keyboard/Mouse ↔ Gamepad Swap button** to open/hide the panel. **Open with Windows** starts it at sign-in and restores saved controls. Win+G → Widgets → Master Panel opens the installed widget; the desktop app supplies its controls.

## In this release

3.3.1 fixes Modern Standby detection: S0-capable PCs could incorrectly report no supported sleep state in 3.3.0. The fix also enables the intended Download Mode screen-on guard on Modern Standby battery. The binding is checked against the installed Windows SDK and raw capability fixtures.

The shared [Tools Overview](TOOLS-OVERVIEW.md) includes Sleep → Hibernate, temporary 8 W Download Mode and manual Memory Reduce. Physical sleep/resume and downloads still need Win 5 testing.

## Install

Use **Settings → Updates → Check for updates → Download → Update & restart** to upgrade both the panel and widget. The 3.0.1 updater first loads a compatibility EXE, then completes the matching full package; keep the app hidden and your game closed while it finishes. Saved settings are retained.

For a fresh install or a manual fallback, exit the old Master Panel copy from its tray menu, then run **Master-Panel-v3.3.1-Setup.exe**. Setup installs the matching desktop app and widget together in **C:\Program Files\Master Panel**, creates shortcuts and adds a Windows uninstall entry. No command window is needed. Your saved settings stay in the existing user data folder.

The widget is signed with the included self-signed certificate. Setup adds that public certificate to Windows Trusted People and grants the widget loopback access to Master Panel. No private signing key is distributed. The Setup EXE has no commercial code-signing certificate, so Windows may show Unknown Publisher.

WebView2 is required for the full interface, PawnIO for supported hardware controls, and Xbox Game Bar for the widget. Settings → Components offers the official optional PawnIO, FxSound and RTSS downloads. Their own Windows installer wizards may require approval or a restart. Open Win+G → Widgets → Master Panel after installation; the desktop app must be running. When Game Bar is dismissed, a pinned widget is telemetry-only in this release. Use Win+G to adjust controls.

## Validation and limits

See VALIDATION-3.3.1.txt for the automated release gate scope. Software checks cover the shared UI, controller policy, installed bridge and package upgrades. Physical controller focus, vibration/flash persistence, display/audio/fan behavior and reboot recovery still need a real Win 5. No BIOS or battery charge-limit writes are added.

## Source and notices

This public repository distributes release files and documentation. GitHub’s automatic source archives contain that documentation. The complete application project is supplied separately to the owner for continued development; it includes vendored Go dependencies and the C# widget source. Third-party notices are available in Settings → Third-party licenses.

Powered by Vincent · mythvietnamese@gmail.com

