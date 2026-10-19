# Master Panel 3.3.4

A compact control panel and Xbox Game Bar widget for GPD Win 5.

[Download the Windows package](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v3.3.4) · [Quick start](QUICK-START.txt)

Run Master Panel and press the physical **Keyboard/Mouse ↔ Gamepad Swap button** to open/hide the panel. **Open with Windows** starts it at sign-in and restores saved controls. Win+G → Widgets → Master Panel opens the installed widget; the desktop app supplies its controls.

## In this release

Improves RTSS overlay coexistence and connects Display colors to AMD Custom Color in both the desktop panel and Xbox Game Bar widget.

- RTSS presets show their selected state, reload and synchronize across both views. Layout actions use the current shared configuration. Grid/Ribbon spacing avoids overlapping labels and values.
- Detects other RTSS providers, including modern 32KB text. Master Panel pauses its own overlay by default while another provider is active and resumes when it stops. Optional “Show alongside other overlays” allows explicit overlap. Stale slots owned by Master Panel are cleared; foreign providers remain untouched.
- RTSS diagnostics show the actual connection error, provider names and running build. RTSS’s own statistics are restored when Master Panel releases its owned settings.
- Display uses AMD ADLX Custom Color for brightness, contrast, saturation, hue and color temperature. Refresh reads the driver without applying a profile; visible idle controls read back live changes.
- Legacy color profiles are kept separately. On first use, the new color store starts from current AMD settings, avoiding automatic replay of old values. Natural captures that starting baseline. Night light remains a separate Windows control.

The shared [Tools Overview](TOOLS-OVERVIEW.md), TDP ceiling presets and FxSound launch controls remain available.

## Install

Use **Settings → Updates → Check for updates → Download → Update & restart** to upgrade both the panel and widget. The 3.0.1 updater first loads a compatibility EXE, then completes the matching full package; keep the app hidden and your game closed while it finishes. Saved settings are retained.

For a fresh install or a manual fallback, exit the old Master Panel copy from its tray menu, then run **Master-Panel-v3.3.4-Setup.exe**. Setup installs the matching desktop app and widget together in **C:\Program Files\Master Panel**, creates shortcuts and adds a Windows uninstall entry. No command window is needed. Your saved settings stay in the existing user data folder.

The widget is signed with the included self-signed certificate. Setup adds that public certificate to Windows Trusted People and grants the widget loopback access to Master Panel. No private signing key is distributed. The Setup EXE has no commercial code-signing certificate, so Windows may show Unknown Publisher.

WebView2 is required for the full interface, PawnIO for supported hardware controls, and Xbox Game Bar for the widget. Settings → Components offers the official optional PawnIO, FxSound and RTSS downloads. Their own Windows installer wizards may require approval or a restart. Open Win+G → Widgets → Master Panel after installation; the desktop app must be running. When Game Bar is dismissed, a pinned widget is telemetry-only in this release. Use Win+G to adjust controls.

## Validation and limits

See VALIDATION-3.3.4.txt for the automated release gate scope. Software checks cover the shared UI, controller policy, installed bridge and package upgrades. Physical controller focus, vibration/flash persistence, display/audio/fan behavior and reboot recovery still need a real Win 5. No BIOS or battery charge-limit writes are added.

## Source and notices

This public repository distributes release files and documentation. GitHub’s automatic source archives contain that documentation. The complete application project is supplied separately to the owner for continued development; it includes vendored Go dependencies and the C# widget source. Third-party notices are available in Settings → Third-party licenses.

Powered by Vincent · mythvietnamese@gmail.com

